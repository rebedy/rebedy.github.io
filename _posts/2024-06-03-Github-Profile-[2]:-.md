---
layout: post
date: 2024-06-03
title: "Github Profile [2]: "
tags: [github-profile, ]
categories: [GitHub, ]
---


       


       


       


![0](/assets/img/2024-06-03-Github-Profile-[2]:-.md/0.png)


![1](/assets/img/2024-06-03-Github-Profile-[2]:-.md/1.png)


       


       


       



## 1. Fork the repo from [productive-box.git](https://github.com/rebedy/productive-box.git)


       


       


       



## 2. Activate `Actions`

1. go to `Actions` tab and click the `enabled` bottom to activate.

       


       


       



## 3. [Generate new public gist](https://gist.github.com/)

1. the title and contents do not matter. It will be overwritten anyway.
2. ⚠️ click `Create public gist`
3. copy the gist ID beforehand.

       


       


       



## 4. [Generate token](https://github.com/settings/tokens/new)

1. check `repo`, `write:packages`, and `gist`.
2. ⚠️ please copy the token and save it somewhere else!!!
3. set the `Expiration` to ‘No expiration’.

![2](/assets/img/2024-06-03-Github-Profile-[2]:-.md/2.png)


       


       


       



## 5. Edit the .yml file 

1. Open `productive-box/.github/workflows/schedule.yml`
2. Change the user name.


{% raw %}
```yaml
...
	steps:
		- name: Update gist
		  uses: rebedy/productive-box@master
```
{% endraw %}



![3](/assets/img/2024-06-03-Github-Profile-[2]:-.md/3.png)

1. And change the gist ID and the timezone.
	1. `GIST_ID` should be the ID you copied at 2)-3.
	2. `TIMEZONE` examples are in the `README.md` of this repository.


{% raw %}
```yaml
...
	steps:
		- name: Update gist
		  uses: rebedy/productive-box@master
		  env:
			  GH_TOKEN: ${{ secrets.GH_TOKEN }}
			  GIST_ID: ...
			  TIMEZONE: Asia/Seoul
```
{% endraw %}



       


       


       



## 6. Add new secret

1. `Settings` of the repository > `Secrets and variables` > `Actions` > `New repository secret`
2. Name: **`GH_TOKEN`**
3. Secret: _token you copied from 3)-2._

![4](/assets/img/2024-06-03-Github-Profile-[2]:-.md/4.png)


       


       


       



## 7. [Fix the gist onto my github profile](https://docs.github.com/en/github/setting-up-and-managing-your-github-profile/pinning-items-to-your-profile)


       


       


       



## 8. Update the gist

1. It will update automatically by the `Actions` cycle. (1 hour)
2. You can also update manually.
	1. Edit README.md or .yml file. It will update instantly.
	2. Go to `Actions` > `Update git` > press `Run workflow` button.

	![5](/assets/img/2024-06-03-Github-Profile-[2]:-.md/5.png)


       


       


       


       


       


       



## References


---

- [productive-box](https://github.com/maxam2017/productive-box)
- [awesome-pinned-gists](https://github.com/matchai/awesome-pinned-gists)
- [http://blog.cowkite.com/blog/2102241544/](http://blog.cowkite.com/blog/2102241544/)
