# Custom Data attribute and js manipulation

We can custom the `data` attribute of elements to pass some parameters to JavaScript functions to achieve some specific unique features.


```html
  <div class="sample" data-rate = '8'> Data Attribute</div>
  <!-- if the keyword after 'data-' contains cplital Characters.When we acquire it's value we will lower case it's keyword-->
  <div class="sample1" data-rateX = '10'> Data AttributeX</div>
  

```

```javascript
  var sample = document.queryselector('sample');
  var getCustomDynamicDate = sample.dataset.rate; // it would be 8


  var sample1 = document.queryselector('sample1');
  var getCustomDynamicDate = sample1.dataset.ratex; // it would be 10. 
  //Notice the key of dataset of spample1 is lower-cased

```