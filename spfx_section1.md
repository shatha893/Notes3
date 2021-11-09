# General Knowledge  


## What is Sharepoint?  
* Organizations use SharePoint to create websites.  
* You can use it as a secure place to store, organize, share, and access information from any device.

## What's SharePoint in Microsoft 365?  
* It's a cloud based service hosted by Microsoft.
* For businesses of all sizes.
* Instead of installing and deploying SharePoint Server on-premises, any business can subscribe to a Microsoft 365 plan or to the standalone SharePoint Online Service.  

## What's SharePoint Server?  
* Organizations can deploy and manage SharePoint Servers on-premises or with an Office 365 Enterprise subscription to take advatage of all the latest features.  

## What is Gulp?  
* A toolkit that when used with JS it automates slow, repetitive workflows and composes them into efficient build pipelines.  
* Modern web development has many repetitive tasks like running a local server, minifying code, optimizing images, preprocessing CSS, cache busting, unit testing, linting, optimization, etc. Gulp is a build tool for automating these tasks.  
* Used as a streaming build system in front-end web development.  
* A task runner built on Node.js and npm.  

## What does Scaffolding the code mean?  
* It's a meta-programming method of building database-backed software applications.
* A technique supported by some model-view-controller frameworks

## What is Boilerplate code?  
<blockquote>
    Boilerplate code means a piece of code which can be used over and over again. On the other hand, anyone can say that it's a piece of reusable code.
</blockquote>

## What is NoJavascript Framework and Knockout?   
* **Knockout** is a JS library that helps you create rich, responsive display and editor user interfaces 


## What is the page's context?  
* The hosted workbench in SharePoint enables access to the page context, which exposes the following key properties such as:
    * Web title `this.context.pageContext.web.title`.
    * Web absolute URL.
    * Web server-relative URL.
    * User sign-in name.   
* `this.context.pageContext` is the code we use to access the context.

## What is CDN and what does it have to do with Sharepoint?
* You can use the built-in Office 365 Content Delivery Network (CDN). Why?  To provide better performance for your sharepoint online pages. How?  by caching static assets closer to the browsers requesting them, which helps to speed up downloads and reduce latency.


## Why are we coding the freaking property pane?  
* It seems I might need to add custom functionalities to the property panel sometimes.  

## Typescript?  
* It's developed by Microsoft.
* It's a strict syntactical superset of JS and adds optional static typing to the language.
* Transcript is designed for the development of large applications and transcompiles to JS. 
* What do we mean by *superset of JS*?
    <blockquote>
    TypeScript is a superset of JavaScript, meaning it’s a layer around JS with more methods and that makes you follow a certain way of development that you don’t have to otherwise in vanilla (like having to set the types of your variables).
    </blockquote>  

* It does not transcompile to web assembly, it does so to vanilla JS.
* WebAssembly (aka Wasm) it's an open standard that defines a portable binary-code format for executable programs. 

<br/><br/>

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


* We can change the link that opens when we run `gulp serve` from the file `serve.json` in the `config` folder
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

* How to write the properties code myself? Do I have to download libraries?What are the properties anyway?


* What are properties in the context we're talking about here?

* What is a freaking culture? 

* SPHttpClient is important when we want to call RESTFUL APIs.   

# Section 3 Working with Property Pane  

* Property pane. We can open it when we click on the "edit" button for the web part.

* This interface is created by the Yeoman
    ```typescript
    export interface INotHelloWorldWebPartProps {
    description: string;
    }
    ```
* Whatever property in this interface we can access it by typing `this.properties.[PROPERTY NAME]`.   

    ```typescript
    protected getPropertyPaneConfiguration(): IPropertyPaneConfiguration {
        return {
        pages: [
            {
            header: {
                description: strings.PropertyPaneDescription
            },
            groups: [
                {
                groupName: strings.BasicGroupName,
                groupFields: [
                    PropertyPaneTextField('description', {
                    label: strings.DescriptionFieldLabel
                    })
                ]
                }
            ]
            }
        ]
        };
    ```  
* This function is created by default.  
* As you can see the `pages` is an array which means we can have multiple pages and each page would have `header` and `groups`.

    ```typescript
    PropertyPaneTextField('description', {
                    label: strings.DescriptionFieldLabel
                    })
    ```  
* The previous code means that this textbox is bound to the description property. 
* And this textbox's descriptions property gets its default value from the `mystrings` file.

* The file `mystrings.d.ts`. Well it has a bunch of strings that we accessed in the code before as we can see.
* In `loc` folder we also have a js file called `en-us.js` and each language has it's own js file.  

* How can we add more properties? 

* `IPropertyPaneConfiguration` we can view the description of the interface that the function extends by right clicking on it and then choosing the option `go to definition`.  

* It's like each property has an object as a value.
* The render function has the output kind of like React.  

* If I want to assign default values to the properties I need to put the default value in the manifest file in this section  
```json
"preconfiguredEntries": [{
    "groupId": "5c03119e-3074-46fd-976b-c60198311f70", // Other
    "group": { "default": "Other" },
    "title": { "default": "notHelloWorld" },
    "description": { "default": "notHelloWorld description" },
    "officeFabricIconFontName": "Page",
    "properties": {
      "description": "notHelloWorld"
    }
  }]
```  

* We put our properties in the `"properties"` object above.
* Each time we change any value in a manifest file we need to `gulp serve` again.

* In the `onInit` function we can put default values of our properties in it or in the json manifest file.  

* In our solution we can disable reactive web parts using the function  
    ```typescript
    protected get disableReactivePropertyChanges():boolean{
        return true; //or false
    }
    ```  

# Section 4 Working with Property Pane Various Controls  

* Property Pane Toggle is the toggle option that takes a true/false value depending on the user's toggle (It's a property control).  

* We also have something called a "Slider Control". We have to import "PropertyPaneSlider" from '@microsoft/sp-property-pane'.  


* The property pane choice group we can create by importing sth like previously.
    ```typescript
    PropertyPaneChoiceGroup([PROPERTY NAME],{
        label: [STRING],
        options: [
            //[A BUNCH OF OBJECTS (CHOICES)]
        ]
    })
    ```  

* To put options with images in the property pane we can put the following code  

    ```typescript
    PropertyPaneChoiceGroup([PROPERTY NAME],{
        label: [STRING],
        options:[
            {
                key:[STRING], text: [STRING],
                imageSrc: [IMAGE LINK],
                imageSize: {width:[NUMBER], height:[NUMBER]},
                selectedImageSrc: [LINKE OF SOMETHING]
            }
        ]
    })
    ```   
    
* Property pane dropdown  

* Each one of these controls as we can see is a property.   
    ```typescript
    PropertyPaneDropdown('newProcessorType',{
        label: [STRING],
        options: [
            {key:[STRING], text:[STRING]}//each option should have a "key" and a "text". That's only one option
        ],
        selectedOption:[KEY OF OPTION]
    })
    ```  

* Property Pane Checkbox  

    ```typescript
    PropertyPaneCheckbox([STRING],{
        text:[STRING],
        checked:[BOOLEAN VALUE],
        disabled:[BOOLEAN VALUE]
    })
    ```    

* Property Pane Link   
* In this case we don't bind the link to any property.  

    ```typescript
    PropertyPaneLink('',{
        href: [LINK],
        text:[TEXT],
        target:'_blank',
        popupWindowProps:{
            height:[NUMBER],
            width:[NUMBER],
            positionWindowPosition:[NUMBER],
            title: [TITLE]
        }
    })
    ```  

* Working with multiple groups  
    <!-- Write codeee!!!!  Video 33-->
    ```typescript
    //New code for creating multiple groups in the same page   
    //The groups will be viewed in an accordion
    pages:[
        {
            header:{
                description: "Page 1"
            },
            groups:[
                {
                    groupName:[GROUP NAME],
                    groupFields:[
                        //Here we put the controls we want to be viewed in this group
                        //We put the function of the control  
                        PropertyPaneToggle([PROPERTY NAME],{
                            label:[TEXT]
                        })
                        //So here we've only put one control in the group
                    ]
                },
                {
                    groupName: [TEXT],
                    groupFields:[
                        PropertyPaneTextField([PROPERTY NAME],{
                            label: [TEXT]
                        })
                    ]
                }],
            displayGroupAsAccordion:true //true is just an example
        }
    ] 
    ```   

* Multiple Pages   
    ```typescript
        pages:[
            {
                header:{
                    description: "Page 1"
                },
                groups:[
                    {
                        groupName:[GROUP NAME],
                        groupFields:[
                            PropertyPaneToggle([PROPERTY NAME],{
                                label:[TEXT]
                            })
                        ]
                    },
                    {
                        groupName: [TEXT],
                        groupFields:[
                            PropertyPaneTextField([PROPERTY NAME],{
                                label: [TEXT]
                            })
                        ]
                    }],
                displayGroupAsAccordion:true //true is just an example
            },
            {
                header:{
                    description: "Page 2"
                },
                groups:[
                    {
                        groupName:[GROUP NAME],
                        groupFields:[
                            //Here we put the controls we want to be viewed in this group
                            //We put the function of the control  
                            PropertyPaneToggle([PROPERTY NAME],{
                                label:[TEXT]
                            })
                            //So here we've only put one control in the group
                        ]
                    },
                    {
                        groupName: [TEXT],
                        groupFields:[
                            PropertyPaneTextField([PROPERTY NAME],{
                                label: [TEXT]
                            })
                        ]
                    }],
                displayGroupAsAccordion:true //true is just an example
            },
            {
                header:{
                    description: "Page 3"
                },
                groups:[
                    {
                        groupName:[GROUP NAME],
                        groupFields:[
                            //Here we put the controls we want to be viewed in this group
                            //We put the function of the control  
                            PropertyPaneToggle([PROPERTY NAME],{
                                label:[TEXT]
                            })
                            //So here we've only put one control in the group
                        ]
                    },
                    {
                        groupName: [TEXT],
                        groupFields:[
                            PropertyPaneTextField([PROPERTY NAME],{
                                label: [TEXT]
                            })
                        ]
                    }],
                displayGroupAsAccordion:true //true is just an example
            }
        ] 
    ```
* It's not good practice to put comments inside JSON objects.  

## Modify Default Icon  
* How do we accomplish that?  
    * In the manifest file we have a json object property called "officeFabricIconFontName" which is "page" by default.   
    * When we change the name of the icon in this option the icon changes but we have to get the name from the icons available on the website "Fabric ui".  
    * We can also use any image we want by replacing the option "officeFabricIconFontName" into "iconImageUrl" and we give it the value as the link of the image.  
    * Or We can use an image but in base64 by converting the image into base64 on this website **https://www.base64-image.de/**
* What *is* that for God's sake!?   
    It seems like it's the icon of the website.

# Section 5 Working with SPHttpClient  

* What is SPHttpClient?  
    * So it seems it's something that helps me to send api's. Turns out it is. It's used to perform REST calls against SharePoint.  
    * It's a class and obviously it has methods:  
        * `beginBatch(batchCreationOptions)`, begins an ODATA batch, which allows multiple REST queries to be bundled into a single web request .  
        * `fetch(url,configuration,options)`, perform a REST service call.  
        * `get(url,configuration,options)`, Calls fetch(), but sets the method to "GET".  
        * `getWebUrlFromRequestUrl(requestUrl)`, Use a heuristic to infer the base URL for authentication.  
        * `post(url, configuration, options)`, calls fetch(), but sets the method to "POST".  
        * The ODATA batch allows multiple REST queries to be bundled into a single web requests.
    * So why are we using it to enable the user to create sites and lists?  
    Because we need to post the site created or the list created.

* How to create a new list using SPHttpClient  
    * It's like I'm making n UI to be able to create a list.  


* Create a new site using sphttpclient  
    * Which means to make the UI that allows users to create a website
     