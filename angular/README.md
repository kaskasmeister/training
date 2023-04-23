# ANGULAR OVERVIEW

> `npm install -g @angular/cli`

> `npm uninstall -g @angular/cli`

> `npm cache clean`

> `npm cache verify`

> `npm -g install @angular/cli@version.* # For ^5.0.0`

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

# Component

`@Component({
   selector: 'app-servers',
   ...
})`

`<app-server></app-server>`

# Component as an attribute
`
@Component({
   selector: '[app-servers]',
   ... 
})
`

`<div app-server></div>`

# Component as a class

`@Component({ 
   selector: '.app-servers'
})`

`<div class="app-servers"></div>`

# Databinding

You could basicall translate databinding with communication. Communication between your Typescript code, of your business logic, and template, you might have some result in your Typescript code. 
(Communication between template (HTML) and ts file).

## Output Data
- **String Interpolation** `{{ data }}`

- **Property Binding** `[property] = "data"`
 
## React to (User) Events (Input)
- **Combination of Both:** ***Two-Way-Binding*** (`[(ngModel)]="data"`)

# Property Binding vs String Interpolation

Don't mix property binding and string interpolation.

- **Data binding** If you need to use directives, or change some html attribute

>`<p [innerText]="allowNewServer"></p>`

- **String interpolation** If you need print any value in your template, you can use string interpolation

>`<p>{{ allowNewServer }}</p>`

## Event Binding

-`(click)="myFunction()"`
-`(dblclick)="myFunction()"` 
-`(submit)="myFunction()"`
-`(blur)="myFunction()"`
-`(focus)="myFunction()"`
-`(scroll)="myFunction()"`
-`(cut)="myFunction()"`
-`(copy)="myFunction()"`
-`(paste)="myFunction()"`
-`(keyup)="myFunction()"`
-`(keypress)="myFunction()"`
-`(keydown)="myFunction()"`
-`(mouseup)="myFunction()"`
-`(mousedown)="myFunction()"`
-`(mouseenter)="myFunction()"`
-`(drag)="myFunction()"`
-`(drop)="myFunction()"`


 
 


