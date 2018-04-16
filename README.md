# Digital :rocket: Future Website

This repository is the [Digital :rocket: Future Community Page](https://jmgama.github.io/Digital-Future/) that is powered by [Jekyll](https://jekyllrb.com/)<img src="http://talk.jekyllrb.com/uploads/jekyllrb/original/1X/8b614a6e66f98a2596bea71530911af993b41747.png" alt="Jekyll icon" width="26px" height="26px"/>, [Amp Project](https://www.ampproject.org/) <img src="https://www.corsia.us/wp-content/uploads/2017/03/amp-icon.jpg" alt="Jekyll icon" width="26px" height="26px"> and [GitHub Pages](https://pages.github.com/) :octocat: with the incredible [Hanuman](https://github.com/samanyougarg/hanuman) theme.

![Digital-Future](https://image.ibb.co/jEu8oH/Screenshot_from_2018_02_26_11_24_21.png)

# Creating Posts and News :memo:

In Digital-Future we give the opportunity that **everyone** can upload any posts or news. Before uploading anything, it needs to be **reviewed** by other administrators to determine if the publication doesn't brake any **rule of content** or it have something inappropriate.

## Rules of publications :cop:

These are some **rules** that all posts or news need to accomplish:

- All the content is **truthful** and extracted from trusty sources _(giving the appropriate credit to the source)_. :bookmark:

## Writing post's :black_nib:

Since the Website is made with Jekyll and Amp, you can create your post using **markdown**. Here you can find a great guide about [writing with markdown :pencil2:](https://guides.github.com/features/mastering-markdown/), but since it uses Amp you would need to see the [Amp documentation](https://www.ampproject.org/docs)  in case of using responsive media like **images, videos, etc**.

**Example:**

**Images:** `<amp-img src="welcome.jpg" alt="Welcome" height="400" width="800"></amp-img>`

**Videos:** `<amp-youtube data-videoid="mGENRKrdoGY" layout="responsive" width="480" height="270"></amp-youtube>`

You can see other posts already published in [\_posts](/_posts/) folder, or see the **examples and tutorials** in the [\_howto](/_howto/) folder to have an idea.

**Remember, if you have any question or something, feel free to open an issue.**

### Using AMP Components
Some AMP components require you to specify external scripts before using them. You can specify these scripts in the head.html file in the includes directory after the already imported scripts and then use these components in any post.

Here are some nice tutorials and recommendations of **how to** write a post the right way and make it reach more people.
- [How to make a good post.](https://masymejor.com/hacer-un-buen-post/)
- [How to write an attractive post.](https://www.40defiebre.com/como-escribir-post/)
- [27 recommendations for writing a post](https://www.40defiebre.com/consejos-escribir-post/)

If you want to know more about the syntax of writing posts, you can read the [Jekyll posts documentation :book:.](https://jekyllrb.com/docs/posts/)

### Post header

All the posts need to have a **header** where you specify the **info** of the post. This needs to be at the top of your **post.md** document

```
---
layout: post
cover: assets/posts/2018-02-23-Google_anuncia_ARCore1.0/cover.png
title: Google Anuncia ARCore 1.0 y Google Lens
date: 2018-02-23T13:09:00.000Z
tags: Google VR AR
author: José Manuel Gama
---
```
- It takes the basic **layout** of a post that gives it the style.
- The **cover** is the image that is going to be used for the publication cover _(this need to be in your images folder of the post, you can see how this work in the **Storing files section**)_.
- The **title** is going to be show above the cover with white letters.
- The **publication date**.
- Some **tags** that relate the post with others.
- The **author** that wrote the post.

### Naming documents

When you write a post or new, the **name of the document** need to be like:

```java
YYYY-MM-DD-name_of_the_post.md
-----------------------------------
Example:
2018-02-26-writing_my_first_post.md
```
### Storing files
The document with the **.md** file where you write the post, need to by **stored** in the [\_posts](/_posts/) folder :open_file_folder:.

If you are using **local images**, you need to create a **new folder** with the name of your post inside [assets/posts](/assets/posts/). Then you can save all your images in your folder.

**Example:** _saving the (cover.png, imagen1.jpg, imagen2.jpg)_
```
assets
    |
    posts
        | ****this is the folder you create with the name of your post****
        2018-02-26-writing_my_first_post
            | ****here is where you store your images****
            cover.png
            imagen1.jpg
            imagen2.jpg
```
