# Margin and Padding interactions
## 1. collapsing margings
Assume we have a wraper box under which nested two son-boxes. 

> Problem 1: Background won't apply on margin area.

  Anytime something has a background you have to give it padding.**Solid rule**.

> problem 2: Margin will collapse.

  If we give the first son box a bottom margin 100px and give the second one 100px on the top. Those 2 margins will merge and it was called **margin collapsing**. The bigger margin will win on this competation.

> problem 3: The first son box will push the whole wrapper downward.

  Because of the **collapsing margin**,  the wrapper's margin and the first son's margin are merging together. So if we apply a bigger margin on the son box than on the wrapper, the whole wrapper will be push away.

   >> solution: give the wrapper box a transparent border; `border: 1px;` or a padding `padding:1px`




