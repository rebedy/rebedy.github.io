---
layout: post
date: 2024-05-28
title: "Github Blog [1]: Using Jekyll"
tags: [blog, ]
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

- HTTPs의 주소를 복사하고 컴퓨터의 터미널을 열어 clone하고 싶은 폴더에서
 `git clone {HTTPs주소}` 입력.
- Permission error
	- 20년 11월부터 비밀번호를 허용하지 않는다. 21년 8월13일부터는 모든 Git 작업에는 토큰(또는 SSH 키) 인증이 필요


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

- If you are using a M1 Macbook you may have this error…[Ruby Problem]


{% raw %}
```bash
[NOTE]
You may have encountered a bug in the Ruby interpreter or extension libraries.
...
```
{% endraw %}



**→ Re-Install Ruby with specific version**

	1. rbenv 설치

		
{% raw %}
```bash
		brew install rbenv ruby-build
```
{% endraw %}


	2. ruby version 확인 (현재 사용중인 버전)

		
{% raw %}
```bash
		rbenv versions
```
{% endraw %}


	3. 설치 가능한 버전 확인

		
{% raw %}
```bash
		rbenv install -l
```
{% endraw %}


	4. 루비 설치하고 버전 바꾸기

		
{% raw %}
```bash
		rbenv install x.x.x
		rbenv global x.x.x
```
{% endraw %}


	5. zsh를 사용 중인지 확인 후, 설정 파일 수정.

		
{% raw %}
```bash
		echo $SHELL
			-> /bin/zsh 나오면..
		
		vi ~/.zshrc 후, 아래 명령어 추가.
		
		export PATH={$Home}/.rbenv/bin:$PATH && \
		eval "$(rbenv init -)"
```
{% endraw %}


	6. 변경된 파일 적용

		
{% raw %}
```bash
		source ~/.zshrc
```
{% endraw %}


	7. 다시 다운 받기

		
{% raw %}
```bash
		gem install bundler
		rbenv rehash
```
{% endraw %}


	8. 다시 앞서 clone한 repository 저장소로가서 jekyll 다운 받기

		
{% raw %}
```bash
		gem install jekyll
```
{% endraw %}


	9. jekyll을 이용해 기본 번들 설치

		
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


These pages offer Jekyll Themes

- http://jekyllthemes.org/
- [https://jekyllthemes.io/free](https://jekyllthemes.io/free)
- [https://themes.jekyllrc.org/](https://themes.jekyllrc.org/)
- [https://github.com/topics/jekyll-theme](https://github.com/topics/jekyll-theme)


#### Step 1. Download Theme

1. github에서 직접 내려 받는 방법
2. 홈페이지에서 다운 받는 방법


#### Step 2. Create a new folder in local and connect to the GitHub repository


해도되고 안 해도 되고 


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
# 폴더에 git 생성하기
git init
# blog 폴더에 github homepage repository 연결하기
git remote add origin {github_HTTPS_address}
# repository에 있는 데이터를 blog 폴더에 내려받기
git pull origin main
# 연결 완료!
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


> 👸 _**If you are suffering from the error message below, please make sure this process is done.**_  
> **`ERROR ‘/assets/js/dist/home.min.js’ not found.`**

- Do either one of the commands below.


{% raw %}
```bash
$ NODE_ENV=production npx rollup -c --bundleConfigAsCjs

OR

$ npm install && npm run build bundle update
```
{% endraw %}


- Result

![6](/assets/img/2024-05-28-Github-Blog-[1]:-Using-Jekyll.md/6.png)



## References


---

- [https://jason-api.tistory.com/79](https://jason-api.tistory.com/79)
