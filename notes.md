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