<img src="pix/logo.png" align="right" />

FilterCodes filter plugin for Moodle
====================================
![PHP](https://img.shields.io/badge/PHP-v5.6%20%2F%20v7.0%20%2F%20v7.1-blue.svg)
![Moodle](https://img.shields.io/badge/Moodle-v2.7%20to%20v3.4-orange.svg)
[![GitHub Issues](https://img.shields.io/github/issues/michael-milette/moodle-filter_filtercodes.svg)](https://github.com/michael-milette/moodle-filter_filtercodes/issues)
[![Contributions welcome](https://img.shields.io/badge/contributions-welcome-green.svg)](#contributing)
[![License](https://img.shields.io/badge/License-GPL%20v3-blue.svg)](#license)

# Table of Contents

- [Basic Overview](#basic-overview)
- [Requirements](#requirements)
- [Download FilterCodes for Moodle](#download-filtercodes-for-moodle)
- [Installation](#installation)
- [Usage](#usage)
- [Updating](#updating)
- [Uninstallation](#uninstallation)
- [Limitations](#limitations)
- [Language Support](#language-support)
- [Frequently Asked Questions (FAQ)](#faq)
- [Contributing](#contributing)
- [Motivation for this plugin](#motivation-for-this-plugin)
- [Further information](#further-information)
- [License](#license)

# Basic Overview

FilterCodes filter for Moodle enables content creators to easily customize
and personalize site and course content using plain text tags.

In addition, it also enables you to:
* Inserting non-breaking spaces;
* Tagging text as being in a different language;

Usage of the {FilterCodes} tags requires no knowledge of HTML but might be
important for sites wishing to comply with accessibility requirements.

IMPORTANT: Although we expect everything to work, this BETA release has not been fully tested in every situation. If you find a problem, please help by reporting it in the [Bug Tracker](http://github.com/michael-milette/moodle-filter_filtercodes/issues).

[(Back to top)](#table-of-contents)

# Requirements

This plugin requires Moodle 2.7+ from http://moodle.org/

[(Back to top)](#table-of-contents)

# Download FilterCodes for Moodle

The most recent STABLE release of FilterCodes for Moodle is available from:
https://moodle.org/plugins/filter_filtercodes

The most recent DEVELOPMENT release can be found at:
https://github.com/michael-milette/moodle-filter_filtercodes

[(Back to top)](#table-of-contents)

# Installation

Install the plugin, like any other plugin, to the following folder:

    /filter/filtercodes

See http://docs.moodle.org/34/en/Installing_plugins for details on installing Moodle plugins.

In order for the filters to work, the plugin must be installed and activated.

To activate, go to Site Administration > Plugins > Filters > Manage filters" and set the FilterCodes plugin to "On". Make sure it is set to Apply To: Content or optionally "Content and headings" if you also want the tags to affect headings.

[(Back to top)](#table-of-contents)

# Usage

IMPORANT: Although we expect everything to work, this BETA release has not been fully tested in every situation. If you find a problem, please help by reporting it in the [Bug Tracker](http://github.com/michael-milette/moodle-filter_filtercodes/issues).

There are no configurable settings for this plugin at this time.

{FilterCodes} are meant to be entered as regular text in the Moodle WYSIWYG editor through they will work equally well if entered in the code view.

Moodle metadata filters

* {firstname} : Display the user's first name.
* {surname} : Display the user's surname (family/last name).
* {fullname} : Display the user's first name and surname.
* {alternatename} : Display the user's alternate name. If blank, will display user's first name instead.
* {city} : Display the user's city.
* {country} : Display the user's country.
* {email} : Display the user's email address.
* {userid} : Display the user's ID.
* {username} : Display the user's username.
* {userpictureurl X} : Display the user's profile picture URL. X indicates the size and can be **sm** (small), **md** (medium) or **lg** (large). If the user does not have a profile picture or is logged out, the default faceless profile photo URL will be shown instead.
* {userpictureimg X} : Generates an <img> html tag containing the user's profile picture. X indicates the size and can be **sm** (small), **md** (medium) or **lg** (large). If the user does not have profile picture or is logged out, the default faceless profile photo will be used instead.
* {coursename} : Display the name of the current course or the site name if not in a course.
* {mycourses} : Display an unordered list of links to all my enrolled courses.
* {mycoursesmenu} : A second level list of courses with links for use in custom menus (filtering must be supported by the theme).
* {institution} : Display the name of the institution from the user's profile.
* {department} : Display the name of the department from the user's profile.
* {courseid} : Display a course's ID.
* {wwwroot} : Display the root URL of the Moodle site.
* {protocol} : http or https
* {referrer} : Referring URL
* {ipaddress} : User's IP Address.
* {recaptcha} : Display the recaptcha field - for use with Contact Form for Moodle. (UNTESTED)

Conditionally display content filters

* {ifenrolled}{/ifenrolled} : Will display the enclosed content only if the user **is** enrolled in the current course.
* {ifnotenrolled}{/ifnotenrolled} : Will display the enclosed content only if the user is **not** enrolled in the current course.
* {ifloggedin}{/ifloggedin} : Will display the enclosed content only if the user is logged in as non-guest.
* {ifloggedout}{/ifloggedout} : Will display the enclosed content only if the user is logged out or is loggedin as guest.
* {ifguest}{/ifguest} : Will display the enclosed content only if the user is logged-in as guest.
* {ifstudent}{/ifstudent} : Will display the enclosed content only if the user is logged-in and enrolled in the course (no other roles).
* {ifassistant}{/ifassistant} : Will display the enclosed content only if the user is logged-in as a non-editing teacher in the current course.
* {ifminassistant}{/ifminassistant} : Will display the enclosed content only if the user is logged-in as a non-editing teacher or above in the current course.
* {ifteacher}{/ifteacher} : Will display the enclosed content only if the user is logged-in as a teacher in the current course.
* {ifminteacher}{/ifminteacher} : Will display the enclosed content only if the user is logged-in as a teacher or above in the current course.
* {ifcreator}{/ifcreator} : Will display the enclosed content only if the user is logged-in as a course creator.
* {ifmincreator}{/ifmincreator} : Will display the enclosed content only if the user is logged-in as a course creator or above.
* {ifmanager}{/ifmanager} : Will display the enclosed content only if the user is logged-in as a manager.
* {ifminmanager}{/ifminmanager} : Will display the enclosed content only if the user is logged-in as a manager or above.
* {ifadmin}{/ifadmin} : Will display the enclosed content only if the user is logged-in as an administrator.

If the condition is not met in the particular context, the specified tag and it's content will be removed.

HTML and "lang" tagging

* {nbsp} : Is substituted for a non-breaking space when displayed.
* {langx xx}{/langx} : Tag specific text in a particular language by wrapping the text in a plain text pair of {langx xx} {/langx} tags. This makes no visible changes to the content but wraps the content in an HTML <span lang="xx"></span> inline tag. As a result, screen readers will make use of this information to use a particular kind of pronunciation if the text is in a different language than the language of the rest of the page. This is required for compliance with W3C Web Content Accessibility Guidelines (WCAG 2.0)

The opening {langx xx} tag should also include two [ISO 639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) language code abbreviation letters in lowercase associated with language's name. French, for example, has the code **fr**:

    {langx fr}Contenu{/langx}

The {langx fr}{/langx} filter will convert this into the following HTML

    <span lang="fr">Contenu</span>

[(Back to top)](#table-of-contents)

# Updating

There are no special considerations required for updating the plugin.

The first public ALPHA version was released on 2017-07-07.

For more information on releases since then, see
[CHANGELOG.md](https://github.com/michael-milette/moodle-filter_filtercodes/blob/master/CHANGELOG.md).

[(Back to top)](#table-of-contents)

# Uninstallation

Uninstalling the plugin by going into the following:

Home > Administration > Site Administration > Plugins > Manage plugins > Lang X

...and click Uninstall. You may also need to manually delete the following folder:

    /filter/filtercodes

Note that, once uninstalled, any tags and content normally handled by this plugin will become visible to all users.

# Limitations

* The {langx xx}{/langx} tag only supports inline text, not blocks of text.
* Unpredictable results may occur if you interweave HTML code with {FilterCodes} tags.

Incorrect example:

    <strong>{FilterCode}Content</strong>{/FilterCode}

Correct example:

    {FilterCode}<strong>Content</strong>{/FilterCode}

# Language Support

This plugin includes support for the English language.

If you need a different language that is not yet supported, please feel free
to contribute using the Moodle AMOS Translation Toolkit for Moodle at

https://lang.moodle.org/

This plugin has not been tested for right-to-left (RTL) language support.
If you want to use this plugin with a RTL language and it doesn't work as-is,
feel free to prepare a pull request and submit it to the project page at:

http://github.com/michael-milette/moodle-filter_filtercodes

# FAQ

## Frequently Asked Questions

IMPORANT: Although we expect everything to work, this ALPHA release has not been fully tested in every situation. If you find a problem, please help by reporting it in the [Bug Tracker](http://github.com/michael-milette/moodle-filter_filtercodes/issues).

### {FilterCodes} Why are tags displayed as entered instead of being converted to data?

Here are a few things you can check:
* Make sure the plugin is enabled. See installation instructions.
* If the tag is in a heading, make sure you have enabled the plugin for both content and headings.
* For the {langx} tag, make sure you included the 2 letter language code in the opening tag. The closing tag must not contain any language code.
* If the tags required a closing tag, make sure that it includes a forward slash. Example: {/ifenrolled}.
* Try a different tag like {protocol}. If it still doesn't get replaced with http or https either, chances are that this part of Moodle doesn't support filters yet. Please report the part of Moodle that doesn't support filters in the Moodle Tracker. If the problem is with a 3rd party plugin, please report the issue to the developer of that plugin using the Bug Tracker link on the plugin's page on moodle.org/plugins.

### Can I nest tags? For example, {ifloggedin}{ifenrolled}Message to appear if enrolled and loggedin.{/ifenrolled}{/ifloggedin}

Yes. In this case, both conditions must be met for the message to appear.

### How can I use this to pre-populate one or more fields in a Contact Form for Moodle?

Just put the tag in the input's value parameter. Here are a couple of examples:

    <input id="email" name="email" type="email" required="required" value="{email}">
    <input id="name" name="name" type="text" required="required" value="{fullname}">

Pro Tip: You can pre-populate a field and make it non-editable for logged-in users using a conditional tag:

    <input id="email" name="email" type="email" required="required" {ifloggedin}readonly{/ifloggedin} value="{email}">
    <input id="name" name="name" type="text" required="required" {ifloggedin}readonly{/ifloggedin} value="{fullname}">

### Why do administrators see the text of all other roles when using {ifminxxxx}Content{/ifminxxxx} tags?

This is normal as the administrator has the permission of all other roles. the {ifmin...} tags will display content if the user has a minimum of the specified role or above. For example, {ifminteacher}Content here!{/ifminteacher} will display "Content here!" whether the user is a teacher, course creator, manager or administrator even if they are not a teacher.

### Is there a tag to display...?

Only the tags listed in the documentation are currently supported. We are happy to add new functionality in future releases of FilterCodes. Please post all requests in the [Bug Tracker](http://github.com/michael-milette/moodle-filter_filtercodes/issues). You'll find a link for this on the plugin's page. The subject line should start with "Feature Request: ". Please provide as much detail as possible on what you are trying to accomplish and, if possible, where in Moodle the information would come from. Be sure to check back on your issue as we may have further questions for you.

### How can I test to see if all of the tags are working?

Create a Page on your Moodle site and include the following code:
* First name: {firstname}
* Surname: {surname}
* Fullname: {fullname}
* Alternate name: {alternatename}
* City: {city}
* Country: {country}
* Email: {email}
* User ID: {userid}
* Username: {username}
* User profile picture URL (small): {userpictureurl sm}
* User profile picture URL (medium): {userpictureurl md}
* User profile picture URL (large): {userpictureurl lg}
* User profile picture URL (small): {userpictureimg sm}
* User profile picture URL (medium): {userpictureimg md}
* User profile picture URL (large): {userpictureimg lg}
* Course or Site name: {coursename}
* Institution: {institution}
* Department: {department}
* Course ID: {courseid}
* My Enrolled Courses: {mycourses}
* My Enrolled Courses menu: {mycoursesmenu}
* WWWroot: {wwwroot}
* Protocol: {protocol}
* IP Address: {ipaddress}
* Referer: {referer}
* Recaptcha: {recaptcha} (will be available in a future release)
* Non-breaking space: This{nbsp}: Is it! (view source code to see the non-breaking space)
* English: {langx en}Content{/langx}
* Enrolled: {ifenrolled}You are enrolled in this course.{/ifenrolled}
* Not Enrolled: {ifnotenrolled}You are not enrolled in this course.{/ifnotenrolled}
* LoggedIn: {ifloggedin}You are logged-in.{/ifloggedin}
* LoggedOut: {ifloggedout}You are logged-out.{/ifloggedout}
* Guest: {ifguest}You are a guest.{/ifguest}
* Student: {ifstudent}You are student who is logged-in and enrolled in this course and have no other roles.{/ifstudent}
* Non-editing Teacher: {ifassistant}You are an assistant teacher.{/ifassistant}
* Non-editing Teacher (minimum): {ifminassistant}You are an assistant teacher or above.{/ifminassistant}
* Teacher: {ifteacher}You are a teacher.{/ifteacher}
* Teacher (minimum): {ifminteacher}You are a teacher or above.{/ifminteacher}
* Course Creator: {ifcreator}You are a course creator.{/ifcreator}
* Course Creator (minimum): {ifmincreator}You are a course creator or above.{/ifmincreator}
* Manager: {ifmanager}You are a manager.{/ifmanager}
* Manager (minimum): {ifminmanager}You are a manager or administrator.{/ifminmanager}
* Admin: {ifadmin}You are an administrator.{/ifadmin}

You can switch to different roles to see how each will affect the content being displayed.

### When a user is logged out, the First name, Surname, Full Name, Email address and Username are empty. How can I set default values for these tags?

You can do this using the language editor built into Moodle. There is currently support for the following defaults: defaultfirstname, defaultsurname, defaultusername, defaultemail. By default, these are blank. As for the Full Name, it is made up of the firstname and surname separated by a space and is therefore not settable.

### Can I use FilterCodes in custom menus?

Technically for sure! But only of the theme supports it. If it doesn't, contact the theme's developer and request that they add support for Moodle filters.

### Why is the IP Address listed as 0:0:0:0:0:0:0:1?

0:0:0:0:0:0:0:1 is the same as localhost and it means that your web browser is probably on the same computer as your web server. This shouldn't happen with users accessing your Moodle site from their own desktop or mobile device.

### Can I combine conditional tags?

Yes. However you can only combine (AND) them so that two or more tags must be true in order for the content to be displayed. For example:

{ifloggedin}{ifenrolled}You are logged-in and enrolled in this course.{/ifenrolled}{/ifloggedin}

This plugin does not support {if this OR that} type conditions at this time. Depending on your requirement, the {ifmin...} tags might help you achieve this. These tags enable you to display content to users with a minimum role level. This could be useful if you wanted to only display a message to faculty such as (teacher or above).

### Why does it show me as enrolled on the front page?

The Front Page is a course in Moodle. All users are enrolled by default in this course.

### Are there any security considerations?

There are no known security considerations at this time.

## Other questions

Got a burning question that is not covered here? If you can't find your answer, submit your question in the Moodle forums or open a new issue on Github at:

http://github.com/michael-milette/moodle-filter_filtercodes/issues

[(Back to top)](#table-of-contents)

# Contributing

If you are interested in helping, please take a look at our [contributing](https://github.com/michael-milette/moodle-filter_filtercodes/blob/master/CONTRIBUTING.md) guidelines for details on our code of conduct and the process for submitting pull requests to us.

## Contributors

Michael Milette - Author and Lead Developer

## Pending Features

Some of the features we are considering for future releases include:

* Finish unit testing script.
* Add ability to access additional information from profile fields.
* Add ability to access information in custom profile fields.
* Add ability to access course meta information. Example, teacher's name.
* Add ability to list courses in the current course's category.
* Add ability to list subcategories of the current category.
* Add ability to define custom code blocks - useful for creating global content blocks that can be centrally updated.
* Add the ability for {langx xx}{/langx} tag to supports blocks of text (using DIV), not just inline text (using SPAN).
* Option to disable unused or unwanted filters in order to optimize performance.
* Create an Atto add-on to make it easier to insert FilterCodes tags.

If you could use any of these features, or have other requirements, consider contributing or hiring us to accelerate development.

[(Back to top)](#table-of-contents)

# Motivation for this plugin

The development of this plugin was motivated through our own experience in Moodle development and topics discussed in the Moodle forums. The project is sponsored and supported by TNG Consulting Inc.

[(Back to top)](#table-of-contents)

# Further Information

For further information regarding the filter_filtercodes plugin, support or to
report a bug, please visit the project page at:

http://github.com/michael-milette/moodle-filter_filtercodes

[(Back to top)](#table-of-contents)

# License

Copyright © 2017 TNG Consulting Inc. - http://www.tngconsulting.ca/

This file is part of FilterCodes for Moodle - http://moodle.org/

FilterCodes is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

FilterCodes is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with FilterCodes.  If not, see <http://www.gnu.org/licenses/>.

[(Back to top)](#table-of-contents)