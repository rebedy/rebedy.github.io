---
layout: post
date: 2024-06-01
title: "GitHub Blog [4]: Managing"
tags: [blog, ]
categories: [GitHub, ]
---



## Prerequisites


---


[Github Blog [1]: Using Jekyll](https://rebedy.github.io/posts/Github-Blog-1-Using-Jekyll/)


[GitHub Blog [2]: Customizing](https://rebedy.github.io/posts/GitHub-Blog-2-Customizing/)



## [**Google Search Console**](https://search.google.com/search-console/about?hl=ko&utm_source=wmx&utm_medium=wmx-welcome)


---


A device that allows your blog posts to appear when searched on Google


![0](/assets/img/2024-06-01-GitHub-Blog-[4]:-Managing.md/0.png)



#### Step 1. Add your site


![1](/assets/img/2024-06-01-GitHub-Blog-[4]:-Managing.md/1.png)



#### Step 2. Download HTML file


Download the HTML file and place it in where the `Gemfile` is. And commit and push the repo.


![2](/assets/img/2024-06-01-GitHub-Blog-[4]:-Managing.md/2.png)



#### Step 3. Edit `Gemfile`


Add the code line below at the very last in the `Gemfile`



{% raw %}
```text
gem 'jekyll-sitemap'
```
{% endraw %}



And run the command below.



{% raw %}
```bash
bundle install
```
{% endraw %}




#### Step 4. sitemap.xml


Run local server and then go to [http://localhost:4000/sitemap.xml](http://localhost:4000/sitemap.xml).



{% raw %}
```bash
 jekyll serve
```
{% endraw %}



You will see a page written in XML. Copy it and make a `sitemap.xml` in where the `Gemfile` is.


…


OR


…


you also can just copy the XML code below to the `sitemap.xml` . Oh but you need to change the blog address part.



{% raw %}
```xml
---
layout: null
---
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.sitemaps.org/schemas/sitemap/0.9 http://www.sitemaps.org/schemas/sitemap/0.9/sitemap.xsd" xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
<url>
  <loc>https://rebedy.github.io/</loc>
  <lastmod>2024-05-29T08:34:20+00:00</lastmod>
  <priority>1.00</priority>
</url>
<url>
  <loc>https://rebedy.github.io/about/</loc>
  <lastmod>2024-05-29T08:34:20+00:00</lastmod>
  <priority>0.80</priority>
</url>
  {% for post in site.posts %}
    <url>
      <loc>{{ site.url }}{{ post.url }}</loc>
      {% if post.last_modified_at == null %}
        <lastmod>{{ post.date | date_to_xmlschema }}</lastmod>
      {% else %}
        <lastmod>{{ post.last_modified_at | date_to_xmlschema }}</lastmod>
      {% endif %}

      {% if post.sitemap.changefreq == null %}
        <changefreq>weekly</changefreq>
      {% else %}
        <changefreq>{{ post.sitemap.changefreq }}</changefreq>
      {% endif %}

      {% if post.sitemap.priority == null %}
        <priority>0.5</priority>
      {% else %}
        <priority>{{ post.sitemap.priority }}</priority>
      {% endif %}
    </url>
  {% endfor %}
</urlset>
```
{% endraw %}



…


OR


…


you also can visit sites generate `sitemap.xml` for you!


[https://www.xml-sitemaps.com/](https://www.xml-sitemaps.com/)



#### Step 5. robots.txt


Copy the code below and make a `robots.txt` file where the `Gemfile` and the `sitemap.xml` is.



{% raw %}
```text
User-agent: *
Allow: /

Sitemap: https://rebedy.github.io/sitemap.xml
```
{% endraw %}



Of course you gotta change the blog address!


And commit/push!



#### Step 6. Add new Sitemaps on the [Google Search Console](https://search.google.com/search-console)


![3](/assets/img/2024-06-01-GitHub-Blog-[4]:-Managing.md/3.png)


Within 7 days, your blog will be exposed on the search engine.



## [**Google Analytics**](https://analytics.google.com/analytics/web/#/)


---


It is a tool that analyzes various factors such as who accessed my blog, when, where, and how much.


![4](/assets/img/2024-06-01-GitHub-Blog-[4]:-Managing.md/4.png)



#### Step 1. Start


Press ‘start’ button and make a name for the account. And then leave other things as default.


Since the Google Analytics upgraded their service from Universal Analytics to GA4, things are much simple and easier.


![5](/assets/img/2024-06-01-GitHub-Blog-[4]:-Managing.md/5.png)



#### Step 2. Make new attribute

1. (Mandatory) Attribute name: yours
2. Time for the analytics: Kor
3. Currency: $ (can be anything)

![6](/assets/img/2024-06-01-GitHub-Blog-[4]:-Managing.md/6.png)



#### Step 3. Details for your Analytics


Since this is just for your blog (not some kind of serious business😂), the size of the business will be the smallest one and the category of the business will be etc.


Same with ‘the purpose of business’. Choose anything you like for the 4th step.


![7](/assets/img/2024-06-01-GitHub-Blog-[4]:-Managing.md/7.png)


![8](/assets/img/2024-06-01-GitHub-Blog-[4]:-Managing.md/8.png)


And agree to the GDR.


![9](/assets/img/2024-06-01-GitHub-Blog-[4]:-Managing.md/9.png)



#### Step 4. Measurement ID to `_config.yml`

- **How to get there?**

‘Manage' > ‘Attribute Setting’ > ‘Data Collection and Edit’ > ‘Data Stream’ > Choose your stream > ‘Stream Details’ > ‘Measurement ID’


![10](/assets/img/2024-06-01-GitHub-Blog-[4]:-Managing.md/10.png)

- `_config.yml`


{% raw %}
```yaml
# Web Analytics Settings
analytics:
  google:
    id: G-xxxxxxxxxx # fill in your Google Analytics ID
```
{% endraw %}



Again, since the Google Analytics upgraded their service from Universal Analytics to GA4, your measurement ID is also starts with `G` not `UA`.



## [**Google Adsense**](https://www.google.com/adsense/new/u/0/pub-2215052066308993/onboarding)


---


A tool that generates revenue through advertising and allows you to earn advertising fees.


![11](/assets/img/2024-06-01-GitHub-Blog-[4]:-Managing.md/11.png)



#### Step 1. Sign up 


After accessing the site and sign up using your blog’s URL and email address and so on. The region should be where you live and agree to the terms and conditions.


Register a profile in order to receive payments. Enter personal information such as address and contact information.



#### Step 2. Apply Google AdSense code to website


Add code below to the bottom of `_includes/head.html`.



{% raw %}
```html
<!--...-->

  <!-- Google Addsence -->
  <script data-ad-client="ca-pub-8857040748920572" async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
  
</head>
```
{% endraw %}




## References


---

- [https://wlqmffl0102.github.io/posts/Making-Git-blogs-for-beginners-4/](https://wlqmffl0102.github.io/posts/Making-Git-blogs-for-beginners-4/)
