# Polymer Components Installation and Development Guide

Writing code for polymer elements is easy but the consumption and development workflows
can be quite tricky to understand at first. The objective of this guide is to break
down this workflow and explain it, the target audience of this article is somebody who
has novice level experience in web technologies like `npm` and `bower`.

# Dependency Management

All the polymer elements are written to be consumed by the `bower` dependency manager.
`bower` is a flat dependency manager, this can be contrasted with `npm` which is a
hierarchichal dependency manager. This can be seen very easily by observing the directory
structure of `bower_components` and `node_modules`, the dependencies of a package are
installed alogside it by the `bower` while `npm` installs those dependencies inside
a separate directory `node_modules` located inside the package\`s directory. This
nature of bower is important to understand while developing Polymer components, you should
have a look at the structure of Polyemer's [seed-element](https://github.com/polymerelements/seed-element), note how the [dependency](https://github.com/PolymerElements/seed-element/blob/master/seed-element.html#L11) `polymer` consumed.
All the components should be consumed in above fashion.

# Installing Dependencies

Above section mentions how should a dependency be consumed in your code but it doesn't
specify how to install the dependencies themselves. Writing `link` tag referencing the
dependency doesn't install the dependency, you have to install it using the following
command.

```
bower install --save PolymerElements/seed-element
```

A breakdown of parts of above command is provided below.

1. `bower install` instructs bower to install a dependency
2. `--save` add the dependency in `bower.json` file. Run `bower init` if you don't have the file.
3. `PolymerElements/seed-element` instructs bower to find `seed-eleement` repository
    in the organization `PolymerElements` on `github.com`. Refer [docs](http://bower.io/docs/api/#install) for more information.

Now you can use the server of your choice to serve the `bower_components` directory.
I prefer a simple http server called `http-server`, it can be installed and used with following
commands.

```
npm install -g http-server
cd <your application root directory
http-server
```

# Developing Components

Now you might wonder how would you go about developing your own components? or you 
want to clone an existing component and develop that?. Following steps will outline
the workflow for develop.

1. Clone an existing component or create a new one following the directory structure of
   `seed-element`. Note that you can also use the `yeoman` generator provided by Polymer
   team for [creating a new element](https://github.com/yeoman/generator-polymer#element-alias-el).
2. Run `bower install` to instll the dependencies listed in `bower.json` file. Both 
   `dependencies` and `devDependencies` are installed.
3. Install the `polyserve` using command `npm i -g polyserve`.
4. Run the command `polyeserve` in the root directory of your component.

Note the need to use `polyserve` to browse the component. Each components references
its dependencies as if they exist in the same directory as the component, this is true
when the component is consumed in an application, but when developing the component all
its dependencies will installed in a directory `bower_components` located in the root
of the component repository. This is a problem, if you use `http-server` to serve the
component instead of `polyserve` the browser will throw dependency not found errors.
