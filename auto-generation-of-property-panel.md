## What is property panel auto-generation?
The atom elements browser provides the capability to automatically generate a form using which users can tweak the properties of an element.

## How does this work?
As discussed [here](how-property-panel-works.md), the property panel is generated based on the property.json file present in the element's repo. Below in this article we describe the details of how the property.json file is automatically generated for an element, if it does not exist (at the time of setting up the elements browser).

1. If a property.json file is already present in the element's repo, then it is not disturbed, and the property panel is generated as described [here](how-property-panel-works.md).
2. If a property.json file is not present in the element's repo, then its gets created and all the public properties of the element get a corresponding UI control to represent them in the property panel.
3. The following mapping is used to make this happen. If the data type of the property is
  * `Boolean`, it is represented by a checkbox
  * `Date`, it is represented by a calendar
  * `Number`, it is represented by an input field
  * `String`, it is represented by an input field
  * `Object`, it is represented by a JSON editor
  * `Array`, it is represented by a compound control that can be a 
    * list of strings (if it is an array of strings)
    * list of numbers (if it is an array of numbers)
    * list of checkboxes (if it is an array of boolean values)
    * JSON editor (if it is an array of dates, objects, arrays or anything else)
4. The order of these UI controls in the property panel is the same as the order of the properties in the element's definition. They are not sorted alphabetically or based on any other organizing criterion as of now.
5. Default values are populated.



