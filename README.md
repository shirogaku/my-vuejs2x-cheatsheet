# My Vue.JS 2.x Cheatsheet

## Vue instance

new Vue(option object);  
option object

### el
```
    el: '#root'
```  
> Bind Vue instance with element "id = root"  

### data
```
    data: {  
        greeting: 'Hello',
        count: 1
    }
``` 
> Data in Vue instance can be use in binded element

> e.g.  
> `<h1>{{ greeting }}<h1>`  
> OR  
> `<input v-model="greeting">`

### methods  
```
    methods: {
        addSomething: function(message, event) {  
            return this.cats.push({ name : this.newCat })
        }  
    }
```
> Method is function use with event such as @click or @keyup.enter

### filters  
```
    filters: {
        capitalize: function(value) {
        return value.toUpperCase()
        }
    }
```
> Filter is function use in element interpolation.
> Value in data isn't change.

> e.g.  
> `<span>{{ cat.name | capitalize }}</span>`

***

## Vue directive
### v-model  
> Bind data with Vue instance "data" object.  
> When binded value changed by user input.  
> Data in "data" will also change

### v-if
### v-else-if
### v-else

> Evaluate true or false to show to hide element (Not remain in the DOM)

> e.g.  
> `<div v-if="count === 1">Green</div>`  
> `<div v-else-if="count === 2">Red</div>`  
> `<div v-else>Orange</div>`

### v-show
> Evaluate true or false to show to hide element (Still in the DOM)

> e.g.  
> `<div v-show="count === 1">`

### v-bind:(html attribute)
### :(html attribute)

> Evaluate expression and apply to attribute of element

> e.g.   
> `<button v-bind:disabled="data.length < 2">`  
> OR  
> `:class = "{red: data.length < 2}"`  
> OR  
> `:class = "[data.length < 2 ? 'red' : 'green']"`

### v-text
> Bind text to innerText

> e.g.  
> `<p v-text="email">`

### v-html
> Bind text and render as HTML

>e.g.  
> `<p v-text="value">`  
> and value = `<h1>YOLO</h1>`
> will render "value" as HTML

### v-once
> Render element only once even data is changed by another element.  
> This also apply to sub-element.

> e.g.  
> When data is changed become "aaabbb@gmail"  
> `<p v-once>{{ email }}</p>   << aaabbb@gmail.com`  
> `<p>{{ email }}</p>          << aaabbb@gmail`

### v-on
> Bind event handler to element

> e.g.  
> `<button v-on:click="functionHere('someArgs')">`  
> OR  
> `<button v-on:click.prevent.stop="functionHere">`  
> OR  
> `<button @click="functionHere">`  
> OR  
> `<input v-on:keyup.enter="functionHere">`



### v-for
> Looping through array

> e.g.  
> ```
> data: {  
>    cats : [  
>        { name : 'aaa' }, 
>        { name : 'bbb' },
>        { name : 'ccc' }
>    ]
> }
> ```
> ```
> <ul>
>    <li v-for="cat in cats">{{ cat.name }}</li>
> </ul>
> ```

[From Now](https://youtu.be/4deVCNJq3qc?t=1467)