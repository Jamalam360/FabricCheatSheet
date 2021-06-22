[Back to contents](../README.md)

### Summons a lightning bolt onto an entity

```java
public static void smiteTarget(Entity target) {
        if (!user.world.isClient) { //Checks we are server side
            BlockPos blockPos = target.getBlockPos(); //Stores position of target for later use

            LightningEntity lightningEntity = EntityType.LIGHTNING_BOLT.create(target.world); //Creates the lightning entity
            lightningEntity.refreshPositionAfterTeleport(Vec3d.ofBottomCenter(blockPos)); //Teleports the lightning entity to the block pos

            target.world.spawnEntity(lightningEntity); //Actually spawns the lightning entity

            target.playSound(SoundEvents.ITEM_TRIDENT_THUNDER, 5.0F, 1.0F); //Plays the trident lightning sound
        }
    }
```
