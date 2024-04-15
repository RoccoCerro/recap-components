<template>
        <li class="col">
            <div class="name">
                {{ name }}
            </div>
            <div class="image">
                <img :src="image" alt="">
            </div>
        </li>
</template>

<script>
    export default {
        props: {
            name: "string",
            image: "string",
        }
    }
</script>

<style lang="scss" scoped>
@use '../assets/scss/general.scss';

.name{
    font-size: large;
    font-weight: bold;
    padding: 10px 0;
    color: rgba(0, 0, 0, 0.445);
}
</style>