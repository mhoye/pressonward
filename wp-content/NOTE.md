## An important note:

The db.php file in this folder comes from:

https://github.com/aaemnnosttv/wp-sqlite-db

... and supports the use of SQLite as a backing
store for Wordpress rather than MySQL. You will
need to define your DB_DIR and DB_FILE names in
the text of db.php yourself in lines reading:

define('DB_DIR', '/absolute/path/to/your/directory/');
define('DB_FILE', 'your_sqlite_filename');

in your wp-config.php file. You can find them at line
40 of the wp-config-sample.php file provided in the
root directory of this project.
