<template lang="">
    <section id='characters' class="container">
        <!-- <article></article> -->
        <div class="row">
            <article v-for="character in store.charactersList" :key="character.id" class="col-6 col-md-3 col-lg-2 mb-5">
                <SingleCharacter :character="character" />
            </article>
        </div>
    </section>
</template>

<script>
import { store } from '../js/store.js';
import SingleCharacter from './SingleCharacter.vue';

export default {
    data() {
        return {
            store,
        }
    },

    components:{
        SingleCharacter
    },
}
</script>

<style lang="scss">

</style>