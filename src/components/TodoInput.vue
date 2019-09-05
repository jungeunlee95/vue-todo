<template>
  <div class="inputBox shadow container">
    <input type="text" ref="todo" v-model="newTodoItem" placeholder="할 일을 입력하세요."
           v-on:keyup.enter="addTodo">
    <span class="addContainer" v-on:click="addTodo">
        <i class="addBtn fas fa-plus" aria-hidden="true"></i>
    </span>

    <modal v-if="showModal" @close="showModal = false">
      <h3 slot="header"> 경고 </h3> <!--모달 헤더-->
      <span slot="footer" @click="showModal = false"> <!--모달 푸터-->
        할 일을 입력해주세요 !!
        <i class="closeModalBtn fa fa-times" aria-hidden="true"></i>
      </span>
    </modal>
  </div>
</template>

<script>
    import Modal from './common/Modal'

    export default {
        data() {
            return {
                newTodoItem: '',
                showModal : false,
            }
        },
        methods: {
            addTodo() {
                if (this.newTodoItem !== "") {
                    var value = this.newTodoItem && this.newTodoItem.trim();
                    this.$emit('addTodo', value)
                    this.clearInput();
                } else {
                    // alert("할 일을 적어주세요!")
                    this.showModal = !this.showModal;
                }
            },
            clearInput() {
                this.newTodoItem = '';
            }
        },
        watch:{
            showModal: function(){
                this.$refs.todo.focus();
            }
        },
        components: {
            Modal: Modal
        }
    }
</script>

<style>
  input:focus {
    outline: none;
  }

  .inputBox {
    text-align: center;
    background: white;
    height: 50px;
    width: 400px;
    line-height: 50px;
    border-radius: 5px;
    margin: 0 auto;
  }

  .inputBox input {
    border-style: none;
    font-size: 0.9rem;
    width: 300px;
    margin-left: 30px;
  }

  .addContainer {
    float: right;
    background: linear-gradient(to right, #6478FB, #8763FB);
    display: block;
    width: 3rem;
    border-radius: 0 5px 5px 0;
  }

  .addBtn {
    color: white;
    vertical-align: middle;
  }

  .closeModalBtn{
    color:red;
  }
</style>
