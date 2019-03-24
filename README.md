# CSS3D Book

  

VueJS based application using a model created on http://tridiv.com (created by  [Julien Garnier](https://github.com/juliangarnier)) to generate customized 3D Books. 

  

## Getting Started

##### Requirements

* [Node.JS](https://nodejs.org/en/)
* [Vue CLI](https://cli.vuejs.org/)
#### Install Vue Cli
```
npm install -g @vue/cli
```
---
#### Run Locally 
```
#In the project's root folder
npm install
npm run serve

```
Console should provide a local address to view the project

---
#### Build For Deployment 
```
#In the project's root folder
npm run build
```
Vue CLI's process for creating a static web site for the project, stored within the __dist__. The default is __"/"__ (the folders root), however, it is currently set to  __"/3d-book"__. (If the the project should be deployed at a site's root then __"/"__ would be the correct choice)

This is editale in  __vue.config.js__ 

For more information checkout the [Vue CLI's Docs](https://cli.vuejs.org/guide/deployment.html)

---

## Editing the Project

##### Project Structure

The project's logic is mostly in the __src__ folder. __src__ contains an __assets__ folder, for images and more, a __components__ folder where [*single file components*](https://vuejs.org/v2/guide/single-file-components.html) are stored, and the main JavaScript files.

__Run the program locally__ to see your changes implemented real time. Once you are ready to deploy your changes, run the __build__ command to create the static website content inside __dist__.


---

*note: the project is currently hosted on firebase. I've left in firebase config files so one can better understand the Vue Cli configuration choices left.