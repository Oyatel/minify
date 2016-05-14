MINIFY
====

*Minify is an HTTP content server. It compresses sources of content 
(usually files), combines the result and serves it with appropriate 
HTTP headers. These headers can allow clients to perform conditional 
GETs (serving content only when clients do not have a valid cache) 
and tell clients to cache the file for a period of time.* 

More info: [http://code.google.com/p/minify/][1]


----------


Wordpress User
-------------

These WP plugins integrate Minify into WordPress's style and script hooks to
get you set up faster.

 - [http://wordpress.org/extend/plugins/bwp-minify/][2]
 - [http://wordpress.org/extend/plugins/w3-total-cache/][3]


----------


Installation
------------

**Using composer:**

NOTE: Check [Composer Starting Guide][4] for a more detailed explanation on how using composer to download and manage this package.

 1. Download composer.phar from [here][5] or downloading through the console/command line by using this command in your project root folder: `curl -s https://getcomposer.org/installer | php`
 2. Create a ***composer.json*** file in your project root directory
 3. Although Minify is accessible in the packagist repository, this fork is not, so you have to put these lines in your ***composer.json*** file:


    {
        "repositories": [
            {
                "name": "minify/minify",
                "type": "git",
                "url": "https://github.com/tivie/minify.git"
            }
        ],
        "require": {
            "minify/minify": "2.1.5"
        }
    }

 4. Then run (again in your project root directory) `php composer.phar install`


**Zipped Download:**

You can also download **Minify** zipped directly from github, but this package is prepared for Composer Autoload. 


----------


Configuration & Usage
---------------------

See the MIN.txt file and [http://code.google.com/p/minify/wiki/UserGuide][6]

Minify also comes with a URI Builder application that can help you write URLs
for use with Minify or configure groups of files. See here for details:

[http://code.google.com/p/minify/wiki/BuilderApp][7]

The cookbook also provides some more advanced options for magnification:

[http://code.google.com/p/minify/wiki/CookBook][8]


----------


Upgrading
---------

See UPGRADING.txt for instructions.



Unit Testing
------------

1. Place the /min_unit_tests/ directory as a child of your DOCUMENT_ROOT 
directory: i.e. you will have: */home/example/www/min\_unit\_tests*

2. To run unit tests, access: *http://example.org/min\_unit\_tests/test_all.php*

(If you wish, the other test_*.php files can be run to test individual
components with more verbose output.)

3. Remove */min\_unit\_tests/* from your DOCUMENT_ROOT when you are done.


----------


File Encodings
--------------

Minify *should* work fine with files encoded in UTF-8 or other 8-bit 
encodings like ISO 8859/Windows-1252. By default Minify appends
";charset=utf-8" to the Content-Type headers it sends. 

Leading UTF-8 BOMs are stripped from all sources to prevent 
duplication in output files, and files are converted to Unix newlines.


  [1]: http://code.google.com/p/minify/
  [2]: http://wordpress.org/extend/plugins/bwp-minify/
  [3]: http://wordpress.org/extend/plugins/w3-total-cache/
  [4]: http://getcomposer.org/doc/00-intro.md
  [5]: http://getcomposer.org/download/
  [6]: http://code.google.com/p/minify/wiki/UserGuide
  [7]: http://code.google.com/p/minify/wiki/BuilderApp
  [8]: http://code.google.com/p/minify/wiki/CookBook