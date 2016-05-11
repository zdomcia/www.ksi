# www.ksi
New website of KSI UJ  - basic jekyll version v1 - it's located in jekyll/ folder

## Code of Conduct
* If you are forbidden by local authorities to touch UX/UI  * do not commit anything related to it (only backend code or content).
* SASS is used here.
* Do not use raw html if not necessary in text body.

## General Instructions
* RTFM of Jekyll -> [https://jekyllrb.com/docs/home/](https://jekyllrb.com/docs/home/)
* Learn Markdown (kramdown flavour, not github's one) -> [https://daringfireball.net/projects/markdown/basics](https://daringfireball.net/projects/markdown/basics)

### How to add post
1. Create file _posts/YYYY-MM-DD-some-super-fancy-title.markdown where YYYY is year, MM - month and DD - date; some-super-fancy-title should not have spaces (dashes are preferred) and should easily tell you what is content of that file, though this won't be used anywhere
2. Fill it with content using template below:
```
---
layout:	halfpage
title:	Biblioteka KSI zaprasza
date:	   2015-01-01 12:14:29
post_img_url: https://fbcdn-sphotos-g-a.akamaihd.net/hphotos-ak-xfa1/t31.0-8/12492032_1083729518327483_2672522444431790535_o.jpg
language: pl
---
Zapraszamy do korzystania z naszej biblioteki. Przyjmujemy także książki związane z informatyką/matematyką (ale nie przynoście nam dokumentacji Turbo Pascala 4.0).

[Katalog online](http://erc.ksi.ii.uj.edu.pl/ksiegozbior)
```

   * do not change ```layout``` declaration
   * ```title``` is what will be displayed in ```<title>``` tag, header in articles list and of course in that's post page
   * ```date``` should match one from filename; if you are lazy you can leave time as-is but it's used for sorting newest to oldest so be  careful
   * ```post_img_url``` is image URL (either relative or absolute - can be full whith http://) related to post - it looks nice in articles list and adds some colors to post view, but you can ommit  line or simply leave it without any content
   * ```language``` is language; if this field is ommited bad things happen!
   * Add your elaborate text after second ```---```
   * First paragraph of text will be post's excerpt (sometimes called lead) - it should be short as it's displayed in articles list as invitation to read more.

To divide article text into paragraphs use empty line.

### How to add static page (as if jekyll generates anything dynamic in end-user terms)
1. Create file some-super-fancy-title.md where; some-super-fancy-title should not have spaces (dashes are preferred) and should easily tell you what is content of that file, if no ```permalink``` is specified that page will be accessible as /some-super-fancy-title.html
2. Fill it with content using template below:
```
---
layout:		halfpage
permalink:	/about/
title:		O KSI
excerpt:	Kilka słów o naszym Kole
---
lorem ipsum dolor sit amet
```

   * do not change ```layout``` declaration
   * ```title``` is what will be displayed in ```<title>``` tag, header in articles list and of course in that's post page
   * ```permalink``` is nice URL for page; in this project we use english names for main pages like about, projects etc.
   * ```excerpt``` - unlike in posts you ahve to manually define excerpt because it's used in different purpose - it's displayed below  huge title in page view - it can be different from first paragraph, preferably descriptive about page content so there won't be  "tl;dr" reaction
   * Add your elaborate text after second ```---```

You can use .HTML instead of .md but first method is preferred - you can still embed html code in md if really needed - just use ```<div> html content </div>```

### How to add gallery to post
1. Put photos in some folder (eg. photos/gallery1)
2. Add following text to body of post/page
```
{% image_set path/to/directory %}
````