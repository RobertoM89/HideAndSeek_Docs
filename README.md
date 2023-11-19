Shelf Picker - A Maya tool for animators
========================================

---

**Version 1.0 Beta**
**November 2023**

**Tested on Maya: 2023**

**Shelf Picker** is a Maya tool for 3D animators developed by *[Roberto Menicatti](https://linktr.ee/robertomenicatti)*, which allows you to easily build a shelf-based picker for any rig you want.

Give a look at the video or read the guide below if you want to see its functionalities.

---

- [Download and Install](https://robertom89.github.io/ShelfPicker_Docs/#download-and-install)
- [Quick Guide](https://robertom89.github.io/ShelfPicker_Docs/#quick-guide)
- [Tool Icons](https://robertom89.github.io/ShelfPicker_Docs/#tool-icons)
- [Command List](https://robertom89.github.io/ShelfPicker_Docs/#command-list)

## Download and Install

After downloading the zipped folder, uncompress it and move *ShelfPicker* folder (the one without the Version number in the name), to Maya scripts folder.

You can find Maya scripts folder here:

- on **Windows**

```
    <user’s directory>/Documents/maya/scripts/  
```

- on **macOS**

```
    Library/Preferences/Autodesk/maya/scripts/  
```

With Maya open, simply drag the file **Installer.py** onto the viewport to add the tool to the current shelf.
Click on the new shelf button to run **Shelf Picker**.

---

## Quick Guide

Start by creating a new shelf for your picker by clicking on *Create Picker Shelf.*
Select a control on your rig and look for the side tag in its name.
Then, type the left and right tag in the corresponding fields in the UI.
Choose the icon set and click on the icon that best matches your selection.
A new picker-icon will appear on the shelf.
You can customize any new icon with an optional label or a background color through the corresponding buttons at the bottom of the UI.
If you prefer, you can take a screenshot rather than use one of the icons: tick *ScreenCap*, center your subject in the persp camera and click on the camera button.
Tick *ShowNurbs* if you want to keep the visibility of the controls in the screenshot.

Now, left-click the picker icon on the shelf to select the left control of your character.
Right-click it to select the right one. Middle-click it to select both.
If you'd rather think in terms of screen left and screen right, click on the Left-Right icon (see [here](https://robertom89.github.io/ShelfPicker_Docs/#tool-icons)) to toggle side mode.
Hold Shift while clicking the picker icon to add the control to the current selection.
Hold Control to remove it.

If more rigs share the same naming convention, you can use the same picker button for all of them.
Just select first a random control of the rig you want to work with and let the shelf buttons detect its namespace 
automatically to apply the selection to the character you're currently animating.
Alternatively, you can create a Preselection Button for the rig. Center your subject in the persp camera and click on *Add Preselection Button*.

If you want to select all the controls of your rig, select three random controls and run *Select All Controls*.

You can also use the tool to toggle visibility of objects of faces in the scene.
Switch to *Visibility Toggler* mode, make a selection and click any icon button to add a visibility toggler button to the shelf.

To arrange the shelf layout, you can add separators, display the icons over two rows or open the Shelf Editor through the buttons at the top of the UI.

Remember to run *Refresh Shelf* button (see [here](https://robertom89.github.io/ShelfPicker_Docs/#tool-icons)) at every new session of Maya to rebuild the hotkeys for the shelf-picker.

---

## Tool Icons

The first time you add a picker icon to the active shelf or whenever you create a new shelf through the *Create Picker Shelf* button, these four icons will appear on the shelf.

##### Shelf Picker button

<div class="row">
  <div class="column">
    <img src="https://robertom89.github.io/ShelfPicker_Docs/images/ShelfPicker_icon.png" alt="Icon" width="15%"/>
  </div>
</div>

Click on this icon to run **Shelf Picker** tool.

##### Refresh Shelf button

<div class="row">
  <div class="column">
    <img src="https://robertom89.github.io/ShelfPicker_Docs/images/refresh_shelf_126.png" alt="Icon" width="15%"/>
  </div>
</div>

Click on this icon whenever you start a new session of Maya. This is needed to reload all the hotkeys of the picker icons.

##### Left Right button

<div class="row">
  <div class="column" >
    <img src="https://robertom89.github.io/ShelfPicker_Docs/images/sel_screen.png" alt="Icon" width="15%"/>
    <img src="https://robertom89.github.io/ShelfPicker_Docs/images/sel_char.png" alt="Icon" width="15%"/>
  </div>
</div>

If the first of these two icons is visible (the other one will be hidden), "left selection" and "right selection" will refer to the left and right sides of the *screen*.

If the second of these two icons is visible (the other one will be hidden), "left selection" and "right selection" will refer to the left and right side of the *character*.

Clicking on any of the two will toggle the selection mode and the icon.

---

## Command List

### Create Picker Shelf

Even if the picker buttons can be added to any shelf, it is adviced to create a specific shelf for your character's picker. Click on *Create Picker Shelf* to create a new shelf. Optionally, enter a name for the new shelf.

The new shelf will be created and populated with the *Shelf Picker* button, the *Refresh Shelf* button and the *Left Right* button (see [here](https://robertom89.github.io/ShelfPicker_Docs/#tool-icons)).

### Open Shelf Editor

Open Maya Shelf Editor to rearrange icons and separators on the shelf. You can also reach it through *Windows -> Settings/Preferences -> Shelf Editor.*

### Add Shelf Separator

Add a shelf separator to the current shelf. 

### One/Two Rows Shelf Layout

If too many icons are on the shelf, some of them will be hidden. Click on *Two Rows Shelf Layout* to increase the height of the shelf and arrange the icons across two rows. Click on *One Row Shelf Layout* to revert the shelf back to its default height.

### Select Mode: Picker / Visibility Toggler

**Shelf Picker** tool can work in two modes.

- **Picker**  mode:  the icons added to the shelf will work as selection buttons;
- **Visibility Toggler** mode: the icons added to the shelf will toggle the visibility of the meshes/faces associated to the button.

### Select All Controls

This command tries to select all the controls of a rig. Successful behavior highly depends on the  naming conventions of the rig. Select three controls and run the command.

The command tries to extract the common suffix or prefix from the selected controls names. Therefore, it is suggested to select three controls which have very different names, such as head, hand and foot. Selecting three controls of the same body part may lead to an unaccurate result. For example:

- from *"head_JohnDoe_CTRL"*, *"hand_JohnDoe_CTRL"*, *"foot_JohnDoe_CTRL"* the script would extract "_JohnDoe_CTRL" and would find all the objects in the scene which ends with such a tag, which are hopefully all the desired ones;
- from *"fk1_arm_JohnDoe_CTRL"*, *"fk2_arm_JohnDoe_CTRL"*, *"fk3_arm_JohnDoe_CTRL"* the script would extract *"_arm_JohnDoe_CTRL"* and would find all the objects in the scene which ends with such a tag, which are most probably just a small subset.

### Add Preselection Button

If more rigs in the scene share the same control names, you can use the same picker button for all of them. You just need to select first a random control of the rig you want to work with before running any shelf button so that the tool can detect its namespace.

Alternatively, you can create a Preselection Button for each rig. Center the face or the whole character in the persp camera and click on *Add Preselection Button*. A screenshot will be taken and a button will appear on the shelf. Clicking on this button will preselect the character so that clicking on a picker button will use the correct namespace.

### Left and Right Controls Tags

Insert here the tags used in control names to differentiate between left and right side. This of course is not needed if you are creating a picker button for a control that has no side (e.g. nose, head, chest...).

### Icon Set Selection

Choose the icon set to use among the three given. Custom icons can be used, by replacing the icons in one of the sets in the folder:

```
HideAndSeek/icons/
```

Keep the same file names and resolutions. For each image you'll need to have a 40x40 and a 128x128 version.

#### ScreenCap

Tick ScreenCap if you want to make a screenshot of the viewport and use it as icon. The screenshot will use the **persp** camera with a 1:1 format, so switch to persp view and center your subject. You can activate the resolution gate to have a preview of the height of the icon. Consider the same length for the width.

Click on the camera icon to create the shelf button with the screenshot icon.

Tick **Show Nurbs** if you want the nurbs to be visible in your screenshot.

### Add Icon to Shelf

Select the icon the better represents your selection to create a shelf button that will:

- select again your selection if in **Picker Mode**
- toggle the visibility of your selection if in **Visibility Toggler Mode**

If the button was created in Picker Mode, use:

- **LMB**: to select the stored control on the left side
- **RMB**: to select the stored control on the right side
- **MMB**: to select the stored control on both sides
- **Alt** + **LMB/RMB/MMB**: to force the usage of the namespace stored when creating the button
- **Shift** + **LMB/RMB/MMB**: to add to selection
- **Ctrl** + **LMB/RMB/MMB**: to remove from selection
- **Shift** + **Alt** + **LMB/RMB/MMB**: combination of the above
- **Ctrl** + **Alt** + **LMB/RMB/MMB**: combination of the above
- Double **LMB**: to delete the shelf button

### Optional Label for Shelf Button

Enter here a label for the shelf button before clicking on the icon buttons when creating a shelf button. This is optional.

### Add Background Color

Tick the checkbox and select a background color for the shelf button before clicking on the icon buttons when creating the shelf button. This is optional.

<button onclick="topFunction()" id="myBtn" title="Go to top" style="display: none;   width: 50px;   height: 50px;   position: fixed;   bottom: 20px;   right: 30px;   z-index: 99;   font-size: 18px;   display: inline-flex;   flex-direction: column;   justify-content: center;   align-items: center;   border: none;   outline: none;   background-color: #2D7180;   color: white;   cursor: pointer;   padding: 15px;   border-radius: 100%;">Top </button>

<script>
//Get the button
var mybutton = document.getElementById("myBtn");

// When the user scrolls down 20px from the top of the document, show the button
window.onscroll = function() {scrollFunction()};

function scrollFunction() {
  if (document.body.scrollTop > 20 || document.documentElement.scrollTop > 20) {
    mybutton.style.display = "block";
  } else {
    mybutton.style.display = "none";
  }
}

// When the user clicks on the button, scroll to the top of the document
function topFunction() {
  document.body.scrollTop = 0;
  document.documentElement.scrollTop = 0;
}
</script>

<style>
* {
  box-sizing: border-box;
}

.column {
  float: left;
  width: 50%;
  padding: 5px;
}

/* Clearfix (clear floats) */
.row::after {
  content: "";
  clear: both;
  display: table;
}
</style>
