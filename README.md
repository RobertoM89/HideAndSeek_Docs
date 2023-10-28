Hide and Seek - A Maya tool for animators
=========================================

---

**Version 1.0 Beta**
**October 2023**

**Tested on Maya: 2023**

**Hide and Seek** is a Maya tool for 3D animators developed by *[Roberto Menicatti](https://linktr.ee/robertomenicatti)*, which allows you to easily build a shelf-based picker for any rig you want.

Give a look at the video or read the guide below if you want to see its functionalities.

{% include youtube.html id="qKnVufSUqgc" %}

---

- [Download and Install](https://robertom89.github.io/HideAndSeek_Docs/#download-and-install)
- [Create a New Shelf](https://robertom89.github.io/HideAndSeek_Docs/#create-a-new-shelf)

## Download and Install

After downloading the zipped folder, uncompress it and move *HideAndSeek* folder (the one without the Version number in the name), to Maya scripts folder.

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
Click on the new shelf button to run **Hide and Seek**.

---

## Quick Guide

## Tool Icons

The first time you add a picker icon to the active shelf or whenever you create a new shelf through the *Create Shelf* button, these four icons will appear on the shelf.

<div class="row">
  <div class="column">
    <img src="https://robertom89.github.io/HideAndSeek_Docs/images/HideAndSeek_icon.png" alt="Icon" width="15%"/>
  </div>
</div>

Click on this icon to run **Hide and Seek** tool.

<div class="row">
  <div class="column">
    <img src="https://robertom89.github.io/HideAndSeek_Docs/images/refresh_shelf_126.png" alt="Icon" width="15%"/>
  </div>
</div>

Click on this icon whenever you start a new session of Maya. This is needed to reload all the hotkeys of the picker icons.

<div class="row">
  <div class="column" >
    <img src="https://robertom89.github.io/HideAndSeek_Docs/images/has_sel_screen.png" alt="Icon" width="15%"/>
    <img src="https://robertom89.github.io/HideAndSeek_Docs/images/has_sel_char.png" alt="Icon" width="15%"/>
  </div>
</div>

If the first of these two icons is visible (the other one will be hidden), "left selection" and "right selection" will consider the left and right sides of the *screen*.

If the second of these two icons is visible (the other one will be hidden), "left selection" and "right selection" will consider the left and right side of the *character*.

Clicking on any of the two will toggle the selection mode and the icon.


## Command List

### Create a New Shelf

Even if the picker buttons can be added to any shelf, it is adviced to create a specific shelf for your character's picker. Click on *Create Shelf* to create a new shelf. Optionally, enter a name for the new shelf.

The new shelf will be created and populated with the *Hide and Seek* button, the *Refresh Shelf* button and the *Left Right* button (see below).

### Add Shelf Separator

Add a shelf separator to the current shelf. To move the shelf separator along the shelf, go to *Windows -> Settings/Preferences -> Shelf Editor.*

### One/Two Rows Shelf Layout

If too many icons are on the shelf, some of them will be hidden. Click on *Two Rows Shelf Layout* to increase the height of the shelf and arrange the icons across two rows. Click on *One Row Shelf Layout* to revert the shelf back to its default height.

### Select Mode: Picker / Visibility Toggler

**Hide and Seek** tool can work in two modes. If *Picker* mode is selected, the icons added to the shelf will work as selection buttons, if *Visibility Toggler* mode is selected, the icons added to the shelf will toggle the visibility of the meshes/faces associated to the button.

### Select All Controls

This command tries to select all the rig controls. Successful behavior highly depends on the  naming conventions of the rig. Select three controls and run the command.

The command tries to extract from the selected controls names the common suffix or prefix. Therefore, it is suggested to select three controls which have very different names, such as head, hand and foot. Selecting three controls of the same body part may lead to an unaccurate result. For example:

- from *"head_JohnDoe_CTRL"*, *"hand_JohnDoe_CTRL"*, *"foot_JohnDoe_CTRL"* the script would extract "_JohnDoe_CTRL" and would find all the objects in the scene which ends with such a tag, which are hopefully all the desired ones;
- from *"fk1_arm_JohnDoe_CTRL"*, *"fk2_arm_JohnDoe_CTRL"*, *"fk3_arm_JohnDoe_CTRL"* the script would extract *"_arm_JohnDoe_CTRL"* and would find all the objects in the scene which ends with such a tag, which are most probably just a small subset.

### Add Preselection Button

If more rigs in the scene share the same control names, you will have to select a random control of the rig you need before executing any shelf button so that the tool can detect its namespace and then select the corresponding selection set. Rather then selecting a random control from the viewport you can create a preselection button for each rig.

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

### Optional Label for Shelf Button

Enter here a label for the shelf button before clicking on the icon buttons when creating a shelf button. This is optional.

### Add Background Color

Select an optional background color for the shelf button. Tick the checkbox before clicking on the icon buttons when creating the shelf button.

`<button onclick="topFunction()" id="myBtn" title="Go to top" style="display: none;   width: 50px;   height: 50px;   position: fixed;   bottom: 20px;   right: 30px;   z-index: 99;   font-size: 18px;   display: inline-flex;   flex-direction: column;   justify-content: center;   align-items: center;   border: none;   outline: none;   background-color: #2D7180;   color: white;   cursor: pointer;   padding: 15px;   border-radius: 100%;">`Top `</button>`

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
