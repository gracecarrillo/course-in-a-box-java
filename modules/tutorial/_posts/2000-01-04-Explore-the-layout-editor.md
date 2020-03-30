---
title: Explore the layout editor
---

# Explore the layout editor

Generally, each screen in your Android app is associated with one or more [fragments](https://developer.android.com/guide/components/fragments). The single screen displaying "Hello first fragment" is created by one fragment, called `FirstFragment`. This was generated for you when you created your new project. Each visible fragment in an Android app has a layout that defines the user interface for the fragment. Android Studio has a layout editor where you can create and define layouts.

Layouts are defined in [XML](https://en.wikipedia.org/wiki/XML). The layout editor lets you define and modify your layout either by coding XML or by using the interactive visual editor.

Every element in a layout is a view. In this task, you'll explore some of the panels in the layout editor, and you'll learn how to change properties of views.

## Step 1: Open the layout editor

1. Find and open the layout folder **app > res > layout** on the left side in the Project panel.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/bb7b4fe5af80859d.png" width="50%" height="50%">

2. Double-click `fragment_first.xml`.

**Troubleshooting: If you don't see the `file fragment_first.xml`, confirm you are running Android Studio 3.6 or later, which is required for this codelab.**

The panels to the right of the Project view comprise the **Layout Editor**. They may be arranged differently in your version of Android Studio, but the function is the same.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/356e0f1c3bbc6e40.png" width="50%" height="50%">

On the left is a **Palette** of views you can add to your app.

Below that is a **Component Tree** showing the views currently in this file, and how they are arranged in relation to each other.

In the center is the **Design editor**, which shows a visual representation of what the contents of the file will look like when compiled into an Android app. You can view the visual representation, the XML code, or both.

3. In the upper right corner of the Design editor, above **Attributes**, find the three icons that look like this:

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/c60f285cb7fbc306.png" width="50%" height="50%">

These represent **Code** (code only), **Split** (code + design), and **Design** (design only) views.

4. Try selecting the different modes. Depending on your screen size and work style, you may prefer switching between Code and Design, or staying in Split view. If your Component Tree disappears, hide and show the Palette.

Split view:

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/32d3075ed7f5c02c.png">

5. At the lower right of the Design editor you see **+** and **-** buttons for zooming in and out. Use these buttons to adjust the size of what you see, or click the zoom-to-fit button so that both panels fit on your screen. 

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/a7d0a08766682f9.png">

The Design layout on the left shows how your app appears on the device. The Blueprint layout, shown on the right, is a schematic view of the layout.

6. Practice using the layout menu in the top left of the design toolbar to display the design view, the blueprint view, and both views side by side.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/6572c0c05460eafd.png">

Depending on the size of your screen and your preference, you may wish to only show the Design view or the Blueprint view, instead of both.

7. Use the orientation icon to change the orientation of the layout. This allows you to test how your layout will fit portrait and landscape modes.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/c40138d924cedb8f.png" width="50%" height="50%">

8. Use the device menu to view the layout on different devices. (This is extremely useful for testing!)

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/46754977c9c3d6c9.png" width="50%" height="50%">

On the right is the Attributes panel. You'll learn about that later.

## Step 2: Explore and resize the Component Tree

1. In `fragment_first.xml`, look at the **Component Tree**. If it's not showing, switch the mode to Design instead of Split or Code.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/855789e5c4867c8f.png">

This panel shows the view hierarchy in your layout, that is, how the views are arranged in relation to each other.

2. If necessary, resize the Component Tree so you can read at least part of the strings.

3. Click the Hide icon at the top right of the Component Tree. The Component Tree closes.

4. Bring back the Component Tree by clicking the vertical label Component Tree on the left.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/35c14a27fd2ce30a.png">

## Step 3: Explore view hierarchies

1. In the **Component Tree**, notice that the root of the view hierarchy is a `ConstraintLayout` view.

Every layout must have a root view that contains all the other views. The root view is always a view group, which is a view that contains other views. A `ConstraintLayout` is one example of a view group.

2. Notice that the `ConstraintLayout` contains a `TextView`, called `textview_first` and a `Button`, called `button_first`.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/506cf77387f00782.png">

3. If the code isn't showing, switch to Code or Split view using the icons in the upper right corner.

4. In the XML code, notice that the root element is `<androidx.constraintlayout.widget.ConstraintLayout>`. The root element contains a `<TextView>` element and a `<Button>` element.

```
<androidx.constraintlayout.widget.ConstraintLayout
  ... >

   <TextView
      ...  />

   <Button
      ...  />

</androidx.constraintlayout.widget.ConstraintLayout>
```

## Step 4: Change property values

1. In the code editor, examine the properties in the `TextView` element.

```
<TextView
   android:layout_width="wrap_content"
   android:layout_height="wrap_content"
   android:text="Hello first fragment"
   ... />
```
2. Click on the string in the text property, and you'll notice it refers to a string resource, `hello_first_fragment`.

```
android:text="@string/hello_first_fragment"
```
3. Right-click on the property and click **Go To > Declaration or Usages**

`values/strings.xml` opens with the string highlighted.

```
<string name="hello_first_fragment">Hello first fragment</string>
```
4. Change the value of the `string` property to `Hello World!`.
5. Switch back to `fragment_first.xml`.
6. Select `textview_first` in the Component Tree.
<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/19cfd9f54f58b379.png">

7. Look at the **Attributes** panel on the right, and open the **Declared Attributes** section if needed.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/549f087103c9acbe.png">

**Troubleshooting this step: If the Attributes panel is not visible, click the vertical Attributes label at the top right.**

9. In the text field of the `TextView` in **Attributes**, notice it still refers to the string resource `string/hello_first_fragment`. Having the strings in a resource file has several advantages. You can change the value of string without having to change any other code. This simplifies translating your app to other languages, because your translators don't have to know anything about the app code.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/8bb6bf0caffa82a4.png">

*Tip: To find a property in the list of all the properties, click on the magnifying glass icon to the right of Attributes, and begin typing the name of the property. Android Studio will show just the properties that contain that string.*

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/1e116f4ea013be17.png">

10. Run the app to see the change you made in **strings.xml.** Your app now shows "Hello World!".

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/d2103406630c3527.png" width="50%" height="50%">

## Step 5: Change text display properties

1. With `textview_first` still selected in the **Component Tree**, in the layout editor, in the list of attributes, under **Common Attributes**, expand the `textAppearance` field. (You may need to scroll down to find it.)

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/37c72a9385dab52d.png">

2. Change some of the text appearance properties. For example, change the font family, increase the text size, and select bold style. (You might need to scroll the panel to see all the fields.)
3. Change the text colour. Click in the `textColor` field, and enter `g`.

A menu pops up with possible completion values containing the letter `g`. This list includes predefined colours.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/39597ff5cf9661da.png">

4. Select `@android:color/darker_gray` and press **Enter**.

Below is an example of the textAppearance attributes after making some changes.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/8751426a21281f94.png">

5. Look at the XML for the `TextView`. You see that the new properties have been added.
```
<TextView
   android:id="@+id/textview_first"
   android:layout_width="wrap_content"
   android:layout_height="wrap_content"
   android:fontFamily="sans-serif-condensed"
   android:text="@string/hello_first_fragment"
   android:textColor="@android:color/darker_gray"
   android:textSize="30sp"
   android:textStyle="bold"
```
6. Run your app again and see the changes applied to your Hello World! string

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/c715d9230068d0f8.png" width="50%" height="50%" >

## Step 6: Display all attributes

1. In the **Attributes** panel, scroll down until you find **All Attributes**.

**Tip: If you don't see any attributes in the Attributes panel, make sure `textview_first` is still selected in the Component Tree.**

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/6e28336e8d85fa14.png" width="50%" height="50%">

2. Scroll through the list to get an idea of the attributes you could set for a `TextView`.

### Up next: Add colour resources

