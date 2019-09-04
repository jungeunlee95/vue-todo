<template>
  <div id="app">
    <TodoHeader></TodoHeader>
    <TodoInput v-on:addTodo="addTodo"></TodoInput>
                                          <!-- v-on:removeTodo약식 -->
    <TodoList v-bind:propsdata="todoItems" @removeTodo="removeTodo"></TodoList>
    <TodoFooter v-on:removeAll="clearAll"></TodoFooter>
  </div>
</template>

<script>
    import TodoHeader from "./components/TodoHeader";
    import TodoList from "./components/TodoList";
    import TodoInput from "./components/TodoInput";
    import TodoFooter from "./components/TodoFooter";

    export default {
        data() {
            return {
                todoItems: []
            }
        },
        components: {
            'TodoHeader': TodoHeader,
            'TodoInput': TodoInput,
            'TodoList': TodoList,
            'TodoFooter': TodoFooter,
        },
        created() {
            if (localStorage.length > 0) {
                for (var i = 0; i < localStorage.length; i++) {
                    this.todoItems.push(localStorage.key(i))
                }
            }
        },
        methods: {
            addTodo(todoItem) {
                localStorage.setItem(todoItem, todoItem);
                this.todoItems.push(todoItem);
            },
            clearAll() {
                localStorage.clear();
                this.todoItems = [];
                alert("모든 할일 목록이 삭제되었습니다.")
            },
            removeTodo(todoItem, index){
                localStorage.removeItem(todoItem);
                this.todoItems.splice(index, 1); // 배열의 특정 인덱스 삭제
            }
        }
    }
</script>

<style>
  body {
    text-align: center;
    background-color: #F6F6F8;
  }

  input {
    border-style: groove;
    width: 200px;
  }

  button {
    border-style: groove;
  }

  .shadow {
    box-shadow: 5px 10px 10px rgba(0, 0, 0, 0.03);
  }
</style>
