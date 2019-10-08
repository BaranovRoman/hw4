<template>
    <div class="form-group" v-for="(inp, index) in answers" :key="index">
        <input type="checkbox" :value="inp" v-model="b"> {{ inp }}
    </div>
</template>

<script>
export default {
    data(){
        return {
            answers: ['div', 'a', 'span', 'table']
        }
    }
}
</script>


<style scoped>

</style>
