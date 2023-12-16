---
title: "Experiences Packages"
permalink: /docs/tutorial1/
---

To start working in the Kengin Editor, you need to make a workspace called an
Experiences Package. This is the main container for your work.

## Create a new Package

To create a new Package:

- Go to the File menu and select 'New Package'.
- On the new screen, select a directory for the Package then click the 'Next'
  button.
- Check the details and click the 'Create' button to finish making the Package.

If you look in the directory selected above you'll see some new files and
subdirectories have been added including:

- `assets/` subdirectory: This contains your static scene data like `.usda`
  files and textures
- `experiences/` subdirectory: This contains the Experiences contained within
  the Package.

Now that we’ve got a Package to hold our game, we can add an Experience which
represents a scene.

## Create a new Experience

Before creating a new Experience, we need a scene to base it on. You
can place any `.usda` file in the `assets/` subdirectory of the Package. Most
modern 3d tools like Blender and Maya let you export your scene in `.usda`
format. When copying the `.usda` file to the `assets/` subdirectory of the
Package, don't forget to include any subdirectories which contain textures or
other related scene files.

To create a new Experience in the Kengin Editor:

- Go to the Experiences menu and select 'New Experience'. If you can't see the
  Experiences menu, make sure you have a Package open in the Editor.
- Select the `.usda` file which contains your main scene data using the file
  picker. It should be in the `assets/` subdirectory of your Package. Click 
  'Next'
- Give your Experience a name and click 'Next'.
- Check the details and click 'Create'.

You will now have an Experience in your Package. You can add more Experiences
to the Package and switch between them using the button next to the Experience
name at the top of the screen.
