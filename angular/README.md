# ANGULAR OVERVIEW

For create a new project

>`ng new <project_name> --no-strict`

**`--global`** To install a module from npm globally `-g`.
**`--save`** installs the package and updates the dependencies in your package.json.
**`--no-save`** installs the package but does not update the dependencies as listed in your package.json.
**`--save-dev`** updates the devDependencies in your package. These are only used for local testing and development. 

>`npm install --save bootstrap`

After that add a new styles setting in angular.json file for bootstrap.


**`main.ts`** This is the first code which gets to executed, inside of this exists the **`bootstrapModule(AppModule)`** which starts our Angular application by passing an app.module to this method.
**`app.module`**  inside of that exists **`bootstrap`** line too, and declare AppComponent, bootstrap is an array, which should be known to Angular, at the point of time, it analyzes our index.html file.
