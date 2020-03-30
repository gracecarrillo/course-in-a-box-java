---
title: Add views and constraints
---

# Add views and constraints
<br><br>

In this task, you will add two more buttons to your user interface, and update the existing button, as shown below.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/94e4cf7f4bb5264b.png">

<br><br>
## Step 1: View constraint properties
<br><br>

1. In `fragment_first.xml`, look at the constraint properties for the `TextView`.

```
app:layout_constraintBottom_toTopOf="@id/button_first"
app:layout_constraintEnd_toEndOf="parent"
app:layout_constraintStart_toStartOf="parent"
app:layout_constraintTop_toTopOf="parent"
```

These properties define the position of the `TextView`. Read them carefully.

You can constrain the top, bottom, left, and right of a view to the top, bottom, left, and right of other views.

2. Select `textview_first` in the **Component Tree** and look at the **Constraint Widget** in the **Attributes** panel.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/938d3a1c319e1f.png">

The square represents the selected view. Each of the grey dots represents a constraint, to the top, bottom, left, and right; for this example, from the `TextView` to its parent, the `ConstraintLayout`, or to the **Next** button for the bottom constraint.

3. Notice that the blueprint and design views also show the constraints when a particular view is selected. Some of the constraints are jagged lines, but the one to the Next button is a squiggle, because it's a little different. You'll learn more about that in a bit.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/7d73d3d74c8ebbb9.png">

<br><br>
## Step 2: Add buttons and constrain their positions
<br><br>

To learn how to use constraints to connect the positions of views to each other, you will add buttons to the layout. Your first goal is to add a button and some constraints, and change the constraints on the **Next** button.

1. Notice the Palette at the top left of the layout editor. Move the sides if you need to, so that you can see many of the items in the palette.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/47603a2d993c378b.png">

2. Click on some of the categories, and scroll the listed items if needed to get an idea of what's available.
3. Select **Button**, which is near the top, and drag and drop it onto the design view, placing it underneath the `TextView` near the other button.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/91ddff47af3cde61.png">

**Notice that a `Button` has been added to the Component Tree under `ConstraintLayout`.**

<br><br>
## Step 3: Add a constraint to the new button
<br><br>

You will now constrain the top of the button to the bottom of the `TextView`.

1. Move the cursor over the circle at the top of the `Button`.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/9e7bcb556cd2b58c.png">

2. Click and drag the circle at the top of the `Button` onto the circle at the bottom of the `TextView`.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/9e7bcb556cd2b58c.png">

The` Button` moves up to sit just below the `TextView` because the top of the button is now constrained to the bottom of the `TextView`.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/7aa4fd347b3ebde9.png">

4. Take a look at the **Constraint Widget** in the **Layout** panel of the **Attributes** panel. It shows some constraints for the `Button`, including **Top -> BottomOf textView**.

5. Take a look at the XML code for the button. It now includes the attribute that constrains the top of the button to the bottom of the `TextView`.

```
app:layout_constraintTop_toBottomOf="@+id/textview_first"
```

6. You may see a warning, **"Not Horizontally Constrained"**. To fix this, add a constraint from the left side of the button to the left side of the screen.
7. Also add a constraint to constrain the bottom of the button to the bottom of the screen.

Before adding another button, relabel this button so things are a little clearer about which button is which.

1. Click on the button you just added in the design layout.
2. Look at the **Attributes** panel on the right, and notice the **id** field.
3. Change the id from `button` to `toast_button`.

<br><br>
## Step 4: Adjust the Next button
<br><br>

You will adjust the button labeled **Next**, which Android Studio created for you when you created the project. The constraint between it and the `TextView` looks a little different, a wavy line instead of a jagged one, with no arrow. This indicates a [chain](https://developer.android.com/reference/android/support/constraint/ConstraintLayout#Chains), where the constraints link two or more objects to each other, instead of just one to another. For now, you'll delete the chained constraints and replace them with regular constraints.

**To delete a constraint:**

- In the design view or blueprint view, hold the `Ctrl` key (`Command` on a Mac) and move the cursor over the circle for the constraint until the circle highlights, then click the circle. 
<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/1f8c250ad15873d5.png">
- Or click on one of the constrained views, then right-click on the constraint and select Delete from the menu.
- Or in the Attributes panel, move the cursor over the circle for the constraint until it shows an x, then click it.
<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/7f4931356c145bab.png">

If you delete a constraint and want it back, either undo the action, or create a new constraint.

<br><br>
## Step 5: Delete the chain constraints
<br><br>

1. Click on the **Next** button, and then delete the constraint from the top of the button to the `TextView`.
2. Click on the `TextView`, and then delete the constraint from the bottom of the text to the **Next** button.

<br><br>
## Step 6: Add new constraints
<br><br>

1. Constrain the right side of the **Next** button to the right of the screen if it isn't already.
2. Delete the constraint on the left side of the **Next** button.
3. Now constrain the top and bottom of the **Next** button so that the top of the button is constrained to the bottom of the `TextView` and the bottom is constrained to the bottom of the screen. The right side of the button is constrained to the right side of the screen.
4. Also constrain the `TextView` to the bottom of the screen.

It may seem like the views are jumping around a lot, but that's normal as you add and remove constraints.

Your layout should now look something like this.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/7fb69c02100a87f6.png">

<br><br>
## Step 7: Extract string resources
<br><br>

1. In the `fragment_first.xml` layout file, find the text property for the `toast_button` button.

```
<Button
   android:id="@+id/toast_button"
   android:layout_width="wrap_content"
   android:layout_height="wrap_content"
   android:text="Button"
```

2. Notice that the text `"Button"` is directly in the layout field, instead of referencing a string resource as the `TextView` does. 3. This will make it harder to translate your app to other languages.
3. To fix this, click the highlighted code. A light bulb appears on the left.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/47544075e3e5ecdb.png">

4. Click the lightbulb. In the menu that pops up, select **Extract string resource**.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/ca47cfeb06a1602.png">

5. In the dialog box that appears, change the resource name to `toast_button_text` and the resource value to `Toast` and click **OK**.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/8fa866598929c1b4.png">

6. Notice that the value of the android:text property has changed to `@string/toast_button_text`.

```
<Button
   android:id="@+id/button"
   android:layout_width="wrap_content"
   android:layout_height="wrap_content"
   android:text="@string/toast_button_text"
```

7. Go to the **res > values > strings.xml** file. Notice that a new string resource has been added, named `toast_button_text`.

```
<resources>
   ... 
   <string name="toast_button_text">Toast</string>
</resources>
```

8. Run the app to make sure it displays as you expect it to.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/73c7729f2d8329df.png">

You now know how to create new string resources by extracting them from existing field values. (You can also add new resources to the `strings.xml` file manually.) And you know how to change the id of a view.

**Note: The [id](https://developer.android.com/reference/android/view/View#ids) for a view helps you identify that view distinctly from other views. You'll use this later to find particular views using the `findViewById()` method in your Kotlin code.**

<br><br>
## Step 8: Update the Next button
<br><br>

The **Next** button already has its text in a string resource, but you'll make some changes to the button to match its new role, which will be to generate and display a random number.

1. As you did for the **Toast** button, change the id of the **Next** button from `button_first` to `random_button` in the **Attributes** panel.
2. If you get a dialog box asking to update all usages of the button, click **Yes**. This will fix any other references to the button in the project code.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/434e77fabe53b6a3.png">

3. In `strings.xml`, right-click on the `next` string resource.
4. Select **Refactor > Rename**... and change the name to `random_button_text`.
5. Click **Refactor** to rename your string and close the dialog.
6. Change the value of the string from `Next` to `Random`.
7. If you want, move `random_button_text` to below `toast_button_text`.

<br><br>
## Step 9: Add a third button
<br><br>

Your final layout will have three buttons, vertically constrained the same, and evenly spaced from each other.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/7e6529faadd88569.png">

1. In `fragment_first.xml`, add another button to the layout, and drop it somewhere between the **Toast** button and the **Random** button, below the `TextView`.
2. Add vertical constraints the same as the other two buttons. Constrain the top of the third button to the bottom of `TextView`; constrain the bottom of the third button to the bottom of the screen.
3. Add horizontal constraints from the third button to the other buttons. Constrain the left side of the third button to the right side of the **Toast** button; constrain the right side of the third button to the left side of the **Random** button.

Your layout should look something like this:

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/7588895a67295422.png">

5. Examine the XML code for `fragment_first.xml`. Do any of the buttons have the attribute `app:layout_constraintVertical_bias?` It's OK if you do not see that constraint.

The "bias" constraints allows you to tweak the position of a view to be more on one side than the other when both sides are [constrained in opposite directions](https://developer.android.com/reference/android/support/constraint/ConstraintLayout.html#CenteringPositioning). For example, if both the top and bottom sides of a view are constrained to the top and bottom of the screen, you can use a vertical bias to place the view more towards the top than the bottom.

Here is the XML code for the finished layout. Your layout might have different margins and perhaps some different vertical or horizontal bias constraints.The exact values of the attributes for the appearance of the `TextView` might be different for your app.

```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout <?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
   xmlns:app="http://schemas.android.com/apk/res-auto"
   xmlns:tools="http://schemas.android.com/tools"
   android:layout_width="match_parent"
   android:layout_height="match_parent"
   android:background="@color/screenBackground"
   tools:context=".FirstFragment">

   <TextView
       android:id="@+id/textview_first"
       android:layout_width="wrap_content"
       android:layout_height="wrap_content"
       android:background="@color/colorPrimaryDark"
       android:fontFamily="sans-serif-condensed"
       android:text="@string/hello_first_fragment"
       android:textColor="@android:color/white"
       android:textSize="30sp"
       android:textStyle="bold"
       app:layout_constraintBottom_toBottomOf="parent"
       app:layout_constraintEnd_toEndOf="parent"
       app:layout_constraintStart_toStartOf="parent"
       app:layout_constraintTop_toTopOf="parent" />

   <Button
       android:id="@+id/random_button"
       android:layout_width="wrap_content"
       android:layout_height="wrap_content"
       android:text="@string/random_button_text"
       app:layout_constraintBottom_toBottomOf="parent"
       app:layout_constraintEnd_toEndOf="parent"
       app:layout_constraintTop_toBottomOf="@+id/textview_first" />

   <Button
       android:id="@+id/toast_button"
       android:layout_width="wrap_content"
       android:layout_height="wrap_content"
       android:text="@string/toast_button_text"
       app:layout_constraintBottom_toBottomOf="parent"
       app:layout_constraintStart_toStartOf="parent"
       app:layout_constraintTop_toBottomOf="@+id/textview_first" />

   <Button
       android:id="@+id/button2"
       android:layout_width="wrap_content"
       android:layout_height="wrap_content"
       android:text="Button"
       app:layout_constraintBottom_toBottomOf="parent"
       app:layout_constraintEnd_toStartOf="@+id/random_button"
       app:layout_constraintStart_toEndOf="@+id/toast_button"
       app:layout_constraintTop_toBottomOf="@+id/textview_first" />
</androidx.constraintlayout.widget.ConstraintLayout>
```
<br><br>
## Step 10: Get your UI ready for the next task
<br><br>
   
The next task is to make the buttons do something when they are pressed. First, you need to get the UI ready.

1. Change the text of the `TextView` to show **0** (the number zero).
2. Change the text alignment to center.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/7084faa39a820830.png">

3. Change the `id` of the last button you added, `button2`, to `count_button` in the **Attributes** panel in the design editor.
4. In the XML, extract the string resource to `count_button_text` and set the value to `Count`.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/bbe0bcab6903ea27.png">

The buttons should now have the following text and ids:

|  Button | text  |  id |
|:-:|---|---|
| Left button | Toast | @+id/toast_button |
| Middle button | Count  | @+id/count_button |
| Right button  | Random | @+id/random_button |

<br><br>
6. Run the app!

<br><br>
## Step 11: Fix errors if necessary
<br><br>

If you edited the XML for the layout directly, you might see some errors.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/c01516073934ed58.png">

The errors occur because the buttons have changed their id and now these constraints are referencing non-existent views.

If you have these errors, fix them by updating the `id` of the buttons in the constraints that are underlined in red.

```
app:layout_constraintEnd_toStartOf="@+id/random_button"
app:layout_constraintStart_toEndOf="@+id/toast_button"
```

## Up next: Update the appearance of the buttons and the TextView


