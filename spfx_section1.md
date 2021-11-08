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








     