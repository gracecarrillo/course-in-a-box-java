---
title: Update the appearance of the buttons and the TextView
---

# Update the appearance of the buttons and the TextView
<br><br>

Your app's layout is now basically complete, but its appearance can be improved with a few small changes.

<br><br>
## Step 1: Add new color resources
<br><br>

1. In `colors.xml`, change the value of `screenBackground` to `#2196F3`, which is a blue shade in the [Material Design palette](https://material.io/guidelines/style/color.html#color-color-palette).
2. Add a new color named `buttonBackground`. Use the value `#BBDEFB`, which is a lighter shade in the blue palette.

```
<color name="buttonBackground">#BBDEFB</color>
```
<br><br>
## Step 2: Add a background color for the buttons
<br><br>

1. In the layout, add a background color to each of the buttons. (You can either edit the XML in fragment_first.xml or use the Attributes panel, whichever you prefer.)

```
android:background="@color/buttonBackground"
```
<br><br>
## Step 3: Change the margins of the left and right buttons
<br><br>

1. Give the **Toast** button a left (start) margin of 24dp and give the **Random** button a right (end) margin of 24dp. (Using start and end instead of left and right makes these margins work for all language directions.)
2. One way to do this is to use the **Constraint Widget** in the **Attributes** panel. The number on each side is the margin on that side of the selected view. Type `24` in the field and press **Enter**.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/81c294a2cf04b801.png">

<br><br>
## Step 4: Update the appearance of the TextView
<br><br>

1. Remove the background color of the `TextView`, either by clearing the value in the **Attributes** panel or by removing the `android:background` attribute from the XML code.

When you remove the background, the view background becomes transparent.

2. Increase the text size of the `TextView` to 72sp.

```
android:textSize="72sp"
```

3. Change the font-family of the `TextView` to `sans-serif` (if it's not already).
4. Add an `app:layout_constraintVertical_bias` property to the `TextView`, to bias the position of the view upwards a little so that it is more evenly spaced vertically in the screen. Feel free to adjust the value of this constraint as you like. (Check in the design view to see how the layout looks.)

```
app:layout_constraintVertical_bias="0.3"
```

5. You can also set the vertical bias using the **Constraint Widget**. Click and drag the number **50** that appears on the left side, and slide it upwards until it says **30**.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/7c73e04dc2f35d00.png">

**Tip: Using the bias attribute instead of margins or padding results in a more pleasing layout on different screen sizes and orientations.
- If a view is constrained to other views on both its top and bottom edges, use vertical bias to tweak its vertical position.**
**- If a view is constrained on both its left and right edges, use horizontal bias to tweak its horizontal position.**

6. Make sure the **layout_width** is **wrap_content**, and the horizontal bias is 50 (`app:layout_constraintHorizontal_bias="0.5" in XML`).

<br><br>
## Step 5: Run your app
<br><br>

If you implemented all the updates, your app will look like the following figure. If you used different colors and fonts, then your app will look a bit different.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/214cfb8299ed8d36.png" width="50%" height="50%">

