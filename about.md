---
layout: page
title: About
permalink: /about/
---

Jekyll-theme-space is my new Jekyll theme for my [blog (in spanish)](https://son-link.github.io)

This theme is lighwight and responsive, this last include tables, images, videos and iframe videos, like **Youtube** and **Vimeo**

Include support for jekyll-seo-tag, Google Analytics and Disqus for comments, and include links on any post for share on various social networks, WhatsApp and Telegram. And support too categories and tags.

## Installation

Add this lines to your Jekyll site's `Gemfile`:

```ruby
gem "jekyll-theme-space"
gem "jekyll-paginator" # This line isn't necessary if you use github-pages
gem "jekyll-seo-tag" # If you can use this plugin
```

Add this lines to your Jekyll site's `_config.yml`:

```yaml
theme: jekyll-simple-dark
plugins:
- jekyll-paginate
- jekyll-seo-tag #if you use this.
paginate: 5 # Posts per page
paginate_path: "page:num/"
```

Rename **index.md** to **index.html** and change **layout** to *home*

For search create a new file on the site root foolder called **search.json** with this content:

```json
---
---
[
  {% for post in site.posts %}
    {

      "title"    : "{{ post.title | strip_html | escape }}",
      "url"      : "{{ site.baseurl }}{{ post.url }}",
      "category" : "{{post.categories | join: ', '}}",
      "tags"     : "{{ post.tags | join: ', ' }}",
      "date"     : "{{ post.date }}",
      "description" : "{{post.description | strip_html | strip_newlines | escape }}"

    } {% unless forloop.last %},{% endunless %}
  {% endfor %}
]
```
**Note**: You can change post.description to post.content, but innsert description is much better, use post.content only create a big file and also inaccurate search result.

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install jekyll-theme-space

## Usage

### Social links:

For activate social links add these lines on your _config.yml:

```yaml
social_links: true  # If true show social links
rss: true # For add icon to link feed.xml
facebook:
github:
gplus:
instagram:
linkedin:
pinterest:
twitter:
vimeo:
youtube:
```
Just add the ones you're going to use.

**Note:** gplus is for Google+ link.

### Responsive iframe for Youtube or Vimeo videos:

Insert the iframe code into a div whit the class **video** and remove **width** and **height** attributes, like this:

```html
<div class="video">
  <iframe  src="https://www.youtube.com/embed/<videoID>" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
</div>
```

### Google Analytics:
For use Google Analytics include this line  on **_config.yml** and replace &lt;code> for your Google Analytics code:

```yaml
google-analytics: <code>
```
Where &lt;code> is your Google Analytics code.

### jekyll-seo-tag:
For use you only need add this plugin on the plugins array on **_config.yml**

### categories and tags pages:
Simple create a new file on the root and set categories as layout. Same for tags.
For add simple add these variables on YAML head of post. For example:

```yaml
category: Jekyll
tags:
- jekyll
- tutorial
```

### Exclude pages on menu:
If you do not want a page to appear in the menu, simply add this is the YAML header on the desired pages:

### Related posts:
include this in **_config.yml**

```yaml
related_post: true
```

```yaml
onmenu: false
```

### Custom 404 page error:
For add custom 404 page create a new page in your site root folder called **404.md** or **404.html** start width this yaml head:

```yaml
---
layout: 404
permalink: /404.html
---
```

## Other credits:
* [normalize.css](http://necolas.github.io/normalize.css/) use for reset default styles on browsers.
* [Fontello](http://fontello.com/) for make the icon font.
* [Simple-Jekyll-Search](https://github.com/christian-fei/Simple-Jekyll-Search) for search. Thans to [Webjeda](https://blog.webjeda.com/instant-jekyll-search/) for the tutorial.
* [Exo](https://fonts.google.com/specimen/Exo) as the default font.
* Monokai for highlight thakns to [https://github.com/richleland/pygments-css](https://github.com/richleland/pygments-css)
* Background image is [donwload from here](https://pxhere.com/es/photo/114960)

## License

The theme is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).
