# Gemavatar 2 (Redmine 4.1+)
``Gemavatar 2`` is the (inofficial) successor of the original Gemavatar plugin for [Redmine](https://www.redmine.org/).
It's replacing the Gravatars of users by JPEG pictures that are stored in the ldap _auth_source_ of Redmine.
Make sure to enable [Gravatars](https://www.redmine.org/projects/redmine/wiki/RedmineSettings#Use-Gravatar-user-icons)!

**This plugin is no longer maintained!**

Installation
------------

1. Download the [latest release](https://github.com/Boy132/redmine_gemavatar/releases/latest) (or git clone the repo `git clone git@github.com:Boy132/redmine_gemavatar.git`) and unzip it in the plugins folder.
Please be sure to rename the folder to `redmine_gemavatar` if necessary.

2. Install required gems:
`bundle install --without development test --no-deployment`

3. Do the database migration:
`bundle exec rake redmine:plugins NAME=redmine_gemavatar RAILS_ENV=production`

4. Restart the web server service. (e.g. `touch tmp/restart.txt`)

Configuration
-------------

First, make sure that the [Gravater feature](https://www.redmine.org/projects/redmine/wiki/RedmineSettings#Use-Gravatar-user-icons) of Redmine is enabled.

Then go to Administration > Plugins and click ``Configure`` on the Gemavatar
plugin.

There you must set:

- The maximum time the avatars are cached on disk.
- Whether to allow users to refetch their own avatar from AD.
- The string that defines the property in your LDAP server where the photo is stored (`thumbnailphoto` works for me, but `jpegphoto` was the original plugin value)

Checking that it works
----------------------

* Just go to your user page, and your avatar should be visible there.
* Note that the jpeg pictures are **automatically cropped to be squared**
