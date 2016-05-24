## Atom Elements Browser
The atom elements browser is an interactive documentation system for web components. For any web component, it automaticaly generates a panel using which the user can interact with the public properties of the elements. Support for interacting with methods and events will be added later.

**Prerequisites**

For the bower install instructions to be shown
- The elements must be [bower installable](http://bower.io/docs/api/#install)

To be able to use status indicator feature
- Hosted on github (or a git based version control system)
- Have Travis CI as the build system 

## Features
The elements browser has the following aspects
- **Easy Setup & Updates** 
   - To setup the browser for your elements, use the [ap-io command line interface](https://github.com/atomproject/ap-io) and modify a config file in the site generated to add urls of your elements there. Replace the atom logo with your own to brand it for your project. ![](https://github.com/atomproject/docs/blob/master/images/Screen%20Shot%202016-03-15%20at%202.16.52%20pm.png) *Figure: An example of the config file*
   - The elements browser for your elements can be hosted publicly on github or locally.
   - To update the elements browser for feature upgrades, update the package and run the site generation command again. 
- **Build Status & Element Count Indicators** 
   - The build status for every element is represented next to its name. This is available only if builds using travis CI are setup.
   - Status for all the elements is represented in the footer of the navigation. Green indicates that all elements are passing. Red indicates one or more elements are failing. Grey indicates that status is loading. ![](https://github.com/atomproject/docs/blob/master/images/Screen%20Shot%202016-03-16%20at%209.23.08%20am.png) *Figure: Build Status & Element Count Indicators* 
- **Design documentation support:** A markdown file called 'design-doc.md' in the repo of the element is used as the source for content in the 'Design Considerations' tab for the element. If the file is not present, the tab will be empty.
- **Developer Documentation:** Integrated with iron-doc-viewer, which is the default documentation component for polymer elements. As long as your element is documented, the docs will show up in the 'Dev Zone' tab for the element.
- **Demos**
   - Auto-generation of demo and property panel: An interactive demo of your polymer element will be created based on the first instance of your element in the demo folder/index.html.
   - Device Viewer Integration: Preview how your elements look across desktop, tablet and mobile devices without leaving the elements browser. ![](https://github.com/atomproject/docs/blob/master/images/Screen%20Shot%202016-03-16%20at%209.41.25%20am.png) *Figure: Device Viewer Integration*
   - Element code view with dynamic updation: As the user interacts with the element's properties using the panel on the right, the code of the element is updated below.
   - Install and usage instructions for your elements: Instructions to use your element via CDN and Bower are automatically generated and displayed below the element's code. ![](https://github.com/atomproject/docs/blob/master/images/Screen%20Shot%202016-03-16%20at%209.48.38%20am.png) *Figure: Dynamic code view, install and usage instructions*
