<template>
  <div class="container">
    <NavBar></NavBar>

    <!-- HERO -->
    <section class="hero">
      <div class="hero__text">
        <h1 class="header__text">Create, Sell & Collect Your Own Creative <span class="header__text main__text__color">NFT</span></h1>
        <p class="main__p">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc vulputate libero et velit.</p>
        <div style="margin: 20px 5px;">
          <button class="base__button">Explore Now</button>
          <button class="base__button" style="margin-left: 13px; background: rgba(255, 255, 255, 0.1)!important;">Sell NFT</button>
        </div>
        <div class="hero__layouts">
          <div class="sub__layouts">
            <h1>37k+</h1>
            <p>Artworks</p>
          </div>

          <div class="sub__layouts">
            <h1>20k+</h1>
            <p>Artists</p>
          </div>

          <div class="sub__layouts">
            <h1>99k+</h1>
            <p>Aucations</p>
          </div>
        </div>
      </div>

      <div class="hero__img">
        <img src="../assets/images/heroimage.png" alt="image">
      </div>

    </section>

    <!-- COMPANIES -->
    <section class="companies__logo">
      <div class="companies__logo-sub">
        <img src="../assets/images/Binance_logo logo.png" alt="image">
        <img src="../assets/images/Group.png" alt="image">
        <img src="../assets/images/Page-1.png" alt="image">
      </div>
    </section>

    <!-- ABOUT -->
    <section class="about__main">
      <div class="about__header">
        <h1 class="header__text">About Us</h1>
        <p class="main__p">Best NFT website of this year for <br>selling online assets</p>
      </div>
      <div class="about__content">
        <img src="../assets/images/Group 18.png" alt="image">
        <div class="content__text">
          <h1 class="header__text">Get Popular <span class="header__text main__text__color">NFT</span></h1>
          <p class="main__p">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Etiam eu turpis molestie, dictum est a, mattis tellus. Sed dignissim, metus nec fringilla accumsan, risus sem sollicitudin lacus, ut interdum tellus elit sed risus. Maecenas eget condimentum velit, sit amet feugiat lectus. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Praesent auctor purus luctus enim egestas, ac scelerisque ante pulvinar. </p>
        </div>
      </div>
    </section>

    <!-- COLLECTION -->
    <section class="collectoin__container">
      <div class="about__header">
        <h1 class="header__text">Collection</h1>
        <p class="main__p">Best NFT collection, we have <br>for your interest</p>
      </div>

      <div class="collection__buttom">
        <div class="c__b__btn__main">
          <button class="c__b__btn" :class="{c__b__btn__active: activeBtn == 'art'}" @click="changeActiveBtn('art')">Art</button>
          <button class="c__b__btn" :class="{c__b__btn__active: activeBtn == 'sport'}" @click="changeActiveBtn('sport')">Sport</button>
          <button class="c__b__btn" :class="{c__b__btn__active: activeBtn == 'photograpy'}" @click="changeActiveBtn('photograpy')">Photograpy</button>
          <button class="c__b__btn" :class="{c__b__btn__active: activeBtn == 'pattern'}" @click="changeActiveBtn('pattern')">Pattern</button>
        </div>

        <div class="gird__NFT">
          <div class="collection__main__nft" v-for="NFT in NFTs" :key="NFT.NFTname">
            <div class="col__item">
              <img class="NFT__img" :src="'../src/assets/images/nfts/' + NFT.url + '.png'" alt="">
              <div class="main__NFT__div">
                <div class="first__NFT">
                  <p class="main__p" style="font-size: 1rem;">@{{ NFT.userName }}</p>
                  <h3 class="NFT__title">{{ NFT.NFTname }}</h3>
                </div>
                <div class="second__NFT__div">
                  <p class="main__p sub__title__NFT" style="font-size: 1rem;">Current Bid</p>
                  <h3 class="NFT__title">{{ NFT.price }} ETH</h3>
                </div>
              </div>
              <button class="NFT__btn c__b__btn">Place a bid</button>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- TOP CREATORS -->
    <section class="creators__container">
      <div class="about__header">
        <h1 class="header__text">Top Creator</h1>
        <p class="main__p">Best Creator, which will help for your <br>interest in NFTs</p>
      </div>

      <div class="gird__NFT" style="padding: 2px 23px;">
          <div class="collection__main__nft" v-for="creator in creators" :key="creator.userName">
            <div class="col__item cr__main">
              <img class="creators__backimg" :src="'../src/assets/images/creators/banner'+ creator.bannerUrl  + '.png'" alt="">
              <img class="creators__profile__pic" :src="'../src/assets/images/creators/photo'+ creator.bannerUrl  + '.png'" alt="">
              <h2 class="NFT__title">{{ creator.userName }}</h2>
              <p class="main__p creator__discription">{{ creator.discription }}</p>
              <button class="c__b__btn creator__btn active__follow" v-if="creator.isFollow" @click="followCreator(creator)">+ Followed</button>
              <button class="c__b__btn creator__btn" v-else @click="followCreator(creator)">+ Follow</button>
            </div>
          </div>
        </div>
    </section>

    <!-- FAQ -->
    <section class="creators__container">
      <div class="about__header">
        <h1 class="header__text">Frequently <br>Asked Questions  </h1>
        <p class="main__p">Wanna ask something</p>
      </div>

      <div class="faq__container">
        
      </div>
    </section>

  </div>
</template>


<script>
import NavBar from "../components/NavBar.vue";

export default {
  components: {
    NavBar,
  },
  data() {
    return {
      activeBtn: 'art',
      creators: [
      {
          userName: 'Lisa',
          discription: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
          bannerUrl: '1',
          isFollow: false,
        },
        {
          userName: 'John Wick',
          discription: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
          bannerUrl: '2',
          isFollow: false,
        },
        {
          userName: 'James Pot',
          discription: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
          bannerUrl: '3',
          isFollow: false,
        },
      ]
    }
  },
  computed: {
    NFTs() {
      return [
        {
          userName: 'Jhon',
          NFTname: 'Yellow Painting',
          price: '0.005',
          url: 'Rectangle 23'
        },
        {
          userName: 'Alia',
          NFTname: 'Red Painting',
          price: '0.003',
          url: 'fakurian-design-LoLiXKJEvgE-unsplash 1'
        },
        {
          userName: 'James',
          NFTname: 'White Painting',
          price: '0.0009',
          url: 'fakurian-design-PGdW_bHDbpI-unsplash 1'
        },
        {
          userName: 'Lisa',
          NFTname: 'Blue Painting',
          price: '0.0007',
          url: 'daniels-joffe--SmCKTIcH5E-unsplash 1'
        },
        {
          userName: 'James',
          NFTname: 'Blue Painting',
          price: '0.0009',
          url: 'dynamic-wang-TQFtvtTLMAg-unsplash 1'
        },
        {
          userName: 'Alone',
          NFTname: 'Dark Painting',
          price: '0.009',
          url: 'collection6'
        },
      ]
    },
  },
  
  methods: {
    changeActiveBtn(name) {
      this.activeBtn = name
    },
    followCreator(f) {
      if (f.isFollow) {
        f.isFollow = false
      } else {
        f.isFollow = true
      }
    }
  }
};
</script>

<style scoped>
.main__text__color {
  background: linear-gradient(214.02deg, #b75cff 6.04%, #671ae4 92.95%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}
.header__text {
  font-weight: 700;
  font-size: 40px;
}
.main__p {
  font-weight: 400;
  font-size: 20px;
  line-height: 180%;
  color: rgba(255, 255, 255, 0.5);
}
.hero {
  margin: 3rem;
  padding: 20px;
  display: flex;
  flex-direction: row;
}
.hero__layouts {
  display: flex;
  flex-direction: row;
  gap: 55px;
}
.hero__img img {
  width: 28rem;
}
.companies__logo {
  margin: 3rem;
  padding: 20px;
}
.companies__logo-sub {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}
.about__header {
  text-align: center;
}
.about__content {
  padding: 2rem;
  display: flex;
  flex-direction: row;
  gap: 2rem;
}
.about__content img {
  width: 28rem;
  margin-top: 2rem;
}
.content__text {
  margin-top: 3rem;
  padding: 1rem;
}
.collectoin__container {
  margin-top: 2rem;
  padding: 0 23px;
}
.collection__buttom {
  margin-top: 13px;
}
.c__b__btn__main {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  gap: 10px;
}
.c__b__btn {
  color: white;
  font-size: 1rem;
  font-weight: 500;
  padding: 5px 106px;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 10px;
  border: none;
  cursor: pointer;
  width: 288px;
  height: 40px;
}
.c__b__btn__active {
  background: linear-gradient(214.02deg, #B75CFF 6.04%, #671AE4 92.95%);
}
.collection__main__nft {
  margin: 1rem 0;
}
.col__item {
  padding: 10px 11px;
  width: 345px;
  height: 530px;
  background: rgba(255, 255, 255, 0.1);
  box-shadow: 0px 5px 4px rgba(0, 0, 0, 0.25);
  border-radius: 10px;
}
.NFT__img {
  width: 324px;
  height: 380px;
  border-radius: 10px;
}
.main__NFT__div {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  gap: 50px;
}
.NFT__title {
  font-weight: 700;
  font-size: 20px;
}
.sub__title__NFT {
  text-align: right;
}
.NFT__btn {
  background: linear-gradient(214.02deg, #B75CFF 6.04%, #671AE4 92.95%);
  width: 324px;
  height: 50px;
  margin-top: 0.7rem;
  transition: .3s ease-out;
}
.NFT__btn:hover {
  background: linear-gradient(214.02deg, #B75CFF 6.04%, #671AE4 92.95%);
  transition: 0.3s ease-in-out;
  transform: translateY(-3px);
}
.NFT__btn:active {
  color: linear-gradient(214.02deg, #B75CFF 6.04%, #671AE4 92.95%);
  transform: translateY(-2px);
}
.gird__NFT {
  display: grid;
  grid-template-columns: repeat(3, 347px);
  gap: 10px;
}
.creators__container {
  margin-top: 2.5rem;
}
.cr__main {
  padding: 0 0;
  height: 445px;
}
.cr__main h2 {
  text-align: center;
}
.creators__backimg {
  background-size: cover;
  background-position: center;
  width: 345px;
  height: 233px;
  border-radius: 10px;
}
.creators__profile__pic {
  border-radius: 50px;
  position: relative;
  margin-top: -68px;
  margin-left: 117px;
  width: 7rem;
}
.creator__discription {
  font-size: 15px;
  font-weight: 500;
  text-align: center;
}
.creator__btn {
  height: 44px;
  width: 300px;
  margin-left: 22px;
  background: linear-gradient(214.02deg, #B75CFF 6.04%, #671AE4 92.95%);
  margin-top: 0.7rem;
  transition: .3s ease-out;
}
.creator__btn:hover {
  transform: translateY(-2px);
}
.active__follow {
  background: rgba(255, 255, 255, 0.5);
  color: #671AE4;
  transition: .3s ease-out;
}
</style>