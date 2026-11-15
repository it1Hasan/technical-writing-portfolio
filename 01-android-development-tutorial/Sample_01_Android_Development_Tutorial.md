# Technical Documentation Portfolio

## Sample 01: Android Development -- Building a LinearLayout with a Button Using XML and Kotlin

**Document Type:** Step-by-Step Technical Tutorial\
**Technology:** Android Studio, XML, Kotlin\
**Target Audience:** Beginner Android Developers\
**Content Creator:** Hasan Mukhtar\
**Source:** ITech Aspirant -- Android Development Tutorial Series

------------------------------------------------------------------------

## 1. Introduction

This tutorial demonstrates how to create a basic Android user interface
using XML and implement button-click functionality using Kotlin.

The tutorial is designed for beginners and follows a practical,
step-by-step approach. By the end, learners will understand how Android
layout resources connect with Kotlin activity code and how to handle
basic user interactions.

### Learning Objectives

By completing this tutorial, learners will be able to:

-   Create an Android layout resource directory.
-   Create and configure an XML layout file.
-   Understand the LinearLayout container.
-   Add and customize a Button component.
-   Connect XML views with Kotlin activity code.
-   Implement an OnClickListener.
-   Display a Toast message in response to a button click.
-   Run and test the application on an Android device.

## 2. Creating the Layout Resource File

Before designing the user interface, an XML layout resource must be
created.

**Procedure:**

1.  Open Android Studio and navigate to the `res` directory.
2.  Right-click on `res` and select **New → Android Resource
    Directory**.
3.  Select `layout` as the resource type.
4.  Click OK to create the directory.
5.  Right-click on the newly created `layout` directory.
6.  Select **New → XML → Layout XML File**.
7.  Name the file `activity_main`.
8.  Keep LinearLayout as the root element and click Finish.

### Understanding LinearLayout

LinearLayout is a ViewGroup that arranges its child elements in a single
direction.

Its `orientation` property determines how child elements are positioned:

-   `vertical`: Elements are arranged from top to bottom.
-   `horizontal`: Elements are arranged from left to right.

Android Studio also provides a Split view that allows developers to
inspect the XML source code alongside the visual layout preview.

## 3. Designing the User Interface

Open `activity_main.xml` and configure the root LinearLayout.

The main layout properties include:

  Property          Purpose
  ----------------- -----------------------------------------------------
  `layout_width`    Defines the width of the layout
  `layout_height`   Defines the height of the layout
  `orientation`     Controls the arrangement of child elements
  `gravity`         Controls the alignment of content within the layout

For this example, configure the layout to occupy the available screen
width and height and use a vertical orientation.

### Adding a Button

Add a Button element inside the LinearLayout.

Configure the following properties:

-   Set its width and height using `wrap_content`.
-   Define its displayed text using the `android:text` attribute.
-   Assign a unique ID using `android:id`.

The ID allows the Button to be referenced from the Kotlin activity code.

**Important:** Use Android Studio's Extract String Resource
functionality to move hardcoded interface text into the appropriate
string resource file.

## 4. Finalizing the XML Layout

After adding the Button:

1.  Ensure the Button XML element is properly closed.
2.  Configure the layout's gravity to center the content.
3.  Adjust the text size.
4.  Apply bold text styling where appropriate.
5.  Review the layout in Android Studio's visual preview.

At this stage, the user interface is ready. The next step is connecting
it to the Kotlin activity.

## 5. Connecting the XML Layout to Kotlin

Open `MainActivity.kt`.

The activity must load the XML layout using `setContentView()`.

The layout resource name must match the XML filename.

Next, retrieve the Button using its assigned ID with `findViewById()`.

This establishes the connection between the visual interface and the
application logic.

### Key Concepts

-   `setContentView()`: Loads the activity's user interface.
-   `findViewById()`: Retrieves a view using its resource ID.
-   `MainActivity.kt`: Contains the activity's Kotlin implementation.

## 6. Implementing Button Click Functionality

To respond to user interaction, implement an `OnClickListener` for the
Button.

When the user clicks the Button, the application displays a Toast
notification containing the message:

**Button Clicked!**

A Toast is a small notification that appears temporarily on the screen.

### Handling Import Errors

If Android Studio reports an unresolved reference for `Toast`, check
whether the required Android widget import is present.

The required import is:

`import android.widget.Toast`

This makes the Toast class accessible within the activity.

## 7. Running and Testing the Application

Once the XML layout and Kotlin logic are complete:

1.  Connect an Android mobile device to your computer.
2.  Ensure USB debugging is enabled.
3.  Select the connected device in Android Studio.
4.  Run the application.
5.  Wait for the application to install and launch.
6.  Tap the Button to verify that the Toast notification appears.

### Expected Result

The application displays a screen containing a centered Button. When the
user taps it, a temporary Toast notification appears with the message
"Button Clicked!"

## 8. Tutorial Summary

In this tutorial, we covered the fundamental process of creating an
interactive Android interface using XML and Kotlin.

The key concepts included:

-   Creating a LinearLayout resource.
-   Configuring layout orientation and alignment.
-   Adding and identifying a Button.
-   Connecting XML components to Kotlin.
-   Implementing button-click events.
-   Displaying Toast notifications.

### Next Learning Module

The next tutorial extends this example by introducing navigation between
Android screens.

Learners will connect the existing Button to a second activity and
develop a basic calculator that accepts two numbers and performs
addition.

------------------------------------------------------------------------

**Portfolio Note**

This documentation sample is adapted from an independently scripted and
produced Android development tutorial published on the ITech Aspirant
YouTube channel. It demonstrates the ability to transform practical
software development workflows into structured technical documentation
for beginner-level users.
