# MaterialSpinner
[![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-MaterialSpinner-brightgreen.svg?style=flat)](http://android-arsenal.com/details/1/1720)

Spinner with Material Design

This library provides you a Spinner with the Material style. You can use it like any regular Spinner. 
Add floating label text, hint and error messages.

## Screenshots
![MaterialSpinner](./screenshots/screenshot.gif)

## Gradle Dependency
Use this dependency in your build.gradle file to reference this library in your project

```groovy
compile 'com.github.ganfra:material-spinner:2.0.0'
```

If you use other libraries requiring appcompat-v7 like [MaterialEditText](https://github.com/rengwuxian/MaterialEditText/) make sure to exclude them if you have issue at compile time :
```groovy
compile ('com.github.ganfra:material-spinner:2.0.0'){
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
        app:msp_multiline="false"
        app:msp_dropDownHintView="@layout/my_custom_dropdown_hint_item_layout"
        app:msp_hintView="@layout/my_custom_hint_item_layout"
        app:msp_hint="hint"
        app:msp_enableFloatingLabel="false"
        app:msp_enableErrorLabel="false"
        app:msp_floatingLabelText="floating label"
        app:msp_baseColor="@color/base"
        app:msp_highlightColor="@color/highlight"
        app:msp_errorColor="@color/error"
        app:msp_typeface="typeface.ttf"
        app:msp_thickness="2dp"
        app:msp_hintColor="@color/hint"
        app:msp_arrowColor="@color/arrow"
        app:msp_arrowSize="16dp"
        app:msp_alignLabels="false"
        app:msp_floatingLabelColor="@color/floating_label"/>
```
You can set a hint and a floating label text. If no floating label text is provided, the hint will be set instead.


Java side, you use it like a regular spinner, setting an adapter to it.
```java
 String[] ITEMS = {"Item 1", "Item 2", "Item 3", "Item 4", "Item 5", "Item 6"};
 ArrayAdapter<String> adapter = new ArrayAdapter<String>(this, android.R.layout.simple_spinner_item, ITEMS);
 adapter.setDropDownViewResource(android.R.layout.simple_spinner_dropdown_item);
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
You can choose to have a scrolling animation or to set the error message on multiple lines with the "msp_multiline" attribute in xml (default is true).


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



