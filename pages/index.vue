<template>
  <div class="container">

<!--    renderingページ-->
    <header>
      <img src="mokuhub-logo.png" />
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
        パッションを持った仲間と繋がることで、ひとり⾃宅でも最高のアウトプットを⽣みすことが出来る<b>オンライン上のコワーキングスペース</b>です。 <br>
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
          <div class="rule_item"><p>寝癖、パジャマは禁止<br>(私服、ノーメイクはok)</p></div>
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
        }else {
            //メインビジュアルより下までスクロールしたので、クラスを付けて色を変える
            header.css('background', "none");
        }
    });
},
    methods:{
      moveToForm(){
          var formTop =$('#contact').offset().top;
          $("html, body").animate({ scrollTop: formTop }, 500);
      }
    }
}
</script>

<style>
  body,html{
    margin: 0;
    padding: 0;
    font-family: "Yu Gothic UI Semibold", "Noto Sans JP", sans-serif;
  }
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
}
</style>
