<template>
    <div class="app">
        <h1>Qiita情報の取得</h1>
        <select @change="fetchBlog" v-model="selectedIndex">
            <option v-for="(url, target) in targetInfo" :key="target">{{ target }}</option>
        </select>
        <ul>
            <component v-for="(post, index) in posts" :key="index" :is="targetCard" :item="post" />
		</ul>
    </div>
</template>

<script>
import QiitaItemsCard from "../components/qiita/QiitaItemsCard"
import QiitaTagsCard from "../components/qiita/QiitaTagsCard"

export default {
    components: {
        QiitaItemsCard,
        QiitaTagsCard,
    },
    data() {
        return {
            content: "TEST",
            posts: [],
            targetInfo: {
                "新着記事": {
                    url: "https://qiita.com/api/v2/items",
                    card: "QiitaItemsCard",
                },
                "タグ": {
                    url: "https://qiita.com/api/v2/tags?sort=count",
                    card: "QiitaTagsCard",
                },
            },
            selectedIndex: "",
            targetCard: "",
        }
    },
    methods: {
        async fetchBlog() {
            const selectedTarget = this.$data.selectedIndex
            const targetInfo = this.$data.targetInfo[selectedTarget]

            const response = await this.$axios.$get(targetInfo.url)
            console.log(response)
            this.$data.posts = response
            this.$data.targetCard = targetInfo.card
        }
    },
}
</script>

<style lang="scss">
body {
    background-color: #bdf3f4;
}
</style>