#Organizing Theme Files

While WordPress themes technically only require two files (`index.php` and `style.css`), they usually are made up of many files. That means they can quickly become disorganized! This section will show you how to keep your files organized.

##Theme folder and file structure

As mentioned previously, the default Twenty themes are some of the best examples of good theme development. For instance, here is how the [Twenty Twelve theme](https://wordpress.org/themes/twentytwelve/) organizes its [file structure](https://core.trac.wordpress.org/browser/trunk/src/wp-content/themes/twentytwelve):

```
css (dir)
inc (dir)
js (dir)
languages (dir)
page-templates (dir)
404.php
archive.php
author.php
category.php
comments.php
content.php
content-aside.php
content-image.php
content-link.php
content-none.php
content-page.php
content-quote.php
content-status.php
editor-style-rtl.css
editor-style.css
footer.php
functions.php
header.php
image.php
index.php
page.php
rtl.css
screenshot.png
search.php
sidebar.php
sidebar-front.php
single.php
style.css
tag.php
```

You can see that the main theme template files are in the root directory, while JavaScript, languages, CSS, and page template files are placed in their own folders.

At this time there are **no required folders within a WordPress theme**. However, WordPress does recognize the following folders by default.

##Page templates folder

Custom page templates have their own directory, `page-templates`, which allows for better organization of page template files. Custom page templates are page templates that can be applied to individual pages to change their design and layout (more on those later!) Custom page templates in this folder are automatically recognized by WordPress.

##Languages folder

It’s best practice to internationalize your theme so it can be translated into other languages. Default themes include the `languages` folder, which contains a .pot file for translation and any translated .mo files. While `languages` is the default name of this folder, you can change the name. If you do so, you must update [load_theme_textdomain()](https://developer.wordpress.org/reference/functions/load_theme_textdomain/).