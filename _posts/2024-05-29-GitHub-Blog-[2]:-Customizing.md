---
layout: post
date: 2024-05-29
title: "GitHub Blog [2]: Customizing"
tags: [blog, chirpy, github, jekyll, google, ]
categories: [GitHub, ]
---


            


            


            



## Prerequisites


---


**[1]** [**Github Blog [1]: Using Jekyll**](https://rebedy.github.io/posts/Github-Blog-1-Using-Jekyll/)


            


            


                        


            


            



## Customizing Jekyll Chirpy Theme


---



### 1. Initializing ‘Chirpy Theme’



{% raw %}
```bash
./tools/init.sh
```
{% endraw %}


- This process will do …
	- remove `.travis.yml`
	- remove files under `_posts`
	- delete .hook from `.github/workflows/pages-deploy.yml.hook`
	- delete other folders and files in .github
	- delete `Gemfile.lock` from .gitignore
	- automatically generate commits to save changes

            


            



### 2. Dependencies



{% raw %}
```bash
bundle
```
{% endraw %}



            


            



### 3. Chirpy Environment Settings



#### source code guide

- `_config.yml`: The blog’s basic configuration. Basic environment settings.
- `_data`: You can change the configuration of the sidebar and post sharing buttons. Depending on your language settings, you can change the words by default.
- `_include`: You can change the UI inserted into most modules such as sidebar, ToC, Google Analytics, footer, and comments.
- `_layout`: You can change the basic format applied throughout the blog, the format applied to categories, posts, etc.
- `_posts`: This saves the created posts.
- `_sass`: To customize css files.
- `_site`: Everything that makes up the screen UI when running locally. Changes made here will be reflected locally, but will not be uploaded to GitHub. Also, if you change the contents of other basic directories and build, the contents here will change.
- `_tabs`: Landing page for the sidebar's default tab menus.
- `assets`: css, img, etc. Images to be included in the post are placed under `assets/img/favicon`. You can create a Favicon [here](https://realfavicongenerator.net/).
- `tools`: Code for automatic deployment on github. Just don't touch it at all.


#### `_config.yml`

- `lang` : choose language you want to display (eg. `en` or `ko` ). 
Search your language from http://www.lingoes.net/en/translator/langcode.htm.
- `timezone` : Change to your timezone. Search your timezone from [here](https://zones.arilyn.cc/).
- `title` : The main title. This will displayed on the sidebar.
- `tagline` : The sub-title. This will displayed on the sidebar under the title.
- `description` : SEO meta and the atom feed.
- `url` : ‘https://username.github.io’. Don’t add ‘/’ at the end.
- `github > username` : Your GitHub username.
- `twitter > username` : Your twitter username.
- `social`
	- `name` : Your name or nickname.
	- `email` : Your email address. (Note that if you don’t want to expose, don’t fill this in)
	- `links`:
		- ‘https://twitter.com/xxx’ : Your Twitter homepage.
		- ‘https://github.com/xxx’ : Your GitHub homepage.
		- ‘https://www.linkedin.com/in/xxx’ : Your LinkenIn homepage.
		- ‘https://www.facebook.com/username’ : Your Facebook homepage.
- `analytics > google > id` : ‘G-xxxxxxxxxx’ Your Google Analytics ID from Google Search Console.
- `theme_mode` : [light | dark] Keep empty will follow the system prefer color and there will be a toggle in the bottom of sidebar.
- `cdn` : The CDN endpoint for media resources. For example; "https://xxx.netlify.app".
- `avatar` : The avatar on sidebar, the profile image.
- `toc` : boolean type, the global switch for Table of Contents in posts.
- `paginate` : How many post will be appeared on a list. I set it to 10.


{% raw %}
```yaml
# The Site Configuration

# Import the theme
theme: jekyll-theme-chirpy

# The language of the webpage › http://www.lingoes.net/en/translator/langcode.htm
# If it has the same name as one of the files in folder `_data/locales`, the layout language will also be changed,
# otherwise, the layout language will use the default value of 'en'.
lang: en

# Change to your timezone › https://kevinnovak.github.io/Time-Zone-Picker
timezone: Asia/Seoul

title: xxx # the main title

tagline: ~~~ # it will display as the sub-title

description: >- # used by seo meta and the atom feed
  ~~~

# Fill in the protocol & hostname for your site.
# e.g. 'https://username.github.io', note that it does not end with a '/'.
url: "https://xxx.github.io"

github:
  username: xxx # change to your github username

twitter:
  username: xxx # change to your twitter username

social:
  # Change to your full name.
  # It will be displayed as the default author of the posts and the copyright owner in the Footer
  name: xxx
  email: xxx@xxx # change to your email address
  links:
    # The first element serves as the copyright owner's link
    - https://twitter.com/xxx # change to your twitter homepage
    - https://github.com/xxx # change to your github homepage
    # Uncomment below to add more social links
    # - https://www.facebook.com/username
    - https://www.linkedin.com/in/xxx # change to your linkenin homepage
...

# Web Analytics Settings
analytics:
  google:
    id: G-xxxxxxxxxx # fill in your Google Analytics ID
...

# Prefer color scheme setting.
#
# Note: Keep empty will follow the system prefer color by default,
# and there will be a toggle to switch the theme between dark and light
# on the bottom left of the sidebar.
#
# Available options:
#
#     light  - Use the light color scheme
#     dark   - Use the dark color scheme
#
theme_mode: # [light | dark] 
...

# The CDN endpoint for media resources.
# Notice that once it is assigned, the CDN url
# will be added to all media resources (site avatar, posts' images, audio and video files) paths starting with '/'
#
# e.g. 'https://cdn.com'
cdn: "https://xxx.netlify.app"

# the avatar on sidebar, support local or CORS resources
avatar: "/assets/img/favicons/mstile-150x150.png"
...

# boolean type, the global switch for TOC in posts.
toc: true # -> Table of Contents
...

paginate: 10  # -> How many post will be appeared on a list
...
```
{% endraw %}



            


            



### 4. Sidebar background with image

- `_sass/addon/commons.scss`


{% raw %}
```scss
  /* background: var(--sidebar-bg); */
  background-image: url('/assets/img/favicons/sidebar-bg-img.jpg');
  background-size: cover; /* cover the whole area when the image size and the background size are different */ 
  background-repeat: no-repeat; /* do not repeat the image when the image size and the background size are different */
```
{% endraw %}



![0](/assets/img/2024-05-29-GitHub-Blog-[2]:-Customizing.md/0.png)


            


            



### 5. Color styles per mode

- `_sass/colors/typography-dark.scss`  or `_sass/colors/typography-light.scss`


{% raw %}
```scss
/* these are what I changed */

 /* Common color */
  --link-color:
  --link-underline-color:
  ...
  --checkbox-color:
  ...
  
  /* Sidebar */
  --site-title-color:
  --site-subtitle-color:
  ...
  --sidebar-muted-color: 
  --sidebar-active-color:
  ...
  --avatar-border-color:
```
{% endraw %}



            


            


                        


            


            



## Connecting Github Pages and Notion based on Jekyll


---

- A repo provides a blog template that automatically imports Notion by linking Notion and Next.js.
	- [morethan-log](https://github.com/morethanmin/morethan-log)
- _**Just follow the link below.**_
	- [Shout out to lourcode!](https://lourcode.kr/posts/Integrating-Jekyll-based-Github-pages-with-Notion-pages/)

            


            


                        


            


            



## References


---

- [https://velog.io/@coastby/Git-GitBlog-Chirpy-Jekyll-Theme-적용하기](https://velog.io/@coastby/Git-GitBlog-Chirpy-Jekyll-Theme-%EC%A0%81%EC%9A%A9%ED%95%98%EA%B8%B0)
