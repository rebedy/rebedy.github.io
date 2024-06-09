---
layout: post
date: 2024-06-04
title: "Github Profile [3]: Commit Stat (feat.gist)"
tags: [github-profile, github, ]
categories: [GitHub, ]
---


       


       


       


![0](/assets/img/2024-06-04-Github-Profile-[3]:-Commit-Stat-(feat.gist).md/0.png)


![1](/assets/img/2024-06-04-Github-Profile-[3]:-Commit-Stat-(feat.gist).md/1.png)



## Prerequisites


---


**[1]** [**Github-Profile-1-README.md**](https://rebedy.github.io/posts/Github-Profile-1-README.md/)


**[2]** [**Github-Profile-2-GitHub-Stats**](https://rebedy.github.io/posts/Github-Profile-2-GitHub-Stats/)


       


       



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

![2](/assets/img/2024-06-04-Github-Profile-[3]:-Commit-Stat-(feat.gist).md/2.png)


       


       


       



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



![3](/assets/img/2024-06-04-Github-Profile-[3]:-Commit-Stat-(feat.gist).md/3.png)

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
3. Secret: _**token you copied from 3)-2.**_

![4](/assets/img/2024-06-04-Github-Profile-[3]:-Commit-Stat-(feat.gist).md/4.png)


       


       


       



## 7. [Fix the gist onto my GitHub profile](https://docs.github.com/en/github/setting-up-and-managing-your-github-profile/pinning-items-to-your-profile)

1. On the top right corner of GitHub > Click your profile photo > Click **`Your profile`**.

![5](/assets/img/2024-06-04-Github-Profile-[3]:-Commit-Stat-(feat.gist).md/5.png)

1. At the left top of the `Pinned` section, click **`Customize your pins`**.

	![6](/assets/img/2024-06-04-Github-Profile-[3]:-Commit-Stat-(feat.gist).md/6.png)

1. Select up to six repositories and gists, combined > Click **`Save pins`****.**

![7](/assets/img/2024-06-04-Github-Profile-[3]:-Commit-Stat-(feat.gist).md/7.png)

	- (Optional) To change which items are included in the searchable list, next to `Show`, select or deselect **`Repositories`** and **`Gists`**.
	- (Optional) To make it easier to find a specific item, in the `Filter repositories and gists` field, type the name of a user, organization, repository, or gist.

       


       



## 8. Update the gist

1. It will update automatically by the `Actions` cycle. (1 hour)
2. You can also update manually.
	1. Edit README.md or .yml file. It will update instantly.
	2. Go to `Actions` > `Update git` > press `Run workflow` button.

	![8](/assets/img/2024-06-04-Github-Profile-[3]:-Commit-Stat-(feat.gist).md/8.png)


       


       


       


       


       


       



## References


---

- [productive-box](https://github.com/maxam2017/productive-box)
- [awesome-pinned-gists](https://github.com/matchai/awesome-pinned-gists)
