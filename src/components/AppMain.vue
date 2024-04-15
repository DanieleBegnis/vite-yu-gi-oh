<script>
import YugiCard from './YugiCard.vue';

export default {
    name: 'AppMain',
    components: {
        YugiCard
    }
}
</script>

<template>
    <section class="cards-list">
        <div class="container">
            <div class="yugi-cards">
                <YugiCard></YugiCard>
                <YugiCard></YugiCard>
                <YugiCard></YugiCard>
                <YugiCard></YugiCard>
                <YugiCard></YugiCard>
                <YugiCard></YugiCard>
                <YugiCard></YugiCard>
                <YugiCard></YugiCard>
            </div>
        </div>
    </section>
</template>

<style scoped lang="scss">
.cards-list {
    background-color: #d48f38;
    padding-top: 24px ;
    padding-bottom: 24px;
}
.container {
    width: 80%;
    margin: 0 auto;
    background-color: #fff;
    .yugi-cards {
        display: flex;
        flex-wrap: wrap;
    }
}
</style>