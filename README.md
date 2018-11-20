# MaterialSpinner
[![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-MaterialSpinner-brightgreen.svg?style=flat)](http://android-arsenal.com/details/1/1720)

Spinner with Material Design

Slightly modified version of original [ganfra/MaterialSpinner](https://github.com/ganfra/MaterialSpinner). Library also provides own array adapter, which does not have annoying left padding. 


## Screenshot
![spinner](https://user-images.githubusercontent.com/36644697/48788083-5d806c80-ecea-11e8-96a0-f84be9ff14a3.PNG)

## Gradle Dependency
Step 1. Add the JitPack repository to your build file

Add it in your root build.gradle at the end of repositories:

	allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}
Step 2. Add the dependency

	dependencies {
	        implementation 'com.github.Moravec-Jan:MaterialSpinner:2.0.5'
	}

If you use other libraries requiring appcompat-v7 like [MaterialEditText](https://github.com/rengwuxian/MaterialEditText/) make sure to exclude them if you have issue at compile time :
```groovy
implementation ('com.github.Moravec-Jan:MaterialSpinner:2.0.5'){
        exclude group: 'com.android.support', module: 'appcompat-v7'
}
```

## Thanks

Many thanks to Matías Dumrauf to help me supporting this library!


## Usages

In the xml : 

```xml
<fr.ganfra.materialspinner.MaterialSpinner
        android:id="@+id/spinner"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" 
        app:ms_multiline="false"
        app:ms_dropDownHintView="@layout/my_custom_dropdown_hint_item_layout"
        app:ms_hintView="@layout/my_custom_hint_item_layout"
        app:ms_hint="hint"
        app:ms_enableFloatingLabel="false"
        app:ms_enableErrorLabel="false"
        app:ms_floatingLabelText="floating label"
        app:ms_baseColor="@color/base"
        app:ms_highlightColor="@color/highlight"
        app:ms_errorColor="@color/error"
        app:ms_typeface="typeface.ttf"
        app:ms_thickness="2dp"
        app:ms_hintColor="@color/hint"
        app:ms_arrowColor="@color/arrow"
        app:ms_arrowSize="16dp"
        app:ms_alignLabels="false"
        app:ms_floatingLabelColor="@color/floating_label"/>
```
You can set a hint and a floating label text. If no floating label text is provided, the hint will be set instead.

  MaterialSpinner.createDefaultSpinner(EnergyVisualizationApp.getInstance(), items);
Java side, you use it like a regular spinner, setting an adapter to it.
```java
 String[] ITEMS = {"Item 1", "Item 2", "Item 3", "Item 4", "Item 5", "Item 6"};

 ArrayAdapter<String> adapter =  MaterialSpinner.createDefaultSpinner(this, ITEMS);
 spinner = (MaterialSpinner) findViewById(R.id.spinner);
 spinner.setAdapter(adapter);
```

If you need to set an error message, you can do it the same way than with an EditText :
```java
 //Activate
 spinner.setError("Error");
 //Desactivate
 spinner.setError(null);
```
You can choose to have a scrolling animation or to set the error message on multiple lines with the "ms_multiline" attribute in xml (default is true).


## License

    Copyright 2017 François Ganard

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.



