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

## What is SPPNP (SharePoint Patterns and Practices or maybe not?)?   

## What do we mean by provisioning assets?  
* Site Provisioning: is a process of creating SharePoint sites *programmatically* to meet business requirements. Plus, it helps with maintaining the site.

## What do we mean by SharePoint Artifacts?
* Artifacts refers to items that are typically deployed to a SharePoint environment.
* Artifacts typically include:
    * JS Files.
    * CSS Files.
    * Image Files (.jpg, .gif, .png, etc).
    * Master Pages.
    * Page Layouts.
    * List Items.

## What is the point of the `Site Assets Library` that should exist in every Sharepoint site?  
* Anytime you upload a company logo to the site, the default location is set to to Site Assets Library. While you can change the location it's *recommended* to keep it as is for consistency reasons.  
* When creating a new "Team Site", the site automatically contains a OneNote notebook which is stored in the Site Assets Library.
 

## What does the gulp bundle and build do?  
* I think we bundle or package the project so that we can deploy it and drag/drop it in the application catalog on the SharePoint online.


## What is an app catalog?
* I'm putting the sppkg file in the app catalog.
* We `gulp build` before we package as written below.
* What is the sppkg file anyway? I think it's the file created after we write the command `gulp package-solution`. We use it to deploy the project to the tennant site.   

## What is Deploying generally and what is it with regards to SharePoint specifically?

## How to create a list on SharePoint?   

* In this page that is viewed after you choose the site you want to edit choose the option `New` then `list` this will create a list that you can CRUD inside using either ways we talked about whether it was the pnp or the sphttpclient.

    <img src="screenshots\screenshot_1.png">   

## GUID   
* An internal ID number used in the database. The GUID element generates a globally unique identifier.
* The guy put it in a file that he called `elements.xml` and he created this file in and after creating the folder `sharepoint` and then inside it the folder `assets`. 
* Inside the file `elements.xml` we put xml code that I'm not sure what means 


## What can we include int he elements.xml file?  
* We can provision the following with the SPFx solution package  
    * Document Library (ListInstance).
    * Custom Lists (ListInstance).
    * Custom List and Libarary Schemas (CustomSchema).
    * Web and List PropertyBag properties (PropertyBag).
    * Site Columns(Field).
    * Content Types (ContentType).
    * Images and other types of files e.g. xlsx, .docx templates (Module).
    * Custom Actions (CustomAction).
    * Modern Site pages with even our custom SPFx Client side webparts predefined on them (Module).
    * Old Wiki Pages and Web Part Pages (Module).
    * Pre-populated list and library items as part of the ListInstance or CustomSchema, but please do not do it. If you ever re-activate that feature the pre-populated data would double.

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
    * Or We can use an image but in base64 by converting the image into base64 on this website **https://www.base64-image.de/**.  

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

* When creating a subsite I need to make a constant in a "createSubSite" function:   
```typescript
const spHttpClientOptions: ISPHttpClientOptions = {
    body: `{
        "parameters" : {
            "@odata.type": "SP.WebInfoCreationInformation",
            "Title": "${subSiteTitle}",
            "Url": "${subSiteUrl}",
            "Description":"${subSiteDescription}",
            "Language":1033,
            "WebTemplate":"STS#0",
            "UseUniquePermissions":true
        }
    }`
};
```   
* The values inside the body object are reserved and should be included each time.  
* So after this we need to make a post request as follows:  
    ```typescript
    this.context.spHttpClient.port(url,SPHttpClient.configurations.v1,spHttpClientOptions)
        .then((response:SPHttpClientResponse) => {
            if(response.status == 200){
                alert("Site created successfully");
            }else{
                alert("Error");
            }
        })
    ```   

# Section 6 CRUD Operations with NoJavascript Framework  

* Most crucial import statement is  
    ```typescript
    import { ISPHttpClientOptions, SPHttpClient, SPHttpClientResponse } from '@microsoft/sp-http';
    ```   
* So we're creating a form that would be used to create a list item.

* We can bind an event with an html component by **creating** a function like so  
    ```typescript
    private _bindEvents(): void{
        this.domElement.querySelector('[ID OF THE HTML COMPONENT]').addEventListener('click', ()=>{this.FUNCTION_TO_GET_CALLED();});
    }
    ```   

* To get the value of the html components we can do the following:  

    ```typescript
    private addListItem(): void{
        var VARIABLE_NAME = document.getElementById("[ID OF COMPONENT]")["value"];
    }
    ```

* To make the restful api after getting the values we do the following  

    ```typescript   
    const siteurl: string = this.context.pageContext.site.absoluteUrl + "/_api/web/lists/getbytitle('SoftwareCatalog')/items";   //What is "getbytitle('softwarecataloge')"
    const itemBody: any = {
        "VARIABLE_NAME": VARIABLE_NAME
    }
    ```  
* In the `"VARIABLE_NAME"` above we have to make sure that the name is the same as the one in the lists in the catalog on SharePoint.  

* We then create a constant that has the itemBody we've written above but stringified:  
    ```typescript
    const spHttpClientOptions: ISPHttpClientOptions = {
        "body": JSON.stringify(itemBody)
    };
    ```   

* Then the post statement:  
    ```typescript
    this .context.spHttpClient.post(siteurl, SPHttpClient.configurations.v1, spHttpClientOptions)
        .then((response:SPHttpClientResponse) => {
            if(response.status === 201){
                let statusMessage: Element = this.domElement.querySelector('#[ID]');
                statusMessage.innerHTML = 'List created successfully';
                this.clear();//find out what this function does?
            }
        })
    ```

* Each request post, get or whatever will need to use the same values so we can make an interface and put them in it to make it reusable.

* To **read** we do the following:  

    * Put this line in the function `_bindEvents()`: `this.domElement.querySelector('#btnRead').addEventListener('click', () => { this.readListItem();});`.    


    * The `readListItem` body is as follows:  
        ```typescript
        private readListItem(): void{
            let id: string= document.getElementById("txtID")["value"];
            this._getListItemByID(id).then(listItem =>{
                //Then we give each element a value  
                document.getElementById("[ID]")["value"] = listItem.Title;

            })
        }

        private _getListItemByID(id: string): Promise<ISoftwareListItem> // Where the ISoftwareListItem is the interface we created for the values we crud
        {
            const url: string = this.context.pageContext.site.absoluteUrl+"/_api/web/lists/getbytitle('SoftwareCatalog')/items?$filter=Id eq"+id;
            return this.context.spHttpClient.get(url, SPHttpClient.configurations.v1)
            .then((response:SPHttpClientResponse) => {
                return response.json();
            })
            .then( (listItems:any) => {
                const untypedItem:any = listItems.value[0];
                const listItem: ISoftwareListItem = untypedItem as ISoftwareListItem;
                return listItem;
            }) as Promise <ISoftwareListItem>;
        }
        ```
    * When making a get request we have to give it the following parameters *the url*, *the configurations*, *the options*.  

* The **update** listItem   
    * Add this in the `_bindEvents()` function `this.domElement.querySelector('[BTN ID]').addEventListener('click', () => {this.updateListItem();});`
    * Then we create an `updateListItem()` function:  
        ```typescript
        private updateListItem(): void{
            const url: string = this.context.pageContext.site.absoluteUrl + '/_api/web/lists/getbytitle("SoftwareCatalog")/items('+id+')';  
            const itemBody: any={
                "Title": title,
                "SoftwareVendor": softwareVendor,
                "SoftwareDescription":softwareDescription,
                "SoftwareName": softwareName,
                "SoftwareVersion": softwareVersion
            };
            const headers: any = {
                "X-HTTP-Method": "MERGE",
                "IF-MATCH": "*"
            }  
            const spHttpClientOptions: ISPHttpClientOptions = {
                "headers": headers,
                "body": JSON.stringify(itemBody)
            };  

            this.context.spHttpClient.post(url, SPHttpClient.configurations.v1, spHttpClientOptions)
            .then((response:SPHttpClientResponse) => {
                if(response.status == 204){
                    let message: Element = this.domElement.querySelector('#[ID]');
                    message.innerHTML = "List Item has been updated successfully";
                }  else{
                    let message: Element = this.domElement.querySelector('#[ID]');  
                    message.innerHTML = "List Item updation failed"+response.status+" - "+response.statusText; 
                }

            })
        }
        ```

* The **delete** listItem   
    * Add the following to the `_bindEvents()` function: `this.domElement.querySelector('[BTN ID]').addEventListener('click', () => {this.deleteListItem(); });`.

    * Create `updateListItem` function:  
        ```typescript
        private deleteListItem(): void {
            let id: string = document.getElementById("[ID]")["value"];
            const url: string = this.context.pageContext.site.absoluteUrl + "/_api/web/lists/getbytitle('SoftwareCatalog')/items("+id+")";
            // In the update the method was called "MERGE" and here it's "DELETE"
            const headers: any = { "X-HTTP-Method": "DELETE", "IF-MATCH": "*"};

            const spHttpClientOptions: ISPHttpClientOptions = {
                "headers":headers
            };

            this.context.spHttpClient.post(url, SPHttpClient.configuration.v1, spHttpClientOptions)
                .then((response: SPHttpClientResponse) => {
                    if(response.status === 204)
                    {let message: Element = this.domElement.querySelector('[ELEMENT ID]');
                    message.innerHTML = "Delete: List Item has been deleted successfully.";
                    this.readAllItems();}
                    else{
                        let message: Element = this.domElement.querySelector("[ELEMENT ID]");
                        message.innerHTML = "Failed to Delete" + response.status + " - " + response.statusText;
                    }
                })
        }
        ```   

* How to **read all records** in a list  
    ```typescript
    private _getListItems(): Promise<ISoftwareListItem[]> {
        const url string = this.context.pageContext.site.absoluteUrl+"/_api/web/lists/getbytitle('SoftwareCatalog')/items";
        return this.context.spHttpClient.get(url,SPHttpClient.configurations.v1)
            .then(response => {
                return response.json();
            })
            .then(json => {
                return json.value;
            }) as Promise<ISoftwareListItem[]>;
    }
    ```   

* Then we create function `readAllItems`  
    ```typescript
    private readAllItems():void{
        this._getListItems().then(listItems => {
            let html: string = '<table border=1 width=100% style="border-collapse: collapse;">';
            html += '<th>Title</th> <th>Vendor</th><th>Description</th><th>Name</th><th>Version</th>';  

            listItems.forEach(listItem => {
                html += `<tr>
                <td>${listItem.Title}</td>
                <td>${listItem.SoftwareVendor}</td>
                //etc...
                </tr>`;
            });  
            html += '</table>';
            const listContainer: Element = this.domElement.querySelector('[ID]');
            listContainer.innerHTML = html;
        });
    }
    ```  

# Section 7 CRUD Operations with sp-pnp-js Library  

* We can install `sp-pnp-js` with this command  `npm install sp-pnp-js --save`.  
* We use the command `npm shrinkwrap` to shrink lock the dependencies of the solution.
* Then we import it as follows `import * as pnp from 'sp-pnp-js';`.  

* The difference between this and the sphttpclient way is 
    * To **add** an entry:
    ```typescript
    pnp.sp.web.lists.getByTitle("SoftwareCatalog").items.add({
      Title: softwaretitle,
      SoftwareVendor: softwarevendor,
      SoftwareName: softwarename,
      SoftwareVersion: softwareversion,
      SoftwareDescription: softwareDescription,
      
    }).then(r => {
     
      alert("success");

    }); 
    ```

    * To **read** an entry:  
    ```typescript
    const id = document.getElementById("txtID")["value"];

    pnp.sp.web.lists.getByTitle("SoftwareCatalog").items.getById(id).get().then((item: any) => {
      document.getElementById("txtSoftwareTitle")["value"] = item["Title"];
      document.getElementById("txtSoftwareName")["value"] = item["SoftwareName"];
      document.getElementById("txtSoftwareVersion")["value"] = item["SoftwareVersion"];
      document.getElementById("txtSoftwareDescription")["value"] = item["SoftwareDescription"];      
      document.getElementById("ddlSoftwareVendor")["value"] = item["SoftwareVendor"];
      
    });
    ```   

    * To **update** an entry:    
    ```typescript
    private updateListItem(): void{
        var title = document.getElementById("[ID]")["value"];
        //I take the values of each element 
        var softwareVendor = document.getElementById("ddlSoftwareVendor")["value"];
        var softwareDescription = document.getElementById("txtSoftwareDescription")["value"];
        var softwareName = document.getElementById("txtSoftwareName")["value"];
        var softwareVersion = document.getElementById("txtSoftwareVersion")["value"];
        

        let id: number = document.getElementById("txtID")["value"];

        pnp.sp.web.lists.getByTitle("SoftwareCatalog").items.getById(id).update({
        Title: title,
        SoftwareVendor: softwareVendor,
        SoftwareName: softwareName,
        SoftwareDescription: softwareDescription,
        SoftwareVersion: softwareVersion        
        }).then(r => {
        
        alert("Details Updated");

        });

    }
    ```

# Section 8 Creating SharePoint Artifacts  

* We create a folder called `sharepoint`, then a folder inside of it called `assets` and inside this folder we create an `elements.xml` file that I guess is where we provision assets. 
* It's said that it's recommended that we not create more than one `elements.xml` file.  

# Section 9  Working with Libraries

* A library is a class that contains a bunch of functions. 
* In the videos he made a `getCurrentTime()` function.

* The file `index.js` exports our library.

* We can create a library instead of a Webpart when typing the command `yo @microsoft/sharepoint`.  

* When we want a web part to work in a library we make a *symbolic link* using this command `npm link [LIBRARY NAME]`. 
* Since libraries are like classes, when we link the web part with the library we can use the functions of the library.  

* To have Full Width layout we set the value of `"supportsFullBleed"` to true in the manifest file. This gives the ability when making a page to put this webpart as full length