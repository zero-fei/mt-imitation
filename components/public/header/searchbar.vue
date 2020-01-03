<template>
  <div class='search-panel'>
    <el-row class='m-header-searchbar'>
      <el-col
        :span='3'
        class='left'
      >
        <img
          alt='美团'
          src='https://s0.meituan.net/bs/fe-web-meituan/fa5f0f0/img/logo.png'
        />
      </el-col>
      <el-col
        :span='15'
        class='center'
      >
        <div class='wrapper'>
          <el-input
            @blur='blur'
            @focus='focus'
            @input='input'
            placeholder='搜索商家或地点'
            v-model='search'
          ></el-input>
          <button class='el-button el-button--primary'>
            <i class='el-icon-search' />
          </button>
          <dl
            class='hotPlace'
            v-if='isHotPlace'
          >
            <dt>热门搜索</dt>
            <dd
              :key='index'
              v-for='(item, index) in hostPlace'
            >{{ item }}</dd>
          </dl>
          <dl
            class='searchList'
            v-if='isSearchList'
          >
            <dd
              :key='index'
              v-for='(item, index) in searchList'
            >{{ item }}</dd>
          </dl>
        </div>
        <p class='suggset'>
          <a href='#'>故宫博物院</a>
          <a href='#'>故宫博物院</a>
          <a href='#'>故宫博物院</a>
          <a href='#'>故宫博物院</a>
          <a href='#'>故宫博物院</a>
          <a href='#'>故宫博物院</a>
        </p>
        <ul class='nav'>
          <li>
            <nuxt-link
              class='takeout'
              to='/'
            >美团外卖</nuxt-link>
          </li>
          <li>
            <nuxt-link
              class='moive'
              to='/'
            >猫眼电影</nuxt-link>
          </li>
          <li>
            <nuxt-link
              class='hotel'
              to='/'
            >美团酒店</nuxt-link>
          </li>
          <li>
            <nuxt-link
              class='apartment'
              to='/'
            >民宿/公寓</nuxt-link>
          </li>
          <li>
            <nuxt-link
              class='business'
              to='/'
            >商家入住</nuxt-link>
          </li>
        </ul>
      </el-col>
      <el-col
        :span='6'
        class='right'
      >
        <ul class='security'>
          <li>
            <i class='refund' />
            <p class='txt'>随时退</p>
          </li>
          <li>
            <i class='single' />
            <p class='txt'>不满意免单</p>
          </li>
          <li>
            <i class='overdue' />
            <p class='txt'>过期退</p>
          </li>
        </ul>
      </el-col>
    </el-row>
  </div>
</template>


<script>
export default {
  data () {
    return {
      isFocus: false,
      search: '',
      hostPlace: ['火锅', '火锅', '火锅', '火锅'],
      searchList: []
    }
  },
  computed: {
    isHotPlace: function () {
      return this.isFocus && !this.search
    },
    isSearchList: function () {
      return this.isFocus && !!this.search
    }
  },
  methods: {
    focus: function () {
      this.isFocus = true
    },
    blur: function () {
      const self = this;
      setTimeout(function () {
        self.isFocus = false
      }, 200)
    },
    input: function () {
      console.info('input')
    }
  }
}
</script>

<style lang="scss">
</style>