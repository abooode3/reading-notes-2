#### Working with Relationships in Spring Data REST

1. One-to-One Relationship

-  The Data Model
  * use the @OneToOne annotation
@Entity
public class Library {

    @Id
    @GeneratedValue
    private long id;

    @Column
    private String name;

    @OneToOne
    @JoinColumn(name = "address_id")
    @RestResource(path = "libraryAddress", rel="address")
    private Address address;
    
    // standard constructor, getters, setters
}
@Entity
public class Address {

    @Id
    @GeneratedValue
    private long id;

    @Column(nullable = false)
    private String location;

    @OneToOne(mappedBy = "address")
    private Library library;

    // standard constructor, getters, setters
}

-  The Repositories
 ublic interface LibraryRepository extends CrudRepository<Library, Long> {}
 public interface AddressRepository extends CrudRepository<Address, Long> {}


- Creating the Resources
curl -i -X POST -H "Content-Type:application/json" 
  -d '{"name":"My Library"}' http://localhost:8080/libraries
The API returns the JSON object:

{
  "name" : "My Library",
  "_links" : {
    "self" : {
      "href" : "http://localhost:8080/libraries/1"
    },
    "library" : {
      "href" : "http://localhost:8080/libraries/1"
    },
    "address" : {
      "href" : "http://localhost:8080/libraries/1/libraryAddress"
    }
  }
}

##### Before we create an association, sending a GET request to this endpoint will return an empty object.


- Creating the Associations

##### After persisting both instances, we can establish the relationship by using one of the association resources.
> This is done using the HTTP method PUT, which supports a media type of text/uri-list, and a body containing the URI of the resource to bind to the association.


2. One-to-Many Relationship
> A one-to-many relationship is defined using the @OneToMany and @ManyToOne annotations and can have the optional @RestResource annotation to customize the association resource.

- The Data Model

@Entity
public class Book {

    @Id
    @GeneratedValue
    private long id;
    
    @Column(nullable=false)
    private String title;
    
    @ManyToOne
    @JoinColumn(name="library_id")
    private Library library;
    
    // standard constructor, getter, setter
}
Let's add the relationship to the Library class as well:

public class Library {
 
    //...
 
    @OneToMany(mappedBy = "library")
    private List<Book> books;
 
    //...
 
}

-  The Repository
public interface BookRepository extends CrudRepository<Book, Long> { }

- The Association Resources

curl -i -X POST -d "{\"title\":\"Book1\"}" 
  -H "Content-Type:application/json" http://localhost:8080/books



3. Many-to-Many Relationship
> A many-to-many relationship is defined using @ManyToMany annotation, to which we can add @RestResource.

 - The Data Model
@Entity
public class Author {

    @Id
    @GeneratedValue
    private long id;

    @Column(nullable = false)
    private String name;

    @ManyToMany(cascade = CascadeType.ALL)
    @JoinTable(name = "book_author", 
      joinColumns = @JoinColumn(name = "book_id", referencedColumnName = "id"), 
      inverseJoinColumns = @JoinColumn(name = "author_id", 
      referencedColumnName = "id"))
    private List<Book> books;

    //standard constructors, getters, setters
}

- The Repository
public interface AuthorRepository extends CrudRepository<Author, Long> { }


- The Association Resources

curl -i -X POST -H "Content-Type:application/json" 
  -d "{\"name\":\"author1\"}" http://localhost:8080/authors
Next, let's add a second Book record to our database:

curl -i -X POST -H "Content-Type:application/json" 
  -d "{\"title\":\"Book 2\"}" http://localhost:8080/books


#### Integration Testing in Spring

- Enable Spring in Tests with JUnit 5
> JUnit 5 defines an extension interface through which classes can integrate with the JUnit test.
> We can enable this extension by adding the @ExtendWith annotation to our test classes and specifying the extension class to load. To run the Spring test, we use SpringExtension.class.
> We also need the @ContextConfiguration annotation to load the context configuration and bootstrap the context that our test will use.


- The WebApplicationContext Object
WebApplicationContext provides a web application configuration. It loads all the application beans and controllers into the context.

- Mocking Web Context Beans
>MockMvc provides support for Spring MVC testing. It encapsulates all web application beans and makes them available for testing.

private MockMvc mockMvc;
@BeforeEach
public void setup() throws Exception {
    this.mockMvc = MockMvcBuilders.webAppContextSetup(this.webApplicationContext).build();
}


- Verify Test Configuration
Let's verify that we're loading the WebApplicationContext object (webApplicationContext) properly

- Writing Integration Tests