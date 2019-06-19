<template>
  <div class="m-istyle">
    <dl>
      <dt>有格调</dt>
      <dd
        @mouseover="hover"
        :class="{active:kind==='all'}"
        kind="all"
      >全部</dd>
      <dd
        @mouseover="hover"
        :class="{active:kind==='part'}"
        kind="part"
      >约会聚餐</dd>
      <dd
        @mouseover="hover"
        :class="{active:kind==='spa'}"
        kind="spa"
      >丽人SPA</dd>
      <dd
        @mouseover="hover"
        :class="{active:kind==='movie'}"
        kind="movie"
      >电影演出</dd>
      <dd
        @mouseover="hover"
        :class="{active:kind==='travel'}"
        kind="travel"
      >品质出游</dd>
    </dl>
    <ul class="ibody">
      <li
        v-for="(item,index) in cur"
        :key="index"
      >
        <el-card :body-style="{ padding: '0px' }">
          <img src="https://shadow.elemecdn.com/app/element/hamburger.9cf7b091-55e9-11e9-a976-7f4d0b07eef6.png" class="image">
          <ul class="cbody">
            <li class="title">{{ item.title }}</li>
            <li class="pos"><span>{{ item.pos }}</span></li>
            <li class="price">￥<em>{{ item.price }}</em><span>/起</span></li>
          </ul>
        </el-card>
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    data(){
      return {
        kind:'all',
        list:{
          all: [
            {
              title:"必胜客",
              pos:"（台江万达店）",
              price:"177"
            },
            {
              title:"必胜客",
              pos:"（台江万达店）",
              price:"177"
            },
            {
              title:"必胜客",
              pos:"（台江万达店）",
              price:"177"
            },
            {
              title:"必胜客",
              pos:"（台江万达店）",
              price:"177"
            },
            {
              title:"必胜客",
              pos:"（台江万达店）",
              price:"177"
            },
            {
              title:"必胜客",
              pos:"（台江万达店）",
              price:"177"
            }
          ],
          part: [
            {
              title:"后来音乐餐吧",
              pos:"（台江万达店）",
              price:"177"
            }
          ],
          spa: [],
          movie: [],
          travel: []
        }
      }
    },
    computed:{
      cur(){
        return this.list[this.kind]
      }
    },
    methods:{
      hover(e){
       this.kind = e.target.getAttribute('kind')
      }
    }
  }
</script>

<style lang="scss">
  @import "@/assets/css/index/artistic.scss";
</style>
