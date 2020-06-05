---
layout: post
title:  Template Post
date:   2020-06-01
updated: 2020-06-01
categories: bioinformatics
permalink: /bioinformatics/Template-Post
toclink: /OCMS-blog/bioinformatics/Template-Post
author: Your Name
contributors: Other Authors or Contributors
excerpt_separator: <!--more-->

postid: bioin_00x
---

## Executive Summary
All posts will start with an executive summary. This is a
brief (1-2 paragraphs) summary of findings from the report and any findings/actionables/recommendations that stem from the study. The executive summary will be the excerpt of the post shown when listing all posts.

<!--more-->

## Front matter

The section at the very top, also called front matter, contains instructions on how the post is incorporated into the blog. You can ignore most of the tags in the front matter, but please update the following:

* title
* date
* updated
* author
* contributors
* categories

Note that categories _must_ be one of the following, depending on the type of content you are creating:
* `white_paper`
* `bioinformatics`
* `training`

The markdown code used to generate this template post can be found at the bottom of this post. [mdpost](#mdpost)
## Section Title

Add any sections and text. Generally, lab report style of Intro, Objective, Methods, Results/Discussion Conclusion works well. Keep in mind that this is an outward facing platform, where readers are likely current and prospective client/collaborators. We will try to keep content targeted to a generic scientific audience.

### Subheading

The title of the post is automatically the top header. Subsequent headers are marked by using `#`. Lower levels of section headers are marked with addional `#`s. You can **bold text**, _italicise text_, embed `in-text code`.

Code blocks can also be made in the markdown, with syntax highlighted to your language of choice:

{% highlight R %}
my_function <- function(d) {
    # do something with data, d
    out_df <- apply(d, 2, function(x) x^2/x)
    return(out_df)
}
{% endhighlight %}

Bullet points are made with `*`:
* first bullet point
* second bullet point

You can embed links in text with a variable and define the link at the bottom of the page. For example [this link][thislink] is to the OCMS blog home page.

You can insert figures are reference those figures in text by placing an anchor in the text and assign an anchor to your figure ([Figure 1](#figure_anchor_label)). In the place where you want your figure to be placed, follow the syntax below, where you give a figure label and the name of the figure file. Don't worry about the path to the file (all images will go in `_/assets/images`). That will need to be updated once the post in put in the blog. Figures should be in `.jpeg` or `.png` format.

<a name="figure_anchor_label"></a>
![figure_label]({{ site.baseurl }}/assets/images/beaker.jpg)
<br>
**Figure 1. Give a figure caption in bold**

You can insert a table:
1. save your data as csv file with no spaces in the file name. Data files will be stored in `_data` in blog directory.
2. replace `mytable` in the code below with the name of your csv file (no extension).
3. Similar to linking to figures, you can give your table an anchor to create a link to [your table](#mytable_anchor).

<a name="mytable_anchor"></a>
**Table 1. caption describing table**
<table>
  {% for row in site.data.mytable %}
    {% if forloop.first %}
    <tr>
      {% for pair in row %}
        <th>{{ pair[0] }}</th>
      {% endfor %}
    </tr>
    {% endif %}
    {% tablerow pair in row %}
      {{ pair[1] }}
    {% endtablerow %}
  {% endfor %}
</table>

<!-- link definition -->
[thislink]: https://oxfordcms.github.io/OCMS-blog/

## Submitting your blog post
Once you have written your blog as a markdown file (`.md`), email Sandi your blog file and all associated figure and table files. Blog contributors will be featured on the home page :)

## Template Markdown Code<a name="mdcode"></a>

{% highlight markdown %}
---
layout: post
title:  Template Post
date:   2020-06-01
updated: 2020-06-01
categories: bioinformatics
permalink: /bioinformatics/Template-Post
toclink: /OCMS-blog/bioinformatics/Template-Post
author: Your Name
contributors: Other Authors or Contributors
excerpt_separator: <!--more-->

postid: bioin_00x
---

## Executive Summary
This post serves as an example and how-to on how to write a markdown file and how to create a blog post on the OCMS blog.

All posts will start with an executive summary. This is a
brief (1-2 paragraphs) summary of findings from the report and any findings/actionables/recommendations that stem from the study. The executive summary will be the excerpt of the post shown when listing all posts.

<!--more-->

## Front matter

The section at the very top, also called front matter, contains instructions on how the post is incorporated into the blog. You can ignore most of the tags in the front matter, but please update the following:

* title
* date
* updated
* author
* contributors
* categories

Note that categories _must_ be one of the following, depending on the type of content you are creating:
* `white_paper`
* `bioinformatics`
* `training`

The markdown code used to generate this template post can be found at the bottom of this post. [mdpost](#mdpost)
## Section Title

Add any sections and text. Generally, lab report style of Intro, Objective, Methods, Results/Discussion Conclusion works well. Keep in mind that this is an outward facing platform, where readers are likely current and prospective client/collaborators. We will try to keep content targeted to a generic scientific audience.

### Subheading

The title of the post is automatically the top header. Subsequent headers are marked by using `#`. Lower levels of section headers are marked with addional `#`s. You can **bold text**, _italicise text_, embed `in-text code`.

Code blocks can also be made in the markdown, with syntax highlighted to your language of choice:

{% highlight R %}
my_function <- function(d) {
    # do something with data, d
    out_df <- apply(d, 2, function(x) x^2/x)
    return(out_df)
}
{% endhighlight %}

Bullet points are made with `*`:
* first bullet point
* second bullet point

You can embed links in text with a variable and define the link at the bottom of the page. For example [this link][thislink] is to the OCMS blog home page.

You can insert figures are reference those figures in text by placing an anchor in the text and assign an anchor to your figure ([Figure 1](#figure_anchor_label)). In the place where you want your figure to be placed, follow the syntax below, where you give a figure label and the name of the figure file. Don't worry about the path to the file (all images will go in `_/assets/images`). That will need to be updated once the post in put in the blog. Figures should be in `.jpeg` or `.png` format.

<a name="figure_anchor_label"></a>
![figure_label]({{ site.baseurl }}/assets/images/beaker.jpg)
<br>
**Figure 1. Give a figure caption in bold**

You can insert a table:
1. save your data as csv file with no spaces in the file name. Data files will be stored in `_data` in blog directory.
2. replace `mytable` in the code below with the name of your csv file (no extension).
3. Similar to linking to figures, you can give your table an anchor to create a link to [your table](#mytable_anchor).

<a name="mytable_anchor"></a>
**Table 1. caption describing table**
<table>
  {% for row in site.data.mytable %}
    {% if forloop.first %}
    <tr>
      {% for pair in row %}
        <th>{{ pair[0] }}</th>
      {% endfor %}
    </tr>
    {% endif %}
    {% tablerow pair in row %}
      {{ pair[1] }}
    {% endtablerow %}
  {% endfor %}
</table>

<!-- link definition -->
[thislink]: https://oxfordcms.github.io/OCMS-blog/

## Submitting your blog post
Once you have written your blog as a markdown file (`.md`), email Sandi your blog file and all associated figure and table files. Blog contributors will be featured on the home page :)

{% endhighlight %}
