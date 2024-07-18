# Compass Device for UEFN

Guides players to specific points of interest in your game.

## Files

1. `compass_device.verse`: Contains the main compass device class
2. `example_device.verse`: Contains an example implementation of the compass device
3. UI Textures: A folder containing all necessary compass textures (N, NE, E, SE, S, SW, W, NW)

## Installation Steps

1. **Add UI Textures**

   - Create a folder named "UI" in your project's Content folder.
   - Copy all compass textures (N, NE, E, SE, S, SW, W, NW) into this UI folder.

2. **Copy Verse Files**

   - Copy `compass_device.verse` and `example_device.verse` into your project's Verse folder.
   - Then add the devices to the Outliner.

3. **Configure the Compass Device (Optional)**

   - Adjust the editable properties as needed:
     - `CompassTextureSize`: Set the size of the compass texture (default: 45.0)
     - `DistanceToHideCompass`: Set the distance at which the compass will hide (default: 300.0)
     - `WidgetPos`: Set the screen position of the compass (default: X:0.5, Y:0.9)
     - `WidgetAlignment`: Set the alignment of the compass (default: X:0.5, Y:1.0)

4. **Implement the Example Device (Optional)**

   - Link the `Compass` property of the example device to your compass device.
   - Add two button devices to your scene and link them to the `EnableButton` and `DisableButton` properties of the example device.

   Using the example device:

   - When a player interacts with the enable button, the compass will be activated and point to one of the 4 random locations.
   - When a player interacts with the disable button, the compass will be deactivated.

## Functions

1. `Navigate(Player : player, Target : vector3)` displays the compass widget and guides the player to target location.
2. `Disable(Player : player)` disables the compass and removes it from the player.

## Usage

To use the compass in your game:

```
# Enable compass and set target location
Compass.Navigate(CurrentPlayer, TargetLocation)

# Disable compass
Compass.Disable(CurrentPlayer)
```

## Troubleshooting

- If the textures are not found, make sure to build the verse code before the "Copy Verse Files" step. This will create the `Assets.digest.verse` file.
