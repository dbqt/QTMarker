# QTMarker
Marker / Pen for VRChat Avatar SDK 3.0

- Not Quest compatible.
- Simple pen that can be toggled on or off with expressions.
- Can be rainbow ink or any flat color, selectable with a color wheel.
- Works on any avatar built with VRCAvatarSDK 3.0, works with vroid avatars and doesn't require a CATS converted avatar (but will work with CATS avatars).
- Visible in mirrors.
- Simple setup.

# Installation

[Youtube video on how to setup](https://youtu.be/xSBAWNONgvo)

## Requirements
 - Unity 2019.4.31f1 (recommended)
 - Latest VRCAvatarSDK3.0
 - An avatar already setup and ready to be uploaded to VRChat

## Simple setup for empty avatar (no existing FX layer)
1. Get the latest version of the unity package [in the releases](https://github.com/dbqt/QTMarker/releases)
2. Import into your Unity project
3. Add the QTMarker prefab to the hierarchy and unpack it
4. Move the QTMarkerPosition game object as the child of the bone you want to draw from, and align it(typically the tip of the right hand index finger)
5. Move the QTMarker game object as the child of the avatar object, the parent of this should have the animation controller / VRCAvatarDescriptor
6. On the QTMarker game object, on the ParentConstraint component, click on Zero and then Activate.
7. On the avatar's VRCAvatarDescriptor, replace the FX in the playable layers with QTMarkerFX (WD)
8. On the avatar's VRCAvatarDescriptor, replace the Expressions Menu with QTMarkerExampleMenu asset
9. On the avatar's VRCAvatarDescriptor, replace the Expressions Parameters with QTMarkerExampleParameters asset
10. Upload the avatar and you are done!

## Setup for avatar with existing FX layer (merge with existing setup)
1. Get the latest version of the unity package [in the releases](https://github.com/dbqt/QTMarker/releases)
2. Import into your Unity project
3. Add the QTMarker prefab to the hierarchy and unpack it
4. Move the QTMarkerPosition game object as the child of the bone you want to draw from, and align it (typically the tip of the right hand index finger)
5. Move the QTMarker game object as the child of the avatar object, the parent of this should have the animation controller / VRCAvatarDescriptor
6. On the QTMarker game object, on the ParentConstraint component, click on Zero and then Activate.
7. Download and install the latest version of AV3Manager.unitypackage from [VRCLabs](https://github.com/VRLabs/VRChat-Avatars-3.0/releases)
8. From the VRLabs menu, open the Avatars 3.0 Manager.
9. Drag your VRC avatar descriptor into the panel.
10. Open the FX section and click on add animator to merge.
11. If you know what is 'Write Default' and know whether you use it or not, pick from the appropriate animator from the QTMarkerFXs folder. If you have no idea what 'Write Default' is, you will be using the QTMarkerFX (WD) from the QTMarkerFXs folder.
12. Drag the appropriate QTMarkerFX (WD) or (no-WD) into the controller to merge and merge as new.
13. On the avatar's VRCAvatarDescriptor, open your existing Expression Menu and add QTMarkerSubMenu as a sub menu item to your existing menu.
14. On the avatar's VRCAvatarDescriptor, open your existing Expression Parameters and copy all the parameters from QTMarkerExampleParameters over exactly the same way.
15. That's it!

## Basic usage
To draw, toggle on from the expressions menu the "Marker Toggle". 
Use the fist gesture on the left and and fingerpoint gesture with the right hand to draw.
Use the fist gesture on both hands to delete.
You can use a simple color instead of rainbow by using the "Use simple color" toggle.
You can select the simple color with the color wheel.

# For advanced users

[Youtube video on how to add to customize gestures](https://youtu.be/Cx3EOIctzJ8)

- You can look at the animation controller "QTMarkerFX (WD)" or "QTMarkerFX (no-WD)" to see how the 3 layers are built.

- If you wish to change the gestures used to draw or clear the drawings, you need to edit the QTMarkerInking layer of the animation controller by changing the conditions in the transition between "Any state" and "QTMarkerInking" or "QTMarkerClear". Don't forget to change the reverse conditions for "QTMarkerIdle". This is also useful if you want to switch it to be left handed. Just swap all the GestureRight for GestureLeft and vice-versa in this layer. You also will want to place the QTMarkerPosition game object on the left hand.

# License
This asset is under GNU General Public License v3.0
So do whatever with it, I will not be liable for anything and I provide no warranty.