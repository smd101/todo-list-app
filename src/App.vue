<template>
  <div id="app">
    <h1>My Pomodoro App</h1>
    <div>
      <Clock class="clock" location="TOKYO" :diff="0" />
    </div>
    <div>
      <label for="title">タイトル：</label>
      <input type="text" v-model="title" placeholder="タイトル">
    </div>
    <div>
      <label for="body">内容：</label>
      <textarea v-model="body" placeholder="内容"></textarea>
    </div>
    <div>
      <input type="submit" value="追加" @click="addList">
    </div>
    <ul v-for="(list, i) in lists" v-bind:key="i">
      <li>id: {{i}}, title: {{ list.title }} <button @click="deleteList(i)">削除</button></li>
    </ul>
    <pre>
      {{$data}}
    </pre>
  </div>
</template>

<script>
import Clock from "@/components/Clock"

export default {
  components: {
    Clock,
  },
  data: () => ({
    lists: [
      {title: 'mytodo', body: 'contentcontent'},
      {title: 'hogehoge', body: 'yuuyuuyuyuyu'}
    ],
    title: '',
    body: ''
  }),
  methods: {
    // リストの追加
    addList: function(){
      if(this.title === '' || this.body === '') return

      this.lists.push({title: this.title, body: this.body})
      this.title = ''
      this.body = ''
    },
    // リストの削除
    deleteList: function(i){
      this.lists.splice(i,1)
    }
  }
};
</script>

<style scoped>
.clock {
  width: 80%;
  max-width: 500px;
  margin: 30px auto;
}
</style>

<style>
html {
  font-size: 62.5%;
}
body {
  margin: 0;
}
p {
  margin: 0;
}
</style>