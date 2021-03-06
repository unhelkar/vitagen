# vitagen
A web application to easily, flexibly, and incrementally develop a CV that is viewable from the web, a mobile device, and optimized for printing.

# Introduction #

The following are the basic steps to get started with vitagen:
  1. Check out the trunk to a PHP-enabled directory
  1. Copy-paste `index.inc.php.default` to `index.inc.php`
  1. Edit `index.inc.php` to customize your page

Vitagen imposes relatively light requirements, detailed below.

## User Information ##

First, uncomment and fill in details for the `$user` array. You will see how this changes the page title and header. There are optional features for LinkedIn, Flickr, and Google Analytics if you so choose (otherwise leave them commented/null). You can refer to the top of the `index.php` file to see how the default information is populated/used.

The `tabs` array and `handler` string setup the page tabs and callback function to implement the tab content. The keys of the `tabs` array will be sent to the callback function to identify the tab, whereas the value will title the tab. If there is only one value in this array, no tabs will be visible. The `handler` function should accept an `id` (key from the `tabs` array) and a `prefix` string to prepend to each line of outputted code (optional: just makes the resulting HTML nicer). Again, look to the top of the `index.php` file to see how the default page was generated, including a sample set of `tabs` and `handler`.

## Useful Functions ##

The `handler` can output any tab content. However, a couple functions are provided to facilitate fast content development and improve aesthetic consistency. The first is `misc_section`, which takes as parameters a section title (string), content (string), and prefix for each line (string), and will produce a nicely formatted section. The second is `misc_list`, which takes as parameters an array of strings and, optionally, a prefix string, and produces a bulleted list.

Feel free to implement your own utility functions within the `index.inc.php` file.

## Misc ##

The `svn:ignore` property has been set to facilitate certain patterns in the main directory. First, all PDFs are ignored, as well as the `.project` file (to help Eclipse users). The `index.inc.php` file is also ignored, such that you can make all the changes you want. Finally, an `ignore` directory can be optionally added to shield additional content from change detection. The intent is to allow users to customize the site and keep the source up to date without too much interference/hassle.
