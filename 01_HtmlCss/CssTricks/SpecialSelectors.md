# Css special selectors
There are multiple special (maybe we can call them advanced) css selectors beside class selector `.`, id selector `#` and element selectors.


## universal selector: `*`
This selects EVERYTHING. Every single thing
(except ::before and ::after...).



```css
*, *::before, *::after {
  margin:0;
  padding:0;
  box-sizing:border-box;
}

#someElement *{
  background:red;
}
```


## direct children selector: `>`;
This selector only select the direct-children elements.
Deeper child elements won't be affected

```html
<section class="direct-children">
  <h2><span>></span>Direct children</h2>
  <p willselected>You can create selectors like this:</p>
  <code>.direct-children p</code>
  <p>That will select all paragraphs inside of .direct-children</p>
  <div class="example">
    <p willnotselected>But <code>.direct-child > p</code> will not select this paragraph.</p>
  </div>
</section>

```

```css
/* affect [willselected] only */
.direct-children > p{
  font-size:2rem;
}
/* affect both [willselected] [willnotselected]  */
.direct-children  p{
  font-size:2.5em;
}

```

## adjacent sibling: `+`
This selector will affect the target's siblings, it will recalculate once it was interrupted by some else elements.
```html
<section class="adjacent-sibling">
  <h2> <span>+</span>Adjacent sibling</h2>
  <div class="box"></div>
  <div class="box"></div>
  <a href="#">hi</a>
  <div class="box"></div>
  <div class="box"></div>
</section>
```
```css
  .adjacent-sibling .box + .box{
    background:red;
  }
```

## general sibling selector
All the target's siblings will be affected;
```css
  .adjacent-sibling .box ~ .box{
    background:pink;
  }
```

## attribute selector
### Match elements by using it's attribute in `[]` symbol
```css
  [src]{
    background:blue;
  };

  img[src]{
    background:darkblue;
  }
```

### Match specific element by using attribute and value all together
```css
  img[src="./img/logo.png"]{
    width:150px;
    height:auto;
  }
```

### Matches elements with an attr attribute whose value is exactly value, or contains value in its (space separated) list of values.

```css
p[class~="special"]{
  ling-height:2;
}

```
### Matches elements with an attr attribute whose value is exactly value or begins with value immediately followed by a hyphen.

```css
div[lang|="zh"]{
  border:1px solid black;
}

```

### Substring matching selectors
These selectors allow for more advanced matching of substrings inside the value of your attribute. For example, if you had classes of `box-warning `and `box-error `and wanted to match everything that started with the string "box-", you could use `[class^="box-"]` to select them both (or `[class|="box"]` as described in section above).

|   selector   |    example   |    description  |
| ---- | ---- | ---- |
|`[attr^=value]` | `li[class^="box-"]` | Matches elements with an attr attribute (whose name is the value in square brackets), whose value begins with value.|
|`[attr$=value]`|`li[class$="-box"]`| Matches elements with an attr attribute whose value ends with value.|
|`[attr*=value]`|	`li[class*="box"]`|	Matches elements with an attr attribute whose value contains value anywhere within the string.|

```css
li[class^="box-"]{

};

li[class$="-box"]{


};

li[class*="box"]{

};

```



