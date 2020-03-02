# Floats

Float is another property which you can use to position elements on your page. There are only 3 possible float properties (other than inherit).

* Left
* Right
* None

Floating is mainly used to move things either to the left of right of its parent container.  
```css 
#element{
    float: right;
}
```
This example would be for floating an element to the right of its container.  

### Layout
Floats are commonly used in layout design to move elements so they are inline with each other.  
Elements which are floated and are in the same container will move next to each other rather than stack on top of each other. So using floats, you can now layout your website to have multiple elements in the same line.  

```html 
<div class="container">
    <div class="column"></div>
    <div class="column"></div>
</div>
```
```css 
.container{
    width: 1000px;
}
.column{
    width: 500px;
    float: left;
}
```
This example would give us two even columns inside of the container.

### Clearing
One issue that will occur when you float elements is that other elements will either go underneath them, or they will warp around them. This works well for text wrapping around an image, but doesn't for other situations (download the repo and see what can happen when you don't use clear). Floating elements also mess up the height of the parent containers as they don't acknowledge floating elements when deciding what their height would be if you aren't setting it yourself.  

What we need to do is clear our floats so other elements don't wrap around them. 
```css 
.clear{
    clear: left;
}
```
This example will prevent any left floating elements from floating next to this element. There are 3 options for floating and you should match what type of float you are using.  
* Left
* Right
* Both (this will stop either left or right flosts)

##### Clearfix hack
Something you will see is what is called the clearfix hax. This will help any floating elements from messing up your layout of your site.  
The clearfix hack requires you to put all floating elements inside of a container and using the Pseduo-Element ::after, clear both of your floats by creating a 0px height barrier to stop any floats.
```html 
<div class="container">
    <div class="column"></div>
    <div class="column"></div>
</div>
```
```css 
.container{
    width: 1000px;
}
.container::after{
    /* You need to use all 3 of these properties for it to work. */
    clear: both;
    display: block;
    content: '';
}
.column{
    width: 500px;
    float: left;
}
```

