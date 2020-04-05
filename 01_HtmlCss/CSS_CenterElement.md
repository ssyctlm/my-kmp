# How to center an element

## Place-items
- This method will apply styles on father element. 


> Using the css `place-items` shorthand property sets the `align-items` and `justify-items`properties respectively.If the second value is not set, the first value is also used for it.

```css
/* Keyword values */
place-items: auto center;
place-items: normal start;

/* Positional alignment */
place-items: center normal;
place-items: start auto;
place-items: end normal;
place-items: self-start auto;
place-items: self-end normal;
place-items: flex-start auto;
place-items: flex-end normal;
place-items: left auto;
place-items: right normal;

/* Baseline alignment */
place-items: baseline normal;
place-items: first baseline auto;
place-items: last baseline normal;
place-items: stretch auto;

/* Global values */
place-items: inherit;
place-items: initial;
place-items: unset;


```
- the place-items property can use both in flexbox and grid model.I did an example on [codepen](https://codepen.io/ssyctlm/full/WNvqEaz)

- It will come after `display:grid` or `dispplay:flex`, I think grid is better.

- `display` and `place-items` properties will apply on the father or the ancestor box, to make boxes which nested in it align (center) vertically or horizontaly.
```css
#container {
  height:200px;
  width: 240px;
  place-items: center; /* You can change this value by selecting another option in the list */
  background-color: #8c8c8c;
}

.flex {
  display: flex;
  flex-wrap: wrap;
}

.grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, 50px);
}

```


## Transform & position to center an element
- This method will apply the styles on the target element itself.

```css  
.parent_box{
      position: relative;
  }

.child_box{
    width: 200px;
    height: 100px;
    background: #9ff;
    position: absolute; 
    /* relativ works also */
    top: 50%;
    left: 50%;
    transform: translate( -50%,-50%);
}
```

