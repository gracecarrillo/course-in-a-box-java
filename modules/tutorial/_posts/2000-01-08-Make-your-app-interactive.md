---
title: Make your app interactive
---

# Make your app interactive
<br><br>

You have added buttons to your app's main screen, but currently the buttons do nothing. In this task, you will make your buttons respond when the user presses them.

First you will make the **Toast** button show a pop-up message called a toast. Next you will make the **Count** button update the number that is displayed in the `TextView`.

<br><br>
## Step 1: Enable auto imports
<br><br>

To make your life easier, you can enable auto-imports so that Android Studio automatically imports any classes that are needed by the Kotlin code.

1. In Android Studio, open the settings editor by going to **File > Other Settings > Preferences for New Projects**.
2. Select Auto Import. In the Java and Kotlin sections, make sure **Add Unambiguous Imports on the fly** is checked.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/5507aa63b0db10d5.png">

3. Close the settings editor.

<br><br>
## Step 2: Show a toast
<br><br>

In this step, you will attach a Kotlin method to the **Toast** button to show a toast when the user presses the button. A toast is a short message that appears briefly at the bottom of the screen.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/b3d6daf5bb6784d9.png" width="50%" height="50%">

1. Open `FirstFragment.kt`. (**app > java > com.example.android.myfirstapp > FirstFragment**).

This class has only two methods, `onCreateView()` and `onViewCreated()`. These methods execute when the fragment starts.

As mentioned earlier, the [id](https://developer.android.com/reference/android/view/View#ids) for a view helps you identify that view distinctly from other views. Using the `findViewByID()` method, your code can find the `random_button` using its id, `R.id.random_button`.

2. Take a look at `onViewCreated()`. It sets up a click listener for the `random_button`, which was originally created as the Next button.

```
view.findViewById<Button>(R.id.random_button).setOnClickListener {
        findNavController().navigate(R.id.action_FirstFragment_to_SecondFragment)
}
```

Here is what this code does:

- Use the `findViewById()` method with the id of the desired view as an argument, then set a click listener on that view.
- In the body of the click listener, use an action, which in this case is for navigating to another fragment, and navigate there. (You will learn about that later.)

3. Just below that click listener, add code to set up a click listener for the `toast_button` that creates and displays a toast. Here is the code:

```
// find the toast_button by its ID and set a click listener
view.findViewById<Button>(R.id.toast_button).setOnClickListener {
   // create a Toast with some text, to appear for a short time
   val myToast = Toast.makeText(context, "Hello Toast!", Toast.LENGTH_SHORT)
   // show the Toast
   myToast.show()
}
```

4. Run the app and press the **Toast** button. Do you see the toasty message at the bottom of the screen?

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/b3d6daf5bb6784d9.png" width="50%" height="50%">

5. If you want, extract the message string into a resource as you did for the button labels.

You have learned that to make a view interactive you need to set up a click listener for the view that says what to do when the view (button) is clicked on. The click listener can either:

- Implement a small amount of code directly.
- Call a method that defines the desired click behavior in the activity.

<br><br>
## Step 3: Make the Count button update the number on the screen
<br><br>

The method that shows the toast is very simple; it does not interact with any other views in the layout. In the next step, you add behavior to your layout to find and update other views.

Update the **Count** button so that when it is pressed, the number on the screen increases by 1.

1. In the `fragment_first.xml` layout file, notice the `id` for the `TextView`:

```
<TextView
   android:id="@+id/textview_first"
```

2. In `FirstFragment.kt`, add a click listener for the count_button below the other click listeners in `onViewCreated()`. Because it has a little more work to do, have it call a new method, `countMe()`.

```
view.findViewById<Button>(R.id.count_button).setOnClickListener {
   countMe(view)
}
```

3. In the `FirstFragment` class, add the method `countMe()`, which takes a single View argument. This method is invoked when the Count button is clicked and the click listener called.

```
private fun countMe(view: View) {

}
```

4. Use the `findViewById()` method to get the `TextView` that shows the count. This method returns a `View`, so you must cast the result to a `TextView`. Specify the id of the view to get, `textview_first`.

```
   ...
   // Get the text view
   val showCountTextView = view.findViewById<TextView>(R.id.textview_first)
```

5. Get the value of the `showCountTextView`.

```
   ...
   // Get the value of the text view.
   val countString = showCountTextView.text.toString()
```

6. Convert the value to a number, and increment it.

```
   ...
   // Convert value to a number and increment it
   var count = countString.toInt()
   count++
```

7. Display the new value in the `TextView` by programmatically setting the text property of the `TextView`.

```
   ...
   // Display the new value in the text view.
   showCountTextView.text = count.toString()
```

Here is the whole method:

```
private fun countMe(view: View) {
   // Get the text view
   val showCountTextView = view.findViewById<TextView>(R.id.textview_first)

   // Get the value of the text view.
   val countString = showCountTextView.text.toString()

   // Convert value to a number and increment it
   var count = countString.toInt()
   count++

   // Display the new value in the text view.
   showCountTextView.text = count.toString()
}
```

8. Run your app. Press the Count button and watch the count update.

<img src="https://codelabs.developers.google.com/codelabs/build-your-first-android-app-kotlin/img/f2b19b9209cad4f4.png" width="50%" height="50%">

## Up next: Implement the second fragment
