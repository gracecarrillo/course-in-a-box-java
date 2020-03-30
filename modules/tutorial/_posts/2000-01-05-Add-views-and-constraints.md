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

1. In `fragment_first.xml`, look at the constraint properties for the TextView.
app:layout_constraintBottom_toTopOf="@id/button_first"
app:layout_constraintEnd_toEndOf="parent"
app:layout_constraintStart_toStartOf="parent"
app:layout_constraintTop_toTopOf="parent"
These properties define the position of the TextView. Read them carefully.

You can constrain the top, bottom, left, and right of a view to the top, bottom, left, and right of other views.

Select textview_first in the Component Tree and look at the Constraint Widget in the Attributes panel.



The square represents the selected view. Each of the grey dots represents a constraint, to the top, bottom, left, and right; for this example, from the TextView to its parent, the ConstraintLayout, or to the Next button for the bottom constraint.
Notice that the blueprint and design views also show the constraints when a particular view is selected. Some of the constraints are jagged lines, but the one to the Next button is a squiggle, because it's a little different. You'll learn more about that in a bit.


Step 2: Add buttons and constrain their positions
To learn how to use constraints to connect the positions of views to each other, you will add buttons to the layout. Your first goal is to add a button and some constraints, and change the constraints on the Next button.

Notice the Palette at the top left of the layout editor. Move the sides if you need to, so that you can see many of the items in the palette.


Click on some of the categories, and scroll the listed items if needed to get an idea of what's available.
Select Button, which is near the top, and drag and drop it onto the design view, placing it underneath the TextView near the other button.


Notice that a Button has been added to the Component Tree under ConstraintLayout.

Step 3: Add a constraint to the new button
You will now constrain the top of the button to the bottom of the TextView.

Move the cursor over the circle at the top of the Button.


Click and drag the circle at the top of the Button onto the circle at the bottom of the TextView.



The Button moves up to sit just below the TextView because the top of the button is now constrained to the bottom of the TextView.


Take a look at the Constraint Widget in the Layout pane of the Attributes panel. It shows some constraints for the Button, including Top -> BottomOf textView.
Take a look at the XML code for the button. It now includes the attribute that constrains the top of the button to the bottom of the TextView.
app:layout_constraintTop_toBottomOf="@+id/textview_first"
You may see a warning, "Not Horizontally Constrained". To fix this, add a constraint from the left side of the button to the left side of the screen.
Also add a constraint to constrain the bottom of the button to the bottom of the screen.
Before adding another button, relabel this button so things are a little clearer about which button is which.

Click on the button you just added in the design layout.
Look at the Attributes panel on the right, and notice the id field.
Change the id from button to toast_button.
Step 4: Adjust the Next button
You will adjust the button labeled Next, which Android Studio created for you when you created the project. The constraint between it and the TextView looks a little different, a wavy line instead of a jagged one, with no arrow. This indicates a chain, where the constraints link two or more objects to each other, instead of just one to another. For now, you'll delete the chained constraints and replace them with regular constraints.

To delete a constraint:
In the design view or blueprint view, hold the Ctrl key (Command on a Mac) and move the cursor over the circle for the constraint until the circle highlights, then click the circle.

Or click on one of the constrained views, then right-click on the constraint and select Delete from the menu.
Or in the Attributes panel, move the cursor over the circle for the constraint until it shows an x, then click it.


If you delete a constraint and want it back, either undo the action, or create a new constraint.

Step 5: Delete the chain constraints
Click on the Next button, and then delete the constraint from the top of the button to the TextView.
Click on the TextView, and then delete the constraint from the bottom of the text to the Next button.
Step 6: Add new constraints
Constrain the right side of the Next button to the right of the screen if it isn't already.
Delete the constraint on the left side of the Next button.
Now constrain the top and bottom of the Next button so that the top of the button is constrained to the bottom of the TextView and the bottom is constrained to the bottom of the screen. The right side of the button is constrained to the right side of the screen.
Also constrain the TextView to the bottom of the screen.

It may seem like the views are jumping around a lot, but that's normal as you add and remove constraints.
Your layout should now look something like this.


Step 7: Extract string resources
In the fragment_first.xml layout file, find the text property for the toast_button button.
<Button
   android:id="@+id/toast_button"
   android:layout_width="wrap_content"
   android:layout_height="wrap_content"
   android:text="Button"
Notice that the text "Button" is directly in the layout field, instead of referencing a string resource as the TextView does. This will make it harder to translate your app to other languages.
To fix this, click the highlighted code. A light bulb appears on the left.


Click the lightbulb. In the menu that pops up, select Extract string resource.


In the dialog box that appears, change the resource name to toast_button_text and the resource value to Toast and click OK.


Notice that the value of the android:text property has changed to @string/toast_button_text.
<Button
   android:id="@+id/button"
   android:layout_width="wrap_content"
   android:layout_height="wrap_content"
   android:text="@string/toast_button_text"
Go to the res > values > strings.xml file. Notice that a new string resource has been added, named toast_button_text.
<resources>
   ... 
   <string name="toast_button_text">Toast</string>
</resources>
Run the app to make sure it displays as you expect it to.

You now know how to create new string resources by extracting them from existing field values. (You can also add new resources to the strings.xml file manually.) And you know how to change the id of a view.

Note: The id for a view helps you identify that view distinctly from other views. You'll use this later to find particular views using the findViewById() method in your Kotlin code.

Step 8: Update the Next button
The Next button already has its text in a string resource, but you'll make some changes to the button to match its new role, which will be to generate and display a random number.

As you did for the Toast button, change the id of the Next button from button_first to random_button in the Attributes panel.
If you get a dialog box asking to update all usages of the button, click Yes. This will fix any other references to the button in the project code.

In strings.xml, right-click on the next string resource.
Select Refactor > Rename... and change the name to random_button_text.
Click Refactor to rename your string and close the dialog.
Change the value of the string from Next to Random.
If you want, move random_button_text to below toast_button_text.
Step 9: Add a third button
Your final layout will have three buttons, vertically constrained the same, and evenly spaced from each other.



In fragment_first.xml, add another button to the layout, and drop it somewhere between the Toast button and the Random button, below the TextView.
Add vertical constraints the same as the other two buttons. Constrain the top of the third button to the bottom of TextView; constrain the bottom of the third button to the bottom of the screen.
Add horizontal constraints from the third button to the other buttons. Constrain the left side of the third button to the right side of the Toast button; constrain the right side of the third button to the left side of the Random button.
Your layout should look something like this:



Examine the XML code for fragment_first.xml. Do any of the buttons have the attribute app:layout_constraintVertical_bias? It's OK if you do not see that constraint.

The "bias" constraints allows you to tweak the position of a view to be more on one side than the other when both sides are constrained in opposite directions. For example, if both the top and bottom sides of a view are constrained to the top and bottom of the screen, you can use a vertical bias to place the view more towards the top than the bottom.
Here is the XML code for the finished layout. Your layout might have different margins and perhaps some different vertical or horizontal bias constraints.The exact values of the attributes for the appearance of the TextView might be different for your app.

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
Step 10: Get your UI ready for the next task
The next task is to make the buttons do something when they are pressed. First, you need to get the UI ready.

Change the text of the TextView to show 0 (the number zero).
Change the text alignment to center.


Change the id of the last button you added, button2, to count_button in the Attributes panel in the design editor.
In the XML, extract the string resource to count_button_text and set the value to Count.

The buttons should now have the following text and ids:

Button

text

id

Left button

Toast

@+id/toast_button

Middle button

Count

@+id/count_button

Right button

Random

@+id/random_button

Run the app.
Step 11: Fix errors if necessary
If you edited the XML for the layout directly, you might see some errors.



The errors occur because the buttons have changed their id and now these constraints are referencing non-existent views.

If you have these errors, fix them by updating the id of the buttons in the constraints that are underlined in red.

app:layout_constraintEnd_toStartOf="@+id/random_button"
app:layout_constraintStart_toEndOf="@+id/toast_button"
