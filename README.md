# vue_todolist

vue写的todolist练习项目

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

# 总结

1. 组件化编码流程：
    1. 拆分静态组件：组件要按功能点拆分，命名不要与html元素冲突
    2. 实现动态组件：考虑好数据的存放位置，数据一个组件在用还是一些组件在用：
        * 一个组件在用：放在组件自身即可；
        * 一些组件在用：放在他们共同的父组件上；
    3. 实现交互：从绑定事件开始
2. props适用于：
    1. 父组件--》子组件通信
    2. 子组件--》父组件通信（要求父组件先给子组件一个函数）
3. 使用v-model时切记：v-model绑定的值不能是props传过来的值，因为props是不可以修改的
4. props传过来的若是对象类型的值，修改对象中的属性时vue不会报错，但不推荐这样做；