---
layout: coding_post
title: Add favicon to a Jekyll site
category: [Coding]
tags: [jekyll, favicon, web]
description: 
unsplash: ncIKFAWcE2k
---



![result](/assets/images/posts/favicon-in-jekyll/favicon_darkato42.png)

## 1. Create favicon using online tools

It’s very easy to create a simple favicon asset using [favicon.io](https://favicon.io) or [websiteplanet's favicon generator](https://www.websiteplanet.com/webtools/favicon-generator/).

## 2. Unzip the package and rename the chosen file

![favicon_io](/assets/images/posts/favicon-in-jekyll/favicon_io.png)

Rename `favicon-32x32.png` to `favicon.png` and copy the file into root folder of your Jekyll repository.

## 3. Add a link tag in the head.html

Add `<link rel="shortcut icon" type="image/png" href="favicon.png">`

into `./_includes/head.html`

```html
{% raw %}
<head>
	<title>{% if page.title %}{{ page.title }} | {% endif %}{{ site.title }}</title>
	<meta charset="utf-8" />
	<meta name="viewport" content="width=device-width, initial-scale=1, user-scalable=no" />
	<!--[if lte IE 8]><script src="{{ "assets/js/ie/html5shiv.js" | relative_url }}"></script><![endif]-->
	<link rel="stylesheet" href="{{ "assets/css/main.css" | relative_url }}" />
	<!--[if lte IE 9]><link rel="stylesheet" href="{{ "assets/css/ie9.css" | relative_url }}" /><![endif]-->
	<!--[if lte IE 8]><link rel="stylesheet" href="{{ "assets/css/ie8.css" | relative_url }}" /><![endif]-->
	<link rel="shortcut icon" type="image/png" href="favicon.png">
</head>
{% endraw %}
```

`head.html` is likely being used in all your html layouts similar to the below.

```html
{% raw %}
<!DOCTYPE html>
<html>

{% include head.html %}

<body>

	{% include header.html %}

	<!-- Main -->
	<div id="main" class="alt">

		<!-- One -->
		<section id="one">
			<div class="inner">
				<header class="major">
					<h1>{{ page.title }}</h1>
				</header>
				<blockquote>
					<p>{{ page.description}}</p>
				</blockquote>

				{{ content }}
			</div>
		</section>

	</div>

	{% include footer.html %}

</body>

</html>
{% endraw %}
```