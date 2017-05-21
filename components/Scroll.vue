<template>
    <div class="scroll">
        <div class="main" ref="main" :style="{
            transform: `translate3d(0, ${height}%, 0)`
        }">
            <slot></slot>
        </div>
    </div>
</template>
<script>
    export default {
        name: 'scroll',
        data () {
            return {
                index: 1,
                lock: false,
                old: null,
                startY: null,
                touchAction: null
            }
        },
        mounted () {
            this.$children[this.index - 1].$emit('start', null, this.index)
            this.$nextTick(() => {
                document.addEventListener('mousewheel', this.scroll)
                this.touchEvent()
            })
        },
        methods: {
            scroll (event) {
                if (this.lock) return
                if (event.wheelDeltaY > 0) {
                    this.scrollPrev()
                } else {
                    this.scrollNext()
                }
            },
            scrollNext () {
                if (this.index !== this.length) {
                    this.old = this.index
                    this.$children[this.index - 1].$emit('start', this.old, this.index + 1)
                    this.lock = true
                    this.$refs.main.addEventListener('transitionend', this.end, false)
                    this.index++
                }
            },
            scrollPrev () {
                if (this.index !== 1) {
                    this.old = this.index
                    this.$children[this.index - 1].$emit('start', this.old, this.index - 1)
                    this.lock = true
                    this.$refs.main.addEventListener('transitionend', this.end, false)
                    this.index--
                }
            },
            end (event) {
                this.$refs.main.removeEventListener('transitionend', this.end)
                this.lock = false
                this.$children[this.index - 1].$emit('end', this.old, this.index)
            },
            touchEvent () {
                document.addEventListener('touchstart', this.touchStart)
                document.addEventListener('touchmove', this.touchMove)
                document.addEventListener('touchend', this.touchEnd)
            },
            touchStart (event) {
                event.preventDefault()
                let touch = event.changedTouches[0]
                this.startY = touch.pageY
            },
            touchMove (event) {
                let touch = event.changedTouches[0]
                if (touch.pageY - this.startY > 10) {
                    this.touchAction = 'prev'
                } else if (touch.pageY - this.startY < -10) {
                    this.touchAction = 'next'
                }
            },
            touchEnd () {
                if (this.touchAction === 'prev') {
                    this.scrollPrev()
                } else if (this.touchAction === 'next') {
                    this.scrollNext()
                }
            }
        },
        computed: {
            length () {
                let s = 0
                this.$children.forEach(e => {
                    s++
                })
                return s
            },
            height () {
                return (this.index - 1) * -50
            }
        }
    }
</script>
