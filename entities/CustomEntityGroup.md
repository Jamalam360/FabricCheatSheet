[Back to contents](https://github.com/Jamalam360/FabricCheatSheet/blob/main/README.md)

## Creating a Custom Entity Group

Entity groups are useful for things like Enchantments that do extra damage to certain entities

### Creating the group

In your mod initialiser or a util class of your choice:
```java
public static final EntityGroup CUSTOM_ENTITY_GROUP = new EntityGroup();
```

### Using your entity group with a custom entity

Simply override `getGroup()` within your entity class:

```java
@Override
public EntityGroup getGroup() {
    return ModInit.CUSTOM_ENTITY_GROUP;
}
```

Then to check if an `LivingEntity` instance is in a specific `EntityGroup`, do `livingEntityInstance.getGroup() == ModInit.CUSTOM_ENTITY_GROUP`>
