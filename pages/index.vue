<template>
  <div class="">
    <div class="mx-10 mb-16">
      hogehogejgoe
      <div class="">
        <!-- <div
          class="absolute inset-0 w-screen h-screen bg-pink-500 text-white flex items-center justify-center text-5xl transition-all ease-in-out duration-1000 transform translate-x-0 slide"
          id="slide1"
        >
          Hello
        </div>
        <div
          class="absolute inset-0 w-screen h-screen bg-purple-500 text-white flex items-center justify-center text-5xl transition-all ease-in-out duration-1000 transform translate-x-full slide"
          id="slide2"
        >
          There
        </div> -->

        <div class="relative z-0">
          <img src="https://www.pakutaso.com/shared/img/thumb/yamasha_eternal_2_TP_V.jpg" alt="" />
          <div
            class="absolute flex items-center bottom-0 left-0 bg-black w-full h-16 bg-opacity-50 text-white text-xl font-bold"
          >
            <div class="ml-16 text-opacity-100">「気持ちいいのはなぜだろう」</div>
          </div>
        </div>
      </div>

      <div>----</div>
    </div>
    <div class="w-full bg-gray-200">
      ニュースリリース <br />
      2021.02.10 「無印良品 シエスタハコダテ」増床リニューアルオープンお知らせ <br />
      2021.02.10 「無印良品 シエスタハコダテ」増床リニューアルオープンお知らせ <br />
      2021.02.10 「無印良品 シエスタハコダテ」増床リニューアルオープンお知らせ <br />
      2021.02.10 「無印良品 シエスタハコダテ」増床リニューアルオープンお知らせ <br />
      2021.02.10 「無印良品 シエスタハコダテ」増床リニューアルオープンお知らせ <br />
      2021.02.10 「無印良品 シエスタハコダテ」増床リニューアルオープンお知らせ <br />
      2021.02.10 「無印良品 シエスタハコダテ」増床リニューアルオープンお知らせ <br />
      2021.02.10 「無印良品 シエスタハコダテ」増床リニューアルオープンお知らせ
    </div>
  </div>
</template>

<script>
// import Logo from '~/components/Logo.vue'

export default {
  // components: {
  //   Logo
  // },
  head() {
    return {
      script: [{ src: 'https://identity.netlify.com/v1/netlify-identity-widget.js' }],
    }
  },
  mounted: function () {
    setInterval(
      function () {
        let slide1 = document.querySelector('#slide1')
        let slide2 = document.querySelector('#slide2')
        let activeSlide = slide1 ? slide2.contains('translate-x-0') : slide2
        let nextSlide = slide2 ? slide2.contains('translate-x-0') : slide1

        activeSlide.classList.remove('translate-x-0')
        activeSlide.classList.add('-translate-x-full')

        nextSlide.classList.remove('translate-x-full')
        nextSlide.classList.add('translate-x-0')
      }.bind(this),
      3000
    )
  },
}
</script>
