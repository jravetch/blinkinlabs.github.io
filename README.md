# This is the data for the Blinkinlabs Website

It is automatically transformed by [Jekyll](http://github.com/mojombo/jekyll) using the included `./publish.sh` script.


# License

The following directories and their contents are Copyright Blinkinlabs. You may not reuse anything therein without my permission:

* Any directory with `_posts` in the name.
* `images/`

All other directories and files are MIT Licensed. Feel free to use the HTML and CSS as you please. If you do use them, a link back to http://github.com/blinkinlabs/blinkinlabs.github.io would be appreciated, but is not required.

----

# Setup

Jekyll is built on Ruby. You'll need Ruby version 1.9.3 or greater.

It is recommended that you use a Ruby manager such as [rbenv](https://github.com/sstephenson/rbenv) or [rvm](http://rvm.io/).

If you opt not to use a Ruby manager, you may need to install the `bundler` gem:

	$ gem install bundler

You'll also need [git](http://git-scm.com/). Probably some other things.

## Clone the Repository

	$ git clone git@github.com:blinkinlabs/blinkinlabs.github.io.git

From now on, you'll be working within the `blinkinlabs.github.io/` directory.

	$ cd blinkinlabs.github.io

You should be on the `source` branch. You can verify this like so:

	$ git status
	# On branch source
	# Everything is up to date.
	$

## Install Dependencies

	$ bundle install

----

# Running the Site Locally

You'll want to see your changes as you work on the site. You can have Jekyll run
a local server with your version of the site very easily:

	$ jekyll serve --watch

You'll then be able to see the site by pointing your browser at http://localhost:4000/

----

# Making a new Blog Post

## Blog Post Files

Blog posts go in `blog/_posts/` and they must have a date in the file name. For example:

	blog/_posts/2013-03-19-tiny-led-controller.md

A `.md` extension indicates that the contents of the post will be in Markdown format.

## YAML Front Matter

Each blog post has a section of YAML at the top describing some important information.

Here's an example.

	---
	layout: post
	category: post
	author: Matt Mets
	title: Tiny LED Controller and the Cheapest Buttons, Ever
	img: blog/2013-03-19-tiny-led-controller
	preview: led1-preview-2up.jpg
	---

Let's break this down.

* `layout: post` - This indicates which layout to wrap this content in. All blog
posts use the `post` layout.
* `category: post` - This indicates that this file contains a blog post.
* `author: Matt Mets` - The byline that will appear on the post.
* `title: Tiny LED ...` - The title of the post.
* `img: blog/...` - The subdirectory under `images/` where you will place images
for this post.
* `preview: foo.jpg` - The file in the "`img`" directory to use when this post
appears on the front page of the site. The image should be 500x300px.

### Images

Create a subdirectory for images for you blog post under `images/blog/`. For example: `images/blog/YYYY-MM-DD-blog-post-short-name/`.

Make sure you set `img:` to `blog/YYYY-MM-DD-blog-post-short-name` in the post's
YAML front matter.

With this done, you can put image files in the directory that you created, and
include them in your posts with:

	![Alt Text](/images/{{page.img}}/filename.jpg)

That's pretty much it.

----

# Creating new Pages

Our page management is pretty gross and kind of all over the place. Here are
some basic guidelines.

* If there's already a page that is kind of like what you want, copy all the
things that it does.
	* For example, the `installations.md` file describes the `http://blinkinlabs.com/installations/` page.
* You can put raw HTML in your markdown files for complex styling goodness.
	* We use an older version (v3?) of [Zurb's Foundation](http://foundation.zurb.com/).
	* This is supposed to let you easily style things just by using the right
	markup.
	* The reality is a bit different.
* Images should go in `images/my-page-name/`, and `img:` should be set to match in the front matter for the page.
* Use `layout: project` for two-column pages with the sidebar. Use `layout: docs`
for no sidebar.

# Custom CSS

Put it in `stylesheets/web.css`.

# Publishing!

You'll need push permissions on the repo at git@github.com:blinkinlabs/blinkinlabs.github.io.

Assuming you've got your git SSH stuff configured correctly, you should only
need to run a single script:

	$ ./publish.sh

This will render out the site to a temporary directory, the replace the `master`
branch in the git repository with the contents of the static site.

----

# TODOs

* Put images on an asset host like S3 instead of keeping them in the git repo.
* Fix pagination on `/blog/`. It is broken because we store things wrong.
* The main BlinkyTape page should get some love in the form of fancy styling and
images instead of acting like a long form content page.
* Lots of old projects should be moved to the blog section.
* ???
