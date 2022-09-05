<template>
    <div :style="msg.style" class="msg-cont">
        <p>{{ msg.vale }}</p>
    </div>
</template>


<script>
export default {
    name: "MsgComp",
    props:{
        msg:{
            type: Object,
            required:true
        }
    }
}
</script>


<style scoped>
    .msg-cont{
        max-width: 251px;
        padding: 1px;
        margin: auto;
        color: white;
    }
</style>