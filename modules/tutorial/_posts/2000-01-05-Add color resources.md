---
title: Add color resources
---

# Add color resources
<br><br>

So far you have learned how to change property values. Next, you will learn how to create more resources like the string resources you worked with earlier. Using resources enables you to use the same values in multiple places, or to define values and have the UI update automatically whenever the value is changed.

What you'll learn
How resources are defined.
Adding and using color resources.
The results of changing layout height and width.
Step 1: Add color resources
First, you'll learn how to add new color resources.

Change the text color and background of the TextView

In the Project panel on the left, double-click on res > values > colors.xml to open the color resource file.



<resources>
    <color name="colorPrimary">#6200EE</color>
    <color name="colorPrimaryDark">#3700B3</color>
    <color name="colorAccent">#03DAC5</color>
</resources>
The colors.xml file opens in the editor. So far, three colors have been defined. These are the colors you can see in your app layout (for example, purple for the app bar).

Go back to fragment_first.xml so you can see the XML code for the layout.
Add a new property to the TextView called android:background, and start typing to set its value to @color. You can add this property anywhere inside the TextView code.

A menu pops up offering the predefined color resources:



Choose @color/colorPrimaryDark.
Change the property android:textColor and give it a value of @android:color/white.

The Android framework defines a range of colors, including white, so you don't have to define white yourself.
In the layout editor, you can see that the TextView now has a dark blue or purple background, and the text is displayed in white.


Step 2: Add a new color to use as the screen background color
Back in colors.xml, create a new color resource called screenBackground:
<color name="screenBackground">#FFEE58</color>

A Color can be defined as 3 hexadecimal numbers (#00-#FF, or 0-255) representing the red, blue, and green (RGB) components. The color you just added is yellow. Notice that the colors corresponding to the code are displayed in the left margin of the editor.



Note that a color can also be defined including an alpha value (#00-#FF), which represents the transparency (#00 = 0% = fully transparent, #FF = 100% = fully opaque). When included, the alpha value is the first of 4 hexadecimal numbers (ARGB).

The alpha value is a measure of transparency. For example, #88FFEE58 makes the color semi-transparent, and if you use #00FFEE58, it's fully transparent and disappears from the left-hand bar.

Go back to fragment_first.xml.
In the Component Tree, select the ConstraintLayout.

In the Attributes panel, select the background property and press Enter. Type "c" in the field that appears.
In the menu of colors that appears, select @color/screenBackground. Press Enter to complete the selection.


Click on the yellow patch to the left of the color value in the background field.




It shows a list of colors defined in colors.xml. Click the Custom tab to choose a custom color with an interactive color chooser.

Feel free to change the value of the screenBackground color, but make sure that the final color is noticeably different from the colorPrimary and colorPrimaryDark colors.
Step 3: Explore width and height properties
Now that you have a new screen background color, you will use it to explore the effects of changing the width and height properties of views.

In fragment_first.xml, in the Component Tree, select the ConstraintLayout.



In the Attributes panel, find and expand the Layout section.


The layout_width and layout_height properties are both set to match_parent. The ConstraintLayout is the root view of this Fragment, so the "parent" layout size is effectively the size of your screen.
Tip: All views must have layout_width and layout_height properties.

Notice that the entire background of the screen uses the screenBackground color.



Select textview_first. Currently the layout width and height are wrap_content, which tells the view to be just big enough to enclose its content (plus padding)
Change both the layout width and layout height to match_constraint, which tells the view to be as big as whatever it's constrained to.

The width and height show 0dp, and the text moves to the upper left, while the TextView expands to match the ConstraintLayout except for the button. The button and the text view are at the same level in the view hierarchy inside the constraint layout, so they share space.


Explore what happens if the width is match_constraint and the height is wrap_content and vice versa. You can also change the width and height of the button_first.
Set both the width and height of the TextView and the Button back to wrap_content.
