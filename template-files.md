#Template Files

Template files are used throughout WordPress themes, but first let’s learn about the terminology.

##Template Terminology

The term “template” is used in different ways when working with WordPress themes:

- Templates files exist within a theme and express how your site is displayed.
- Page Templates are a templates that are applied only to pages to change their look and feel.  A page template can be applied to a single page, a page section, or a class of pages.
- Template Tags are built-in WordPress functions you can use inside a template file to retrieve and display data (such as [the_title()](https://developer.wordpress.org/reference/functions/the_title/) and [the_content()](https://developer.wordpress.org/reference/functions/the_content/)).
- Template Hierarchy is the logic WordPress uses to decide which theme template file(s) to use, depending on the content being requested.

##Template files #

WordPress themes are made up of template files. These are PHP files that contain a mixture of HTML, Template Tags, and PHP code.

When you are building your theme, you will use template files to affect the layout and design of different parts of your website. For example, you would use the `header.php` template to create a header, or the `comments.php` template to include comments.

When someone visits a page on your website, WordPress loads a template based on the request. The Template Hierarchy describes which template file WordPress will load based on the type of request and whether the template exists in the theme. The server then parses the PHP in the template and returns HTML to the visitor.

The most critical template file is `index.php`, which is the catch-all template if no more specific template can be found up the template hierarchy.

Although a theme only needs an `index.php` template, typically a theme will include numerous templates to different the display of content types and context.

##Template partials

A template partial is a section of a template that is included as a part of another template, such as a site header. They can be embedded in multiple templates, and simplify theme authoring by separating concerns. Template partials common in a themes are

- `header.php` for generating the site’s header
- `footer.php` for generating the footer
- `sidebar.php` for generating the sidebar

While the above PHP template files apply to one section of a page, templates are also used to control how different types of content are displayed on your website.

##Common WordPress template files

Below is a list of some basic theme templates and files recognized by WordPress.

- **index.php** The main template file. It is required in all themes.
- **style.css** The main stylesheet. It is required in all themes and contains the information header for your theme.
- **rtl.css** The right-to-left stylesheet is included automatically if the website language’s text direction is right-to-left.
- **comments.php** The comments template.
- **front-page.php** The front page template is loaded if a static front page is specified under Admin > Settings > Reading.
- **home.php** The home page template is the front page by default. If you do not set WordPress to use a static front page, this template is used to show latest posts.
- **header.php** The header template file usually contains your site’s document type, meta information, links to stylesheets and scripts, and other data.
- **single.php** The single post template is used when a visitor requests a single post. For this, and all other query templates, `index.php` is used if the query template is not present.
- **single-{post-type}.php** The single post template used when a visitor requests a single post from a custom post type. For example, single-book.php would be used for displaying single posts from a custom post type named book. The `index.php` is used if a specific query template for the custom post type is not present.
- **archive-{post-type}.php** The archive post type template is used when visitors request a custom post type archive. For example, archive-books.php would be used for displaying an archive of posts from the custom post type named books. The `archive.php` template file is used if the `archive-{post-type}.php` is not present.
- **page.php** The page template is used when visitors request individual pages, which are a built-in template.
- **page-{slug}.php** The page slug template is used when visitors request a specific page, for example one with the “about” slug (page-about.php).
- **category.php** The category template is used when visitors request posts by category.
- **tag.php** The tag template is used when visitors request posts by tag.
- **taxonomy.php** The taxonomy term template is used when a visitor requests a term in a custom taxonomy.
- **author.php** The author page template is used whenever a visitor loads an author page.
- **date.php** The date/time template is used when posts are requested by date or time. For example, the pages generated with these slugs: `http://example.com/blog/2014/, http://example.com/blog/2014/05/, http://example.com/blog/2014/05/2`6/
- **archive.php** The archive template is used when visitors request posts by category, author, or date. Note: this template will be overridden if more specific templates are present like `category.php`, `author.php`, and `date.php`.
- **search.php** The search results template is used to display a visitor’s search results.
- **attachment.php** The attachment template is used when viewing a single attachment like an image, pdf, or other media file.
- **image.php** The image attachment template is a more specific version of `attachment.php` and is used when viewing a single image attachment. If not present, WordPress will use `attachment.php` instead.
- **404.php** The 404 template is used when WordPress cannot find a post, page, or other content that matches the visitor’s request.

##Using template files

Within WordPress templates, you can use Template Tags to display information dynamically, include other template files, or otherwise customize your site.

For example, in your `index.php` you can include other files in your final generated page:

- To include the header, use [get_header()](https://developer.wordpress.org/reference/functions/get_header/)
- To include the sidebar, use [get_sidebar()](https://developer.wordpress.org/reference/functions/get_sidebar/)
- To include the footer, use [get_footer()](https://developer.wordpress.org/reference/functions/get_footer/)
- To include the search form, use [get_search_form()](https://developer.wordpress.org/reference/functions/get_search_form/)
- To include custom theme files, use [get_template_part()](https://developer.wordpress.org/reference/functions/get_template_part/)

Here is an example of WordPress template tags to include specific templates into your page:

```php
<?php get_sidebar(); ?>
<?php get_template_part( 'featured-content' ); ?>
<?php get_footer(); ?>
```