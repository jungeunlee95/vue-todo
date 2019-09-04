<template>
  <div class="clearAllContainer">
    <span class="clearAllBtn" @click="clearTodo"> Clear All </span>
  </div>
</template>

<script>
    export default {
        methods:{
            clearTodo() {
                localStorage.clear();
                alert("모든 할일 목록이 삭제되었습니다.")
            }
        }
    }
</script>

<style>
  .clearAllContainer {
    width: 8.5rem;
    height: 50px;
    line-height: 50px;
    background-color: white;
    border-radius: 5px;
    margin: 0 auto;
  }

  .clearAllBtn {
    color: #e20303;
    display: block;
  }
</style>
