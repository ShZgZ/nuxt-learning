<template>
    <li class="card">
        <a class="title" :href="item.url" target="_blank" rel="noopener noreferrer">{{ item.title }}</a>
        <div class="info">
            <span class="timestamp">{{ item.created_at }}</span>
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 564.81 145.68" style="display: inline-block; width: 40px; height: 9.10569px; fill: rgb(153, 153, 153);"><path d="M0 3.85h38.39v106.5h64.16v32H0zM195.41 66.82h71.82q.91 17.84-4 32.35A68.89 68.89 0 01248.71 124a65.49 65.49 0 01-22.9 16 74.08 74.08 0 01-29.17 5.65 78.16 78.16 0 01-54.17-21.32 74.1 74.1 0 01-16.42-23.21 68.08 68.08 0 01-6-28.41 67.7 67.7 0 016-28.42 74.44 74.44 0 0116.42-23.1 76.37 76.37 0 0124.32-15.52 78.92 78.92 0 0184.43 16.06l-25 25A36.52 36.52 0 00213.57 36a37.65 37.65 0 00-31.83-.87 37.7 37.7 0 00-12.08 8.57 40.75 40.75 0 00-8.17 12.91 42.8 42.8 0 00-3 16.22 42.91 42.91 0 003 16.17 40.44 40.44 0 008.17 13 37.4 37.4 0 0012.08 8.57 36.07 36.07 0 0014.9 3.11q14.38 0 22.13-5.35a25.46 25.46 0 0010.31-14.65h-33.77zM319.44 36.21h-36.55v-32h111.18v32h-36.45v106.5h-38.18zM486.82 109l-29.73-44.18v77.89H418.7V4.24h33.83l39 55.09 39.86-55.09h33.42v138.47h-38.38V65.23L496.19 109z"></path></svg>
            <span class="likes_count">{{ item.likes_count }}</span>
        </div>
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

    .title {
        color: #000;
        text-decoration-color: #000;
        text-decoration: none;
        font-size: 16px;
        margin-bottom: 4px;

        &:visited {
            color: #777;
            text-decoration-color: #777
        }

        &:hover {
            text-decoration: underline;
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