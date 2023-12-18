<template lang="">
    <div class="card">
        <img :src="character.image" class="card-img-top" alt="...">
        <div class="card-body">
            <h5 class="card-title">
                {{ character.name }}
            </h5>
            <p class="card-text">
                Species: {{ character.species }} <br>
                Gender: {{ character.gender }} <br>
                Status: {{ character.status }}
            </p>
        </div>
        <ul class="list-group list-group-flush">
            <li class="list-group-item">Origin: {{ character.origin.name }}</li>
            <li class="list-group-item">Location: {{ character.location.name }}</li>
        </ul>
    </div>
</template>
<script>
export default {
    props:{
        character: {
            type: Object,
            required: true
        }
    },
    data() {
        return {

        }
    },
    methods: {
    },
}
</script>
<style lang="scss">
    div.card{
        height: 100%;
    }
</style>