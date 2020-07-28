<template>
    <li class="card">
        <a class="tag" :href="`https://qiita.com/tags/${item.id.toLowerCase()}`" target="_blank" rel="noopener noreferrer">
            <img :src="item.icon_url">
            <div class="tag_name">{{ item.id }}</div>
        </a>
        <p class="info">記事数: {{ item.items_count }}</p>
    </li>
</template>

<script>
export default {
    props: [
        "item"
    ],
}
</script>

<style scoped lang="scss">
.card {
    width: 90%;
    min-width: 320px;
    position: relative;
    display: inline-block;
    padding: 10px 20px;
    transition: all 0.5s;
    padding-bottom: 5px;
    padding-left: 10px;
    background-color: #FFF;
    border-bottom: 1px solid #e8e8e8;

    &:first-child {
        border-top: 1px solid #e8e8e8;
    }

    .tag {
        color: #000;
        text-decoration-color: #000;
        text-decoration: none;
        font-size: 16px;
        margin-bottom: 4px;
        display: flex;
        justify-content: flex-start;
        align-items: center;

        &:visited {
            color: #777;
            text-decoration-color: #777
        }

        &:hover {
            text-decoration: underline;
        }

        &_name {
            margin-left: 10px;
        }
    }

    .info {
        color: #999;
        font-size: 1.6px;
        .timestamp {
            margin: 0px;
        }
    }
}
</style>