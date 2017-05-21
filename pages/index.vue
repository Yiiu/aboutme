<template>
    <div class="main">
        <Scroll>
            <ScrollList @start="start" @end="end">
                <Info :start="arr[0]"/>
            </ScrollList>
            <ScrollList @start="start" @end="end">
                <Project :start="arr[1]"/>
            </ScrollList>
        </Scroll>
    </div>
</template>
<script>
    import Info from '~components/Info.vue'
    import Project from '~components/Project.vue'
    import Scroll from '~components/Scroll.vue'
    import ScrollList from '~components/Scroll-list.vue'

    export default {
        components: {
            Info,
            Project,
            Scroll,
            ScrollList
        },
        data () {
            return {
                arr: [false, false]
            }
        },
        methods: {
            start (from, to) {
                if (!from) {
                    this.$set(this.arr, to - 1, true)
                    this.arr[to - 1] = true
                } else {
                    this.$set(this.arr, from - 1, false)
                }
            },
            end (from, to) {
                this.$set(this.arr, to - 1, true)
            }
        }
    }
</script>
