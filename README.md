# Press Onward

This is a copy of the [Wordpress source code](https://wordpress.org/latest.tar.gz) obtained under
the terms of the GPL and very lightly modified to use SQLite as a backing store.

## Installation 

This is not a step-by-step guide, and will require some degree of
comfort with your filesystem, editors, and logging. I will need to
skip over some pretty big steps, e.g. "set up Apache", for which I
apologize; for the most part those steps are better covered elsewhere. 

If you are migrating from an existing wordpress installation, please
start by doing a full export of your existing content, and make sure
you have a recent backup of the underlying system available.

_This is not_ an in-place migration or upgrade; it is a backup,
reinstall and restore exercise.

This has been tested on one Debian-based machine running Apache as
its web server. So "works on my machine", yes, but it does work on my
machine.

If you're using other operating systems or web servers, I hope this
gives you enough information to get up and running. I'd would be glad
to include the specific steps you took if you can share them. 

## Details:

* Start by cloning this repository, and moving it's contents into the folder you want Apache to serve up.
* You'll need to install PHP and PHP-SQLite support libraries.
- On Debian, via apt, these are libapache-mod-php(VERSION) and php(VERSION)-sqlite3. (VERSION) has to match.
* Create an empty database file somewhere appropriate with the sqlite3 command-line tool.
* In wp-config.php, define two new variables DB_DIR and DB_FILE.
- These are the path to and name of your SQLite file respectively; see wp-config-sample.php for the specific text.
* Restart your web server, open up the site in a browser open wp-admin/install.php - not the normal login page.
* Let Wordpress complete the installation process, then re-import your downloaded export.
* Check to make sure your user accounts have been restored, and that you have the expected number of users and admins.
* Check your site content for breakage.
* Restart Apache to test that it comes up cleanly.


## Addenda

The db.php file in the wp-content folder comes from [Evan Mattson](https://github.com/aaemnnosttv/)
and is [available here](https://github.com/aaemnnosttv/wp-sqlite-db).

If you haven't already done so get Certbot via your preferred package
manager and let it set up the S in https for you. "sudo certbot --webservername"
and three minutes is all it takes, all software should work this well.

All of the changes from the original Wordpress source in this repo have 
the word "pressonward" in a comment right next to them, and a brief
explanation of why they're there. 

## Participation

Issues are welcome, comments are welcome, showing up in my inbox like I owe
you something is not. Commits _might be_ welcome, but this is a convenience 
repo, not a fork, a project or a job, I do not want it to diverge so far 
from upstream that it might accidentally turn into any of those things. 

- mhoye, 18/Oct/2024
