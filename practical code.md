✅ Practical 1 – Hello World & Android Studio Basics
🔹 Objective:
Introduction to Android & Android Studio

Create a simple “Hello World” app

Understand Android components (Activities, Services, BroadcastReceivers, etc.)

🧩 Step-by-Step:
📌 Step 1: Open Android Studio
Launch Android Studio.

Click on "New Project".

📌 Step 2: Create Project
Select Phone and Tablet > Empty Activity.

Click Next.

Name your project (e.g., HelloWorldApp).

Choose the language: Kotlin or Java (use Kotlin as it’s preferred now).

Click Finish.

📌 Step 3: Design the Layout
Open res/layout/activity_main.xml

You’ll see a default TextView that says "Hello World!" — this is your layout.

xml
Copy
Edit
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hello, World!"
        android:layout_centerInParent="true"
        android:textSize="24sp"/>
</RelativeLayout>
📌 Step 4: Edit MainActivity.kt
kotlin
Copy
Edit
package com.example.helloworldapp

import android.os.Bundle
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
    }
}
📌 Step 5: Run the App
Open AVD Manager → Create a new virtual device (Pixel 8 or similar).

Select a system image (e.g., Android 12).

Click Play to launch the emulator.

Press Run (green triangle) in Android Studio.

✅ Output:
You should see the screen displaying: "Hello, World!"

Would you like me to continue with Practical 2 in the same format?







You said:
yes


ChatGPT said:
Awesome! Let's continue with:

✅ Practical 2 – Programming Resources
🔹 Objective:
Work with Android Resources like:

Color

Theme

String

Drawable (Images)

Dimensions

🧩 Step-by-Step:
🔸 1. Color Resources
📌 Step 1: Open res/values/colors.xml
Add or update custom colors:

xml
Copy
Edit
<resources>
    <color name="purple_200">#BB86FC</color>
    <color name="my_red">#FF0000</color>
    <color name="my_blue">#0000FF</color>
</resources>
📌 Step 2: Update activity_main.xml
xml
Copy
Edit
<TextView
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="Red Text"
    android:textColor="@color/my_red"
    android:textSize="20sp"
    android:layout_marginTop="50dp"
    android:layout_gravity="center_horizontal"/>
🔸 2. Theme
To change your app’s theme:

📌 Step 1: Open res/values/themes/themes.xml
Edit parent style like this:

xml
Copy
Edit
<style name="Theme.MyApp" parent="Theme.Material3.DayNight.DarkActionBar">
You can switch between light and dark themes using DayNight.

🔸 3. String Resources
📌 Step 1: Open res/values/strings.xml
Add your own strings:

xml
Copy
Edit
<resources>
    <string name="app_name">ResourceDemo</string>
    <string name="hello_text">Hello from Strings!</string>
</resources>
📌 Step 2: Use in activity_main.xml:
xml
Copy
Edit
<TextView
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="@string/hello_text"
    android:textSize="22sp"/>
🔸 4. Drawable (Images)
📌 Step 1:
Copy an image (like logo.png)

Paste it into: res/drawable/

📌 Step 2: Use it in activity_main.xml
xml
Copy
Edit
<ImageView
    android:layout_width="200dp"
    android:layout_height="200dp"
    android:src="@drawable/logo"
    android:layout_gravity="center"/>
🔸 5. Dimension Resources
📌 Step 1: Open res/values/dimens.xml (create if not exists)
xml
Copy
Edit
<resources>
    <dimen name="text_margin">16dp</dimen>
    <dimen name="text_size">18sp</dimen>
</resources>
📌 Step 2: Use in layout:
xml
Copy
Edit
<TextView
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:layout_margin="@dimen/text_margin"
    android:textSize="@dimen/text_size"
    android:text="Dimension Resource Demo"/>
✅ Output:
You’ll see:

Colorful text views

Image from drawable folder

Text fetched from string resources

Layout spacing from dimensions

Let me know when you’re ready for Practical 3 – Activities and Fragments.







You said:
yes


ChatGPT said:
Awesome! Let’s move on to:

✅ Practical 3 – Activities and Fragments
🔹 Objective:
Understand Activity Lifecycle

Use multiple activities

Work with Fragments

🧩 Part A: Activity Lifecycle
🔸 Lifecycle Methods in MainActivity.kt
Create a new project or use an existing one, then edit your main activity to include logs for lifecycle methods:

kotlin
Copy
Edit
package com.example.lifecycleapp

import android.os.Bundle
import android.util.Log
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {

    val TAG = "Lifecycle"

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
        Log.d(TAG, "onCreate Called")
    }

    override fun onStart() {
        super.onStart()
        Log.d(TAG, "onStart Called")
    }

    override fun onResume() {
        super.onResume()
        Log.d(TAG, "onResume Called")
    }

    override fun onPause() {
        super.onPause()
        Log.d(TAG, "onPause Called")
    }

    override fun onStop() {
        super.onStop()
        Log.d(TAG, "onStop Called")
    }

    override fun onRestart() {
        super.onRestart()
        Log.d(TAG, "onRestart Called")
    }

    override fun onDestroy() {
        super.onDestroy()
        Log.d(TAG, "onDestroy Called")
    }
}
✅ Open Logcat tab in Android Studio and monitor lifecycle changes when opening, minimizing, or rotating the app.

🧩 Part B: Multiple Activities
🔸 Step 1: Design activity_main.xml
xml
Copy
Edit
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <Button
        android:id="@+id/about_us"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="About Us"
        android:layout_centerHorizontal="true"
        android:layout_marginTop="80dp"/>
</RelativeLayout>
🔸 Step 2: Create AboutUs.kt
Right-click java → New → Kotlin Class → Name: AboutUs
Select Kind: Class → Extend it from AppCompatActivity

kotlin
Copy
Edit
package com.example.lifecycleapp

import android.os.Bundle
import androidx.appcompat.app.AppCompatActivity

class AboutUs : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_about_us)
    }
}
🔸 Step 3: Create activity_about_us.xml
xml
Copy
Edit
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Welcome to About Us"
        android:textSize="24sp"
        android:layout_centerInParent="true"/>
</RelativeLayout>
🔸 Step 4: Update MainActivity.kt to launch second activity
kotlin
Copy
Edit
val aboutUsButton = findViewById<Button>(R.id.about_us)
aboutUsButton.setOnClickListener {
    val intent = Intent(this, AboutUs::class.java)
    startActivity(intent)
}
🔸 Step 5: Declare new activity in AndroidManifest.xml
xml
Copy
Edit
<activity android:name=".AboutUs" />
🧩 Part C: Fragments (Intro)
You’ll explore fragments in more depth in later practicals, but here's a preview:

🔸 Create a simple fragment:
MyFragment.kt

kotlin
Copy
Edit
class MyFragment : Fragment(R.layout.fragment_layout) {
    // You can override onViewCreated here if needed
}
fragment_layout.xml

xml
Copy
Edit
<TextView
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="This is a Fragment"
    android:layout_gravity="center"/>
Add it in an activity like this:

kotlin
Copy
Edit
supportFragmentManager.beginTransaction()
    .replace(R.id.fragment_container, MyFragment())
    .commit()
✅ Output:
Logs printed for lifecycle callbacks.

“About Us” button opens a new screen.

Preview of adding fragments.

Ready for Practical 4 – Layouts (Linear, Relative, Table, Grid, List, etc.)?







You said:
yes


ChatGPT said:
Perfect! Let’s jump into:

✅ Practical 4 – Working with Layouts
🔹 Objective:
Implement various layouts in Android:

Linear

Relative

Table

Frame

Grid View

List View

Absolute

🧩 Layout 1: Linear Layout
🔸 activity_main.xml
xml
Copy
Edit
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="16dp">

    <TextView
        android:text="This is Linear Layout"
        android:textSize="24sp"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content" />

    <Button
        android:text="Click Me"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content" />

</LinearLayout>
🧩 Layout 2: Relative Layout
🔸 activity_main.xml
xml
Copy
Edit
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <Button
        android:id="@+id/button1"
        android:text="Center Button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_centerInParent="true" />

</RelativeLayout>
🧩 Layout 3: Table Layout
🔸 activity_main.xml
xml
Copy
Edit
<TableLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:stretchColumns="*">

    <TableRow>
        <TextView android:text="Row 1 - Col 1" />
        <TextView android:text="Row 1 - Col 2" />
    </TableRow>

    <TableRow>
        <TextView android:text="Row 2 - Col 1" />
        <TextView android:text="Row 2 - Col 2" />
    </TableRow>

</TableLayout>
🧩 Layout 4: Frame Layout
🔸 activity_main.xml
xml
Copy
Edit
<FrameLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <ImageView
        android:src="@drawable/sample_image"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:scaleType="centerCrop"/>

    <TextView
        android:text="Overlay Text"
        android:textColor="#FFFFFF"
        android:textSize="24sp"
        android:layout_gravity="center" />
</FrameLayout>
🧩 Layout 5: Grid View
🔸 activity_main.xml
xml
Copy
Edit
<GridView
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@+id/gridView"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:numColumns="3"
    android:verticalSpacing="10dp"
    android:horizontalSpacing="10dp"
    android:stretchMode="columnWidth"
    android:gravity="center"/>
🔸 MainActivity.kt
kotlin
Copy
Edit
val gridView = findViewById<GridView>(R.id.gridView)
val items = arrayOf("One", "Two", "Three", "Four", "Five", "Six")
val adapter = ArrayAdapter(this, android.R.layout.simple_list_item_1, items)
gridView.adapter = adapter
🧩 Layout 6: List View
🔸 activity_main.xml
xml
Copy
Edit
<ListView
    android:id="@+id/listView"
    android:layout_width="match_parent"
    android:layout_height="wrap_content" />
🔸 MainActivity.kt
kotlin
Copy
Edit
val listView = findViewById<ListView>(R.id.listView)
val data = listOf("Apple", "Banana", "Mango", "Orange")
val adapter = ArrayAdapter(this, android.R.layout.simple_list_item_1, data)
listView.adapter = adapter
🧩 Layout 7: Absolute Layout (deprecated – use with caution)
🔸 activity_main.xml
xml
Copy
Edit
<AbsoluteLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <TextView
        android:id="@+id/textView1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_x="50px"
        android:layout_y="100px"
        android:text="Welcome to Absolute Layout"/>

    <Button
        android:id="@+id/button1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_x="200px"
        android:layout_y="200px"
        android:text="Click me"/>

</AbsoluteLayout>
⚠️ Note: AbsoluteLayout is not recommended in modern Android development. Use ConstraintLayout instead for similar flexibility.

✅ Output:
Try running each layout type in a separate activity or fragment for easy comparison and practice.

Ready for Practical 5 – UI Elements: AppBar, Fragments, Login/Register Screens?







You said:
yes


ChatGPT said:
Great! Let’s get into:

✅ Practical 5 – UI Elements: AppBar, Fragments, Login & Register Screens
🔹 Objective:
Implement common UI components like AppBar

Create Login and Register screens

Understand Fragments and their integration

🧩 Part A: AppBar with Navigation
🔸 activity_main.xml
xml
Copy
Edit
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <androidx.appcompat.widget.Toolbar
        android:id="@+id/toolbar"
        android:layout_width="match_parent"
        android:layout_height="?attr/actionBarSize"
        android:background="?attr/colorPrimary"
        android:titleTextColor="@android:color/white"
        app:title="Main Screen" />

    <!-- Rest of the UI here -->

</LinearLayout>
🔸 MainActivity.kt
kotlin
Copy
Edit
import androidx.appcompat.widget.Toolbar

override fun onCreate(savedInstanceState: Bundle?) {
    super.onCreate(savedInstanceState)
    setContentView(R.layout.activity_main)

    val toolbar = findViewById<Toolbar>(R.id.toolbar)
    setSupportActionBar(toolbar)
}
🧩 Part B: Login & Register Screens
🔸 Step 1: Create new Activities
Right-click java > your.package.name → New → Activity → Empty Activity

Name: LoginActivity

Repeat for: RegisterActivity

🔸 activity_login.xml
xml
Copy
Edit
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:padding="16dp"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <EditText
        android:id="@+id/email"
        android:hint="Email"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"/>

    <EditText
        android:id="@+id/password"
        android:hint="Password"
        android:inputType="textPassword"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"/>

    <Button
        android:id="@+id/loginBtn"
        android:text="Login"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"/>
</LinearLayout>
🔸 activity_register.xml
Similar to login but with extra field:

xml
Copy
Edit
<EditText
    android:id="@+id/confirmPassword"
    android:hint="Confirm Password"
    android:inputType="textPassword"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"/>
🔸 Add Intent in MainActivity.kt to open Login/Register
kotlin
Copy
Edit
startActivity(Intent(this, LoginActivity::class.java))
You can call this on a button click or in the onCreate() to directly test.

🧩 Part C: Fragment Setup (Simple Example)
🔸 Step 1: Create Fragment Layout fragment_sample.xml
xml
Copy
Edit
<FrameLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <TextView
        android:text="This is a fragment"
        android:layout_gravity="center"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"/>
</FrameLayout>
🔸 Step 2: Create Kotlin class SampleFragment.kt
kotlin
Copy
Edit
class SampleFragment : Fragment(R.layout.fragment_sample)
🔸 Step 3: Add a FrameLayout to activity_main.xml
xml
Copy
Edit
<FrameLayout
    android:id="@+id/fragment_container"
    android:layout_width="match_parent"
    android:layout_height="match_parent"/>
🔸 Step 4: Load Fragment in MainActivity.kt
kotlin
Copy
Edit
supportFragmentManager.beginTransaction()
    .replace(R.id.fragment_container, SampleFragment())
    .commit()
✅ Output:
AppBar appears with title

Login/Register screens work with fields

Fragment loads dynamically in layout

Let me know when you're ready for Practical 6 – Menus, Dialogs & Dialog Fragments 🚀







You said:
yes


ChatGPT said:
Awesome! Let’s now cover:

✅ Practical 6 – Menus, Dialogs & Dialog Fragments
🔹 Objective:
Add Options Menu using XML

Show a Dialog

Use a DialogFragment

🧩 Part A: Options Menu
📌 Step 1: Create menu.xml
Right-click on res → New > Android Resource Directory

Resource type: menu

Name: menu

Right-click on menu folder → New > Menu Resource File

File name: main_menu.xml

xml
Copy
Edit
<menu xmlns:android="http://schemas.android.com/apk/res/android">
    <item
        android:id="@+id/item_settings"
        android:title="Settings"/>
    <item
        android:id="@+id/item_about"
        android:title="About"/>
    <item
        android:id="@+id/item_logout"
        android:title="Logout"/>
</menu>
📌 Step 2: Update MainActivity.kt
kotlin
Copy
Edit
override fun onCreateOptionsMenu(menu: Menu?): Boolean {
    menuInflater.inflate(R.menu.main_menu, menu)
    return true
}

override fun onOptionsItemSelected(item: MenuItem): Boolean {
    return when (item.itemId) {
        R.id.item_settings -> {
            Toast.makeText(this, "Settings Clicked", Toast.LENGTH_SHORT).show()
            true
        }
        R.id.item_about -> {
            Toast.makeText(this, "About Clicked", Toast.LENGTH_SHORT).show()
            true
        }
        R.id.item_logout -> {
            Toast.makeText(this, "Logged Out", Toast.LENGTH_SHORT).show()
            true
        }
        else -> super.onOptionsItemSelected(item)
    }
}
🧩 Part B: Simple Dialog
📌 Step 1: Update activity_main.xml
xml
Copy
Edit
<Button
    android:id="@+id/dialogBtn"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="Show Dialog" />
📌 Step 2: Add this to MainActivity.kt
kotlin
Copy
Edit
val dialogBtn = findViewById<Button>(R.id.dialogBtn)
dialogBtn.setOnClickListener {
    val builder = AlertDialog.Builder(this)
    builder.setTitle("My Dialog")
        .setMessage("Do you want to proceed?")
        .setPositiveButton("Yes") { _, _ ->
            Toast.makeText(this, "You clicked Yes", Toast.LENGTH_SHORT).show()
        }
        .setNegativeButton("No") { dialog, _ ->
            dialog.dismiss()
        }
        .show()
}
🧩 Part C: Dialog Fragment
📌 Step 1: Create Layout dialog_fragment.xml
xml
Copy
Edit
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:padding="24dp"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="wrap_content">

    <TextView
        android:text="Hello from Fragment Dialog"
        android:textSize="18sp"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content" />
</LinearLayout>
📌 Step 2: Create MyDialogFragment.kt
kotlin
Copy
Edit
class MyDialogFragment : DialogFragment() {
    override fun onCreateDialog(savedInstanceState: Bundle?): Dialog {
        val builder = AlertDialog.Builder(requireActivity())
        val inflater = requireActivity().layoutInflater
        val view = inflater.inflate(R.layout.dialog_fragment, null)
        builder.setView(view)
            .setPositiveButton("OK") { _, _ ->
                Toast.makeText(requireContext(), "OK clicked", Toast.LENGTH_SHORT).show()
            }
        return builder.create()
    }
}
📌 Step 3: Show Fragment from MainActivity.kt
kotlin
Copy
Edit
val showFragmentBtn = findViewById<Button>(R.id.showFragmentBtn)
showFragmentBtn.setOnClickListener {
    val dialog = MyDialogFragment()
    dialog.show(supportFragmentManager, "MyDialog")
}
Add a button in layout with ID showFragmentBtn for this.

✅ Output:
Options menu available in top-right.

Dialog appears on button click.

DialogFragment launches as a popup with OK button.

Ready for Practical 7 – Intents, Events, Listeners & Adapters?







You said:
yes


ChatGPT said:
Great! Let's dive into:

✅ Practical 7 – Intents, Events, Listeners & Adapters
🔹 Objective:
Work with Intents (explicit)

Handle Events and Listeners

Use Adapters with views like ListView

🧩 Part A: Intents – Open a Second Activity
🔸 Step 1: Create Second Activity
Right-click on java > your.package.name → New > Activity > Empty Activity

Name it: SecondActivity

🔸 Step 2: Design activity_main.xml
xml
Copy
Edit
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:padding="16dp"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <EditText
        android:id="@+id/nameEditText"
        android:hint="Enter Name"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"/>

    <Button
        android:id="@+id/sendBtn"
        android:text="Send to Next Activity"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"/>
</LinearLayout>
🔸 Step 3: Update MainActivity.kt
kotlin
Copy
Edit
val nameEditText = findViewById<EditText>(R.id.nameEditText)
val sendBtn = findViewById<Button>(R.id.sendBtn)

sendBtn.setOnClickListener {
    val name = nameEditText.text.toString()
    val intent = Intent(this, SecondActivity::class.java)
    intent.putExtra("username", name)
    startActivity(intent)
}
🔸 Step 4: Design activity_second.xml
xml
Copy
Edit
<TextView
    android:id="@+id/nameTextView"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:textSize="24sp"
    android:layout_gravity="center"
    android:padding="20dp"/>
🔸 Step 5: Update SecondActivity.kt
kotlin
Copy
Edit
val nameTextView = findViewById<TextView>(R.id.nameTextView)
val name = intent.getStringExtra("username")
nameTextView.text = "Hello, $name!"
🧩 Part B: Event Listeners Example
Already done above with sendBtn.setOnClickListener { }

You can also use setOnLongClickListener, setOnTouchListener, etc.

🧩 Part C: Adapter with ListView
🔸 Add to activity_main.xml (below the existing UI):
xml
Copy
Edit
<ListView
    android:id="@+id/listView"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"/>
🔸 Add to MainActivity.kt:
kotlin
Copy
Edit
val fruits = listOf("Apple", "Banana", "Mango", "Orange")
val listView = findViewById<ListView>(R.id.listView)
val adapter = ArrayAdapter(this, android.R.layout.simple_list_item_1, fruits)
listView.adapter = adapter

listView.setOnItemClickListener { _, _, position, _ ->
    Toast.makeText(this, "You clicked: ${fruits[position]}", Toast.LENGTH_SHORT).show()
}
✅ Output:
Enter name → click button → name displayed on SecondActivity.

Toast on ListView item click.

Uses Intent, Event Listener & Adapter.

Let me know when you're ready for Practical 8 – Services, Notification, BroadcastReceiver 📱🔔📡







You said:
yes


ChatGPT said:
Nice! Let's get into one of the most exciting topics:

✅ Practical 8 – Services, Notifications, and Broadcast Receivers
🔹 Objective:
Create and use a Service

Send a Notification

Implement a BroadcastReceiver

🧩 Part A: Service
🔸 Step 1: Update activity_main.xml
xml
Copy
Edit
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:padding="16dp"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <Button
        android:id="@+id/startServiceBtn"
        android:text="Start Service"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <Button
        android:id="@+id/stopServiceBtn"
        android:text="Stop Service"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />
</LinearLayout>
🔸 Step 2: Create MyService.kt
Right-click → New → Kotlin Class → MyService

kotlin
Copy
Edit
class MyService : Service() {
    override fun onBind(intent: Intent?): IBinder? = null

    override fun onStartCommand(intent: Intent?, flags: Int, startId: Int): Int {
        Toast.makeText(this, "Service Started", Toast.LENGTH_SHORT).show()
        return START_STICKY
    }

    override fun onDestroy() {
        Toast.makeText(this, "Service Stopped", Toast.LENGTH_SHORT).show()
        super.onDestroy()
    }
}
🔸 Step 3: Register Service in AndroidManifest.xml
xml
Copy
Edit
<service android:name=".MyService"/>
🔸 Step 4: Start/Stop in MainActivity.kt
kotlin
Copy
Edit
val startBtn = findViewById<Button>(R.id.startServiceBtn)
val stopBtn = findViewById<Button>(R.id.stopServiceBtn)

startBtn.setOnClickListener {
    startService(Intent(this, MyService::class.java))
}

stopBtn.setOnClickListener {
    stopService(Intent(this, MyService::class.java))
}
🧩 Part B: Notification
🔸 Step 1: Add Button to Layout
xml
Copy
Edit
<Button
    android:id="@+id/notifyBtn"
    android:text="Show Notification"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"/>
🔸 Step 2: Add code to MainActivity.kt
kotlin
Copy
Edit
val notifyBtn = findViewById<Button>(R.id.notifyBtn)

notifyBtn.setOnClickListener {
    val notificationManager = getSystemService(Context.NOTIFICATION_SERVICE) as NotificationManager
    val channelId = "default_channel"

    if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.O) {
        val channel = NotificationChannel(channelId, "Default Channel", NotificationManager.IMPORTANCE_DEFAULT)
        notificationManager.createNotificationChannel(channel)
    }

    val builder = NotificationCompat.Builder(this, channelId)
        .setSmallIcon(R.drawable.ic_launcher_foreground)
        .setContentTitle("Hello!")
        .setContentText("This is a notification")
        .setPriority(NotificationCompat.PRIORITY_DEFAULT)

    notificationManager.notify(1, builder.build())
}
🧩 Part C: BroadcastReceiver
🔸 Step 1: Create MyReceiver.kt
kotlin
Copy
Edit
class MyReceiver : BroadcastReceiver() {
    override fun onReceive(context: Context, intent: Intent) {
        Toast.makeText(context, "Broadcast Received!", Toast.LENGTH_SHORT).show()
    }
}
🔸 Step 2: Register in AndroidManifest.xml
xml
Copy
Edit
<receiver android:name=".MyReceiver">
    <intent-filter>
        <action android:name="com.example.MY_CUSTOM_ACTION"/>
    </intent-filter>
</receiver>
🔸 Step 3: Add Button to activity_main.xml
xml
Copy
Edit
<Button
    android:id="@+id/sendBroadcastBtn"
    android:text="Send Broadcast"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"/>
🔸 Step 4: Add to MainActivity.kt
kotlin
Copy
Edit
val sendBroadcastBtn = findViewById<Button>(R.id.sendBroadcastBtn)

sendBroadcastBtn.setOnClickListener {
    val intent = Intent("com.example.MY_CUSTOM_ACTION")
    sendBroadcast(intent)
}
✅ Output:
Start & stop a background service with toasts.

Show notification using system UI.

Broadcast received triggers toast via BroadcastReceiver.

Let me know when you're ready for Practical 9 – SQLite Database + JSON Network 💾🌐







You said:
yes


ChatGPT said:
Perfect! Let’s move to:

✅ Practical 9 – SQLite Database & Network with JSON
🧩 Part A: SQLite Database
🔹 Objective:
Store, retrieve, delete data using SQLite

Use custom helper and model classes

📦 Step-by-Step Implementation
🔸 Step 1: activity_main.xml
xml
Copy
Edit
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:padding="16dp"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <EditText
        android:id="@+id/etName"
        android:hint="Enter Name"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"/>

    <EditText
        android:id="@+id/etEmail"
        android:hint="Enter Email"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"/>

    <Button
        android:id="@+id/btnAdd"
        android:text="ADD"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"/>

    <Button
        android:id="@+id/btnShow"
        android:text="SHOW ALL"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"/>

    <Button
        android:id="@+id/btnDelete"
        android:text="DELETE"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"/>
</LinearLayout>
🔸 Step 2: Create Model – UserModel.kt
kotlin
Copy
Edit
data class UserModel(val id: Int, val name: String, val email: String)
🔸 Step 3: Create Contract – DBContract.kt
kotlin
Copy
Edit
object DBContract {
    object UserEntry : BaseColumns {
        const val TABLE_NAME = "users"
        const val COLUMN_NAME = "name"
        const val COLUMN_EMAIL = "email"
    }

    const val SQL_CREATE_ENTRIES =
        "CREATE TABLE ${UserEntry.TABLE_NAME} (" +
                "${BaseColumns._ID} INTEGER PRIMARY KEY," +
                "${UserEntry.COLUMN_NAME} TEXT," +
                "${UserEntry.COLUMN_EMAIL} TEXT)"

    const val SQL_DELETE_ENTRIES = "DROP TABLE IF EXISTS ${UserEntry.TABLE_NAME}"
}
🔸 Step 4: Create DBHelper – UserDBHelper.kt
kotlin
Copy
Edit
class UserDBHelper(context: Context) :
    SQLiteOpenHelper(context, "UserDB.db", null, 1) {

    override fun onCreate(db: SQLiteDatabase) {
        db.execSQL(DBContract.SQL_CREATE_ENTRIES)
    }

    override fun onUpgrade(db: SQLiteDatabase, oldVersion: Int, newVersion: Int) {
        db.execSQL(DBContract.SQL_DELETE_ENTRIES)
        onCreate(db)
    }

    fun insertUser(name: String, email: String) {
        val db = writableDatabase
        val values = ContentValues().apply {
            put(DBContract.UserEntry.COLUMN_NAME, name)
            put(DBContract.UserEntry.COLUMN_EMAIL, email)
        }
        db.insert(DBContract.UserEntry.TABLE_NAME, null, values)
    }

    fun getAllUsers(): List<UserModel> {
        val db = readableDatabase
        val projection = arrayOf(BaseColumns._ID, DBContract.UserEntry.COLUMN_NAME, DBContract.UserEntry.COLUMN_EMAIL)
        val cursor = db.query(DBContract.UserEntry.TABLE_NAME, projection, null, null, null, null, null)

        val users = mutableListOf<UserModel>()
        with(cursor) {
            while (moveToNext()) {
                val id = getInt(getColumnIndexOrThrow(BaseColumns._ID))
                val name = getString(getColumnIndexOrThrow(DBContract.UserEntry.COLUMN_NAME))
                val email = getString(getColumnIndexOrThrow(DBContract.UserEntry.COLUMN_EMAIL))
                users.add(UserModel(id, name, email))
            }
        }
        cursor.close()
        return users
    }

    fun deleteAllUsers() {
        val db = writableDatabase
        db.delete(DBContract.UserEntry.TABLE_NAME, null, null)
    }
}
🔸 Step 5: Update MainActivity.kt
kotlin
Copy
Edit
val dbHelper = UserDBHelper(this)

val etName = findViewById<EditText>(R.id.etName)
val etEmail = findViewById<EditText>(R.id.etEmail)

findViewById<Button>(R.id.btnAdd).setOnClickListener {
    dbHelper.insertUser(etName.text.toString(), etEmail.text.toString())
    Toast.makeText(this, "User Added", Toast.LENGTH_SHORT).show()
}

findViewById<Button>(R.id.btnShow).setOnClickListener {
    val users = dbHelper.getAllUsers()
    val result = users.joinToString("\n") { "ID: ${it.id}, Name: ${it.name}, Email: ${it.email}" }
    Toast.makeText(this, result.ifEmpty { "No users found" }, Toast.LENGTH_LONG).show()
}

findViewById<Button>(R.id.btnDelete).setOnClickListener {
    dbHelper.deleteAllUsers()
    Toast.makeText(this, "All users deleted", Toast.LENGTH_SHORT).show()
}
🔸 Step 6: Enable ViewBinding (Optional)
In build.gradle (Module: app):

groovy
Copy
Edit
android {
    ...
    buildFeatures {
        viewBinding true
    }
}
✅ Output:
Add, show, delete user data in SQLite.

Info displayed via Toasts or you can add ListView/RecyclerView.

🧩 Part B: Networking with JSON (Theory Preview)
Since JSON calls require internet permission and libraries like Retrofit or Volley, this part is usually introduced with basics.

🔸 Example (with pseudo-code):
kotlin
Copy
Edit
val json = """
    {
        "name": "Amit",
        "email": "amit@example.com"
    }
""".trimIndent()

val jsonObject = JSONObject(json)
val name = jsonObject.getString("name")
val email = jsonObject.getString("email")

Toast.makeText(this, "Name: $name, Email: $email", Toast.LENGTH_SHORT).show()
✅ This demonstrates basic parsing JSON response in Android.

Let me know when you're ready for the final one: Practical 10 – Media API, Phone Calls & Permissions 🎵📞🔐







You said:
yes


ChatGPT said:
Awesome! Here's the final practical:

✅ Practical 10 – Media API, Telephone API & Permissions
🔹 Objective:
Play audio using Media API

Make calls using Telephone API

Handle runtime permissions in Android

🧩 Part A: Media API (Play Audio)
🔸 Step 1: Add Audio to res/raw/
Right-click res → New → Android Resource Directory

Select raw as resource type.

Paste your audio file (e.g., song.mp3) into the raw folder.

🔸 Step 2: Update activity_main.xml
xml
Copy
Edit
<Button
    android:id="@+id/playBtn"
    android:text="Play Audio"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"/>
🔸 Step 3: Add to MainActivity.kt
kotlin
Copy
Edit
var mediaPlayer: MediaPlayer? = null

val playBtn = findViewById<Button>(R.id.playBtn)
playBtn.setOnClickListener {
    if (mediaPlayer == null) {
        mediaPlayer = MediaPlayer.create(this, R.raw.song)
        mediaPlayer?.start()
    } else {
        mediaPlayer?.start()
    }
}
✅ Add stop functionality if needed using mediaPlayer?.stop().

🧩 Part B: Telephone API (Make a Call)
🔸 Step 1: Add Button in activity_main.xml
xml
Copy
Edit
<Button
    android:id="@+id/callBtn"
    android:text="Call Number"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"/>
🔸 Step 2: Add Permission in AndroidManifest.xml
xml
Copy
Edit
<uses-permission android:name="android.permission.CALL_PHONE"/>
🔸 Step 3: Ask Runtime Permission + Make Call in MainActivity.kt
kotlin
Copy
Edit
val callBtn = findViewById<Button>(R.id.callBtn)

callBtn.setOnClickListener {
    val intent = Intent(Intent.ACTION_CALL)
    intent.data = Uri.parse("tel:1234567890")

    if (ContextCompat.checkSelfPermission(this, Manifest.permission.CALL_PHONE)
        == PackageManager.PERMISSION_GRANTED) {
        startActivity(intent)
    } else {
        ActivityCompat.requestPermissions(this,
            arrayOf(Manifest.permission.CALL_PHONE), 1)
    }
}
🔸 Step 4: Handle Permission Result
kotlin
Copy
Edit
override fun onRequestPermissionsResult(
    requestCode: Int, permissions: Array<out String>, grantResults: IntArray) {
    if (requestCode == 1 && grantResults.isNotEmpty() && grantResults[0] == PackageManager.PERMISSION_GRANTED) {
        Toast.makeText(this, "Permission granted. Please tap again to call.", Toast.LENGTH_SHORT).show()
    } else {
        Toast.makeText(this, "Permission denied.", Toast.LENGTH_SHORT).show()
    }
}
🧩 Part C: General Permissions Handling
This covers common permission flow for:

Storage

Location

Contacts

Phone

The pattern is similar:

Add permission in manifest

Request at runtime using ActivityCompat.requestPermissions()

Handle result in onRequestPermissionsResult()

✅ Output:
Plays audio from raw resource.

Initiates a phone call (with permission).

Runtime permissions handled gracefully.
