<script src="//unpkg.com/vue/dist/vue.js"></script>
<script src="//unpkg.com/element-ui@2.14.1/lib/index.js"></script>
<template lang="pug">
  #app 
    .newscontainer
      .title {{title}}
      .newsFlex
        .newsItem(v-for="item in news")
          .newsImg(:style="{backgroundImage: 'url(' + item.img +')'}")
          .newsText1 {{item.text1}}
          .newsText2 {{item.text2}}
          .newsButton Read More
    .menu
      el-menu#menu(
        :default-active="activeIndex"
        text-color="#ffffff"
        menu-trigger="hover"
        mode="horizontal" 
        background-color="transparent"

        @select="handleSelect"
        )
          el-menu-item.nthuipta(index="2", menu-trigger="hover") HOME
          el-menu-item.nthuipta(index="3", menu-trigger="hover") 最新消息
          el-submenu.nthuipta(index="4", menu-trigger="hover") 
            template.nthuipta(slot="title") 招生資訊
            el-menu-item.nthuipta(index="4-1") 春之清華卓越獎五名
            el-menu-item.nthuipta(index="4-2") 學士班臉書粉絲頁
            el-submenu.nthuipta(index="4-3", menu-trigger="hover") 
              template.nthuipta(slot="title") ２０２０招生資訊
              el-menu-item(index="4-3-1") ２０２０錄取名單
              el-menu-item(index="4-3-2") ２０２０招生簡章
              el-menu-item(index="4-3-3") ２０２０個人申請第二階段甄選注意事項
              el-menu-item(index="4-3-3") ２０２０報名繳交資料
            el-menu-item.nthuipta(index="4-4") 招生Ｑ＆Ａ
            el-submenu.nthuipta(index="4-5", menu-trigger="hover") 
              template(slot="title") 過往招生資訊
              el-submenu.nthuipta(index="4-5-1", menu-trigger="hover") 
                  template.nthuipta(slot="title") ２０１９年招生資訊
                  el-menu-item(index="4-5-1-1") ２０１９錄取名單
                  el-menu-item(index="4-5-1-2") ２０１９招生簡章
                  el-menu-item(index="4-5-1-3") ２０１９個人申請第二階段甄選注意事項
                  el-menu-item(index="4-5-1-4") ２０１９報名繳交資料
              el-submenu.nthuipta(index="4-5-2", menu-trigger="hover") 
                template.nthuipta(slot="title") ２０１８年招生資訊
                el-menu-item(index="4-5-2-1") ２０１８錄取名單
                el-menu-item(index="4-5-2-2") ２０１８招生簡章
                el-menu-item(index="4-5-2-3") ２０１８個人申請第二階段甄選注意事項
                el-menu-item(index="4-5-2-4") ２０１８報名繳交資料

          el-submenu.nthuipta(index="5", menu-trigger="hover") 
            template.nthuipta(slot="title") 學士班
            el-menu-item.nthuipta(index="5-1") 學士班簡介
            el-menu-item.nthuipta(index="5-2") 學士班課程
            el-menu-item.nthuipta(index="5-3") 國際交換
            el-menu-item.nthuipta(index="5-4") 藝術學院大樓(New)

          el-submenu.nthuipta(index="6", menu-trigger="hover") 
            template.nthuipta(slot="title") 師資
            el-menu-item.nthuipta(index="6-1") 學士班師資
            el-menu-item.nthuipta(index="6-2") 藝設系師資
            el-menu-item.nthuipta(index="6-3") 音樂系師資
            el-menu-item.nthuipta(index="6-4") 電資學院師資
          el-submenu.nthuipta(index="7", menu-trigger="hover") 
            template.nthuipta(slot="title") 科藝賞析
            el-menu-item.nthuipta(index="7-1") 數位文創作品
            el-menu-item.nthuipta(index="7-2") 互動藝術作品
            el-menu-item.nthuipta(index="7-3") 動力藝術作品
            el-menu-item.nthuipta(index="7-4") 聲音藝術作品
            el-menu-item.nthuipta(index="7-4") 科技表演藝術
          el-menu-item.nthuipta(index="8", menu-trigger="hover") 聯絡我們
</template>

<script>
export default {
  data(){
    return{
      title: '最新消息',
      news:[
        {img: 'https://ipta.nthu.edu.tw/wp-content/uploads/2020/05/200528.jpg',text1: '【演講】05/28 從腦科學看藝術',text2: ' (Art and the Brain: A Glimpse of Neuroaesthetics)'},
        {img: 'https://ipta.nthu.edu.tw/wp-content/uploads/2020/10/banner.png',text1: '【獲獎】《那顆Ｇ1咻！》',text2: '國立清華大學藝術學院學士班第一屆系展 得獎名單'},
        {img: 'https://ipta.nthu.edu.tw/wp-content/uploads/2020/09/light2-01.jpg',text1: '【獲獎】2020春之清華 – 藝術卓越獎',text2: '科技藝術類 得獎名單'}
      ],
    }
  }
}
</script>
<style lang="sass">
#app
  background-image: url("./assets/web-02.png")
  width: 1440px
  min-height: 2700px
  background-size: cover
  position: relative

.menu
  position: absolute
  top: 50px
  left: 550px

#menu
  border-bottom: 0px

.newscontainer
  width: 76%
  position: absolute
  top: 1730px

.title
  padding-left: 520px
  font-size: 17pt
  padding-bottom: 50px

.newsFlex
  display: flex
  flex-direction: row
  justify-content: space-around

.newsItem
  display: flex
  flex-direction: column
  align-items: center

.newsImg
  width: 250px
  height: 153px
  background-size: cover
  
.newsText1
  font-size: 12pt
  text-align: center
  padding-top: 20px

.newsText2
  font-size: 10pt
  text-align: center
  padding-top: 5px
  
.newsButton
  color: #ffffff 
  padding-top: 8px
  padding-bottom: 8px
  text-align: center
  background-color: #38595E
  width: 100px
  margin: auto
  margin-top: 20px

el-menu
  position: absolute
</style>