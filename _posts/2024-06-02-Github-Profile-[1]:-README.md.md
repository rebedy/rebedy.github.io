---
layout: post
date: 2024-06-02
title: "Github Profile [1]: README.md"
tags: [github-profile, github, ]
categories: [GitHub, ]
math: false
---


            


            


                        


![0](/assets/img/2024-06-02-Github-Profile-[1]:-README.md.md/0.png)


            


            


                        



## **`userid/readme.md`** **for Github Profile!**


---



#### 1. make a repository with a name the same as your github nickname!

- It’s a special repository. It’s `README.md` will appear on your profile!


#### 2. Let’s edit `README.md` file!


![1](/assets/img/2024-06-02-Github-Profile-[1]:-README.md.md/1.png)


            


            


            


                        


            


                        



## 1. Add badges


---


> 💡 **Badge:** [**https://shields.io/**](https://shields.io/)  
> **Icon:** [**https://simpleicons.org/**](https://simpleicons.org/)


       



### `shield.io`



{% raw %}
```markdown
https://img.shields.io/badge/<LABEL>-<MESSAGE>-<COLOR>
```
{% endraw %}



       

- underscores, dash, space == `__`, `--`, `_`

	![2](/assets/img/2024-06-02-Github-Profile-[1]:-README.md.md/2.png)

- `COLOR`: Hex, rgb, rgba, hsl, hsla and css named colors may be used.

       



#### 1) Styles



{% raw %}
```markdown
<img src="https://img.shields.io/badge/{BADGE_NAME}-{BADGE_COLOR}?style={BADGE_STYLE}&logo={LOGO_NAME}&logoColor={LOGO_COLOR}"/>
```
{% endraw %}



examples



{% raw %}
```markdown
<img src="https://img.shields.io/badge/style-plastic-blue?style=plastic"/>
<img src="https://img.shields.io/badge/style-flat-blue?style=flat"/>
<img src="https://img.shields.io/badge/style-square-blue?style=flat-square"/>
<img src="https://img.shields.io/badge/style-forthebage-blue?style=for-the-badge"/>
<img src="https://img.shields.io/badge/style-social-blue?style=social"/>
```
{% endraw %}



![3](/assets/img/2024-06-02-Github-Profile-[1]:-README.md.md/3.png)


       



#### 2) Logo

- any logos provided by [simpleicons](https://simpleicons.org/)

examples



{% raw %}
```markdown
<img src="https://img.shields.io/badge/logo-test-blue?logo=facebook"/>
<img src="https://img.shields.io/badge/logo-test-blue?logo=facebook&logoColor=white"/>
<img src="https://img.shields.io/badge/logo-test-blue?logo=facebook&logoColor=white&logoWidth=40"/>
```
{% endraw %}



![4](/assets/img/2024-06-02-Github-Profile-[1]:-README.md.md/4.png)



{% raw %}
```markdown
<img src="https://img.shields.io/badge/Android-3DDC84?style=flat-square&logo=Android&logoColor=white"/>
```
{% endraw %}



![5](/assets/img/2024-06-02-Github-Profile-[1]:-README.md.md/5.png)


            


                        


            


            


                        



## 2. Add logos


---

- [https://www.vectorlogo.zone](https://www.vectorlogo.zone/)
- githubusercontent

examples



{% raw %}
```markdown
<!-- Logos -->
<a href="https://azure.microsoft.com/en-in/" target="_blank"> 
  <img src="https://www.vectorlogo.zone/logos/microsoft_azure/microsoft_azure-icon.svg" alt="azure" width="30" height="30"/> 
</a>
<a href="https://www.python.org" target="_blank"> 
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" alt="python" width="30" height="30"/> 
</a>

<!-- Your SNS -->
<a href="https://www.instagram.com/xxx/">
  <img align="left" alt="rebedy Instagram" width="21px" src="https://raw.githubusercontent.com/edent/SuperTinyIcons/099dc12b59179d07d534069bc8551718f786d91a/images/svg/instagram.svg" />
</a>
<a href="https://www.linkedin.com/in/xxx/">
  <img align="left" alt="rebedy Linkdin" width="21px" src="https://raw.githubusercontent.com/edent/SuperTinyIcons/099dc12b59179d07d534069bc8551718f786d91a/images/svg/linkedin.svg" />
</a>
<a href="https://www.reddit.com/user/xxx">
  <img align="left" alt="rebedy Reddit" width="21px" src="https://raw.githubusercontent.com/edent/SuperTinyIcons/099dc12b59179d07d534069bc8551718f786d91a/images/svg/reddit.svg" />
</a>
```
{% endraw %}



![6](/assets/img/2024-06-02-Github-Profile-[1]:-README.md.md/6.png)


            


            


                        


            


            


                        



## 3. Add typing svg


---


Find `lines=Please%2C+change+here.;This+is+where+you+should+change.` part and write what you want you say using `%2C` as a comma, `+` as a space and `;` as a line break!



{% raw %}
```markdown
<!-- example1 -->
[![7](/assets/img/2024-06-02-Github-Profile-[1]:-README.md.md/7.png)_Typing SVG_](https://git.io/typing-svg)

<!-- example2 -->
<img src="https://readme-typing-svg.demolab.com/?lines=Please%2C+change+here.;This+is+where+you+should+change.&font=Fira%20Code&center=true&color=e0c8d0&width=380&height=50&duration=4000&pause=1000">
```
{% endraw %}



                        


            


                        


            


                        



## 4. Add moving emoji


---

- Copy link of `.gif` from [slackmojis](https://slackmojis.com/) and copy the address below.


{% raw %}
```markdown
<h1 align="center">
  <img src="https://slackmojis.com/emojis/20940-wave/download" width="30"/>
</h1>
```
{% endraw %}



![8](/assets/img/2024-06-02-Github-Profile-[1]:-README.md.md/8.png)


            


            


                        


            


            


                        



## 5. Add languages and tools badges


---



{% raw %}
```markdown
<h3 align="left">Languages and Tools 🔧</h3>
<p  align="center">
<img  alt="Linux"  src="https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=white"/>
<img  alt="Ubuntu"  src="https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=Ubuntu&logoColor=white"/>
</p>
<p  align="center">
<img  alt="Visual Studio Code"  src="https://img.shields.io/badge/Visual Studio Code-0078d7.svg?style=for-the-badge&logo=visual-studio-code&logoColor=white"/>
<img  alt="PyCharm"  src="https://img.shields.io/badge/PyCharm-000000?style=for-the-badge&logo=PyCharm&logoColor=white"/>
<img  alt="Colab"  src="https://img.shields.io/badge/Google%20Colab-F9AB00?style=for-the-badge&logo=Google%20Colab&logoColor=white"/>
</p>
<p  align="center">
<img  alt="Python"  src="https://img.shields.io/badge/python-%2314354C.svg?style=for-the-badge&logo=python&logoColor=white"/>
<img  alt="PyTorch"  src="https://img.shields.io/badge/PyTorch-%23FF6F00.svg?style=for-the-badge&logo=PyTorch&logoColor=white" />
<img  alt="TensorFlow"  src="https://img.shields.io/badge/Tensorflow-%23FF6F00.svg?style=for-the-badge&logo=TensorFlow&logoColor=white" />
<img  alt="Markdown"  src="https://img.shields.io/badge/markdown-%23000000.svg?style=for-the-badge&logo=markdown&logoColor=white"/>
<!-- <img  alt="C++"  src="https://img.shields.io/badge/C++-00599C?style=for-the-badge&logo=C%2B%2B&logoColor=white"/> -->
<!-- <img  alt="MySQL"  src="https://img.shields.io/badge/mysql-%2300f.svg?style=for-the-badge&logo=mysql&logoColor=white"/> -->
<!-- <img  alt="CSS3"  src="https://img.shields.io/badge/css3-%231572B6.svg?style=for-the-badge&logo=css3&logoColor=white"/> -->
<!-- <img  alt="JavaScript"  src="https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E"/> -->
</p>
<p  align="center">
<img  alt="git"  src="https://img.shields.io/badge/GIT-%23E34F26.svg?style=for-the-badge&logo=git&logoColor=white"/>
<img  alt="Github"  src="https://img.shields.io/badge/github-%23000000.svg?style=for-the-badge&logo=github&logoColor=white"/>
<img  alt="Gitlab"  src="https://img.shields.io/badge/gitlab-%23181717.svg?style=for-the-badge&logo=gitlab&logoColor=white"/>
<img  alt="Anaconda"  src="https://img.shields.io/badge/Anaconda-44A833?style=for-the-badge&logo=Anaconda&logoColor=white"/>
<!-- <img  alt="AWS"  src="https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white"/> -->
<!-- <img  alt="Docker"  src="https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white"/> -->
<!-- <img  alt="Kubernetes"  src="https://img.shields.io/badge/kubernetes-%23326ce5.svg?style=for-the-badge&logo=kubernetes&logoColor=white"/> -->
<!-- <img  alt="Unreal Engine"  src="https://img.shields.io/badge/unreal engine-%23313131.svg?style=for-the-badge&logo=unrealengine&logoColor=white"/> -->
</p>
<p  align="center">
<img  alt="GitHub Actions"  src="https://img.shields.io/badge/github%20actions-%232671E5.svg?style=for-the-badge&logo=githubactions&logoColor=white"/>
</p>
<p  align="center">
<img  alt="Jira"  src="https://img.shields.io/badge/Jira-0052CC?style=for-the-badge&logo=Jira&logoColor=white"/>
<img  alt="Confluence"  src="https://img.shields.io/badge/confluence-%23172BF4.svg?style=for-the-badge&logo=confluence&logoColor=white"/>
<img  alt="Notion"  src="https://img.shields.io/badge/Notion-%23000000.svg?style=for-the-badge&logo=notion&logoColor=white"/>
</p>
<br>
```
{% endraw %}



![9](/assets/img/2024-06-02-Github-Profile-[1]:-README.md.md/9.png)


            


            


                        


            


            


                        



## 6. Add badges for the counts


---

- **A badge that counts hits:** [hit-counter](https://hits.seeyoufarm.com/)
- **A badge that counts profile views:** [github-profile-views-counter](https://github.com/antonkomarev/github-profile-views-counter)

Find `xxxxxxx` and change it to your github username!



{% raw %}
```text
[![10](/assets/img/2024-06-02-Github-Profile-[1]:-README.md.md/10.png)_Hits_](https://hits.seeyoufarm.com)

![11](/assets/img/2024-06-02-Github-Profile-[1]:-README.md.md/11.png)_Views_
```
{% endraw %}



            


            


                        


            


            


                        



## Reference


---

- [https://dev.to/web/design-github-profile-using-readme-md-8al](https://dev.to/web/design-github-profile-using-readme-md-8al)
- [https://blog.cowkite.com/blog/2102241544/](https://blog.cowkite.com/blog/2102241544/)
- [https://github.com/anuraghazra/github-readme-stats/blob/master/docs/readme_kr.md](https://github.com/anuraghazra/github-readme-stats/blob/master/docs/readme_kr.md)
- [https://velog.io/@loakick/Shield-IO-사용법-iojyndy4pi](https://velog.io/@loakick/Shield-IO-%EC%82%AC%EC%9A%A9%EB%B2%95-iojyndy4pi)
