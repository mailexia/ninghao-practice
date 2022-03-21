<template>
  <h3>{{name}}</h3>
  <h4>{{id}}</h4>
  <button v-on:click="resetName">重置</button>
  <button @click='setName'>设置</button>
  <div class='menu'>
  <div :class="{active: currentItem === index}"
       v-for='(post,index) in postlist' :key='index'
      @click='currentItem= index'>
    {{post.content}} - {{post.author}}
  </div>
  </div>
</template>

<script>
export default {
  name: 'app',

  data: function() {
    return {
      name: 'ninghao',
      id: 3,
      currentItem:0,
      postlist:[
        {
          id:1,
          content:"第一行内容",
          author:"作者1"
        },
        {
         id:2,
         content:"第二行内容",
         author: "作者2"
        }
      ]
    };
  },
  watch: {
    name(newName,oldName) {
      console.log(`name 发生了变化：${oldName} -> ${newName}`)
    }
  },
  computed:{
    processStatus(){
      return this.name === 'ninghao' ? '初始化' : '成功设置了数据...';
    }
  },
  created: function() {
    console.log('created');
    this.setName();
  },
  methods: {
    setName: function(){
      setTimeout(() => {
        this.name = '设置名字';
      }, 3000);
    },
    resetName: function(){
      this.name = 'ninghao'
    },
    resetId: function(){
      this.id = 7;
    }
  }

};
</script>

<style scoped>
button {
  margin: 10px;
}
.active{
  font-weight: bold;
  color: blueviolet;
}
.menu{
  display: flex;
  flex-direction: row;
  gap: 16px;
}
</style>