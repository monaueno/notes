# notes
These are my notes I can use for CS 260

## 9/16

go over command lines

## 9/18

### HTML


<html lang="en">
  lang = attribute
  "en" = attribute value
</html>

### Title:
<head> 
</head>

### Body:
<body>
  <p>Hello world</p> (paragraph tags)
</body>

### Another type of attribute: images
<img alt = "beach"
src="https://images.pexels.com/photos/21787/pexels-photo.jpg?w=600&h=300"/>
can insert width and height of an image, usually after the ?

### link references 

#### absolute:
<a href="https://cs260.click/profile.png">

#### Relative:
<a href="profile.png" />

### elements:
div (block division of content

span (inline span of content

h<1-9> (Text heading. From h1, the highest level)

p

table

ol,ul (ordered & unordered lists

a (anchor the text to a hyperlink)

img

9/23

#CSS

p {
  color:red;
}
(changes all the paragraphs red)

p {
  color:red;
  animation-duration: 3s;
  animation-name: slidein;
  animation-iteration-count: infinite;
}

@keyframes slidein {
  from {
    margin-left: 100%;
    width: 300%;
  }

  75% {
    font-size: 300%;
    margin-left: 25%;
    width: 150%;
  }

  to {
    margin-left: 0%;
    width: 100%;
  }
}
(add animation)

<div class="box"></div> (HTML)

.box {
  background-color: rebeccapurple;
  border-radius: 10px;
  width: 100px;
  height: 100px;
}
(CSS)

