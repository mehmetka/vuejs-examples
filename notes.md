# Uncategorized notes:

## Install vue-cli
```bash
$ npm install -g @vue/cli@4.5.13
```

## .vue file structure
There are typically three sections in .vue file:

```vue
<template>
    <!-- HTML -->
</template>

<script>
    // Javascript
    // where we export it so that it can be imported elsewhere
</script>

<style>
    /* CSS */
</style>
```

- Template and Script sections are required. Style section is optional
- No browser is going to be able to render a file like this. ".vue" files are compiled by webpack at build time to generate HTML, Javascript and CSS files that the browser can work with.

## Using Shorthand Bindings
use colon(:) instead of typing v-bind -> v-bind:src= -> :src=  
use @ instead of typing v-on: -> v-on:click -> @click=

## Performance
We can add a v-once tag to any element 
```vue
<div v-once class="robot-name">{{selectedRobot.head.title}}</div>
```
When you do this, any bindings inside that element will be evaluated once and then never again (if you dont expect the data to change)

## v-show
It adds ```style="display:none;"```

## v-if
It removes the element completely from the DOM.

## When should we use v-if and when should we use v-show?
If the content that you are showing and hiding is expensive to generate and it's going to be shown and hiddden frequently then you should use v-show.

## Initializing data() fields
It's important that we initialized this variable in the data function. If we don't do it here, Vue won't notice that the data is changing. Vue's change detection works by hooking into the getters and setters of properties in the data function. 
So any data that you are going to want to bind to that's going to change, you need to make sure to initialize it in the data function. Otherwise, Vue won't be able to notice when it's changing.

## Performance warning
You should never use v-if and v-for **on the same element**.  
Vue doc ref: https://v2.vuejs.org/v2/guide/conditional.html#v-if-with-v-for