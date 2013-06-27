# Zurb's Responsive Email Templates with Sass, Compass, and Jade Support

### HTML Email Design Is Hard

HTML email design is a pain in the rear. In stark contrast to the progress of modern web browsers and mobile platforms, [email client applications](http://www.campaignmonitor.com/css/) are stuck in the 1990's. New responsive design techniques can wreak havoc in some email clients, holding progress in check. We're stuck using tables!

### Modern Techniques For Creating Ancient Code

I find that an HTML pre-processor helps a great deal when managing complex tables, and there's lots of nice output optimizations (great for email design).

Zurb's [responsive email templates](http://zurb.com/playground/responsive-email-templates); I've taken them a step further with preprocessors like [Jade](http://jade-lang.com/) versions of the HTML files, and using SASS more efficiently with variables. 

In my case, I'm using [CodeKit](http://incident57.com/codekit) as a front-end to all the optimizers and minifiers it contains; you can use this code with all the open-source tools to create highly efficient, optimized HTML email templates.

\- AllanWhite, with thanks to JmauPetit.


## Installation

### Jade

For installing Jade, visit the [repo here](https://github.com/visionmedia/jade). Basically, I installed [Node.js](http://nodejs.org) first, then ran ``npm install jade --global`` so I'd have Jade on my system. _If you're using CodeKit_, you'll need to use the external Jade binary if you want to use the CSS inlining features (includes). You could use this for all kinds of great stuff, like template fragments and the like.

The following section is from [ComSource's SASS version](https://github.com/ComSource/zurb-responsive-email-templates-sass) of Zurb's email templates.

### Compass/Sass

The first dependancy is compass (and sass of course). Typically, installation process will looks like: 

	$ gem update --system
	$ gem install compass

If you need more information about compass installation, please refer to its [documentation](http://compass-style.org/install/).

### Python - Premailer (option)

A python CSS inliner is provided for your templates: we choose to integrate [premailer](https://github.com/peterbe/premailer). 

Prior to activate it, you need first to install python, and create a virtualenv for this tool (please check the [virtualenvwrapper documentation](http://virtualenvwrapper.readthedocs.org/en/latest/)). Then, install all python dependancies with:

	$ pip install -r requirements.txt
	
Once installed, activate the inliner by setting `use_css_inliner = true` in your `config.rb`.

## Usage

Clone this repository and start working with:

    $ compass watch

If you want to add your own rules to override default styles, all you need is to create your own `scss` file (e.g. `_myrules.scss`) and import this file at the end of the main scss file `email.scss`:

	@import "myrules";

A sample file `sass/_myrules.scss` as been integrated as a demo.

By default, compiled templates are stored in the `templates-inline` directory.

Have fun!
