# Ex.No:8 To create a gallery control using android studio to display images or photos.


## AIM:

To create a gallery control using android studio to display images or photos.

## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:



## PROGRAM:
```
/*
Program to print the text “GalleryControl”.
Developed by: VELAN D
Registeration Number : 212222040176
*/
```

## In activity_main.xml :
~~~
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <Gallery
        android:id="@+id/gallery"
        android:layout_width="fill_parent"
        android:layout_height="wrap_content"
        android:layout_alignParentTop="true"
        android:layout_centerHorizontal="true"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.889" />

    <ImageView
        android:id="@+id/imageView"
        android:layout_width="fill_parent"
        android:layout_height="fill_parent"
        android:layout_below="@+id/gallery"
        android:layout_centerHorizontal="true"
        android:scaleType="fitCenter"
        app:layout_constraintBottom_toBottomOf="@+id/gallery"
        app:layout_constraintStart_toEndOf="parent"
        app:layout_constraintTop_toTopOf="@+id/gallery"
        app:layout_constraintVertical_bias="0.849" />

    <TextView
        android:id="@+id/textView"
        android:layout_width="174dp"
        android:layout_height="99dp"
        android:text="Gallery Control"
        android:textAlignment="center"
        android:textSize="28sp"
        android:textStyle="bold|italic"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.498"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.045" />

</androidx.constraintlayout.widget.ConstraintLayout>
~~~

## MainActivity.java :
~~~
package com.example.gallerycontrol;

import android.app.Activity;
import android.content.Context;
import android.os.Bundle;
import android.view.View;
import android.view.ViewGroup;
import android.widget.AdapterView;
import android.widget.BaseAdapter;
import android.widget.Gallery;
import android.widget.ImageView;

public class MainActivity extends Activity {

    private Integer[] mImageIds = {
            R.drawable.download,
            R.drawable.australiaflag,
            R.drawable.portugalflag,

    };

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        Gallery gallery = (Gallery) findViewById(R.id.gallery);
        gallery.setAdapter(new ImageAdapter(this));

        gallery.setOnItemClickListener(new AdapterView.OnItemClickListener() {
            @Override
            public void onItemClick(AdapterView<?> parent, View view, int position, long id) {
                ImageView imageView = (ImageView) findViewById(R.id.imageView);
                imageView.setImageResource(mImageIds[position]);
            }
        });
    }

    public class ImageAdapter extends BaseAdapter {
        private Context mContext;

        public ImageAdapter(Context c) {
            mContext = c;
        }

        public int getCount() {
            return mImageIds.length;
        }

        public Object getItem(int position) {
            return null;
        }

        public long getItemId(int position) {
            return 0;
        }

        public View getView(int position, View convertView, ViewGroup parent) {
            ImageView imageView = new ImageView(mContext);
            imageView.setImageResource(mImageIds[position]);
            imageView.setLayoutParams(new Gallery.LayoutParams(150, 100));
            imageView.setScaleType(ImageView.ScaleType.FIT_XY);
            return imageView;
        }
    }
}
~~~

## OUTPUT:

![Screenshot 2024-04-29 093420](https://github.com/VELANDHANANJAYAN/gallerycontrol/assets/119405038/c7043ee9-55ba-490d-837e-4a38d0a05163)

![Screenshot 2024-04-29 093431](https://github.com/VELANDHANANJAYAN/gallerycontrol/assets/119405038/ceb32f11-3de4-47cf-a5a3-1a559cf1dd99)




## RESULT
Thus a Simple Android Application to create a gallery control using android studio to display images or photos is developed and executed successfully.

