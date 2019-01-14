# Constructors

### What is a Constructor?

A Constructor is a special type of method, with the same name as the class name. It is used to initialize the values of an object as soon as it is created.

***Why do we use a constructor?***

As we have seen in the previous sections, this is how we create a new object:

```Java
class Boy{
    String clothes; //instance-variables
    String mood;
    int current_speed;
    
    public void run(){
        //defining run method
    }

    public void jump(){
        //defining jump method
    }
}

public class Main{
    public static void main(String[] args){
        Boy boy_1 = new Boy(); // creating a new Boy object
    }
}
```

But, what are the values of the instance variables? They are all default values of the respective data types. So any `String` will be null, `int` shall be 0 etc.

To change the values, we have to individually, for each object use the `.` operator to assign a value.

Instead, we can use ***constructors***. With the help of constructors, we can initialize the values of an object at the time of object creation.

Let us define a constructor in the `Boy` class:

```Java
class Boy{
    String clothes; //instance-variables
    String mood;
    int current_speed;
    
    Boy(){
        clothes = "Autumn";
        mood = "Happy";
        current_speed = 0;
    }

    public void run(){
        //defining run method
    }

    public void jump(){
        //defining jump method
    }
}

public class Main{
    public static void main(String[] args){
        Boy boy_1 = new Boy(); // creating a new Boy object by calling the constructor

        System.out.println("Clothes = " + boy_1.clothes);
        System.out.println("Mood = " + boy_1.mood);
        System.out.println("Speed = " + boy_1.speed);
    }
}
```

Output:
```
Clothes = Autumn
Mood = Happy
Speed = 0
```

Now, whenever a new Boy object is created using the `new Boy()` command, this method (constructor) will be called. All objects created using the `new Boy()` command will be initialized with the same values: `Autumn`, `Happy`, and `0`

Constructors save us time by allowing us to give default values to new object's data.

**Note: Even though constructors don't have any `return` statement, it stills returns an object. That is the object we just initialized.**

![with & without](https://storage.googleapis.com/edyst-assets/static/with_without_constructor.png)

---

Constructors are another type of method. So, we can do a lot of the things we did with methods.

For example, we can print a pattern or call other methods. These will get executed whenever the constructor is called - at the time of creation of the object. This is ***allowed***. However, we generally don't do this because we use constructors mainly for initializing new objects.