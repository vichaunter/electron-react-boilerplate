# New and Configured Electron + React Starter Boilerplate
_Electron, React, Webpack -- Modern and up-to-date, with all my must have survival stuff_


I've created that boilerplate based on some packages from github, and adapted to fit perfectly
into a real Electron + React development/production environment.

This is not a clean project, due it has lot of preconfigured stuff i use in my projects (listed below).
If you are searching for a clean boilerplate that does the same as this one with Electron and React, but
without all configurations and packages included, you can refer here: [clean-electron-react-boilerplate](https://github.com/pbarbiero/enhanced-electron-react-boilerplate) 

Production builds babel-minify is used, and ES2015/ES6 transpilation is provided -- 
As modern node and chromium versions support 99%+ of the ES6 feature set, I feel those steps are unnecessary.

## Features and packages
As i said, it comes with some preconfigured stuff and useful packages. Lot of them

- Solves CORS problem when using apis, for this in dev mode is rebuilt on save

###What it has

- **styled-components**
- **react-bootstrap**
- **react-router**
- **react-router-dom**
- **fontawesome**
- **axios**

Dev:

- **sass-loader**
- **babel-plugin-transform-class-properties**: allow you to define `state = {}` inside class component 
- **babel-plugin-transform-object-rest-spread**: allow to use spread operator `...props`
- **babel-plugin-macros**: 
- **bootstrap**
 

###What is not included

- Typescript: this depends on each one, and i prefer not to use it. You can implement
  it if you require it.

## To get started:

##### Install all required packages
```
yarn install
```

##### Development
To start webpack-dev-server. Electron will launch automatically after compilation.
```
yarn dev
```

##### Production
_You have two options, an automatic build or two manual steps_

###### One Shot
To have webpack compile your application 
into `dist/bundle.js` and `dist/index.html`, and then an 
electron-packager run will be triggered for the current platform/arch, outputting to `builds/`
```
yarn package
```
###### Manual
_Recommendation: Update the "postpackage" script call in package.json to specify parameters 
as you choose and use the  command instead of running these steps manually_
* Run `yarn build` to have webpack compile and output your bundle to `dist/bundle.js`
* Then you can call electron-packager directly with any commands you choose
```
yarn package
```
If you want to test the production build (In case you think Babili might be breaking something) 
after running `yarn build` you can then call `yarn prod`. This will cause electron to load 
off of the `dist/` build instead of looking for the webpack-dev-server instance. 
Electron will launch automatically after compilation.

### Removing specific packages

Clean all non required packages to make this boilerplate work:
```
yarn remove styled-components react-bootstrap react-router fontawesome axios sass-loader babel-plugin-transform-class-properties bootstrap react-router-dom axios babel-plugin-transform-object-rest-spread babel-plugin-macros              
```

#####react-bootstrap

Run 
```
yarn remove bootstrap react-bootstrap
```

Delete from index.js 
```
import "bootstrap/scss/bootstrap.scss"
```

Delete Fontawesome
```
yarn remove @fortawesome/fontawesome-svg-core  @fortawesome/free-solid-svg-icons @fortawesome/react-fontawesome
```