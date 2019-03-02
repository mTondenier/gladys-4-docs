# Contributing to Gladys Documentation

We love your input! It's always great in open-source to receive help from other people 😄

## We Develop with Github

We use github to host code, to track issues and new documentation requests, as well as accept pull requests.

## Requirements

- Markdown knowledge, [Markdown tutorial](https://www.markdowntutorial.com/)
- HTML knowledge, [HTML tutorial](https://www.w3schools.com/html/)

This site is build with [Jekyll](https://jekyllrb.com/), to install and run Jekyll we recommend using [Bundler](https://bundler.io/). Bundler manages Ruby gem dependencies, reduces Jekyll build errors, and prevents environment-related bugs.

1. First, If you don't have Ruby installed, [install Ruby 2.1.0 or higher](https://www.ruby-lang.org/en/downloads/).

2. Next you can install Bundler 

```` 
gem install bundler
# Installs the Bundler gem 
````

## To contributing documentation

Pull requests are the best way to propose changes. 

### First steps

1. [Fork](https://help.github.com/articles/fork-a-repo/) or [clone](https://help.github.com/articles/cloning-a-repository/) the repo and [create your branch](https://help.github.com/articles/creating-and-deleting-branches-within-your-repository/) from `master`.

2. Move into the clone folder and install dependencies 

Window and Mac

```` 
bundle install
# Install dependencies
````

Linux 

```` 
BUNDLE_GEMFILE="./GemFile" bundle install
# Install dependencies
````

3. And finally build site with automatic reload
```` 
bundle exec jekyll serve
# Build site
````

### For starting 

Folder strucutre:

```
./
├── _data
│   └── translations      // All translations
├── _docs                 // All documentaion markdown files
│   ├── en                // All english documentaion markdown files
│   └── fr                // All french documentaion markdown files
├── _inlcudes     
├── _layouts    
├── _assets               // All assets
│       ├── css 
│       ├── image 
│       └── js
├── _config.yml
├── 404.html
├── GemFile
├── GemFile.lock
├── index.html
└── README.md
```

Docs folder structure:

```
_docs
└── 'lang'                          // the 'lang' can be 'en' or 'fr'
    ├── 1_installation
    │   ├── 1_image.md
    │   ├── 2_manual.md
    │   ├── 3_docker.md
    │   └── index.md
    │
    ├── 2_configuration
    │   ├── 1_house.md
    │   ├── 2_room.md

        ... etc.

    │   ├── 7_gladys-voice.md
    │   ├── 8_gladys-bluetooth.md
    │   └── index.md
    │
    ├── 3_documentation
    │   ├── 1_alarm.md
    │   │    ├── 1_alarm-utility.md
    │   │    └── 2_alarm-management.md
    │   ├── 2_event.md
    │   │    ├── 1_event-utility.md
    │   │    └── 2_event-management.md

        ... etc.

    │   ├── 7_internal-module.md
    │   │    ├── 1_internal-module-utility.md
    │   │    ├── 2_internal-module-management.md
    │   │    └── 3_internal-module-config.md
    │   ├── 8_external-module.md
    │   │    ├── 1_external-module-utility.md
    │   │    ├── 2_external-module-management.md
    │   │    └── 3_external-module-config.md
    │   └── index.md
    │  
    ├── 4_concept
    │   ├── 1_architecture.md
    │   ├── 2_data-model.md
    │   └── index.md
    │
    ├── 5_development
    │   ├── 1_api.md
    │   │    ├── 1_rest.md
    │   │    ├── 2_nodejs.md
    │   │    └── 3_mqtt.md
    │   │ 
    │   ├── 2_tools.md
    │   │    ├── 1_gladys-pod.md
    │   │    └── 2_gladys-mqtt-adapteur.md
    │   │ 
    │   ├── 3_internal-module.md
    │   ├── 4_external-module.md
    │   ├── 5_scrip.md
    │   └── index.md
    │
    ├── faq
    │   ├──                           // all qestions files
    │   └── index.md
    └── index.md
 

```

**About docs folder and rules**

 - All markdown files are sorted by categories and for some by subcategories, if you decide to add a new file place it in the folder corresponding to its category and if necessary in its subcategory. If no category suits you, create a issue to talk about it first !

 - The site is fully generated according to the markdown files present in this folder, for more control of the order of display the files are numbered.

 - The docs folder contains only markdown files, if you want to add images to your files you have to put them in the ``assets/images`` folder. And in your markdown file put ``![My helpful screenshot](/assets/screenshot.jpg)`` to access to your image.

 - Use beautiful images as in the home configuration documentation. To create beautiful images use [Screely](https://www.screely.com/) with no window option and transparent background. 

 - Not use your name on screenshot. Use Tony Stark 😎

 - For the faq, create a markdwon file for one question with the response.
 
 - Do not put header title on the markdown file. The title is automatically added one build whith 'title' meta data. (more information about meta data on "About meta data markdown files")

**About meta data markdown files**

In Jekyll all markdown files start with [front matter](https://jekyllrb.com/docs/front-matter/), which is typically used to set meta data.
On this site, the meta is used to generate the navigation bar, the sidebar in the presentation of the documentation, the presentation of the documentation and the presentation of the FAQ. It is very important for not break the build ;)

All markdown files's meta data => 

- **name:** // Name of article in english, lowercase and without special characters, it was used for links in page
- **title:** // Name of the article in the language in which it was written
- **permalink:** // Useful to control output url, contains language and parent category title in lowercase and without special characters, exmaple: "en/documentation"
- **lang:** // Language of the article
- **category:** // Title of parent category in the language in which it was written, useful for nav-bar generating
- **sub-category:** // Title of sub category in the language in which it was written, useful for nav-bar and side-bar generating

## Any contributions you make will be under the MIT Software License

In short, when you submit code changes, your submissions are understood to be under the same [MIT License](http://choosealicense.com/licenses/mit/) that covers the project.