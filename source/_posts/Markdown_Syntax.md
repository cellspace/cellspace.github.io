---
title: The syntax of markdown language
date: 2021-05-16
tags: Hexo
categories: Note
archives: 
---

To view the source code of this page, please go to [Raw Page](https://raw.githubusercontent.com/cellspace/cellspace.github.io/hexo/source/_posts/Markdown_Syntax.md).
<!-- more -->
---
# <p align="center"></p> <!-- h1 Title -->  

## **Catalog**  <!--h2 title, and "###" is h3 title ...-->
<!--do not use title-mark("#") in catalog-->
> - [Link](#Link)  
> - [Image](#Image)
> - [Layer](#Layer)
>   - [1. Unordered list](#1-Unordered-list)
>   - [2. Ordered list](#2-Ordered-list)
>   - [3. Expand block](#3-Expand-block)
>   - [4. Reference](#4-Reference)
>   - [5. Todo List](#5-Todo-List)
> - [Paragraph](#Paragraph)
> - [Code](#Code)
> - [Anchor](#Anchor)
> - [Style](#Style)
> - [Table](#Table)
> - [*Extended Syntax*](#Extended-Syntax)

---  
<!--"---" can be replaced with "***" or "___"-->
<br>

## Link

[![Shields](https://img.shields.io/static/v1?label=<Label>&message=<Message>&color=<Color>)](https://shields.io)  

<!--
    Specifying title after link is optinal, separated by space.
    For compatibility, if there is a space in url, fill it with '%20'.
-->
[Baidu](https://www.baidu.com "Baidu")  

<!--reference link-->
[Google][google_main]  
[anon_ref_link][]

[google_main]: https://www.google.com "Google" 
[anon_ref_link]: https://www.bilibili.com

<!--Raw urls and e-mail addresses-->
<https://www.github.com>  
<cellskyspace@gmail.com>  


## Image

![Fail to load the image](/images/favicon.ico "qiongmei") <!--can not specify the dimension of the image-->  
`Note: Image can also use reference link.`

<img src="/images/qiongmei.jpg" width="60" alt="Fail to laod theimage"></img>  

## Layer

#### 1. Unordered list
* first <!--'*' can be replaced with '-' or '+'-->
  * one
  * two
* second
  * once
  * twice

#### 2. Ordered list
1. first <!--space between "1." and text-->
   * nested unordered list
2. second
3. third

#### 3. Expand block
<details>
<summary>Click to expand</summary>

1. content  

        Content Code

</details>  

#### 4. Reference
> reference
> 
> >nested reference
> 
> multi line reference

#### 5. Todo List
- [ ] Todo/Not support
- [x] Done/Support

## Paragraph
For text in one paragraph,  <!--2 spaces in the end of this line-->  
we can use two more space and type enter to create a line break.  

For different paragraphs, we can use a blank line to separate them.  

## Code

For `Emphasize` or `Code in line` use backticks(`).  

For multi-line code, use `tab` or `four spaces` :
<!--Code blocksare normally indented four spaces or one tab. When they’re in a list, indent them eight spaces or two tabs.-->
    $ sudo apt-get update
  
For code block, specify what language in the block after backticks.(e.g. ` ```c++ `)
```c++
#include<isotream>
using namespace std;
int main()
{
    return 0;
}
```

## Anchor

> [anchor](#anchor)  
> [second ancher with the same name](#anchor-1)  
> [1. anchor](#1-anchor)  
> [anchor witch space](#anchor-witch-space)  


* ### anchor 

* ### 1. anchor

* ### anchor witch space  

## Style

*Italic*   <!--'*' can be replaced with '_'-->  
**Bold**  
***ItalicBold***

~~Deprecated~~

<kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>Alt</kbd>

<!--The following items do not work in github-->
<u>Underscore</u>
<table><tr><td bgcolor=black>Background Color</td></tr></table> 
<font face="微软" color="red" size=3 >Font Style</font>

## Table

|  symbol    | function    |
| :---:    | :---:       |   
| `:---`/`---`   | align left / default  |
| `:--:`   | align center|
| `---:`   | align right |

| Project    | Price   |  Count  |
|:--------   | -----:  | :----:  |
| Computer   | \$1600  |   5     |
| Phone      | \$12    |   12    |
| Peripheral | \$1     |  234    |

---  
<br>

## Extended Syntax

### 1. Footnote[^fnConent]  

[^fnConent]: This is the content of footnote. Generally be written at the end of an article.

### 2. Math
<!--For formula in line, use single"$", e.g. $E=mc^2$-->
$$E=mc^2$$  
$$\sum_{i=1}^{n} a_i=0$$  
$$f(x_1, x_2, \ldots, x_n) = x_1^2 + x_2^2 + \cdots + x_n^2$$  

For more expression, please go to [LaTex](http://mohu.org/info/symbols/symbols.htm).  

### 3. Graph
- [Flow Chart](https://www.zybuluo.com/mdeditor?url=https://www.zybuluo.com/static/editor/md-help.markdown#7-%E6%B5%81%E7%A8%8B%E5%9B%BE)  
- [Sequ Graph](https://www.zybuluo.com/mdeditor?url=https://www.zybuluo.com/static/editor/md-help.markdown#8-%E5%BA%8F%E5%88%97%E5%9B%BE)

---
<br>

