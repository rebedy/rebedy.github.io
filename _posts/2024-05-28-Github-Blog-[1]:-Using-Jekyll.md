---
layout: post
date: 2024-05-28
title: "Github Blog [1]: Using Jekyll"
tags: [blog, chirpy, ]
categories: [GitHub, ]
---


            


            


            



## GitHub Pages


---


![0](/assets/img/2024-05-28-Github-Blog-[1]:-Using-Jekyll.md/0.png)

- Static site provided by GitHub
- You can manage posts by pushing files to the repository and there is no cost.
- [GitHub Pages Information](https://docs.github.com/ko/pages/getting-started-with-github-pages/about-github-pages)

            


            


           


            


            


             



## Static Site Generator


---



#### Jekyll ✔️


![1](/assets/img/2024-05-28-Github-Blog-[1]:-Using-Jekyll.md/1.png)

- Ruby based
- The most common and popular static site creation framework
- If there are a lot of documents, it may take more than 5 minutes to build.
- Various Themes


#### Hugo


![2](/assets/img/2024-05-28-Github-Blog-[1]:-Using-Jekyll.md/2.png)

- Based on Golang
- Build speed is very fast
- Well-organized documentation
- Not a lot of Themes to use


#### Hexo


![3](/assets/img/2024-05-28-Github-Blog-[1]:-Using-Jekyll.md/3.png)

- Based on JaveScript(Node.js)
- Quite a few Korean references
- Various Themes


## Prerequisites


---

1. GitHub
2. VSCode


## How to build your own Blog with GItHub Pages


---



### 1. Create a new GitHub repository


> 💡 Repository name : `{username}.github.io` 

- Set as ‘**Public’** / Check ‘**Add a README file’** / **Create repository**


#### After creating repository…

- **Settings** > **Pages** > **Build and deployment > Source > choose** **`GitHub Actions`**

            


            


            



### 2. Github r**epository clone**

- After copying the HTTPs address, open the terminal and then run  `git clone {HTTPs_address}`
- Permission error
	- Password is not allowed from November 2020. From 13th August 2021, the certified token (or SSH key) is needed for all git processes.

            


            


            



### 3. npm Installation


Download:  [https://nodejs.org/ko/](https://nodejs.org/ko/)

- NPM will also be installed with Node.js, and you can check whether the installation was successful by checking the version.


{% raw %}
```bash
node -v
npm -v
```
{% endraw %}


- [Detailed Explanation](https://velog.io/@me2designer/NPM-%EC%84%A4%EC%B9%98-%EB%B0%8F-%EC%84%A4%EC%A0%95)

            


            


            



### 4. Ruby Installation 



#### Ubuntu



{% raw %}
```bash
sudo apt-get install ruby-full build-essential zlib1g-dev
```
{% endraw %}




#### MacOS


Ruby is installed on the MacOS initially. But MacOS uses System Ruby so it doesn’t have permissions to install `gem`. You gotta use `rbenv`  to change Ruby version.



{% raw %}
```bash
brew install ruby
```
{% endraw %}




#### `rbenv` versioning



{% raw %}
```bash
rbenv install -l
rbenv install 3.3.1
rbenv global 3.3.1
rbenv versions
which ruby
rbenv init
vim ~/.zshrc
source ~/.zshrc
```
{% endraw %}



            


            


            



### **5. Jekyll and** `gem` **Installation**



{% raw %}
```bash
gem install jekyll bundler
```
{% endraw %}



ref.: [https://jekyllrb-ko.github.io/docs/installation/macos/](https://jekyllrb-ko.github.io/docs/installation/macos/)



#### Dependencies



{% raw %}
```bash
gem install github-pages
```
{% endraw %}



            


            


            



### 6. Generate a basic framework for the homepage



{% raw %}
```bash
jekyll new ./
```
{% endraw %}



![4](/assets/img/2024-05-28-Github-Blog-[1]:-Using-Jekyll.md/4.png)



#### **Re-Install Ruby with specific version**

- If you are using a M1 Macbook you may have this error…[Ruby Problem]


{% raw %}
```bash
[NOTE]
You may have encountered a bug in the Ruby interpreter or extension libraries.
...
```
{% endraw %}



1) `rbenv` installation



{% raw %}
```bash
brew install rbenv ruby-build
```
{% endraw %}



2) Check ruby version (current one)



{% raw %}
```bash
rbenv versions
```
{% endraw %}



3) Check installable versions



{% raw %}
```bash
rbenv install -l
```
{% endraw %}



4) Install ruby and change the version setting.



{% raw %}
```bash
rbenv install x.x.x
rbenv global x.x.x
```
{% endraw %}



5) Check shell and edit the configuration file.



{% raw %}
```bash
echo $SHELL
```
{% endraw %}



→ If it says `/bin/zsh`, add below after `vi ~/.zshrc`



{% raw %}
```bash
export PATH={$Home}/.rbenv/bin:$PATH && \
eval "$(rbenv init -)"
```
{% endraw %}



6) Apply the change



{% raw %}
```bash
source ~/.zshrc
```
{% endraw %}



7) Re-install



{% raw %}
```bash
gem install bundler
rbenv rehash
```
{% endraw %}



8) Download jekyll at the repository you cloned



{% raw %}
```bash
gem install jekyll
```
{% endraw %}



9) Install basic bundle using jekyll



{% raw %}
```bash
jekyll new ./
```
{% endraw %}



            


            


            



### 7. `bundle` Installation



{% raw %}
```bash
bundle install
```
{% endraw %}




#### Execute Jekyll on the local server!

1. Run.


{% raw %}
```bash
boundle exec jekyll serve
```
{% endraw %}


1. **http://127.0.0.1:4000/** on browser.


### 8. Deploy



#### First git push



{% raw %}
```bash
git add .
git commit -m "jekyll start"
git push
```
{% endraw %}



![5](/assets/img/2024-05-28-Github-Blog-[1]:-Using-Jekyll.md/5.png)



### 9. Jekyll Theme



#### Step 1. Download Theme

1. Download directly from github
2. Download from the homepages
	- http://jekyllthemes.org/
	- [https://jekyllthemes.io/free](https://jekyllthemes.io/free)
	- [https://themes.jekyllrc.org/](https://themes.jekyllrc.org/)
	- [https://github.com/topics/jekyll-theme](https://github.com/topics/jekyll-theme)


#### Step 2. Create a new folder in local and connect to the GitHub repository


~~_Doesn’t matter if you don't do this step!_~~


**2-1.** Create an empty folder and get in



{% raw %}
```bash
mkdir {folder_name}
cd {folder_name}
```
{% endraw %}



**2-2.** Connect to the pre-made GitHub homepage repository



{% raw %}
```bash
# Generate git in the folder
git init
# Connect the GitHub homepage repository to the blog
git remote add origin {github_HTTPS_address}
# Download data from repository to blog folder
git pull origin main
# Done!
```
{% endraw %}



**2-3.** Delete all the data in the folder



{% raw %}
```bash
rm -rf {folder_name}
```
{% endraw %}




#### Step 3. Download Jekyll's basic package



{% raw %}
```bash
jekyll new ./
```
{% endraw %}




#### Step 4. Copy and paste the Theme’s contents to the folder


Copy all the contents of the theme folder that you downloaded and paste to the newly made folder. Merge or replace all the files if necessary.



#### Step 5. Add, commit, push



{% raw %}
```bash
git add .
git commit -m "change theme"
git push --set-upstream origin main
git push
```
{% endraw %}




#### **Conflicts**


**1. conflict error**



{% raw %}
```bash
bundle install
bundle exec jekyll build
```
{% endraw %}



 → Delete 404.html, about.md, index.md files


**2. github build failed**


깃헙에 add commit push 하면 에러 메시지: pages build and deployment #20 error



{% raw %}
```bash
github-pages 225 | Error: The jekyll-theme-hydejack theme could not be found
```
{% endraw %}



→ Edit the `_config.yml` file in the folder.



{% raw %}
```bash
vi _config.yml

### code about the Theme
theme: jekyll-theme-hydejack
#remote_theme: hydecorp/hydejack@v9


### Change it to...
#theme: jekyll-theme-hydejack
remote_theme: hydecorp/hydejack@v9
```
{% endraw %}



**3. bundle update**


After you are done with step 9 if you have problem with build, please consider working on this process.


![6](/assets/img/2024-05-28-Github-Blog-[1]:-Using-Jekyll.md/6.png)

- Do either one of the commands below.


{% raw %}
```bash
$ NODE_ENV=production npx rollup -c --bundleConfigAsCjs

OR

$ npm install && npm run build bundle update
```
{% endraw %}


- Result

![7](/assets/img/2024-05-28-Github-Blog-[1]:-Using-Jekyll.md/7.png)


            


            


                        


            


            



## References


---

- [https://jason-api.tistory.com/79](https://jason-api.tistory.com/79)
