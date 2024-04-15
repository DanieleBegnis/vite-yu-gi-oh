<script>
export default {
    name: 'YugiCard',
    props: {
        cardInfo: Object
    }
}
</script>

<template>
    <div class="single-card">
        <div class="image">
            <img src="https://images.ygoprodeck.com/images/cards_small/34541863.jpg" alt="">
        </div>
        <h3 class="card-name">{{ cardInfo.name }}</h3>
        <p>{{ cardInfo.archetype }}</p>
    </div>
</template>

<style scoped lang="scss">
    .single-card {
        width: calc((100% / 5) - 30px);
        text-align: center;
        margin: 15px;
        background-color: #d48f38;
        img {
            width: 100%;
        }
        .card-name {
            color: #fff;
            margin: 12px 0;
        }
        p {
            margin-bottom: 6px;
        }
    }

</style>