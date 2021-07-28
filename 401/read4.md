## OOP

#### Object 
- bjects are key to understanding object-oriented technology.
* objects share two characteristics: They all have state and behavior
-  An object stores its state in fields (variables in some programming languages) and exposes its behavior through methods (functions in some programming languages).

* Bundling code into individual software objects provides a number of benefits, including:

- Modularity
- Information-hiding: 
- Code re-use
- Pluggability and debugging ease

####  Class 
* A class is the blueprint from which individual objects are created.

* example about object & class:

A class declaration for a MountainBike class that is a subclass of Bicycle might look like this:


public class MountainBike extends Bicycle {
        
    // the MountainBike subclass has
    // one field
    public int seatHeight;

    // the MountainBike subclass has
    // one constructor
    public MountainBike(int startHeight, int startCadence,
                        int startSpeed, int startGear) {
        super(startCadence, startSpeed, startGear);
        seatHeight = startHeight;
    }   
        
    // the MountainBike subclass has
    // one method
    public void setHeight(int newValue) {
        seatHeight = newValue;
    }   

}
MountainBike inherits all the fields and methods of Bicycle and adds the field seatHeight and a method to set it (mountain bikes have seats that can be moved up and down as the terrain demands).