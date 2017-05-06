<template>
    <div class="column">
        <div id="display" class="columns is-multiline is-mobile">
            <div id="screen" class="column is-12 ">
                <video id="video" idVideo="idVideo">
                    <source :src="youtubeUrl()" type="video/mp4">
                </video>
            </div>
            <div id="control-panel" class="column is-12">
                <PanelButton v-on:chooseMethod="getButtonStatus"></PanelButton>
            </div>
        </div>
    </div>
</template>

<script>
    import PanelButton from './PanelButton'
    
    export default {
        name: 'video-controller',
        props: ['isPlaying'],
        data: function() {
            return {
                isPlaying: false,
    
            }
        },
        components: {
            PanelButton
        },
        methods: {
            youtubeUrl() {
                return '//youtube.com/embed/' + this.idVideo + '?modestbranding=0&autohide=1&showinfo=0&rel=0&autoplay=1'
            },
            getButtonStatus() {
    
            }
        }
    
    }
</script>

<style lang="scss" scoped>
#display{
    border: 1px solid #EDEDED;
    #screen {
        height: 415px;
        #video {
            min-height: 100%;
            background-color: #444444;
        }
    }
}
</style>
