## [See Output](https://github.com/JoeJebitto/Android-Kotlin/blob/main/Calculator/README.md)

## This Project Is Made Using

![Android](Image/Image3.png)
![Kotlin](Image/Image4.png)

# Build.gradle File

```groovy
    plugins {
    id 'com.android.application'
    id 'kotlin-android'
    id 'kotlin-android-extensions'
}

android {
    compileSdkVersion 30
    buildToolsVersion "30.0.3"

    defaultConfig {
        applicationId "com.joeljebitto.calculatorapp"
        minSdkVersion 16
        targetSdkVersion 30
        versionCode 1
        versionName "1.0"

        testInstrumentationRunner "androidx.test.runner.AndroidJUnitRunner"
    }

    buildTypes {
        release {
            minifyEnabled false
            proguardFiles getDefaultProguardFile('proguard-android-optimize.txt'), 'proguard-rules.pro'
        }
    }
    compileOptions {
        sourceCompatibility JavaVersion.VERSION_1_8
        targetCompatibility JavaVersion.VERSION_1_8
    }
    kotlinOptions {
        jvmTarget = '1.8'
    }
}

dependencies {
    implementation "org.jetbrains.kotlin:kotlin-stdlib:$kotlin_version"
    implementation 'androidx.core:core-ktx:1.5.0'
    implementation 'androidx.appcompat:appcompat:1.3.0'
    implementation 'com.google.android.material:material:1.3.0'
    implementation 'androidx.constraintlayout:constraintlayout:2.0.4'
    androidTestImplementation 'androidx.test.ext:junit:1.1.2'
    androidTestImplementation 'androidx.test.espresso:espresso-core:3.3.0'
}
```

# Strings.xml [File](app/src/main/res/values/strings.xml)

```xml

<resources>
    <string name="app_name">Calculator App</string>
    <string name="_7">7</string>
    <string name="_9">9</string>
    <string name="_8">8</string>
    <string name="_Div">/</string>
    <string name="_4">4</string>
    <string name="_5">5</string>
    <string name="_Multiply">*</string>
    <string name="_1">1</string>
    <string name="_3">3</string>
    <string name="_2">2</string>
    <string name="_Sub">-</string>
    <string name="_Decimal">.</string>
    <string name="_0">0</string>
    <string name="_Add">+</string>
    <string name="_Equal">=</string>
    <string name="_Clear">CLEAR</string>
    <string name="_6">6</string>
</resources>
```

# colors.xml [File](app/src/main/res/values/colors.xml)

```xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <color name="purple_200">#FFBB86FC</color>
    <color name="purple_500">#FF6200EE</color>
    <color name="purple_700">#FF3700B3</color>
    <color name="teal_200">#FF03DAC5</color>
    <color name="teal_700">#FF018786</color>
    <color name="black">#FF000000</color>
    <color name="white">#FFFFFFFF</color>
</resources>
```

# activity_main.xml [File](app/src/main/res/layout/activity_main.xml)

```xml
<LinearLayout
        xmlns:android="http://schemas.android.com/apk/res/android"
        xmlns:tools="http://schemas.android.com/tools"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:orientation="vertical"
        tools:context=".MainActivity"
        android:background="#2EABDD">

    <TextView
            android:id="@+id/tvInput"
            android:layout_width="match_parent"
            android:layout_height="250dp"
            android:background="#49B1FF"
            android:maxLength="12"
            android:textSize="48sp"/>

    <!--  Row 1  -->
    <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_marginTop="2dp"
            android:layout_weight="1"
            android:orientation="horizontal"
            tools:ignore="NestedWeights,RtlHardcoded,UsingOnClickInXml,ButtonStyle">
        <Button
                android:id="@+id/btn7"
                android:layout_width="0dp"
                android:layout_height="match_parent"
                android:layout_weight="1"
                android:text="@string/_7"
                android:layout_marginRight="4sp"
                android:onClick="onDigit"/>
        <Button
                android:id="@+id/btn8"
                android:layout_width="0dp"
                android:layout_height="match_parent"
                android:layout_weight="1"
                android:layout_marginRight="4sp"
                android:text="@string/_8"
                android:onClick="onDigit"/>
        <Button
                android:id="@+id/btn9"
                android:layout_width="0dp"
                android:layout_height="match_parent"
                android:layout_weight="1"
                android:text="@string/_9"
                android:layout_marginRight="4sp"
                android:onClick="onDigit"/>
        <Button
                android:id="@+id/btnDiv"
                android:layout_width="0dp"
                android:layout_height="match_parent"
                android:layout_weight="1"
                android:text="@string/_Div"
                android:onClick="onOperator"/>
    </LinearLayout>

    <!--  Row 2  -->
    <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_marginTop="2dp"
            android:layout_weight="1"
            android:orientation="horizontal"
            tools:ignore="NestedWeights,RtlHardcoded,UsingOnClickInXml,ButtonStyle">
        <Button
                android:id="@+id/btn4"
                android:layout_width="0dp"
                android:layout_height="match_parent"
                android:layout_weight="1"
                android:text="@string/_4"
                android:layout_marginRight="4sp"
                android:onClick="onDigit"/>
        <Button
                android:id="@+id/btn5"
                android:layout_width="0dp"
                android:layout_height="match_parent"
                android:layout_weight="1"
                android:layout_marginRight="4sp"
                android:text="@string/_5"
                android:onClick="onDigit"/>
        <Button
                android:id="@+id/btn6"
                android:layout_width="0dp"
                android:layout_height="match_parent"
                android:layout_weight="1"
                android:text="@string/_6"
                android:layout_marginRight="4sp"
                android:onClick="onDigit"/>
        <Button
                android:id="@+id/btnMultiply"
                android:layout_width="0dp"
                android:layout_height="match_parent"
                android:layout_weight="1"
                android:text="@string/_Multiply"
                android:onClick="onOperator"/>
    </LinearLayout>

    <!--  Row 3  -->
    <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_marginTop="2dp"
            android:layout_weight="1"
            android:orientation="horizontal"
            tools:ignore="NestedWeights,RtlHardcoded,UsingOnClickInXml,ButtonStyle">
        <Button
                android:id="@+id/btn1"
                android:layout_width="0dp"
                android:layout_height="match_parent"
                android:layout_weight="1"
                android:text="@string/_1"
                android:layout_marginRight="4sp"
                android:onClick="onDigit"/>
        <Button
                android:id="@+id/btn2"
                android:layout_width="0dp"
                android:layout_height="match_parent"
                android:layout_weight="1"
                android:layout_marginRight="4sp"
                android:text="@string/_2"
                android:onClick="onDigit"/>
        <Button
                android:id="@+id/btn3"
                android:layout_width="0dp"
                android:layout_height="match_parent"
                android:layout_weight="1"
                android:text="@string/_3"
                android:layout_marginRight="4sp"
                android:onClick="onDigit"/>
        <Button
                android:id="@+id/btnSub"
                android:layout_width="0dp"
                android:layout_height="match_parent"
                android:layout_weight="1"
                android:text="@string/_Sub"
                android:onClick="onOperator"/>
    </LinearLayout>

    <!--  Row 4  -->
    <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_marginTop="2dp"
            android:layout_weight="1"
            android:orientation="horizontal"
            tools:ignore="NestedWeights,RtlHardcoded,UsingOnClickInXml,ButtonStyle">
        <Button
                android:id="@+id/btnDecimal"
                android:layout_width="0dp"
                android:layout_height="match_parent"
                android:layout_weight="1"
                android:text="@string/_Decimal"
                android:layout_marginRight="4sp"
                android:onClick="onDecimalPoint"
                tools:ignore="NestedWeights,RtlHardcoded"/>
        <Button
                android:id="@+id/btn0"
                android:layout_width="0dp"
                android:layout_height="match_parent"
                android:layout_weight="1"
                android:layout_marginRight="4sp"
                android:text="@string/_0"
                android:onClick="onDigit"
                tools:ignore="RtlHardcoded"/>
        <Button
                android:id="@+id/btnClear"
                android:layout_width="0dp"
                android:layout_height="match_parent"
                android:layout_weight="1"
                android:text="@string/_Clear"
                android:layout_marginRight="4sp"
                android:onClick="onClear"
                android:layout_marginEnd="4sp"/>
        <Button
                android:id="@+id/btnAdd"
                android:layout_width="0dp"
                android:layout_height="match_parent"
                android:layout_weight="1"
                android:text="@string/_Add"
                android:onClick="onOperator"/>
    </LinearLayout>

    <!--  R0w 5 -->
    <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_marginTop="2dp"
            android:layout_weight="1"
            android:orientation="horizontal">
        <Button
                android:id="@+id/btnEqual"
                android:layout_width="match_parent"
                android:layout_height="match_parent"
                android:text="@string/_Equal"
                android:onClick="onEqual"
                tools:ignore="UsingOnClickInXml"/>
    </LinearLayout>
</LinearLayout>
```

# MainActivity.kt [File](app/src/main/java/com/joeljebitto/calculatorapp/MainActivity.kt)
```kotlin
package com.joeljebitto.calculatorapp

import android.os.Bundle
import android.view.View
import android.widget.Button
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity
import kotlinx.android.synthetic.main.activity_main.*


class MainActivity : AppCompatActivity() {
    private var lastNumeric = false
    private var lastDot = false

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
    }

    fun onDigit(view: View) {
        tvInput.append((view as Button).text)
        lastNumeric = true
    }


    fun onClear(view: View) {
        tvInput.text = ""
        lastNumeric = false
        lastDot = false
    }

    fun onDecimalPoint(view: View) {
        if (lastNumeric && !lastDot) {
            tvInput.append(".")
            lastNumeric = false
            lastDot = true
        }
    }

    fun onEqual(view: View) {
        if (lastNumeric) {
            val tvValue = tvInput.text.toString()
            try {
                if (tvValue.contains("-")) {
                    val splitValue = tvValue.split("-")
                    val one = splitValue[0].toInt()
                    val two = splitValue[1].toInt()
                    tvInput.text = (one - two).toString()
                } else if (tvValue.contains("+")) {
                    val splitValue = tvValue.split("+")
                    val one = splitValue[0].toInt()
                    val two = splitValue[1].toInt()
                    tvInput.text = (one + two).toString()
                } else if (tvValue.contains("*")) {
                    val splitValue = tvValue.split("*")
                    val one = splitValue[0].toInt()
                    val two = splitValue[1].toInt()
                    tvInput.text = (one * two).toString()
                } else if (tvValue.contains("/")){
                    val splitValue = tvValue.split("/")
                    val one = splitValue[0].toInt()
                    val two = splitValue[1].toInt()
                    tvInput.text = (one / two).toString()
                }
            } catch (e: ArithmeticException) {
                e.printStackTrace()
            }
        }
    }

    fun onOperator(view: View) {
        if (lastNumeric && !isOperatorAdded(tvInput.text.toString())) {
            tvInput.append((view as Button).text)
            lastNumeric = false
            lastDot = false
        }
    }

    private fun isOperatorAdded(value: String): Boolean {
        return if (value.startsWith("-")) {
            false
        } else {
            value.contains("+") || value.contains("*") || value.contains("/") || value.contains("-")
        }
    }

}
```
