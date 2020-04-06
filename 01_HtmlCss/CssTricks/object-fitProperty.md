#[object-fit](https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit)

The object-fit CSS property sets how the content of a replaced element, such as an `<img>` or `<video>`, should be resized to fit its container.

You can alter the alignment of the replaced element's content object within the element's box using the object-position property.

```css 
div img{
  object-fit: fill;
}
div img{
  object-fit: contain;
}
div img{
  object-fit: cover;
}
div img{
  object-fit: none;
}
div img{
  object-fit: scale-down;
}

```


>[mdn specification](https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit)