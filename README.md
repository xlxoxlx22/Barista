[![Build Status](https://travis.schibsted.io/scmspain/barista.svg?token=3kFC3MqgXJW7rpZEMFFo&branch=master)](https://travis.schibsted.io/scmspain/barista)

# Barista
**The guy who serves great Espresso**

Espresso is a great tool to test our Android apps via instrumental tests. With them, we can mimic user actions like clicking a button, scrolling a list, selecting an item on a spinner or swiping on a pager. Then, we can assert that a text appears in the screen, an image is visible or invisible, or a button is enabled or not.

On the other hand, if you tried Espresso, you’ll agree that its API is not discoverable.

Barista introduces a discoverable API for the Espresso features. So, you and all the Android team will write instrumental tests with no effort. 

### Barista’s Actions API
```java
// Click widgets
click(R.id.button);
click("Next");
clickBack();

// Writing into widgets
writeToEditText(R.id.edittext, "A great text");
writeToAutoCompleteTextView(R.id.autocomplete, "Another great text");

// Select items on AdapterViews
clickListViewItem(R.id.listview, 4);
clickListViewItem(R.id.listview, 4, 5, 6);
clickRecyclerViewItem(R.id.recycler, 2);
clickRecyclerViewItem(R.id.recycler, 2, 3, 4);
clickSpinnerItem(R.id.spinner, 1);

// Select items on RadioButtons and CheckBoxes
clickCheckBoxItem(R.id.first_item);
clickCheckBoxItem("The checkbox text");
clickRadioButtonItem(R.id.radiogroup, R.id.first_item);
clickRadioButtonItem(R.id.radiogroup, "The radio text");

// Pick data on pickers
setDateOnPicker(1986, 03, 23);

// Interact with dialogs
clickDialogPositiveButton();
clickDialogNeutralButton();
clickDialogNegativeButton();

// Scroll on scrolls and pagers
scrollTo(R.id.button);
scrollTo("A widget with this text");
swipePagerForward(R.id.pager);
swipePagerBack(R.id.pager);

// Interact with the navigation drawer
openDrawer(R.id.drawer);
closeDrawer(R.id.drawer);
```

### Barista’s Assertions API
```java
// Is this view displayed?
assertDisplayed("Hello world");
assertDisplayed(R.string.hello_world);
assertDisplayed(R.id.button);

// ...or not?
assertNotDisplayed("Hello world");
assertNotDisplayed(R.string.hello_world);
assertNotDisplayed(R.id.button);

// Is this view enabled?
assertEnabled("Hello world");
assertEnabled(R.string.hello_world);
assertEnabled(R.id.button);

// ...or not?
assertDisabled("Hello world");
assertDisabled(R.string.hello_world);
assertDisabled(R.id.button);

// Hope this view doesn't exist!
assertNotExist("Hello world");
assertNotExist(R.string.hello_world);
assertNotExist(R.id.button);

// What's the state of the Drawer
assertDrawerIsOpen(R.id.drawer);
assertDrawerIsClosed(R.id.drawer);

// And another tricky feature
assertThatBackButtonClosesTheApp();
```
# License

```
Copyright 2017 Schibsted Classified Media Spain S.L.


Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
