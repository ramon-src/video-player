<template>
    <div class="container">
        <div class="columns is-multiline is-mobile">
    
            <VideoController v-bind:idVideo="idVideo"></VideoController>
            <div class="column is-half">
                <PlayList></PlayList>
            </div>
        </div>
        <PlayList></PlayList>
    </div>
</template>

<script>
import VideoController from './VideoController'
import PlayList from './PlayList'

export default {
    name: 'screen',
    components: {
        VideoController,
        PlayList
    }
}
</script>

<style lang="scss" scoped>
.container {
    #screen {
        background-color: #444444;
        height: 400px;
    }
}
</style>