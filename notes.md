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

## Using SASS
Install ```npm install node-sass sass-loader --save-dev``` and add ```lang="scss"``` to "style" element.

## Reactivity
- Basically refers to Vue's ability to notice and react to data changes in our app  

Variables in setup function are not automatically wrapped in reactivity
- reactive() -> make objects reactive, it cannot be used to make primitive reactive.
- ref() -> can be used to make objects or primitives reactive
- computed() -> used to execute functions when any of the values in the funciton dependencies change.

## Reactivity Example:
Not reactive:
```vue
<template>
    Count: {{ count }}
    <button @click="increment()">Increment Count</button>
</template>

<script>
export default {
    setup(props) {
        let count = 0;

        const increment = () => count = count + 1; // count is a primitive

        return {
            count,
            increment,
        }
    }
}
</script>
```

Reactive Example:
```vue
<template>
    Count: {{ count }}
    <button @click="increment()">Increment Count</button>
</template>

<script>
import { ref } from 'vue';
export default {
    setup(props) {
        let count = ref(0);

        const increment = () => count.value = count.value + 1; // count is an object not a primitive.

        return {
            count,
            increment,
        }
    }
}
</script>
```

## Difference of ref and reactive
When we use "ref()" to make things reactive, we have to use ".value" (like above), but we don't have to for "reactive()"