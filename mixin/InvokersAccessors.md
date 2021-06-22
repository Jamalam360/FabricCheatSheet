[Back to contents](../README.md)

## Invokers and Accessors

Invokers and accessors can be used to call and set/get methods/fields respectively that are private or package-private to a class.

### Invokers

Invokers are used like so:
```java
@Mixin(TheBestExampleClassEver.class)
public interface InvokerMixin { //Must be an interface
    @Invoker
    int invokeACoolMethod(int param1, double param2); //Invokes a method called 'aCoolMethod' in the target class taht takes an int and a double as arguments. The method to invoke is determined by the invokers name 

    @Invoker("aCoolMethod")
    int invokeACoolMethodDifferently(int param1, double param2); //Invokes a method called 'aCoolMethod' in the target class taht takes an int and a double as arguments. The method to invoke is determined by the invokers argument
}
```

Both of these are valid and you can decide which one you prefer

To call `aCoolMethod` you can now do:

```java
    ((InvokerMixin) theBestExampleClassEverInstance).invokeACoolMethod(1, 5.3);
```

### Accessors

Accessors are used like so:
```java
@Mixin(TheBestExampleClassEver.class) //Has a float called aCoolFloat
public interface AccessorMixin { //Must be an interface
    @Accessor("aCoolFloat")
    float getACoolFloat(); //Gets aCoolFloat

    @Accessor("aCoolFloat")
    void setACoolFloat(float value); //Sets aCoolFloat to the value parameter
}
```

To get and set `aCoolFloat` you can now do:

```java
    float f = ((AccessorMixin) theBestExampleClassEverInstance).getACoolFloat();

    ((AccessorMixin) theBestExampleClassEverInstance).setACoolFloat(f + 0.2f);
```