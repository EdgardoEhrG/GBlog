<template lang="pug">
    section
      article(v-for="edge in $static.allBlogPost.edges" :key="edge.node.id")
        div(v-html="edge.node.content")
        p {{ edge.node.date }}
        g-link(:to="`/posts/${edge.node.slug}`") Read More
</template>

<static-query>
    query LatestPost {
        allBlogPost {
            edges {
                node {
                    content,
                    id,
                    date (format: "Do MMM YYYY"),
                    slug
                }
            }
        }
    }
</static-query>
