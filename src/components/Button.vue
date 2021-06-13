<template>
    <!-- App.vue에서 style에 scope를 지정했기때문에 component에서도 style을 가져올 수 있음 -->
    <button 
        @click="onClick()"
        :style="{background: color}" 
        class="btn"
    >{{text}}</button>
</template>

<script>
    export default {
        name: 'Button',
        props: {
            text: String,
            color: String
        },
        methods: {
            onClick() {
                this.$emit('btn-click')
            }
        }
    }
</script>
