<template>
    <div class="block">
        <b-icon v-on:click="chooseMethod" icon="skip_previous" size="is-medium">
        </b-icon>
        <b-icon v-on:click="chooseMethod" icon="play_arrow" size="is-medium">
        </b-icon>
        <b-icon v-on:click="chooseMethod" icon="skip_next" size="is-medium">
        </b-icon>
    </div>
</template>

<script>
export default {
    name: 'panel-button',
    props: ['btnName'],

    methods: {
        chooseMethod: function () {

            this.$emit('chooseMethod');
        }
    },
}
</script>

<style lang="scss">
.icon {
    cursor: pointer;
}
</style>