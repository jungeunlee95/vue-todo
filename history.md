[TOC]

---

# vue-todo

> A Vue.js project  : [예시 사이트](https://vuejstodo-aa185.firebaseapp.com/)

<br>

## 프로젝트 생성

> `$ mkdir vue-todo`
>
> `$ cd vue-todo/`
>
> ```bash
>$ vue init webpack-simple
> 
>? Generate project in current directory? (Y/n) Y
> ? Generate project in current directory? Yes
> ? Project name (vue-todo) 
> ? Project name vue-todo
> ? Project description (A Vue.js project) 
> ? Project description A Vue.js project
> ? Author (jungeunlee95 <leeap1004@gmail.com>)
> ? Author jungeunlee95 <leeap1004@gmail.com>
> ? License (MIT)
> ? License MIT
> ? Use sass? (y/N) N
> ? Use sass? No
> 
> vue-cli · Generated "vue-todo".
> 
> To get started:
> 
>      npm install
>   npm run dev
>    ```
> 

의존성 항목 설치

`npm install vue vue-loader vue-template-compiler webpack webpack-cli webpack-d`

<br>

## index.html link, meta tag 추가

```html
<!--viewport meta tag-->
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<!--font awesome cdn-->
<link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.0.12/css/all.css">

<!--font, favicon settings - favicon generator-->
<link rel="shortcut icon" href="src/assets/favicon.ico" type="image/x-icon">
<link rel="icon" href="src/assets/favicon.ico" type="image/x-icon">
<link href="https://fonts.googleapis.com/css?family=Ubuntu" rel="stylesheet">
```

<br>

## 컴포넌트 생성

- 사용할 컴포넌트는 총 4개.
  1. TodoHeader
  2. TodoInput
  3. TodoList
  4. TodoFooter

> 프로젝트 구조 `>src>components>..`
>
> ![1567563742721](assets/1567563742721.png)

**각각의 컴포넌트 내용 설정** **ex) TodoFooter.vue**

```vue
<template>
  <div>footer</div>
</template>

<script>
    export default {

    }
</script>

<style>

</style>
```

<br>

## App.vue에 컴포넌트 추가

```vue
<template>
  <div id="app">
    <TodoHeader></TodoHeader>
    <TodoInput></TodoInput>
    <TodoList></TodoList>
    <TodoFooter></TodoFooter>
  </div>
</template>

<script>
    import TodoHeader from "./components/TodoHeader";
    import TodoList from "./components/TodoList";
    import TodoInput from "./components/TodoInput";
    import TodoFooter from "./components/TodoFooter";

    export default {
        components: {
            'TodoHeader' : TodoHeader,
            'TodoInput' : TodoInput,
            'TodoList' : TodoList,
            'TodoFooter' : TodoFooter,
        }
    }
</script>

<style>

</style>
```

<br>

## Vue 프로젝트 실행

`npm run dev`

![1567564378957](assets/1567564378957.png)





















