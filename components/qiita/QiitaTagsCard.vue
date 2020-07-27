<template>
    <li class="card">
        <p class="tag">{{ item.id }}</p>
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
    position: relative;
    display: inline-block;
    padding: 10px 20px;
    transition: all 0.5s;
    width: 700px;
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
        margin-top: 0px;
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