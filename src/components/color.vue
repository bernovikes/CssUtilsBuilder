<template>
    <div>
        <div v-for="item in classList" :class="item" >aaa</div>
<!--        <pre v-highlightjs="css"><code class="css"></code></pre>-->
    </div>
</template>

<script>
    import color from '!!raw-loader!../assets/style/color.scss'
    import '../assets/style/color.scss'
    export default {
        name: "color",
        data() {
            return {
                css: color,
                classList:[]
            }
        },
        mounted() {
            // const css = CSSJSON.toJSON(this.css)
            this.classList = this.css.match(/.*[{]/g)
            this.classList = this.classList.map(item => {
                item = item.replace(/{/g,'').trim().replace(/[.]/g,'')
                return item ;
            })
        }
    }
</script>
