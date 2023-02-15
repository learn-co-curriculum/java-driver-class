# Driver Class

## Learning Goals

- Discuss what a Driver class is in Java

## What is a Driver?

Sometimes in Java, when we want to bring multiple classes together to
create objects and call methods, we will create a **driver** or **runner** class.
A driver class is often just a class with a `main()` method so that it can be
made runnable in Java. We can import numerous classes to instantiate and execute
various methods to "drive" or "run" the program.

For example, we can define the `Liquid` class
with various instance variables and methods, and a separate
driver class named `Main` that contains a `main` method to instantiate
`Liquid` instances and call the methods:

![multiple class folder structure](https://curriculum-content.s3.amazonaws.com/6676/java-multipleclasses/multiple_folder.png)

```java
public class Liquid
{
    private int currentTemp;
    private int boilingPoint;

    public Liquid(int currentTemp, int boilingPoint) {
        this.currentTemp = currentTemp;
        this.boilingPoint = boilingPoint;
    }

    public void setCurrentTemp(int currentTemp) {
        this.currentTemp = currentTemp;
    }

    public boolean isBoiling()
    {
        return currentTemp >= boilingPoint;
    }
}
```


The `Main` class is an example of a driver class.  Notice
the `main` method must call the public methods of the
`Liquid` class to access or modify the private instance variables. 

```java
public class Main {

    public static void main(String[] args) {
        //parameters are current temperature and boiling point
        Liquid potOfMilk = new Liquid(198, 202);
        Liquid potOfWater = new Liquid(230, 212);

        System.out.println( potOfWater.isBoiling() );
        System.out.println( potOfMilk.isBoiling() );
        potOfMilk.setCurrentTemp(205);
        System.out.println( potOfMilk.isBoiling() );
    }
}
```

### Multiple classes in Java Visualizer

IntelliJ's debugger and Java visualizer can work with multiple
public classes each stored in a separate file, as is the case with
`Liquid` and `Main`.

```java
public class Liquid {
    .....
}
```

```java
public class Main {
    ....
}
```


However, the `Python Tutor` visualizer requires a single public class.
If the application involves multiple classes, the other classes must
omit the `public` keyword from the class declaration, which assigns the
default `package` access to the class.


![one public class](https://curriculum-content.s3.amazonaws.com/6676/java-multipleclasses/onepublicclass.png)
