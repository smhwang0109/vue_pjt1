<template>
  <div>
      <h1>영화 예고편 검색</h1>
      <input v-model="value" @keypress.enter="onInput" autofocus>
      <button @click="onInput">검색</button>
  </div>
</template>

<script>
export default {
    name: 'VideoSearch',
    methods: {
        onInput() {
            if (this.value){
                this.$emit('input-change', this.value)
                this.value = ''
            }else{
                alert('영화제목을 입력하세요!')
            }
        }
    },
    data(){
        return {
            value:''
        }
    }

}
</script>

<style>

</style>