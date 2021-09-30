<template>
  <div class="header">
    <input placeholder="请输入你的任务名称,按回车键确认" @keyup.enter="add"/>
  </div>
  
</template>

<script>
export default {
    name: 'MyHeader',
    props:["add"]
}
</script>

<style>
.header, .list, .footer {
  width: 100%;
  height: auto;
  margin: 0 auto;
  border:1px solid #ccc;
  border-radius: 5px;
}

.header input{
  width: 480px;
  height: 28px;
  font-size: 14px;
  border: 1px solid #ccc;
  border-radius: 4px;
  padding: 4px 7px;
}
</style>