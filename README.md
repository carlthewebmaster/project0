# Project 0

Web Programming with Python and JavaScript

Author: Carl Leubsdorf, Jr.

## Overview

This website contains information about Carl's music interests.


Project Requirements:
> Your website must contain at least four different .html pages, and it should be possible to get from any page on your website to any other page by following one or more hyperlinks.

There are four pages on the site:
* `index.html` - Home page with information on some musical genres that Carl likes.
* `instruments.html` - Information on some of Carl's musical instruments.
* `gear.html` - A listing of some of Carl's amplifiers and other gadgets.
* `videos.html` - A few video and audio clips.

> Your website must include at least one list (ordered or unordered), at least one table, and at least one image.

* The homepage contains an unordered list and an image.
* The `gear.html` page contains a table.

> Your website must have at least one stylesheet file.

* See `style.css` and `style.scss`

> Your stylesheet(s) must use at least five different CSS properties, and at least five different types of CSS selectors. You must use the #id selector at least once, and the .class selector at least once.

Properties used:
1. `font-size`, `font-weight`
2. `padding-top`, `padding-left`, `padding-right`
3. `list-style-type`
4. `float`
5. `border-top`, `border-bottom`

Selectors used:

1. element
```
body {
      font-size: 18px;
      padding-top: 55px;
      padding-left: 10px;
      padding-right: 10px;
}
```
2. child element (space)
```
div ul {
  list-style-type: square;
}
```

3. ID (#)
```
#image-carl {
  float: right;
  padding: 16px;
}
```

4. class
5. pseudo element (`visited`)
```
.nav-item {
  a {color: $sitelink;}
  a:visited {color: $sitelinkvisited;}
  a:hover {color: $sitelinkhover;}
}
```

6. direct descendant element (>)
```
blockquote > ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
}
```


7. attribute 
```
a[target="_blank"]:after {
  content: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAAQElEQVR42qXKwQkAIAxDUUdxtO6/RBQkQZvSi8I/pL4BoGw/XPkh4XigPmsUgh0626AjRsgxHTkUThsG2T/sIlzdTsp52kSS1wAAAABJRU5ErkJggg==);
    margin: 0 3px 0 5px;
}
```

> Your stylesheet(s) must include at least one mobile-responsive @media query, such that something about the styling changes for smaller screens.

The page uses Bootstrap media styles to rearrange the list of genres and links on the home page (switching from a column layout to stacked containers).

On smaller screens, the headings disappear, so I use the following `@media` query to apply a different font weight and color to the name of the Genre:
```
@media (min-width: 500px) {
.tablebox-data-genre {
    font-weight: normal;
}
}
@media (max-width: 499px) {
  .tablebox-data-genre {
      font-weight: bold;
      color: seagreen;
  }
}
```

> You must use Bootstrap 4 on your website, taking advantage of at least one Bootstrap component, and using at least two Bootstrap columns for layout purposes using Bootstrap’s grid model.

* Bootstrap 4 is installed:
```
<link rel="stylesheet"
   href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css"
   integrity="sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm" crossorigin="anonymous">
```

* The `navbar` and `nav` components are used to create the top menu.
`<nav class="navbar bg-dark fixed-top">`
``<ul class="nav justify-content-end">``

* `row` and `column` are used to lay out a table on the home page, including a 1/2 page width for the center column:
```
<div class="col-sm tablebox-data tablebox-data-genre">
  <span class="tablebox-data-genre">Grateful Dead</span>
</div>
<div class="col-sm-6 tablebox-data">
  I've always liked improvisational music, rock, and blues, and
[...snip...]
  music.  I've definitely seen GD/D&amp;C  more in concert than any other band.
</div>
<div class="col-sm tablebox-data">
  <blockquote><ul><li><a target=_blank href="https://www.youtube.com/watch?v=-nztDwb8RZc">Eyes of the World</a></li>
    <li><a target=_blank href="https://www.youtube.com/watch?v=_h8bRDoc04g">Goin' Down the Road Feeling Bad</a></li></ul></blockquote>
</div>
</div>
```

> Your stylesheets must use at least one SCSS variable, at least one example of SCSS nesting, and at least one use of SCSS inheritance.

* Variables are used to set link colors for the navigation:
```
/* variables */
$sitelink: yellow;
$sitelinkvisited: khaki;
$sitelinkhover: red;
```

* Nesting example for navbar links (also showing use of variables):
```
.nav-item {
  a {color: $sitelink;}
  a:visited {color: $sitelinkvisited;}
  a:hover {color: $sitelinkhover;}
}
```

* Inheritance: `tablebox-header` and `tablebox-data` extend `tablebox`

```
%tablebox {
  border-top: 1px solid #dee2e6;
  padding: 12px;

}
.tablebox-header {
  @extend %tablebox;
  border-bottom: 2px solid #dee2e6;
  font-weight: bold;
  vertical-align: bottom;
  }

.tablebox-data {
  @extend %tablebox;
  border-bottom: 1px solid #dee2e6;
  vertical-align: top;
  }
  ```
