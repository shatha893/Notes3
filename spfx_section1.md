# Section 1  

## Introduction on SPFx

* 2007 == Fully trusted solutions.
* 2010 == Sandbox & CSOM (Started developing for sharepoint). Here C# is used.
* 2016 == Cloud friendly SPFx. Using Typescript.

* How SPFx is different?

    * Tools we will be using?
        * Node.js, npm, Yeoman, Gulp and TypeScript.
        * REST APIs to communicate with Sharepoint data.

* What the hell is javascript injection?

* spfx does not use iframes.

<blockquote>
SPFX doesn't use any Iframe to render your Web parts, which was the case, in the case of Add-In Models.
</blockquote>

* The key features of SPFx:  
    * We can use frameworks such as React, Angular or Knockout (what the hell is knockout?) to develop the client side as part of my SPFx solution.
    * It supports a lot of open source development tools like *npm, typescript, Yeoman, Scaffold Code Generator, web pack and Gulp Utilities.*
    * What is Fabric React Controls.
    * An elevation of privileges is not allowed when using SPFx.

* SPFx Tool Chain  
    * Using nodejs as web server.
    * npm.
    * Gulp for building solutions (MSBuild. what's that?)
    * We will be using Typescript to develope the client side.
    * Yeoman code generator for scaffolding (what the hell?) of our projects?.    
    * More on these tools later.


* Nodejs is responsible to build and run the applications.
* NPM (Node Packet Manager) maintains an online repository to deploy npm packages.[NPM can be installed locally or globally `-g`].
* Installed npm packages can be found in `node_modules` folder.

* Gulp automates SPFx development and deployment tasks, it also bundles and minifies JS and CSS files and it compiles Typescript files into js.   
* Yeoman is a scaffolding tool for Modern Web Apps, relies on npm & gulp, used as spfx solution code generator.  

* By default spfx is given to us as local SharePoint workbench
* Hosted SharePoint workbench on sharepoint online called workbench.aspx.

* Application Lifecyble Management of my SPFx solutions (ALM):
    1. Install Microsoft/generator with this command `npm install -g @Microsoft/generator-sharepoint`. [A one time job]  
    2. Scaffold our sharepoint web part project `yo @Microsoft/sharepoint`.  
    3. Build Web part code.  
    4. Test the client side web parts both on the local workbench as well as the sharepoint hosted workbench (Tested on the local workbench) using `gulp serve`.  
    5. If I like the results I can take it to pre-production on the UAT server.    


* What npm modules I have on the computer can be viewed using this command `npm list -g --depth=0`.  

* To run a solution that already exists I have to, in the npm command prompt, write the command `npm install` to be able to run the code.
(That abdullah totally tricked me into thinking that it was a problem that can't be solved)


* For a quicker process instead of using `yo microsoft/sharepoint --skip-install` but it won't put the dependencies that are put in when we use without the skip.  

* What are the steps to create an application on Sharepoint


* We can create a folder that we want to have the project in.   
* Then write the following command `yo @microsoft/sharepoint`.  

# Section 2

### Steps for Creating a Sharepoint Application 

1. Create a folder with the project's name `md [FOLDER NAME]`.  
2. Go to the folder `cd [FOLDER NAME]`.  
3. Write the following command (to do what?) `yo @microsoft/sharepoint`.  
4. Then you'll be prompted with the following questions:
    * What is your solution name?(anatomy-demo)  --- You can leave it as default by pressing enter or you can enter the new name that you want.  
    * Only SharePoint Online (latest) is supported.  For earlier versions of SharePoint (2016 and 2019) please
use the 1.4.1 version of the generator. (Use arrow keys)  --- I can only view one option so just choose it `SharePoint Online only (latest)`.
5. For this question  `Where do you want to place the files? (Use arrow keys)` choose this `> Use the current folder`.  
6. This question is prompted next `Do you want to allow the tenant admin the choice of being able to deploy the solution to all sites immediately without running any feature deployment or adding apps in sites? (y/N)` default is "no". When selecting "yes" it means and I quote "That we don't have to install this app, in our SharePoint Tenant side collections". Not sure yet what this means but I guess we'll see later. 
7. `Will the components in the solution require permissions to access web APIs that are unique and not shared with other components in the tenant? (y/N)` not sure what it means yet either. When we select Yes it means we can create an isolated webpart so the option in the next question will only have `webpart`.  


* The `config.json` file will show me how many webparts do we have.
* Also, in the `config.json` file the object "externals" can have some stuff to be able to use external libraries like Jquery (More on that later). 

* The `package-solution.json` file is so important. What does it have?  
* What is the Azure CDN? 

* `gulp build` creates a new file called `lib` which has all the compiled typescript files into JS and the scss files into css.  

* `gulp bundle` creates two other new files `temp` and `dist`.

### skip-feature-deployment 

* When `skip-feature-deployment` is put as true.
* `gulp bundle --ship`
* `gulp package-solution --ship`
* After creating the app with `yo @microsoft/sharepoint` we use these two commands. 
* After writing the two `gulp` commands above we drag the created sppkg file that is in the folders `sharepoint < solution < skip-feature-deployment-demo.sppkg` into the `Apps for Sharepoint` part of the app co.


* I can open my application and create it through the `site` option then `active sites` where I can access my application or create a new one. Access this link here `https://m365x461244-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/home`. 

* My application on microsoft's sharepoint is called `MyNewApp`.

* When using the skip-feature-deployment we don't really install the SPFx solution into the site (It's working automatically NO IDEA WHAT THIS MEANS).  

* When not using the `skip-feature-deployment` we have to install the web component before we're able to use it and see it as an option when creating a new page.

* `gulp bundle` minifies the solution (What does that mean?)









     