# QTMarker
Marker / Pen for VRChat Avatar SDK 3.0

- Simple pen that can be toggled on or off with expressions.
- Can be rainbow ink or any flat color, selectable with a color wheel.
- Works on any avatar built with VRCAvatarSDK 3.0, works with vroid avatars and doesn't need to be a CATS converted avatar.
- Takes literally less than 3 minutes to setup on a new avatar (video proof below!).

# Installation

[Youtube video on how to setup](https://youtu.be/xSBAWNONgvo)

## Requirements
 - Unity 2019.4.29f1 (recommended)
 - VRCAvatarSDK3.0
 - An avatar already setup and ready to be uploaded to VRChat

## Simple setup
1. Get the latest version of the unity package [in the releases](https://github.com/dbqt/QTMarker/releases)
2. Import into your Unity project
3. Add the QTMarker prefab to the hierarchy and unpack it
4. Move the QTMarkerPosition game object as the child of the bone you want to draw from, and align it(typically the tip of the right hand index finger)
5. Move the QTMarker game object as the child of the avatar object, the parent of this should have the animation controller / VRCAvatarDescriptor
6. On the QTMarker game object, on the ParentConstraint component, click on Zero and then Activate.
7. On the avatar's VRCAvatarDescriptor, replace the FX in the playable layers with QTMarkerFX
8. On the avatar's VRCAvatarDescriptor, replace the Expressions Menu with QTMarkerExpressionsMenu asset
9. On the avatar's VRCAvatarDescriptor, replace the Expressions Parameters with QTMarkerExpressions Parameters asset
10. Upload the avatar and you are done!

## Basic usage
To draw, toggle on from the expressions menu the "Marker Toggle". 
Use the fist gesture on the left and and point with the right hand to draw.
Use the fist gesture on both hands to delete.
You can use a simple color instead of rainbow by using the "Use simple color" toggle.
You can select the simple color with the color wheel.

# For advanced users

[Youtube video on how to add to existing FX layer and customize gestures](https://youtu.be/Cx3EOIctzJ8)

## Manual advanced setup
- You can edit the GestureRight and GestureLeft layers to add your own animations to the generic hand gestures, they are currently empty.

- You can look at the animation controller "QTMarkerFX" to see how the 3 layers are built.

- If you wish to change the gestures used to draw or clear the drawings, you need to edit the QTMarkerInking layer of the animation controller by changing the conditions in the transition between "Any state" and "QTMarkerInking" or "QTMarkerClear". Don't forget to change the reverse conditions for "QTMarkerIdle". This is also useful if you want to switch it to be left handed. Just swap all the GestureRight for GestureLeft and vice-versa in this layer. You also will want to place the QTMarkerPosition game object on the left hand.

- If you want to add the marker system to an existing animation controller, you will need to rebuild the three layers (QTMarkerToggle, QTMarkerInking, QTMarkerColor) and add the QTMArker, QTMarkerIsColor, QTMarkerColorWheel parameters to your animation controller. Don't forget to setup your menu and parameters accordingly.
