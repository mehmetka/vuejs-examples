# Uncategorized notes:

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

Source: [Vue.js Fundamentals By Jim Cooper](https://app.pluralsight.com/library/courses/vuejs-fundamentals)