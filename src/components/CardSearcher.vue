<script>
import { store } from '../store.js';

export default {
    name: 'CardSearcher',
    data() {
        return {
            store,
        };
    }
}
</script>

<template>
    <section class="app-search">
        <div class="container">
            {{ store.searchedStatus }}
            <select @change="$emit('searchPerformed')" v-model="store.searchedStatus">
                <option value="">Scegli l'Archetipo</option>
                <option v-for="archetype in store.archetype" :value="archetype.archetype_name">{{ archetype.archetype_name }}</option>
            </select>
        </div>
    </section>
</template>



<style scoped lang="scss">
    .app-search {
        background-color: #d48f38
    }
    .container {
    width: 80%;
    margin: 0 auto;
    select {
        margin: 20px 0;
        padding: 8px;
        font-size: 12px;
    }
    }

</style>