# Ex.No: 11 Develop a application to add animations to ImageView,Move,blink,fade,clockwise,zoom,slide operations are perform in android studio.


## AIM:

To develop a application to add animation to imageview,move,blink,fade,clockwise,zoom,slide operation using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Design the layout using activity_main.xml

Step 3: Add an ImageView to display the image and add buttons for each animation (Move, Blink, Fade, Clockwise, Zoom, Slide).

Step 4: Import the image into the drawable folder.

Step 5: Create animation XML files under res/anim/ for each animation type such as blink, fade, move, rotate, slide and zoom.

Step 6: Type the Java program in MainActivity file.

Step 7: Save and run the application.



## PROGRAM:
```
/*
Program to display animation operation”.
Developed by: VAZHIGA BANU S
Registeration Number : 212225040484
*/
```
## ACTIVITY_MAIN.XML:
```
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center_horizontal"
    tools:context=".MainActivity">

    <ImageView
        android:id="@+id/imageview"
        android:layout_width="218dp"
        android:layout_height="211dp"
        android:layout_marginTop="40dp"
        android:contentDescription="@string/app_name"
        android:src="@drawable/img" />

    <LinearLayout
        android:id="@+id/linear1"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="30dp"
        android:orientation="horizontal"
        android:weightSum="3">

        <!--To start the blink animation of the image-->
        <Button
            android:id="@+id/blink"
            style="@style/TextAppearance.MaterialComponents.Button"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_margin="10dp"
            android:layout_weight="1"
            android:padding="3dp"
            android:text="Blink"
            android:textColor="@color/white" />

        <!--To start the rotate animation of the image-->
        <Button
            android:id="@+id/rotate"
            style="@style/TextAppearance.MaterialComponents.Button"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_margin="10dp"
            android:layout_weight="1"
            android:padding="3dp"
            android:text="Clockwise"
            android:textColor="@color/white" />

        <!--To start the fading animation of the image-->
        <Button
            android:id="@+id/fade"
            style="@style/TextAppearance.MaterialComponents.Button"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_margin="10dp"
            android:layout_weight="1"
            android:padding="3dp"
            android:text="Fade"
            android:textColor="@color/white" />

    </LinearLayout>

    <LinearLayout
        android:id="@+id/linear2"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="30dp"
        android:orientation="horizontal"
        android:weightSum="3">

        <!--To start the move animation of the image-->
        <Button
            android:id="@+id/move"
            style="@style/TextAppearance.MaterialComponents.Button"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_margin="10dp"
            android:layout_weight="1"
            android:padding="3dp"
            android:text="Move"
            android:textColor="@color/white" />

        <!--To start the slide animation of the image-->
        <Button
            android:id="@+id/slide"
            style="@style/TextAppearance.MaterialComponents.Button"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_margin="10dp"
            android:layout_weight="1"
            android:padding="3dp"
            android:text="Slide"
            android:textColor="@color/white" />

        <!--To start the zoom animation of the image-->
        <Button
            android:id="@+id/zoom"
            style="@style/TextAppearance.MaterialComponents.Button"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_margin="10dp"
            android:layout_weight="1"
            android:padding="3dp"
            android:text="Zoom"
            android:textColor="@color/white" />

    </LinearLayout>

    <!--To stop the animation of the image-->
    <Button
        android:id="@+id/stop"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginLeft="30dp"
        android:layout_marginTop="30dp"
        android:layout_marginRight="30dp"
        android:text="STOP ANIMATION" />

</LinearLayout>

```

## BLINK.XML:

```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <alpha android:fromAlpha="0.0"
        android:toAlpha="1.0"
        android:interpolator="@android:anim/accelerate_interpolator"
        android:duration="500"
        android:repeatMode="reverse"
        android:repeatCount="infinite"/>
</set>

```
## FADE.XML:
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android"
    android:interpolator="@android:anim/accelerate_interpolator">

    <!-- duration is the time for which animation will work-->
    <alpha
        android:duration="1000"
        android:fromAlpha="0"
        android:toAlpha="1" />

    <alpha
        android:duration="1000"
        android:fromAlpha="1"
        android:startOffset="2000"
        android:toAlpha="0" />

</set>
```

## MOVE.XML:

```
<?xml version="1.0" encoding="utf-8"?>
<set
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:interpolator="@android:anim/linear_interpolator"
    android:fillAfter="true">

    <translate
        android:fromXDelta="0%p"
        android:toXDelta="75%p"
        android:duration="700" />
</set>

```
## ROTATE.XML:

```
<?xml version="1.0" encoding="utf-8"?>
<set
    xmlns:android="http://schemas.android.com/apk/res/android">
    <rotate
        android:duration="6000"
        android:fromDegrees="0"
        android:pivotX="50%"
        android:pivotY="50%"
        android:toDegrees="360" />

    <rotate
        android:duration="6000"
        android:fromDegrees="360"
        android:pivotX="50%"
        android:pivotY="50%"
        android:startOffset="5000"
        android:toDegrees="0" />

</set>
```


## SLIDE.XML:

```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android"
    android:fillAfter="true" >
    <scale
        android:duration="500"
        android:fromXScale="1.0"
        android:fromYScale="1.0"
        android:interpolator="@android:anim/linear_interpolator"
        android:toXScale="1.0"
        android:toYScale="0.0" />
</set>

```
      
## ZOOM.XML:
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android"
    android:fillAfter="true" >

    <scale
        android:interpolator="@android:anim/linear_interpolator"
        android:duration = "1000"
        android:fromXScale = "1"
        android:fromYScale = "1"
        android:pivotX = "50%"
        android:pivotY = "50%"
        android:toXScale = "2"
        android:toYScale = "2"/>
</set>
```
## MAINACTIVITY.JAVA:
```
package com.example.practice1;

import android.os.Bundle;
import android.view.View;
import android.view.animation.Animation;
import android.view.animation.AnimationUtils;
import android.widget.Button;
import android.widget.ImageView;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {


    private ImageView imageView;
    private Button blink, rotate, fade, move, slide, zoom, stop;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);


        imageView = findViewById(R.id.imageview);
        blink = findViewById(R.id.blink);
        rotate = findViewById(R.id.rotate);
        fade = findViewById(R.id.fade);
        move = findViewById(R.id.move);
        slide = findViewById(R.id.slide);
        zoom = findViewById(R.id.zoom);
        stop = findViewById(R.id.stop);


        createAnimation(blink, R.anim.blink);
        createAnimation(rotate, R.anim.rotate);
        createAnimation(fade, R.anim.fade);
        createAnimation(move, R.anim.move);
        createAnimation(slide, R.anim.slide);
        createAnimation(zoom, R.anim.zoom);


        stop.setOnClickListener(v -> imageView.clearAnimation());
    }


    private void createAnimation(View view, int animResId) {
        view.setOnClickListener(v -> {

            Animation animation = AnimationUtils.loadAnimation(MainActivity.this, animResId);

            imageView.startAnimation(animation);
        });
    }
}
```

## OUTPUT

## ACTIVITY_MAIN.XML:

<img width="1917" height="1142" alt="Screenshot 2026-11-25 104313" src="https://github.com/user-attachments/assets/9932d321-02f9-4e03-99f5-6fd85dd58779" />


## MAINACTIVITY.JAVA:

<img width="1917" height="1146" alt="Screenshot 2026-11-25 110114" src="https://github.com/user-attachments/assets/3291c864-12d6-4426-995e-817b88a79f2b" />


## BLINK:

<img width="1917" height="1145" alt="Screenshot 2026-11-25 104629" src="https://github.com/user-attachments/assets/aa7fcaf1-4643-4c68-8f8e-0fbe1fbcd8e4" />


## FADE:

<img width="1916" height="1150" alt="Screenshot 2026-11-25 104710" src="https://github.com/user-attachments/assets/f19900c7-2f25-4171-8239-0ed5f8f4f6d4" />


## ROTATE:

<img width="1917" height="1146" alt="Screenshot 2026-11-25 104834" src="https://github.com/user-attachments/assets/7cc348f2-68e7-401f-80bb-4a24ec66cea7" />


## MOVE:

<img width="1917" height="1150" alt="Screenshot 2026-11-25 104746" src="https://github.com/user-attachments/assets/f043be72-6273-4b31-8f36-6d0dadbc33e2" />


## SLIDE:

<img width="1917" height="1150" alt="Screenshot 2026-11-25 105113" src="https://github.com/user-attachments/assets/7987084e-9112-4195-9291-ea7ab8dd2a6f" />

## ZOOM:

<img width="1917" height="1136" alt="Screenshot 2026-11-25 104859" src="https://github.com/user-attachments/assets/e63376c7-583a-493d-a157-e6e414ff5369" />


## RESULT
Thus,the experiment Implementation of Animation application using android studio executed successfully.
