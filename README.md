# gulp-pug-starter

! [GitHub release] (https://img.shields.io/github/release/andreyalexeich/gulp-pug-starter.svg)
[! [dependencies Status] (https://david-dm.org/andreyalexeich/gulp-pug-starter/status.svg)] (https://david-dm.org/andreyalexeich/gulp-pug-starter)
[! [devDependencies Status] (https://david-dm.org/andreyalexeich/gulp-pug-starter/dev-status.svg)] (https://david-dm.org/andreyalexeich/gulp-pug-starter ? type = dev)
! [GitHub stars] (https://img.shields.io/github/stars/andreyalexeich/gulp-pug-starter.svg?style=social)
! [GitHub watchers] (https://img.shields.io/github/watchers/andreyalexeich/gulp-pug-starter.svg?style=social)
<a href="https://www.paypal.me/andreyalexeich/">
<img src = "https://img.shields.io/badge/%D0%97%D0%B0%D0%B4%D0%BE%D0%BD%D0%B0%D1%82%D1%8C% 20% D0% BD% D0% B0% 20% D0% BF% D0% B8% D0% B2% D0% BE-PayPal-informational.svg ">
</a>
<a href="https://www.tinkoff.ru/cardtocard/">
<img src = "https://img.shields.io/badge/%D0%97%D0%B0%D0%B4%D0%BE%D0%BD%D0%B0%D1%82%D1%8C% 20% D0% BD% D0% B0% 20% D0% BF% D0% B8% D0% B2% D0% BE-% D0% 9D% D0% B0% 20% D0% BA% D0% B0% D1% 80 % D1% 82% D1% 83% 20 -% 205536% 209137% 205288% 201934-informational.svg ">
</a>

##: fire: Features
* class naming according to [BEM] (https://ru.bem.info/)
* BEM structure is used
* preprocessors are used [Pug] (https://pugjs.org/) and [SCSS] (https://sass-lang.com/)
* uses transpiler [Babel] (https://babeljs.io/) to support modern JavaScript (ES6) in browsers
* used by [Webpack] (https://webpack.js.org/) to build JavaScript modules
* uses CSS-grid [smart-grid] (https://github.com/dmitry-lavrik/smart-grid) based on Bootstrap for fast responsive layout
* using a hard code guide
* used to check the code for errors before committing

##: hammer_and_wrench: Install
* install [NodeJS] (https://nodejs.org/en/) (if required) and [Yarn] (https://yarnpkg.com/en/docs/install)
* download the build in the console using [Git] (https://git-scm.com/downloads): `` 'git clone https: // github.com / andreyalexeich / gulp-pug-starter.git ,,,
* install `` gulp`` globally: `` `` yarn global add gulp-cli``
* install `` bem-tools-core`` globally: `` `yarn global add bem-tools-core``
* go to the downloaded assembly folder: `` `cd gulp-pug-starter``
* download the required dependencies: `` `yarn```
* to get started, enter the command: `` yarn run dev`` (development mode)
* to build the project, enter the command `` yarn run build`` (build mode)

If you did everything correctly, you should open a browser with a local server.
Build mode assumes project optimization: image compression, minification of CSS and JS files for uploading to the server.

##: open_file_folder: File structure

```
gulp-pug-starter
├── dist
├── gulp-tasks
├── src
│   ├── blocks
│   ├── fonts
│   ├── img
│   ├── js
│   ├── styles
│   ├── views
│   └── .htaccess
├── gulpfile.babel.js
├── webpack.config.js
├── package.json
├── .babelrc.js
├── .bemrc.js
├── .eslintrc.json
├── .stylelintrc
├── .stylelintignore
└── .gitignore
```

* Folder root:
    * ``` .babelrc.js``` - Babel settings
    * ``` .bemrc.js``` - BEM settings
    * ``` .eslintrc.json``` - ESLint settings
    * ``` .gitignore``` - disallow Git tracking of files
    * ``` `.stylelintrc``` - Stylelint settings
    * ``` '.stylelintignore``` - prohibition of file tracking by Stylelint
    * ``` 'gulpfile.babel.js``` - Gulp settings
    * ``` 'webpack.config.js``` - Webpack settings
    * ``` `package.json``` - list of dependencies
* Folder ``` src ``` - used during development:
    * BEM blocks and components: ``` src / blocks```
    * fonts: ``` src / fonts```
    * images: ``` src / img```
    * JS files: ``` src / js```
    * site pages: ``` src / views / pages```
    * SCSS files: ``` src / styles```
    * service Pug files: ``` src / views```
    * Apache web server configuration file with settings [gzip] (https://habr.com/ru/post/221849/) (lossless compression): ``` src / .htaccess ```
* ``` Dist ``` folder - the folder from which the local server for development is started (when you start ``` yarn run dev ```)
* Folder ``` gulp-tasks ``` - folder with Gulp-tasks

##: keyboard: Commands
* ``` yarn run lint: styles``` - check SCSS files. For VSCode, you need to install [plugin] (https://marketplace.visualstudio.com/items?itemName=shinnn.stylelint). For WebStorm
or PHPStorm must enable Stylelint in ``` Languages ​​& Frameworks - Style Sheets - Stylelint ``` (errors will be fixed automatically when you save the file)
* ``` yarn run lint: styles --fix``` - fix errors in SCSS files
* ``` yarn run lint: scripts``` - check JS files
* ``` yarn run lint: scripts --fix``` - fix errors in JS files
* ``` yarn run dev``` - start the server for project development
* ``` yarn run build`` - build a project with optimization without starting the server
* ``` yarn run build: views``` - compile Pug files
* ``` yarn run build: styles``` - compile SCSS files
* ``` yarn run build: scripts``` - build JS files
* ``` yarn run build: images``` - build images
* ``` yarn run build: webp``` - convert images to `` .webp```
* ``` yarn run build: sprites```- build sprites
* ``` yarn run build: fonts``` - build fonts
* ``` yarn run build: favicons``` - build favicons
* ``` yarn run build: gzip``` - build Apache configuration
* ``` yarn run bem-m``` - add a BEM block
* ``` yarn run bem-c``` - add component

##: bulb: Recommendations for use
### Component approach to website development
* each BEM block has its own folder inside `` src / blocks / modules ''
* folder of one BEM block contains one Pug file, one SCSS file and one JS file (if the block uses a script)
    * The pug file of the block is imported to the file `` src / views / index.pug '' (or to the required page file from where the block will be called)
    * The SCSS file of the block is imported into the file `` src / blocks / modules / _modules.scss ''
    * JS file of the block is imported into `` src / js / import / modules.js ''

An example of a folder structure with a BEM block:
``
blocks
├── modules
│ ├── header
│ │ ├── header.pug
│ │ ├── header.js
│ │ ├── header.scss
``

In order not to manually create the corresponding folder and files, it is enough to write the following commands in the console:
* `` yarn run bem-m my-block`` - to create a BEM block in `` src / block / modules`` (for main BEM blocks), where `` my-block`` `- the name of the BEM block;
* `` yarn run bem-with my-component`` - to create a component in `` src / blocks / components`` (for components), where `` my-component`` is the name of the component

### Components
* components (for example, icons, buttons) are styled in Pug using mixins
* each component has its own folder inside `` src / blocks / components``
* the folder of one component contains one Pug file, one SCSS file and one JS file (if the component uses a script)
    * The pug file of the component is imported into the main page file `` src / views / index.pug '' (or into the required page file from where the component will be called)
    * The SCSS file of the component is imported into the file `` src / blocks / components / _components.scss``
    * JS file of the component is imported into the file `` src / js / import / components.js ''

### Project Pages
* project pages are located in the folder `` src / views / pages``
    * each page (including the main page) inherits the template `` src / views / layouts / default.pug``
    * main page: `` 'src / views / index.pug``

### Fonts
* fonts are in the `` src / fonts '' folder
    * use [formats] (https://caniuse.com/#search=woff) `` `.woff`` and` `` .woff2```
    * fonts are included in the file `` src / styles / base / _fonts.scss ''
    * you can convert local fonts using [this service] (https://onlinefontconverter.com/)

### Images
* images are in the folder `` src / img ''
    * image for generating favicons must be located in the folder `` src / img / favicon '' and have a size of at least `` 1024px x 1024px ''
    * images are automatically converted to `` .webp '' format. Detailed information on use [here] (https://vk.com/@vk_it-webp).

### Third party libraries
* all third-party libraries are installed in the `` node_modules '' folder
    * to load them use the command `` yarn add package_name``
    * to connect JS files of libraries, import them at the very beginning of the JS file of the BEM block (that is, the BEM block that the script uses), for example:
    javascript
    import $ from "jquery";
    ``
    * to include the style files of the libraries, import them into the file `` src / styles / vendor / _libs.scss ''
    * JS files and library style files cannot be changed by yourself

: warning: If your project uses several libraries that need to be included on several pages, to avoid errors you need to:
* along the path `` src / js / import``, create a folder `` pages``
* in the folder `` pages``, create a js-file for the page, for example, `` pageA.js``, and import a library there that will be used only on this page
    * perform the same step for additional pages
* in the file `` webpack.config.js '' add js-files of pages to the entry point, example:
javascript
entry: {
    main: "./src/js/index.js",
    pageA: "./src/js/import/pages/pageA.js",
    pageB: "./src/js/import/pages/pageB.js"
}
``
* include compiled js-files on the required pages

##: hash: smart-grid CSS
The builder includes the [smart-grid] CSS grid (https://github.com/dmitry-lavrik/smart-grid) from [Dmitry Lavrik] (https://dmitrylavrik.ru/). It allows you to get rid of
unnecessary classes in markup due to the use of mixins in SCSS and speeds up adaptive layout. The configuration is already set up according to the [Bootstrap] grid (https://getbootstrap.com/). Instructions for use [here] (https://grid4web.ru/basics).

##: point_right: Need SCSS without Pug?
Use [this] (https://github.com/andreyalexeich/gulp-scss-starter/) assembly.

##: yellow_heart: Like the project?
Let me know about [bugs] (https://github.com/andreyalexeich/gulp-pug-starter/issues), put an asterisk in the upper right corner, bother me
for beer: beer:
* [On PayPal] (https://www.paypal.me/andreyalexeich)
* [To the card - 5536 9137 5288 1934] (https://www.tinkoff.ru/cardtocard/)

##: envelope: Contacts
* VK: [@andreyalexeich] (https://vk.com/andreyalexeich)
* Telegram: [@andreyalexeich] (https://t-do.ru/andreyalexeich)