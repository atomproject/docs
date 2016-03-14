## Atom Elements Browser
The atom elements browser is an interactive documentation system for polymer elements. For any polymer element, it automaticaly generates a panel using which the user can interact with the public API of the element, including its properties, methods and events.

**Prerequisites**
The elements should be  
- Hosted on github (or a git based version control system)
- Have Travis CI as the build system (Optional. Needed for certain features to work.)

## Features
The elements browser has the following aspects
- **Easy Setup & Updates** 
   - To setup the browser for your elements, simply fork a repo and modify a config file in it to add urls of your elements there. Replace the atom logo with your own to brand it for your project.
   - The elements browser for your elements can be hosted publicly on github or locally.
   - To update the elements browser for feature upgrades, [do this]
- **Build Status & Element Count Indicators** 
   - The build status for every element is represented next to its name. This is available only if builds using travis CI are setup.
   - Status for all the elements is represented in the footer of the navigation. Green indicates that all elements are passing. Red indicates one or more elements are failing. Grey indicates that status is loading.  
- **Design documentation support:** A markdown file called 'design-doc.md' in the repo of the element is used as the source for content in the 'Design Considerations' tab for the element. If the file is not present, the tab will be empty.
- **Developer Documentation:** Integrated with iron-doc-viewer, which is the default documentation component for polymer elements. As long as your polymer element is documented, the docs will show up in the 'Dev Zone' tab for the element.
- **Demos**
   - Auto-generation of demo and property panel: An interactive demo of your polymer element will be created based on the first instance of your element in the demo folder/index.html.
   - Device Viewer Integration: Preview how your elements look across desktop, tablet and mobile devices without leaving the elements browser.
   - Element code view with dynamic updation
   - Install and usage instructions for your elements
