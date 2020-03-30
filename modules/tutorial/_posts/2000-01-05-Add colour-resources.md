---
title: Add colour resources
---

# Add colour resources
<br><br>

So far you have learned how to change property values. Next, you will learn how to create more resources like the string resources you worked with earlier. Using resources enables you to use the same values in multiple places, or to define values and have the UI update automatically whenever the value is changed.

<br><br>
## Step 1: Add colour resources
<br><br>

First, you'll learn how to add new colour resources.

**Change the text colour and background of the TextView**

1. In the Project panel on the left, double-click on **res > values > colors.xml** to open the colour resource file.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/8fa53d358e4a9813.png">

```
<resources>
    <color name="colorPrimary">#6200EE</color>
    <color name="colorPrimaryDark">#3700B3</color>
    <color name="colorAccent">#03DAC5</color>
</resources>
```

The `colors.xml file` opens in the editor. So far, three colours have been defined. These are the colours you can see in your app layout (for example, purple for the app bar).

2. Go back to `fragment_first.xml` so you can see the XML code for the layout.
3. Add a new property to the `TextView` called `android:background`, and start typing to set its value to `@color`. You can add this property anywhere inside the `TextView` code.

A menu pops up offering the predefined color resources:

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/f08dbc2b6d4fc39.png">

4. Choose `@color/colorPrimaryDark`.
5. Change the property `android:textColor` and give it a value of `@android:color/white`.

The Android framework defines a range of colours, including white, so you don't have to define white yourself.

6. In the layout editor, you can see that the `TextView` now has a dark blue or purple background, and the text is displayed in white.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/c0c2141dd09c7ea7.png">

<br><br>
## Step 2: Add a new colour to use as the screen background colour
<br><br>

1. Back in `colors.xml`, create a new colour resource called `screenBackground`:

```
<color name="screenBackground">#FFEE58</color>
```

A [Colour](https://developer.android.com/reference/android/graphics/Color) can be defined as 3 hexadecimal numbers (#00-#FF, or 0-255) representing the red, blue, and green (RGB) components. The colour you just added is yellow. Notice that the colours corresponding to the code are displayed in the left margin of the editor.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/e2749d2e88ddf4a3.png">

Note that a colour can also be defined including an alpha value (#00-#FF), which represents the transparency (#00 = 0% = fully transparent, #FF = 100% = fully opaque). When included, the alpha value is the first of 4 hexadecimal numbers (ARGB).

The alpha value is a measure of transparency. For example, #88FFEE58 makes the color semi-transparent, and if you use #00FFEE58, it's fully transparent and disappears from the left-hand bar.

2. Go back to `fragment_first.xml`.
3. In the **Component Tree**, select the `ConstraintLayout`.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/98c54173559bb461.png">

4. In the **Attributes** panel, select the background property and press **Enter**. Type "c" in the field that appears.
5. In the menu of colours that appears, select `@color/screenBackground`. Press **Enter** to complete the selection.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/4ad182142b7286e6.png">

6. Click on the yellow patch to the left of the colour value in the background field.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/825da5a9b24ce5ff.png">

It shows a list of colours defined in `colors.xml`. Click the **Custom** tab to choose a custom colour with an interactive colour chooser.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/ebd2ec170406402a.png">

7. Feel free to change the value of the **screenBackground** colour, but make sure that the final colour is noticeably different from the `colorPrimary` and `colorPrimaryDark` colors.

<br><br>
## Step 3: Explore width and height properties
<br><br>

Now that you have a new screen background colour, you will use it to explore the effects of changing the width and height properties of views.

1. In `fragment_first.xml`, in the **Component Tree**, select the `ConstraintLayout`.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/3b78c455704d36b8.png">

2. In the **Attributes** panel, find and expand the **Layout** section.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/ef495439c2df9fac.png">

The **layout_width** and **layout_height** properties are both set to **match_parent**. The `ConstraintLayout` is the root view of this `Fragment`, so the "parent" layout size is effectively the size of your screen.

**Tip: All views must have layout_width and layout_height properties.**

3. Notice that the entire background of the screen uses the **screenBackground** colour.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/6cda01dc20388d55.png">

4. Select `textview_first`. Currently the layout width and height are **wrap_content**, which tells the view to be just big enough to enclose its content (plus padding). 
5. Change both the layout width and layout height to **match_constraint**, which tells the view to be as big as whatever it's constrained to.

The width and height show **0dp**, and the text moves to the upper left, while the `TextView` expands to match the `ConstraintLayout` except for the button. The button and the text view are at the same level in the view hierarchy inside the constraint layout, so they share space.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/b8740b4dc43dc9c4.png">

6. Explore what happens if the width is **match_constraint** and the height is **wrap_content** and vice versa. You can also change the width and height of the **button_first**.
7. Set both the width and height of the `TextView` and the Button back to **wrap_content**.

## Up next: Add views and constraints
