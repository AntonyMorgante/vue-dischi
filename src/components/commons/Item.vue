<template>
    <div class="item-container">
        <div class="item">
            <div>
                <img :src=img alt="">
            </div>
            <p class="album-title">{{title}}</p>
            <p class="album-author">{{author}}</p>
            <p class="album-release">{{release}}</p>
        </div>
    </div>
</template>

<script>
export default {
    name: "Item",
    props: {
        img : String,
        title: String,
        author: String,
        release: String
    }
}
</script>


<style lang="scss" scoped>
@import "../../assets/global.scss";
    .item-container{
        flex-basis:calc(100% / 6);
        margin: 15px 10px;
        background-color: $item-background;
    }

    .item{
        width:80%;
        margin: 20px auto;
        text-transform: uppercase;
        text-align: center;

        img{
            width:100%;
        }
    }

    .album-title{
        color:white;
        font-size:20px;
        font-weight: bold;
    }

    .album-author,
    .album-release{
        color: $secondary-color;
    }

    .album-release{
        font-size: 13px;
    }
</style>