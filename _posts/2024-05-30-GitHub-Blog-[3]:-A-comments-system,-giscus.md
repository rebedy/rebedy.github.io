---
layout: post
date: 2024-05-30
title: "GitHub Blog [3]: A comments system, giscus"
tags: [blog, ]
categories: [GitHub, ]
---


 



## Prerequisites


---


[Github Blog [1]: Using Jekyll](https://rebedy.github.io/posts/Github-Blog-1-Using-Jekyll/)


[GitHub Blog [2]: Customizing](https://rebedy.github.io/posts/GitHub-Blog-2-Customizing/)



## giscus


![0](/assets/img/2024-05-30-GitHub-Blog-[3]:-A-comments-system,-giscus.md/0.png)


> A comments system powered by [GitHub Discussions](https://docs.github.com/en/discussions). Let visitors leave comments and reactions on the website via GitHub. Similar to [utterances](https://github.com/utterance/utterances).

- [Open source](https://github.com/giscus/giscus). 🌏
- No tracking, no ads, always free. 📡 🚫
- No database needed. All data is stored in GitHub Discussions.
- Supports [custom themes](https://github.com/giscus/giscus/blob/main/ADVANCED-USAGE.md#data-theme)! 🌗
- Supports [multiple languages](https://github.com/giscus/giscus/blob/main/CONTRIBUTING.md#adding-localizations). 🌐
- [Extensively configurable](https://github.com/giscus/giscus/blob/main/ADVANCED-USAGE.md). 🔧
- Automatically fetches new comments and edits from GitHub. 🔃
- [Can be self-hosted](https://github.com/giscus/giscus/blob/main/SELF-HOSTING.md)! 🤳


## **How to use** **`giscus`** 


---



### 1. Installation


Install [**Giscus App**](https://github.com/apps/giscus) in **“Repository to use comments”**

- **“Repository to use comments”** will be `{username}/{username}.github.io` if you are on GitHub Pages for blog.


### 2. Activation


Activate **`Discussion`** in **`Settings > General > Features`** section and check the tab!


![1](/assets/img/2024-05-30-GitHub-Blog-[3]:-A-comments-system,-giscus.md/1.png)


![2](/assets/img/2024-05-30-GitHub-Blog-[3]:-A-comments-system,-giscus.md/2.png)



### 3. Setting the Configuration


Go into [giscus setting page](https://giscus.app/ko) and follow the instruction.


**(1) Language**


**(2) Repository**


![3](/assets/img/2024-05-30-GitHub-Blog-[3]:-A-comments-system,-giscus.md/3.png)


**(3) Discussion Category** 


	→ choose `General` and check `Only search for discussions in this category`


and rest of them are optional


**result**



{% raw %}
```html
<script src="https://giscus.app/client.js"
        data-repo="rebedy/rebedy.github.io"
        data-repo-id="xxx"
        data-category="General"
        data-category-id="xxx"
        data-mapping="pathname"
        data-strict="0"
        data-reactions-enabled="1"
        data-emit-metadata="0"
        data-input-position="bottom"
        data-theme="preferred_color_scheme"
        data-lang="en"
        crossorigin="anonymous"
        async>
</script>
```
{% endraw %}




### 4. Setting `_config.yml`



{% raw %}
```yaml
...

comments:
  # Global switch for the post comment system. Keeping it empty means disabled.
  provider: giscus # [disqus | utterances | giscus]
	# -> The chirpy supports three different comment providers.
	# Among them `utterances` and `giscus` use GitHub API.
	# `utterances` uses GitHub Issue and `giscus` uses GitHub Discussion.
	# I will go with the `giscus`

  # The provider options are as follows:
  disqus:
    shortname: # fill with the Disqus shortname. › https://help.disqus.com/en/articles/1717111-what-s-a-shortname
  # utterances settings › https://utteranc.es/
  utterances:
    repo: # <gh-username>/<repo>
    issue_term: # < url | pathname | title | ...>
  # Giscus options › https://giscus.app
  giscus:
    repo: "rebedy/rebedy.github.io" # <gh-username>/<repo>
    repo_id: "xxx"
    category: "General"
    category_id: "xxx"
    mapping: # optional, default to 'pathname'
    strict: # optional, default to '0'
    input_position: # optional, default to 'bottom'
    lang: # optional, default to the value of `site.lang`
    reactions_enabled: # optional, default to the value of `1`

...
```
{% endraw %}




### 5. Deployment



{% raw %}
```bash
git add .
git commit -m "giscus"
git push
```
{% endraw %}



**result**


![4](/assets/img/2024-05-30-GitHub-Blog-[3]:-A-comments-system,-giscus.md/4.png)



## References


---

- [https://da-in.github.io/posts/Blog-Comments/](https://da-in.github.io/posts/Blog-Comments/)
- [https://giscus.app/ko](https://giscus.app/ko)
- [https://utteranc.es/?utm_source=saashub&utm_medium=marketplace&utm_campaign=saashub](https://utteranc.es/?utm_source=saashub&utm_medium=marketplace&utm_campaign=saashub)
- [https://help.disqus.com/en/articles/1717053-what-is-disqus](https://help.disqus.com/en/articles/1717053-what-is-disqus)
