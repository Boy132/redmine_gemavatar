# Gemavatar (Redmine 4.1+)

## About
``Gemavatar`` is a ``Redmine`` plugin for replacing the gravatars (they must 
be enabled) with the jpeg pictures stored in the ldap auth_source that 
``Redmine`` is configured to work with.

Installation
------------

1. Git clone the repo in the plugins folder: `git clone git@gitlab.com:aguarino/gemavatar.git`
Please be sure that the folder is named `redmine_gemavatar`.

2. Install required gems:
`bundle install --without development test --no-deployment`

3. Do the database migration on the database:
`bundle exec rake redmine:plugins NAME=redmine_gemavatar RAILS_ENV=production`

4. Restart the web server service.

Configuration
-------------

First, make sure that the Gravater feature of Redmine is enabled.

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
