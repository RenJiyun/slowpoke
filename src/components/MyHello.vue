<template>
    <el-button @click="onClick">点我</el-button>
</template>

<script>
export default {
    methods: {
        onClick() {
            console.log("-------");
            this.$message("hello");
        }
    }
}
</script>