<template lang="pug">
    Layout
        article
        h1 {{ $page.blogPost.title }}
        g-image(:src="$page.blogPost.image")
        div(v-html="$page.blogPost.content")
        p {{ $page.blogPost.date }}
</template>

<page-query>
    query Post ($path: String!) {
        blogPost (path: $path) {
            title,
            content,
            date (format: "Do MMM YYYY")
            tags,
            image (height: 400 width: 1000)
        }
    }
</page-query>
