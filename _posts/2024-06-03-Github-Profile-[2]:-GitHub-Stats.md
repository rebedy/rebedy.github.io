---
layout: post
date: 2024-06-03
title: "Github Profile [2]: GitHub Stats"
tags: [github-profile, github, ]
categories: [GitHub, ]
---


![0](/assets/img/2024-06-03-Github-Profile-[2]:-GitHub-Stats.md/0.png)



## Prerequisite


---


**[1]** [**Github-Profile-1-README.md**](https://rebedy.github.io/posts/Github-Profile-1-README.md/)



## **Top Languages Card**


---


Your most frequently used languages. This language card shows language results only from public repositories. To include languages in private repos, you need to do [deploy your own instance](https://github.com/anuraghazra/github-readme-stats?tab=readme-ov-file#deploy-on-your-own) using your own GitHub API token.


To use ‘Top Language Card’, please copy and paste the code below into your markdown and change the `?username=` value to your GitHub username.



{% raw %}
```markdown
<img align="center" src="https://github-readme-stats.vercel.app/api/top-langs/?username=rebedy"/>
```
{% endraw %}



You can [exclude](https://github.com/anuraghazra/github-readme-stats?tab=readme-ov-file#exclude-individual-repositories) some repos or [hide](https://github.com/anuraghazra/github-readme-stats?tab=readme-ov-file#hide-individual-languages) certain languages by specifying them.



### # of languages


And you also can control how many numbers of languages you want to display with the `&langs_count=` option to increase or decrease the number of languages shown on the card.



### Card Layout


You can use the `&layout=` option to change the card design.


There are `compact` , `donut` , `donut-vertical` , `pie` layout.


Or you also can hide progress bars then the layout will set to `compact` automatically.



### Themes


There are inbuilt themes and you can use them with `&theme={theme_name}` parameter.


**All inbuilt themes:**  [Available themes](https://github.com/anuraghazra/github-readme-stats/blob/master/themes/README.md) 



### Final example



{% raw %}
```markdown
<img align="center" src="https://github-readme-stats.vercel.app/api/top-langs/?username=rebedy&layout=donut-vertical&theme=shadow_green&hide_border=true&no-bg=true&no-frame=true&show_icons=true&langs_count=8"/>
```
{% endraw %}




## **GitHub Readme Streak Stats**


---


Copy and paste line below into your markdown and replace the value after `?user=` with your GitHub username.



{% raw %}
```markdown
<img src="https://github-readme-streak-stats.herokuapp.com?user=rebedy" />
```
{% endraw %}




### Options


There are optional fields besides the `user` field which is mandatory.


| **Parameter**              | **Details**                                          | **Example**                                                                                                  |
| -------------------------- | ---------------------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| `hide_border`              | Make the border transparent (Default: `false`)       | `true` or `false`                                                                                            |
| `border_radius`            | Set the roundness of the edges (Default: `4.5`)      | Number `0` (sharp corners) to `248` (ellipse)                                                                |
| `background`               | Background <u>color</u> (eg. `f2f2f2`, `35,d22,00f`) | **hex code** without `#`, **css color** or
gradient (`angle,start_color,...,end_color`)                      |
| `border`                   | Border <u>color</u>                                  | **hex code** w/o `#` or **css color**                                                                        |
| `stroke`                   | Stroke line <u>color</u> between sections            | **hex code** w/o `#` or **css color**                                                                        |
| `ring`                     | <u>Color</u> of the ring around the current streak   | **hex code** w/o `#` or **css color**                                                                        |
| `fire`                     | <u>Color</u> of the fire in the ring                 | **hex code** w/o `#` or **css color**                                                                        |
| `currStreakNum`            | Current streak number <u>color</u>                   | **hex code** w/o `#` or **css color**                                                                        |
| `sideNums`                 | Total and longest streak # <u>color</u>              | **hex code** w/o `#` or **css color**                                                                        |
| `currStreakLabel`          | Current streak label <u>color</u>                    | **hex code** w/o `#` or **css color**                                                                        |
| `sideLabels`               | Total and longest streak labels                      | **hex code** w/o `#` or **css color**                                                                        |
| `dates`                    | Date range text <u>color</u>                         | **hex code** w/o `#` or **css color**                                                                        |
| `excludeDaysLabel`         | Excluded days of the week text <u>color</u>          | **hex code** w/o `#` or **css color**                                                                        |
| `date_format`              | Date format pattern or empty for locale format       | [📅 Date Formats](https://github.com/DenverCoder1/github-readme-streak-stats/tree/main#-date-formats)        |
| `locale`                   | Locale for labels and numbers (Default: `en`)        | ISO 639-1 code - [🗪 Locales](https://github.com/DenverCoder1/github-readme-streak-stats/tree/main#-locales) |
| `type`                     | Output format (Default: `svg`)                       | Current options: `svg`, `png` or `json`                                                                      |
| `mode`                     | Streak mode (Default: `daily`)                       | `daily` or `weekly` (once per Sun-Sat week)                                                                  |
| `exclude_days`             | List of days of the week to exclude from streaks     | Comma-separated list of day abbreviations e.g. `Sun,Sat`                                                     |
| `disable_animations`       | Disable SVG animations (Default: `false`)            | `true` or `false`                                                                                            |
| `card_width`               | Width of the card in pixels (Default: `495`)         | Positive integer, min width is 100px per col                                                                 |
| `card_height`              | Height of the card in pixels (Default: `195`)        | Positive integer, min height is 170px                                                                        |
| `hide_total_contributions` | Hide the total contributions (Default: `false`)      | `true` or `false`                                                                                            |
| `hide_current_streak`      | Hide the current streak (Default: `false`)           | `true` or `false`                                                                                            |
| `hide_longest_streak`      | Hide the longest streak (Default: `false`)           | `true` or `false`                                                                                            |
| `starting_year`            | Starting year of contributions                       | Integer, must be `2005` or later.
Default: your account creation year.                                       |

undefined

### Theme


[List of all available themes](https://github.com/DenverCoder1/github-readme-streak-stats/blob/main/docs/themes.md)



### Final example



{% raw %}
```markdown
<img src="https://github-readme-streak-stats.herokuapp.com?user=rebedy&theme=shadow_green&hide_border=true&show_icons=true" alt="GitHub Streak" />
```
{% endraw %}




## GitHub Stats Card


---


Just copy and paste this into your markdown!


Don’t forget to change the `?username=` value to your GitHub username.



{% raw %}
```markdown
<img align="center" src="https://github-readme-stats.vercel.app/api?username=rebedy" />
```
{% endraw %}




### **Showing icons**


You can enable icons by passing `&show_icons=true` in the query parameter.



### Themes


There are inbuilt themes and you can use them with `&theme={theme_name}` parameter.


**All inbuilt themes:**  [Available themes](https://github.com/anuraghazra/github-readme-stats/blob/master/themes/README.md) 


![1](/assets/img/2024-06-03-Github-Profile-[2]:-GitHub-Stats.md/1.png)



### **Customization**


You can customize the appearance of all your cards however you wish with URL parameters.


**Common Options**


| **Name**        | **Description**                                                                                                                | **Type**                                           | **Default value** |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------- | ----------------- |
| `title_color`   | Card's title color.                                                                                                            | string (hex color)                                 | `2f80ed`          |
| `text_color`    | Body text color.                                                                                                               | string (hex color)                                 | `434d58`          |
| `icon_color`    | Icons color if available.                                                                                                      | string (hex color)                                 | `4c71f2`          |
| `border_color`  | Card's border color. 
Can’t do when `hide_bordee:T`.                                                                           | string (hex color)                                 | `e4e2e2`          |
| `bg_color`      | Card's background color.                                                                                                       | string (hex color or
a gradient:_angle,start,end_) | `fffefe`          |
| `hide_border`   | Hides the card's border.                                                                                                       | boolean                                            | `false`           |
| `theme`         | Name of the theme.
[all available themes](https://github.com/anuraghazra/github-readme-stats/blob/master/themes/README.md).    | enum                                               | `default`         |
| `cache_seconds` | Sets the cache header manually (min: 21600, max: 86400).                                                                       | integer                                            | `21600`           |
| `locale`        | Sets the language in the card.
Available locales [here](https://github.com/anuraghazra/github-readme-stats#available-locales). | enum                                               | `en`              |
| `border_radius` | Corner rounding on the card.                                                                                                   | number                                             | `4.5`             |

undefined

### Final example



{% raw %}
```markdown
<img align="center" src="https://github-readme-stats.vercel.app/api?username=rebedy&include_all_commits=true&rank_icon=github&theme=shadow_green&hide_border=true&no-bg=true&no-frame=true&show_icons=true" />
```
{% endraw %}




## Result


---


To sum up, something similar to the following code will be in your `{username}/README.md`.



{% raw %}
```markdown
<!-- Github stats -->

<h3 align="left">Github Stats 📈</h3>

<table border="0">
<tr border="0">
<td width="50%" align="center">
<img align="center" src="https://github-readme-stats.vercel.app/api/top-langs/?username=rebedy&layout=donut-vertical&theme=shadow_green&hide_border=true&no-bg=true&no-frame=true&show_icons=true&langs_count=8"/>
</td>

<td width="50%" align="center">
<img src="https://github-readme-streak-stats.herokuapp.com?user=rebedy&theme=shadow_green&hide_border=true&show_icons=true" alt="GitHub Streak" /></a>
<img align="center" src="https://github-readme-stats.vercel.app/api?username=rebedy&include_all_commits=true&rank_icon=github&theme=shadow_green&hide_border=true&no-bg=true&no-frame=true&show_icons=true" />
</td>
</tr>
</table>

<br>
```
{% endraw %}




## References


---

- [https://github.com/anuraghazra/github-readme-stats](https://github.com/anuraghazra/github-readme-stats)
- [https://github-readme-streak-stats.herokuapp.com](https://github-readme-streak-stats.herokuapp.com/)
