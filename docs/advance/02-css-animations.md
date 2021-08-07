# How to create css animations? 
There are two types of animation in css 

The animation that we are going to try to do is move a text from left to the current positions.
## Using transition property. 
## Using the keyframe at-rule

1. we have to use `@keyframes` and then we are goning to give it a name. 
```css
@keyframes moveInLeft{

}
```
so, we indicate a state in the animation by declaring a percentage of the time that we want to do something. 

2. The first state is going to happend in the 0% and we are going to say that the element is not see it, so we can use the attribute opacity in 0 in order to do that. 

```css
@keyframes moveInLeft{
    0%{
        opacity: 0;

    }
    100%{
        opacity: 1;
    }
}
```
so the browser is optimized to animate 2 properties opacity and transform. 

using transform we can do all the kind of animations that we need. 

so what we need is to move from the left to the current position, we are going to say that our initial state strat -100px and our final state is 0

```css
@keyframes moveInLeft{
    0%{
        opacity: 0;
        transform: translateX(-100px);

    }
    100%{
        opacity: 1;
        transform: translate(0);
    }
}
```

and the we need to add or setup this annimations to a class, thus we need to set these two properties in the class selected in this case .headin-primary-main

```css
.heading-primary-main{
    animation-name: moveInLeft;
    animation-duration: 5s;
}
```
There are other properties in the annimations taht we can setup. 

### animation-delay
Specifies how long it will take befor exucute the annimation
```css
.heading-primary-main{
    animation-name: moveInLeft;
    animation-duration: 5s;
    animation-delay: 3s;
}
```
### animation-iteration-count
This property define how many times the animation will hapend. 
```css
.heading-primary-main{
    animation-name: moveInLeft;
    animation-duration: 5s;
    
    animation-delay: 3s;
    animation-iteration-count: 3;
}
```

we also can use animation property in order to setup the animation and the parameter ar put in separated by space, so the browser will figure it out which one is the paramater that we are setting up. 

```css
.heading-primary-main{
    animation: moveInLeft 5s 3s 3;
}
```
