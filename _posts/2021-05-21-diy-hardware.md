---
layout: post
title:  "DIY Laboratory Hardware for the non-engineer in plant sciences"
date:   2021-05-21
excerpt: "Resources to inspire creative problem solving"
project: true
tag:
- DIY 
- maker
- hardware
- hardwareX
- automation
comments: true
---
# DIY Hardware in the Plant Sciences

I hope this website can be a resource for anyone looking into DIY open-source hardware or software for their research. Broadly speaking, my research primarily involves plant sciences and plant pathology; as such, resources found here will initially be focused on hardware and software potentially or currenlty relevant to research in the plant sciences. However, lab hardware and software often transcends disciplines, so I hope you can find useful information regardless of your field. 

* [Peer-reviewed scientific resources](https://github.com/mswiseman/mswiseman.github.io/blob/master/_posts/2021-05-21-diy-hardware.md#peer-reviewed-scienfic-resources)
* [Selected publications](https://github.com/mswiseman/mswiseman.github.io/blob/master/_posts/2021-05-21-diy-hardware.md#selected-publications)
* [Hardware documentation](#hardware-documentation)
    * [Microcontrollers]([#microcontrollers)
    * Stepper drivers
    * Environmental sensors
* Exceptional YouTube tutorials 
* Recommendations on where to purchase components 

## Peer-reviewed scienfic resources
<img align="left" width="100" alt="HardwareX Logo" src="https://raw.githubusercontent.com/mswiseman/mswiseman.github.io/master/assets/img/hardwarexlogo.gif"> [HardwareX](https://www.journals.elsevier.com/hardwarex) is a peer-reviewed open access scientific journal dedicated to the open source design and construction of scientific instrumentation. The journal publishes science hardware shared under an open source hardware license. For DIY hardware, I believe HardwareX has the most detailed manuscripts that enable easier reproducibility. <br clear="left"/><br><br>

<img align="left" width="100" alt="Nature Scientific Reports Logo" src="https://raw.githubusercontent.com/mswiseman/mswiseman.github.io/master/assets/img/ScientificReportsandNatureLogo.png"> [Nature Scientific Reports](https://www.nature.com/srep/) is an open access journal publishing original research from across all areas of the natural sciences, medicine and engineering. To find manuscripts more likely to have DIY hardware, I would explore the tags [*lab-on-a-chip*](https://www.nature.com/search?q=lab-on-a-chip&order=relevance&journal=srep), [*biomedical engineering*](https://www.nature.com/search?q=biomedical%20engineering&order=relevance&journal=srep), or [*mechanical engineering*](https://www.nature.com/search?q=mechanical%20engineering&order=relevance&journal=srep). <br clear="left"/><br><br>

## Selected publications  

[Highly-Customizable 3D Printed Peristaltic Pump Kit](https://www.sciencedirect.com/science/article/pii/S2468067221000316#f0010)<br/>
Keywords: peristaltic pump, fluid handling, cell culture, microfluidics

![Graphical Abstract](https://raw.githubusercontent.com/mswiseman/mswiseman.github.io/master/assets/img/customizable_peristaltic_pump.jpg)
Other HardwareX peristaltic pumps: [Jönsson 2020](https://www.sciencedirect.com/science/article/pii/S2468067220300249), [example2](http://link), [example3](http://link), [example4](http://link)

## Hardware documentation

I've included direct links to the documentation of hardware commonly used in DIY free open source hardware. This field is rapidly evolving, so I imagine this section will change frequently. My last update was on May 21st, 2021. 

### Microcontrollers

### Stepper drivers

### Environmental sensors


{% capture images %}
	https://cloud.githubusercontent.com/assets/754514/14509716/61ac6c8e-01d6-11e6-879f-8308883de790.png
	https://cloud.githubusercontent.com/assets/754514/14509717/61ad05ae-01d6-11e6-85ae-5a817dd8763b.png
	https://cloud.githubusercontent.com/assets/754514/14509714/61a89708-01d6-11e6-8fcd-74b002a060df.png
{% endcapture %}
{% include gallery images=images caption="Screenshots of Moon Theme" cols=3 %}

---

{% capture images %}
	https://cloud.githubusercontent.com/assets/754514/14509718/61b09a20-01d6-11e6-8da1-4202ae4d83cd.png
	https://cloud.githubusercontent.com/assets/754514/14509715/61aa9d00-01d6-11e6-81a6-c6837edf2e84.png
{% endcapture %}
{% include gallery images=images caption="Moon Theme on Small Screen Size" cols=2 %}      
      
See a [live version of Moon](http://taylantatli.github.io/Moon) hosted on GitHub.      

## Site Setup
A quick checklist of the files you’ll want to edit to get up and running.    

### Site Wide Configuration
`_config.yml` is your friend. Open it up and personalize it. Most variables are self explanatory but here's an explanation of each if needed:

#### title

The title of your site... shocker!

Example `title: My Awesome Site`

#### bio

The description to show on your homepage.

#### description

The description to use for meta tags and navigation menu.

#### url

Used to generate absolute urls in `sitemap.xml`, `feed.xml`, and for generating canonical URLs in `<head>`. When developing locally either comment this out or use something like `http://localhost:4000` so all assets load properly. *Don't include a trailing `/`*.

Examples:

{% highlight yaml %}
url: http://taylantatli.me/Moon
url: http://localhost:4000
url: //cooldude.github.io
url:
{% endhighlight %}

#### reading_time

Set true to show reading time for posts. And set `words_per_minute`, default is 200.

#### logo
Your site's logo. It will show on homepage and navigation menu. Also used for twitter meta tags.

#### background
Image for background. If you don't set it, color will be used as a background.

#### Google Analytics and Webmaster Tools

Google Analytics UA and Webmaster Tool verification tags can be entered in `_config.yml`. For more information on obtaining these meta tags check [Google Webmaster Tools](http://support.google.com/webmasters/bin/answer.py?hl=en&answer=35179) and [Bing Webmaster Tools](https://ssl.bing.com/webmaster/configure/verify/ownership) support.

#### MathJax
It's enabled. But if you don't want to use it. Set it false in  `_config.yml`.

#### Disqus Comments
Set your disqus shortname in `_config.yml` to use comments.

---

### Navigation Links

To set what links appear in the top navigation edit `_data/navigation.yml`. Use the following format to set the URL and title for as many links as you'd like. *External links will open in a new window.*

{% highlight yaml %}
- title: Home
  url: /

- title: Blog
  url: /blog/

- title: Projects
  url: /projects/

- title: About
  url: /about/

- title: Moon
  url: http://taylantatli.me/Moon
{% endhighlight %}

---

## Layouts and Content

Moon Theme use [Jekyll Compress](https://github.com/penibelst/jekyll-compress-html) to compress html output. But it can cause errors if you use "linenos" (line numbers). I suggest don't use line numbers for codes, because it won't look good with this theme, also i didn't give a proper style for them. If you insist to use line numbers, just remove `layout: compress` string from layouts. It will disable compressing.

### Feature Image

You can set feature image per post. Just add `feature: some link` to your post's front matter.

```
feature: /assets/img/some-image.png
or
feaure: http://example.com/some-image.png
```    
 This also will be used for twitter card:

![Moon Twitter Card](https://cloud.githubusercontent.com/assets/754514/14509719/61c5751c-01d6-11e6-8c29-ce8ccad149bf.png)

### Comments
To show disqus comments for your post add `comments: true` to your post's front matter.

---

## Questions or comments? 

I'd love for this to be a collaborative process, so please [send me](michele.wiseman@oregonstate.edu) your questions/suggestions/comments or post them to the comments below (let's all be kind humans though, okay?). 

---

## Updated
This page was last updated 05/21/2021.
