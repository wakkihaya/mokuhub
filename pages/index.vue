<template>
  <div class="container">

<!--    renderingページ-->
    <header>
      <span v-on:click="moveToTop">
        <img src="mokuhub-logo.png" />
      </span>
    </header>
    <div class="rendering-page">
      <div class="rendering_title">
        パッションの伝染で、 <br>
        最高のアウトプットを。
      </div>
      <div class="button_to_join" v-on:click="moveToForm">
        参加フォーム ↓
      </div>

    </div>

<!--    moku hubとは-->
    <div class="explain">
      <div class="content_title"> moku hub とは</div>
      <div class="explain_content">
        "moku hub"とは、 <br>
        <span>パッション</span>を持った仲間と繋がることで、ひとり⾃宅でも最高の<span>アウトプット</span>を生み出すことが出来る<span>オンライン上のコワーキングスペース</span>です。 <br>
        また、作業するだけではなくコミュニティ内では議論会や飲み会などイベントが活発に⾏われています。
      </div>
    </div>

<!--    コミュニティ内容-->
    <div class="content_community">
      <div class="content_title"> コミュニティ内容</div>
      <div class="explain_content">
        基本的な流れは、 <br>
        10am-17pmまでは共同作業スペースがzoom上に開かれているので各⾃好きな様に利⽤することが出来ます。 <br>
        また、10時から自由参加のアッセンブリー（当⽇のtodoをシェアしあってモチベを上げる）や雑談会なども開催されています。
      </div>


      <div class="rule">
        <div class="content_sub_title">ルール</div>
        <div class="rule_listing">
          <div class="rule_item"><p>寝癖,パジャマは禁止<br>(私服,ノーメイクはok)</p></div>
          <div class="rule_item"><p>作業中は基本ミュート</p></div>
          <div class="rule_item"><p>自身のビジネスの宣伝や勧誘は禁止</p></div>
        </div>
      </div>

      <div class="environment">
        <div class="content_sub_title">環境</div>
        <div class="environment_list">
          <img src="clock-2.png" width="15%"/>
          <img src="zoom.png" width="15%" />
          <img src="slack.png" width="15%" />
        </div>
      </div>
    </div>

    <!--    moku hub のメリット-->
    <div class="merit">
      <div class="content_title">moku hub に入ると…</div>
      <div class="merit_image">
        <img src="merit.png" width="100%"/>
      </div>
    </div>


<!--    Contact-->
    <div id="contact">
      <div class="content_title">参加したい方はこちら</div>
      <div class="form">
        <iframe src="https://docs.google.com/forms/d/e/1FAIpQLScd4SKkkY5glD4DaZqmkiaa1gHkIs5y0K7xJpAb7ZNoJ2ZXrQ/viewform?embedded=true"
                            width="100%"
                            height="995"
                            frameborder="0"
                            marginheight="0"
                            marginwidth="0">
        Loading…
      </iframe>
      </div>
    </div>

<!--    footer-->
    <footer>
      Copyright © mokuhub team All Rights Reserved.
    </footer>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  },
    mounted(){
    var imgHeight = $('.container').outerHeight(); //画像の高さを取得。これがイベント発火位置になる。
    var header = $('header'); //ヘッダーコンテンツ

    $(window).on('load scroll', function(){
        if ($(this).scrollTop() >100) {
            //メインビジュアル内にいるので、クラスを外す。
            header.css('background', "#ffffff");
            header.css('border-bottom', "solid 1px #fd730b");
        }else {
            //メインビジュアルより下までスクロールしたので、クラスを付けて色を変える
            header.css('background', "none");
            header.css('border-bottom', "none");
        }
    });
},
    methods:{
      moveToForm(){
          var formTop =$('#contact').offset().top;
          $("html, body").animate({ scrollTop: formTop }, 500);
      },
        moveToTop(){
            $("html, body").animate({ scrollTop: 0 }, 500);

        }
    },
    head() {
        return {
            title: 'moku hub 公式ページ',
            meta: [
                { hid: 'description', name: 'description', content: 'moku hubとはパッションを持った仲間と繋がることで、ひとり自宅でも最高のアウトプットを生み出すことが出来るオンライン上のコワーキングスペースです。' },
                { hid: 'og:type', property: 'og:type', content: 'website'},
                { hid: 'og:title', property: 'og:title', content: 'moku hub ~パッションの伝染で、最高のアウトプットを。~' },
                { hid: 'og:description', property: 'og:description', content: 'moku hubとはパッションを持った仲間と繋がることで、ひとり自宅でも最高のアウトプットを生み出すことが出来るオンライン上のコワーキングスペースです。' },
                { hid: 'og:url', property: 'og:url', content: 'https://mokuhub.work' },
                { hid: 'og:image', property: 'og:image', content: 'https://mokuhub.work/ogp.png' },
            ],
        }
    }
}
</script>

<style>
  body,html{
    margin: 0;
    padding: 0;
    font-family: -apple-system, BlinkMacSystemFont, 'Hiragino Sans', 'Hiragino Kaku Gothic ProN',"Yu Gothic UI Semibold","Noto Sans JP", sans-serif;
  }
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
}
</style>
