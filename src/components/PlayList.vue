<template>
    <div id="playlist" class="column">
        <article v-for="video in videos" class="media">
            <figure class="media-left">
                <p class="image is-64x64">
                    <img :src="video.snippet.thumbnails.default.url">
                </p>
            </figure>
            <div class="media-content">
                <div class="content">
                    <p>
                        <strong>{{ video.snippet.title }}</strong>
                    </p>
                </div>
                <nav class="level is-mobile">
                    <div class="level-left">
                        <a class="level-item">
                            <span class="icon is-small">
                                <i class="fa fa-reply"></i>
                            </span>
                        </a>
                    </div>
                    <div class="level-right">
                        <p>
                            {{ video.snippet.publishedAt }}
                        </p>
                    </div>
                </nav>
            </div>
            <div class="media-right">
                <button class="delete"></button>
            </div>
        </article>
    </div>
</template>

<script>
export default {
    name: 'playlist',
    data() {
        return {
            videos: []
        }
    },
    created: function () {
        this.fetchVideosFromYoutube();
    },
    methods: {
        fetchVideosFromYoutube: function () {
            this.$http.get('https://www.googleapis.com/youtube/v3/playlistItems?part=snippet&playlistId=PL3dIVMpwlNmpsfuRFO37xBALGHReOWYwq&key=AIzaSyDC2hJjgy7C97kGS-GfhMK2O1tLg7Wcjhk').then(response => {
                response.body.items.forEach((item) => {
                    this.videos.push(item);
                });
            }, response => {
                // error callback
            });
        }
    },
}
</script>

<style lang="scss">
#playlist {
    margin-left: 70px;
    border: 1px solid #EDEDED;
    .media {
        margin: 10px;
    }
}
</style>