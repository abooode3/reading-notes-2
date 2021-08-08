##### Spring RequestMapping

- RequestMapping Basics
*  @RequestMapping — by Path

  @RequestMapping(value = "/ex/foos", method = RequestMethod.GET)
@ResponseBody
public String getFoosBySimplePath() {
    return "Get some Foos";
}


* @RequestMapping — the HTTP Method

@RequestMapping(value = "/ex/foos", method = POST)
@ResponseBody
public String postFoos() {
    return "Post some Foos";
}

- RequestMapping and HTTP Headers

@RequestMapping With the headers Attribute
@RequestMapping(value = "/ex/foos", headers = "key=val", method = GET)
@ResponseBody
public String getFoosWithHeader() {
    return "Get some Foos with Header";
}


- RequestMapping With Path Variables

* Single @PathVariable

@RequestMapping(value = "/ex/foos/{id}", method = GET)
@ResponseBody
public String getFoosBySimplePathWithPathVariable(
  @PathVariable("id") long id) {
    return "Get a specific Foo with id=" + id;
}

* Multiple @PathVariable

@RequestMapping(value = "/ex/foos/{fooid}/bar/{barid}", method = GET)
@ResponseBody
public String getFoosBySimplePathWithPathVariables
  (@PathVariable long fooid, @PathVariable long barid) {
    return "Get a specific Bar with id=" + barid + 
      " from a Foo with id=" + fooid;
}


##### CrudRepository, JpaRepository, and PagingAndSortingRepository in Spring Data

- Spring Data Repositories
1. CrudRepository provides CRUD functions
2. PagingAndSortingRepository provides methods to do pagination and sort records
3. JpaRepository provides JPA related methods such as flushing the persistence context and delete records in a batch



* CrudRepository

public interface CrudRepository<T, ID extends Serializable>
  extends Repository<T, ID> {

    <S extends T> S save(S entity);

    T findOne(ID primaryKey);

    Iterable<T> findAll();

    Long count();

    void delete(T entity);

    boolean exists(ID primaryKey);
}


*  PagingAndSortingRepository

public interface PagingAndSortingRepository<T, ID extends Serializable> 
  extends CrudRepository<T, ID> {

    Iterable<T> findAll(Sort sort);

    Page<T> findAll(Pageable pageable);
}

* create a Pageable object with certain properties and we've to specify at least:
- Page size
- Current page number
- Sorting


  * JpaRepository

public interface JpaRepository<T, ID extends Serializable> extends
  PagingAndSortingRepository<T, ID> {

    List<T> findAll();

    List<T> findAll(Sort sort);

    List<T> save(Iterable<? extends T> entities);

    void flush();

    T saveAndFlush(T entity);

    void deleteInBatch(Iterable<T> entities);
}

