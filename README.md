# Research Feature Article Starter Template

This is a starter grunt/SASS setup for building Research site featured articles.
This includes some basic mixins, breakpoints and a modified breakpoint mixin that
is a little different from the Responsive Framework. This Breakpoint mixin outputs
IE styles by prepending them with a .lt-ie9 class instead of outputing an IE.css file.
This is because styles/scripts attached via the editorial plugin to a post in Wordpress
cannot load a separate IE stylesheet for older browsers.

## Get Started

New to [Responsive](https://github.com/bu-ist/responsive-framework) and [SASS](http://sass-lang.com)? Follow these steps to get up and running.

### For first timers, you'll need:

- [ ] [Node and Node Package Manager (npm)](#install-node-and-node-package-manager), which install Grunt plugins for you
- [ ] [Grunt](#install-grunt-and-bower), which we use to take care of a bunch of nitty gritty stuff to turn your SASS to CSS
- [ ] [Bundler](#install-bundler), which will make sure this project has all the tools it needs to work - and install them if it doesn't

This part only has to be done once, so if you've already worked on a SASS project here, you're set! You can skip to the [returning users](#returning-users) section.

### If you've already worked on a SASS project here:

Congrats! You can skip ahead to the [returning users](#returning-users) section. You'll only need to do these last three steps to set up your files and get moving.

- [ ] Download and rename this repository
- [ ] [Install development dependencies](#install-development-dependencies)
- [ ] [Do an initial build](#fire-up-grunt)

## New users: Set up your development environment

### Install Node and Node Package Manager

The build process introduced for Responsive uses several Node.js packages including Grunt, Bower and several Grunt plugins. Node packages are installed using the Node Package Manager.

Download and install the latest version of both Node and Node Package Manager from http://nodejs.org/. Choose the stable build if you see that option.

### Change permissions for Node folders

The Mac OS X installer doesn't always set the correct owner for the global node_modules / package cache directories. The way we can fix this is by **changing ownership** of those folders.

You'll need administrative privileges to do this, so we'll use `sudo` in front of the command. This basically says: I'm an admin, and I want to change ownership (chown) recursively (-R, which will affect this folder and all subfolders) in the two places where Node stuff is installed.

You should see a prompt for your password. Go ahead and enter it, and hit enter again to fix the permissions on the folders.

```bash
sudo chown -R `whoami` /usr/local/lib/node_modules ~/.npm `npm -g bin`
```

### Install Grunt and Bower

You'll need to install both Grunt CLI and Bower globally so that you don't have to re-install it for every project. This can be accomplished by running the following command in your Terminal:

```bash
npm install -g grunt-cli bower
```

### Install Bundler

Grunt depends on the Sass Ruby gem to compile Sass files. To ensure all designers working on a project are using the same version of Sass, we're using [Bundler](http://bundler.io). Bundler can be installed using `gem`, the Ruby package manager:

```bash
gem install bundler
```

## Returning users

### Download and rename this repository

[Download this repository](https://github.com/bu-ist/r-research-feature-article-starter/archive/master.zip) and rename the folder according to your article's URL. For more information on how to do this, please see [our Research documentation](http://developer.bu.edu/webteam/design/research/).

### Install development dependencies

The `Grunt` build process depends on several Node packages which must be installed for every theme. These dependencies are captured in the top-level `package.json` file, and installed to a `node_modules` directory for each theme which is ignored by Git when committing changes.

To install these dependencies, run the following in your theme directory:
```bash
npm install
```

Make sure you have the correct version of Sass installed for the current project by running the following:

```bash
bundle install
```

### Fire up Grunt

Now is a perfect time to double check everything went smoothly. Normally, we use `grunt` to watch all our files for changes and compile when it sees a change, but you can also trigger SASS compilation manually. That's what we'll do now to test this.

Run the SASS compile manually by running:

```bash
grunt sass
```

If all went well, you should see a style.css and style.css.map file appear in your directory. Run `grunt` one more time to watch the files and compile automatically!

```bash
grunt
```

Only your compiled CSS files need to be uploaded to the server - no need to upload the SASS.