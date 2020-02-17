<template>
  <div class='m-menu'>
    <dl
      @mouseleave='mouseleave'
      class='nav'
    >
      <dt>全部分类</dt>
      <dd
        :key='index'
        @mouseenter='mouseenter'
        v-for='(item, index) in menu'
      >
        <i :class='item.type' />
        {{item.name}}
        <span class='arrow'></span>
      </dd>
    </dl>
    <div
      @mouseenter='sover'
      @mouseleave='sout'
      class='detail'
      v-if='kind'
    >
      <template v-for='(item, index) in curdetail.children'>
        <h4 :key='index'>{{item.title}}</h4>
        <span
          :key='v'
          v-for='v in item.children'
        >{{v}}</span>
      </template>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      kind: '',
      menu: [
        {
          type: 'food',
          name: '美食',
          children: [
            {
              title: '美食',
              children: ['代金劵', '甜点饮品', '火锅', '自助餐', '小吃快餐']
            }
          ]
        },
        {
          type: 'takeout',
          name: '外卖',
          children: [
            {
              title: '外卖',
              children: ['美团外卖']
            }
          ]
        },
        {
          type: 'hotel',
          name: '酒店',
          children: [
            {
              title: '酒店星级',
              children: ['经济型', '舒适/三星', '高档/四星', '豪华/五星']
            }
          ]
        }
      ]
    }
  },
  computed: {
    curdetail: function () {
      return this.menu.filter((item) => item.type === this.kind)[0]
    }
  },
  methods: {
    mouseleave: function () {
      let self = this
      console.info(2222)
      self._timer = setTimeout(function () {
        self.kind = ''
      }, 150)
    },
    mouseenter: function (e) {
      this.kind = e.target.querySelector('i').className
    },
    sover: function () {
      clearTimeout(this._timer)
    },
    sout: function () {
      this.kind = ''
    }
  }
}
</script>

<style>
</style>