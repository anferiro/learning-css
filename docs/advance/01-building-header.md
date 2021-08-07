# Building header

1. open the index.html in a browser
2. open the index.html in the IDE and add the following tag on the body of the html document
``` html 
<header class="header">some text...</header>
```
3. go to the css file style.css and performe a "basic reset"
4. using a universal selector
   > **universal selector:** select every single element in the page and the it will apply the declarations inside of it. 
```css 
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box; // change the box model so that the borders and the paddings are no longer added to the total width or the total height that we specify for the box  
}
```

5. in the body selector let's add fom front properties, and we do it in the body selector bc the font properties usually are inherited. 

we add fon-family lato, and if it's not available then just som sand-ser 
```css
body {
    font-family: "Lato", sans-serif;
    font-weight: 400;
    font-size: 16px;
    line-height: 1.7; //it's going to be 1.7 times bigger than the predefined line-height
    color: #777;
}
```

6. let's finish the basic reset by adding the class, using the class selector as follows: 
```css
.header {
}
```
7. let's add a viewport in the header that takes 95% of the view
```css
.header{
    height: 95vh;
}
```
8. let's ad some background image
```css
.header{
    height: 95vh;
    background-image: url("../img/hero.jpg");
}
```
9. let's try to fix the background image to the viewport
```css
.header{
    height: 95vh;
    background-image: url("../img/hero.jpg");
    background-size: cover;
}
```

10. now we wanto to fix the top of the image as we change the size of teh page using background-position property

```css
.header{
    height: 95vh;
    background-image: url("../img/hero.jpg");
    background-size: cover;
    background-position: top;
}
```

11. in order to put a gradiant in the background we use the background-image proparty again, but as we already used what we do is add a value infron of the previous one as follows: 

```css
.header{
    height: 95vh;
    background-image: linear-gradient(#7ed56f, #28b485), url("../img/hero.jpg");
    background-size: cover;
    background-position: top;
}
```
12. now we need add a opacity in the gradiento so we can pass our color notation to rgb and add the opacity of 80 in every color
```css
.header {
  height: 95vh;
  background-image: linear-gradient(
      to right bottom,
      rgba(126, 213, 111, 0.8),
      rgba(40, 180, 133, 0.8)
    ),
    url("../img/hero.jpg");
  background-size: cover;
  background-position: top;
}
```
13. now we hwant to add a border in the page, and we can do it by adding the padding property in the body selector.

```css
body {
  font-family: "Lato", sans-serif;
  font-weight: 400;
  font-size: 16px;
  line-height: 1.7;
  color: #777;
  padding: 30px;
}
```
14. we want to add a poligon where the image could be see, so wee are going to use the property clip-path and add a poligon in order to do so. 
```css
clip-path: polygon(0 0, 100% 0, 100% 90%, 0 100%);
```

> there is a real good tool to clip the images bennettfeely.com/clippy/

---
## adding the logo

15. first we are going to ad a container using div in our html code

```html
<div class="logo-box">
    <img src="img/logo-white.png" alt="Logo" class="logo">
</div>
```
16. let's put some style, adding the selector for logo-box
```css
    .logo-box {
    position: absolute;
    top: 40px;
    left: 40px;
}
```
as we put an absolute position in this logo-box the reference that browser is going to take it's from its parent, in this case, the header, so in the header selector we add position attribute ans set it up as relative
```css
.header {
  height: 95vh;
  background-image: linear-gradient(
      to right bottom,
      rgba(126, 213, 111, 0.8),
      rgba(40, 180, 133, 0.8)
    ),
    url("../img/hero.jpg");
  background-size: cover;
  background-position: top;
  position: relative;
  clip-path: polygon(0 0, 100% 0, 100% 75vh, 0 100%);
}
```

17. now we want to change the size of the logo, and we are going to do that by addiong some style in the logo class. 

```css
.logo{
    height: 35px
}
```
we set the height up and let that the browser calculate the weight. 

18. now we want to add some text in the middle of the page, so in order to do that we are going to use h1 tag and add som class in it (heading-primary). 
```html
<h1 class="heading-primary">
    <span class="heding-primary-main">Outdors</span> 
    <span class="heding-primary-sub">is where life happends</span> 
</h1>
```
19. so now we are going to ad styles.

```css
.heading-primary{
    color: #fff;
    text-transform: uppercase;
}

.heading-primary-main{
    display: block; //to render the text separated from the other one
    font-size: 60px
    font-weight: 400;
    letter-spacing: 35px
}
.heading-primary-sub{
    display: block;
    font-size: 20px
    font-weight: 700;
    letter-spacing: 11.5px
}
```

20. now we are going to add this text into a container called text-box

```html
<div class="text-box"> 
</div>
```
21. let's put som style on it

```css
.text-box{
    position: absolute
    top: 50%
    left: 50%
}
```

as we can see if we put the conteiner pointing to the 50% from the top and left... what we are going to se is that the first point of the container will be in the middle of the page moving the container to the left and down from where we want it. 

so what we need to do is to translate our position to the middle of the box top and middle of the left box. 

```css
.text-box{
    position: absolute;
    top: 50%;
    left: 50%;
    transfrom: translate(-50%, -50%);
}
```