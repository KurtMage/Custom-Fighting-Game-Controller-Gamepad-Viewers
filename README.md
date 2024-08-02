If you run into any issues or have any suggestions, feel free to @ me on twitter: @KurtMage. :)

# Gamepad Viewer Layouts

Various controller layouts for gamepad viewer. Example of some 2XKO layouts:

![](https://github.com/KurtMage/KurtMage.github.io/blob/main/gifs/4%20layouts%20including%20stick.gif)

<!----><a name="a-how-to-set-up-for-obs"></a>

# How to set up for OBS
## Video Tutorial:

[<img src="https://github.com/KurtMage/KurtMage.github.io/blob/main/images/click%20here%20for%20video%20tutorial.png" width="400" />](https://youtu.be/DfroDv4Eoyo)

1. Choose a layout from [the layouts section](#layouts-by-controller-layout). Copy the link for the layout you want.
NOTE: Every URL below has `p=1` in it. This is what determines what player your controller is, and you can change it. For example, if the controller that you want to visualize is player 3, you would change this to `p=3`.
2. In OBS, click the + in sources to add a source. Select Browser as the type.
3. In the URL box, put the URL from step 1.
4. Change the Width to 1500.
5. Final important note: you need to give it an input from the controller for it to show up. Other than that, you're all set up!

# How to change your button layout for custom controls

[<img src="https://github.com/KurtMage/KurtMage.github.io/blob/main/images/click%20here%20for%20video%20tutorial.png" width="400" />](https://youtu.be/qON59ngD63A)

1. Right-click on the browser source you created in [the setup section](#a-how-to-set-up-for-obs).
2. Copy-paste the following code into the `Custom CSS` dialog box below the line that says `body { background-color: rgba(0, 0, 0, 0); margin: 0px auto; overflow: hidden; }` (**Make sure you do not delete that line**):
```
:root {
     /***************
     *   0  1  2 3  *
     * 0 L  M  H D  *
     * 1 S1 S2 T P  *
     ****************/

    --top-row-index-finger-button-row: 0;
    --top-row-index-finger-button-col: 0;

    --top-row-middle-finger-button-row: 0;
    --top-row-middle-finger-button-col: 1;

    --top-row-ring-finger-button-row: 0;
    --top-row-ring-finger-button-col: 2;

    --top-row-pinky-finger-button-row: 0;
    --top-row-pinky-finger-button-col: 3;
    
    --bot-row-index-finger-button-row: 1;
    --bot-row-index-finger-button-col: 0;

    --bot-row-middle-finger-button-row: 1;
    --bot-row-middle-finger-button-col: 1;

    --bot-row-ring-finger-button-row: 1;
    --bot-row-ring-finger-button-col: 2;

    --bot-row-pinky-finger-button-row: 1;
    --bot-row-pinky-finger-button-col: 3;
}
```
3. You can change any of the variables in order to change what button goes where. Each variable refers to the row/column of a button. The buttons are referenced by the following table:
   
|   | 0 | 1 | 2 | 3 |
| - | - | - | - | - |
| 0 | L | M | H | D |
| 1 | S1| S2| T | P |

So, for example, if you wanted to set the top-right button to `T`, you would look at the table and see that `T`'s row is 1 and column is 2. The top right button would be your pinky finger on the top row. So you would set `--top-row-pinky-finger-button-row: 1` and `--top-row-pinky-finger-button-row: 2` (replacing the `0` and `3` that these variables are currently set to, to `1` and `2`).

4. Hit "Ok" in the dialog box and then input something on your controller to display your layout.

## Example demo of customizing button layout:
![](https://github.com/KurtMage/KurtMage.github.io/blob/main/gifs/customize%20controls.gif)

# How to create your own buttons or mix and match buttons from other layouts
## Video tutorial for changing a suite of buttons
[<img src="https://github.com/KurtMage/KurtMage.github.io/blob/main/images/click%20here%20for%20video%20tutorial.png" width="400" />](https://youtu.be/HqZfp82sRvM)
## Video tutorial for changing individual buttons
[<img src="https://github.com/KurtMage/KurtMage.github.io/blob/main/images/click%20here%20for%20video%20tutorial.png" width="400" />](https://youtu.be/9nJ42XmqVWk)

There are a number of variables that can be changed in order to make your own custom buttons or use buttons from different layouts with each other. To change a variable, you:
1. Right-click on the browser source you created in [the setup section](#a-how-to-set-up-for-obs).
NOTE: Every URL below has `p=1` in it. This is what determines what player your controller is, and you can change it. For example, if the controller that you want to visualize is player 3, you would change this to `p=3`.
2. Get your variables from the [button variables and how to format your files](#button-variables-and-how-to-format-your-files) section.
3. Get the URL for your image, as described in the [button variables and how to format your files](#button-variables-and-how-to-format-your-files) section.
4. Copy-paste the following code into the `Custom CSS` dialog box below the line that says `body { background-color: rgba(0, 0, 0, 0); margin: 0px auto; overflow: hidden; }` (** Make sure you do not delete that line **):
```
:root {
     /* Your variables will go below here */

     /* Your variables will go above here */
}
```
In between the comments that say "Your variables will go above/below here", add a line for each variable. Each line must be formatted like `--your-variable-name: url(https://your-url.com/1234.png);`. **IMPORTANT NOTE: YOU NEED TO ADD ".png" at the end of your URL** . For example (feel free to test with this example), if you want to change your dash button, you will use the variable `--top-row-pinky-finger-button-source-image` and if the URL to the formatted image with the dash button you want is `https://imgur.com/B0oG3qJ`, then your `Custom CSS section` will have:
```
:root {
     /* Your variables will go below here */

     --top-row-pinky-finger-button-source-image: url(https://imgur.com/B0oG3qJ.png);

     /* Your variables will go above here */
}
```
5. Press "ok" and it should work!

## Button variables and how to format your files

The sections below will provide buttons you can mix and match. It will also describe how you can make your own. The images need to be hosted on a website so that you have a link to them. I use imgur.com and the provided buttons are hosted there. When you have an image that is properly formatted (how to do this is described in the following sections), upload it to imgur and copy the link to the file like this:

![](https://github.com/KurtMage/KurtMage.github.io/blob/main/gifs/how%20to%20copy%20imgur%20link.gif)

Here are the sections for how to format files for each type of button:

[Arrow buttons](#formatting-arrow-buttons)

[Buttons on the right side of the controller](#formatting-buttons-on-the-right-side-of-the-controller)

[Start and back buttons](#formatting-start-and-back-buttons)

### Formatting arrow buttons

There are several arrow button files you can use here: https://imgur.com/a/gAoUWzU.

The variable in order to change the arrows is `--arrow-button-source-image`. You can also change individual arrows with `--left-arrow-source-image`, `--down-arrow-source-image`, `--right-arrow-source-image`, and `--up-arrow-source-image`. 

A properly formatted image for arrow buttons looks like this:

![](https://github.com/KurtMage/KurtMage.github.io/blob/main/images/Arrows%20darkmode%20lighter%20grey%20circle.png)

This file must be 600px by 300px with each circle for your button being 150px by 150px. The unpressed version of the button goes on top and the pressed version goes immediately underneath it. The ordering must be left, down, right, up.

### Formatting buttons on the right side of the controller

There are several right-side-of-the-controller button files you can use here: https://imgur.com/a/qF0SMMX.

The variable in order to change all the buttons is `--button-source-image`. You can also change individual buttons with `--top-row-index-finger-button-source-image`, `--top-row-middle-finger-button-source-image`, `--top-row-ring-finger-button-source-image`, `--top-row-pinky-finger-button-source-image`, `--bot-row-index-finger-button-source-image`, `--bot-row-middle-finger-button-source-image`, `--bot-row-ring-finger-button-source-image`, `--bot-row-pinky-finger-button-source-image`.

Additionally, you can change which button in the file you are referencing by using the variables described in the [how to change your button layout for custom controls](#how-to-change-your-button-layout-for-custom-controls) section. For instance, if you want to put the `P` button from [this file](https://imgur.com/B0oG3qJ) into the top-row-index-finger spot, you would have:
```
:root {
     /* Your variables will go below here */

    --top-row-index-finger-button-source-image: url(https://imgur.com/B0oG3qJ.png);
    --top-row-index-finger-button-row: 1;
    --top-row-index-finger-button-col: 3;

     /* Your variables will go above here */
}
```
The `1` and `3` refers to the row/column of the image file. Think of this image file as a 2-row, 4-column image where each element contains the pressed version of the button on top of the bottom button. This is demonstrated in the image below.

A properly formatted image for arrow buttons looks like this (without the "row"/"col" part, which is to demonstrate how to reference the buttons):

![](https://github.com/KurtMage/KurtMage.github.io/blob/main/images/Row%20Col%20example1.png)


This file must be 600px by 600px with each circle for your button being 150px by 150px. The unpressed version of the button goes on top and the pressed version goes immediately underneath it.

### Formatting start and back buttons

There are several start and back button files you can use here: https://imgur.com/a/FMUPGBl.

The variable in order to change the arrows is `--start-select-button-source-image`. 

A properly formatted image for start/back buttons looks like this:

![](https://github.com/KurtMage/KurtMage.github.io/blob/main/images/StartSelect%20grey.png)

This file must be 200px by 200px with each circle for your button being 100px by 100px. The unpressed version of the button goes on top and the pressed version goes immediately underneath it and the Start button is on the left and the Back button is on the right.

<!----><a name="#layouts-by-controller-layout"></a>

# Layouts by controller layout

[Hitbox](#hitbox-layouts-by-game)

[Fight stick layouts](#fight-stick-layouts-by-game)


[Playstation 4 controller](#playstation-4-controller-layouts-by-game)

# Hitbox layouts by game
[2XKO](#2xko)

[Street Fighter](#street-fighter)
## 2XKO

![](https://github.com/KurtMage/KurtMage.github.io/blob/main/gifs/hitbox/2XKO/4%20hitbox%20layous%20labeled.gif)

### Light mode
```
https://gamepadviewer.com/?p=1&s=7&map=%7B%7D&editcss=https://kurtmage.github.io/hitbox%20layout/2XKO/light-mode.css
```

### Light mode 10px border
```
https://gamepadviewer.com/?p=1&s=7&map=%7B%7D&editcss=https://kurtmage.github.io/hitbox%20layout/2XKO/light-mode-D-P-buttons-10px-border.css
```

### Dark mode
```
https://gamepadviewer.com/?p=1&s=7&map=%7B%7D&editcss=https://kurtmage.github.io/hitbox%20layout/2XKO/dark-mode.css
```

### Dark mode white borders
```
https://gamepadviewer.com/?p=1&s=7&map=%7B%7D&editcss=https://kurtmage.github.io/hitbox%20layout/2XKO/dark-mode-white-outlines.css
```

### Legacy layout 1
![](https://github.com/KurtMage/KurtMage.github.io/blob/main/gifs/hitbox/2XKO/white%20buttons%20with%20border1.gif)
```
https://gamepadviewer.com/?p=1&s=7&map=%7B%7D&editcss=https://kurtmage.github.io/hitbox%20layout/2XKO/white-button-press-outlined-letters.css
```
### Legacy layout 2
![](https://github.com/KurtMage/KurtMage.github.io/blob/main/gifs/hitbox/2XKO/dim%20buttons.gif)
```
https://gamepadviewer.com/?p=1&s=7&map=%7B%7D&editcss=https://kurtmage.github.io/hitbox%20layout/2XKO/dim-buttons.css
```

## Street Fighter
### Layout 1
![](https://github.com/KurtMage/KurtMage.github.io/blob/main/gifs/hitbox/Street%20Fighter/dim%20buttons.gif)
```
https://gamepadviewer.com/?p=1&s=7&map=%7B%7D&editcss=https://kurtmage.github.io/hitbox%20layout/street%20fighter/dim-buttons.css
```

# Fight stick layouts by game
[2XKO](#fight-stick-2xko)

<!----><a name="fight-stick-2xko"></a>

## 2XKO
![](https://github.com/KurtMage/KurtMage.github.io/blob/main/gifs/fight%20stick/sticks.gif)

Light mode (top layout):
```
https://gamepadviewer.com/?p=1&s=7&map=%7B%7D&editcss=https://kurtmage.github.io/fight%20stick/2XKO/light-mode.css
```
Dark mode (bottom layout):
```
https://gamepadviewer.com/?p=1&s=7&map=%7B%7D&editcss=https://kurtmage.github.io/fight%20stick/2XKO/dark-mode.css
```

# Playstation 4 controller layouts by game
[2XKO](#ps4-2xko)

<!----><a name="ps4-2xko"></a>
## 2XKO
![](https://github.com/KurtMage/KurtMage.github.io/blob/main/gifs/Playstation%204%20controller/2XKO/press%20white%20outlined.gif)
```
https://gamepadviewer.com/?p=1&s=5&map=%7B%7D&editcss=https://kurtmage.github.io/PS4%20controller/2XKO/pressed-white-outlined-buttons.css
```
