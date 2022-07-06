<template>
  <div>
    <ul>
      <li v-for="(item,index) in $store.getters.tags"
          :key="item.path"
          :class="$route.path===item.path?'bgc':''"
          @click="$router.push(item.path)"
      >
        {{ item.title }}
        <span v-show="$route.path!==item.path" @click.stop="$store.commit('tags/delTag',index)"><close-circle-outlined/></span>
      </li>
    </ul>
  </div>
</template>

<script setup>
import { CloseCircleOutlined } from '@ant-design/icons-vue'</script>
<style lang="scss" scoped>
ul {
  list-style-type: none;
  display: flex;
  padding-top: 2px;
  padding-left: 0;
  cursor: pointer;
}

li {
  border: 1px solid rgb(255, 255, 255);
  height: 25px;
  line-height: 25px;
  font-size: 16px;
  padding: 0 5px;
  margin: 0 5px;
}

.bgc {
  background: rgba(118, 111, 111, 0.85);
  border: 1px solid rgba(23, 23, 23, 0.85);
  color: #fff;
}
</style>
