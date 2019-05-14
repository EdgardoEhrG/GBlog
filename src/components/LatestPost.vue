<template lang="pug">
    div.article-container
      article(v-for="edge in $static.allBlogPost.edges" :key="edge.node.id")
        h2 {{ edge.node.title }}
        div(v-html="edge.node.content")
        p {{ edge.node.date }}
        g-link(:to="`/posts/${edge.node.slug}`") Read More
</template>

<static-query>
    query LatestPost {
        allBlogPost {
            edges {
                node {
                    title,
                    content,
                    id,
                    date (format: "Do MMM YYYY"),
                    slug
                }
            }
        }
    }
</static-query>

<style lang="scss" scoped>

.article-container {
    article {
        margin: 30px 0;

        h2 {
            margin: 10px 0;
        }

        p {
            margin: 10px 0;
        }
    }
}

</style>

