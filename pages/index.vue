<template>
    <div class="main">
        <div class="sc" :style="{
            transform: `translate3d(0, ${y}%, 0)`
        }">
            <Info></Info>
            <Project></Project>
        </div>
    </div>
</template>
<style lang="less" scoped>
    .main {
        height: 100vh;
        overflow: hidden;
    }
    section.container {
        position: relative;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        min-height: 100vh;
        height: 100vh;
        overflow: hidden;
    }
    .sc {
        transition: .8s cubic-bezier(.86,0,.07,1) all;
        will-change: transform;
    }
</style>
<script>
    import Info from '~components/Info.vue'
    import Project from '~components/Project.vue'

    export default {
        components: {
            Info,
            Project
        },
        data () {
            return {
                index: 1,
                length: 2,
                y: 0
            }
        },
        mounted () {
            this.$nextTick(() => {
                document.addEventListener('mousewheel', this.scroll)
            })
        },
        methods: {
            scroll (event) {
                if (event.wheelDeltaY > 0) {
                    this.scrollPrev()
                } else {
                    this.scrollNext()
                }
            },
            scrollNext () {
                if (this.index === this.length) {
                    return
                } else {
                    this.y -= 50
                    this.index++
                }
            },
            scrollPrev () {
                if (this.index === 1) {
                    return
                } else {
                    this.y += 50
                    this.index--
                }
            }
        }
    }
</script>
