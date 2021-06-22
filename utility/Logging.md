[Back to contents](https://github.com/Jamalam360/FabricCheatSheet/blob/main/README.md)

## Logging

A logger can be used to log messages to the console in a more professional and clean manner than a `System.out.println("your message")`.
Minecraft uses this to log information and errors.

The output is formatted as below:
`22.06 15:28:43 [Server] main/INFO [NoTrample] Initializing`

### Creating a Logging Method

Follow the following steps in your mod initliaser or a new logging utility class

Create a new logger variable:
```java
public static Logger LOGGER = LogManager.getLogger();
```

Ensure you import `org.apache.logging.log4j.Logger` rather than any other class

Then you can create a method to log messages:

```java
public static void log(Level level, String message) {
        LOGGER.log(level, "[" + "Your Mod Name Here!" + "] " + message);
}
```

To use this, simply call `log` when you want to log a message:
```java
YourLoggingClass.log(Level.INFO, "my mod can log stuff!")
```

The `info` parameter defines this part of the log message: `main/INFO`

Options include
- Level.INFO
- Level.WARN
- Level.ERROR
- Level.FATAL
