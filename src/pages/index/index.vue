<template>
  <div class="home">
    <SearchBar
      disabled
      @onClick="onSearchBarClick"
    />
    <home-card/>
    <HomeBanner
      img="http://www.youbaobao.xyz/book/res/bg.jpg"
      title="mpvue 2.0 实战"
      sub-title="立即体验"
      @onClick="onBannerClick"
    />
    <div class="home-book">
      <HomeBook
        title="分类查询"
        :row="2"
        :col="2"
        :data="data"
        mode="category"
        btn-text="更多"
        @onMoreClick="onMoreClick"
        @onBookClick="onBookClick"
      />
    </div>
  </div>
</template>

<script>
import SearchBar from '../../components/home/SearchBar'
import ImageView from '../../components/base/ImageView'
import HomeCard from '../../components/base/homeCard'
import HomeBanner from '../../components/home/HomeBanner'
import HomeBook from '../../components/home/HomeBook'

export default {
  components: {HomeCard, SearchBar, ImageView, HomeBanner, HomeBook},
  data() {
    return {
      data: [
        {
          'cover': 'https://www.youbaobao.xyz/book/res/img/Biomedicine/978-3-319-25474-6_CoverFigure.jpg',
          'category': 12,
          'categoryText': 'Biomedicine',
          'num': 14,
          'cover2': 'https://www.youbaobao.xyz/book/res/img/Biomedicine/978-3-319-72790-5_CoverFigure.jpg'
        },
        {
          'cover': 'https://www.youbaobao.xyz/book/res/img/BusinessandManagement/978-3-319-33515-5_CoverFigure.jpg',
          'category': 13,
          'categoryText': 'BusinessandManagement',
          'num': 16,
          'cover2': 'https://www.youbaobao.xyz/book/res/img/BusinessandManagement/978-3-319-95261-1_CoverFigure.jpg'
        },
        {
          'cover': 'https://www.youbaobao.xyz/book/res/img/ComputerScience/978-3-319-90415-3_CoverFigure.jpg',
          'category': 1,
          'categoryText': 'ComputerScience',
          'num': 56,
          'cover2': 'https://www.youbaobao.xyz/book/res/img/ComputerScience/978-3-319-96142-2_CoverFigure.jpg'
        },
        {
          'cover': 'https://www.youbaobao.xyz/book/res/img/EarthSciences/978-981-10-3713-9_CoverFigure.jpg',
          'category': 14,
          'categoryText': 'EarthSciences',
          'num': 16,
          'cover2': 'https://www.youbaobao.xyz/book/res/img/EarthSciences/978-3-319-65633-5_CoverFigure.jpg'
        },
        {
          'cover': 'https://www.youbaobao.xyz/book/res/img/Economics/978-3-319-69772-7_CoverFigure.jpg',
          'category': 3,
          'categoryText': 'Economics',
          'num': 30,
          'cover2': 'https://www.youbaobao.xyz/book/res/img/Economics/978-3-319-91400-8_CoverFigure.jpg'
        },
        {
          'cover': 'https://www.youbaobao.xyz/book/res/img/Education/978-3-319-39450-3_CoverFigure.jpg',
          'category': 4,
          'categoryText': 'Education',
          'num': 60,
          'cover2': 'https://www.youbaobao.xyz/book/res/img/Education/978-3-319-52980-6_CoverFigure.jpg'
        },
        {
          'cover': 'https://www.youbaobao.xyz/book/res/img/Engineering/978-3-319-91707-8_CoverFigure.jpg',
          'category': 5,
          'categoryText': 'Engineering',
          'num': 23,
          'cover2': 'https://www.youbaobao.xyz/book/res/img/Engineering/978-3-319-64816-3_CoverFigure.jpg'
        },
        {
          'cover': 'https://www.youbaobao.xyz/book/res/img/Environment/978-3-319-29671-5_CoverFigure.jpg',
          'category': 6,
          'categoryText': 'Environment',
          'num': 42,
          'cover2': 'https://www.youbaobao.xyz/book/res/img/Environment/978-4-431-54895-9_CoverFigure.jpg'
        },
        {
          'cover': 'https://www.youbaobao.xyz/book/res/img/Geography/978-3-319-75593-9_CoverFigure.jpg',
          'category': 7,
          'categoryText': 'Geography',
          'num': 7,
          'cover2': 'https://www.youbaobao.xyz/book/res/img/Geography/978-3-319-92813-5_CoverFigure.jpg'
        },
        {
          'cover': 'https://www.youbaobao.xyz/book/res/img/History/978-3-319-64337-3_CoverFigure.jpg',
          'category': 8,
          'categoryText': 'History',
          'num': 18,
          'cover2': 'https://www.youbaobao.xyz/book/res/img/History/978-3-319-92964-4_CoverFigure.jpg'
        },
        {
          'cover': 'https://www.youbaobao.xyz/book/res/img/Laws/978-3-319-71087-7_CoverFigure.jpg',
          'category': 9,
          'categoryText': 'Laws',
          'num': 13,
          'cover2': 'https://www.youbaobao.xyz/book/res/img/Laws/978-981-13-1232-8_CoverFigure.jpg'
        },
        {
          'cover': 'https://www.youbaobao.xyz/book/res/img/LifeSciences/978-3-319-68152-8_CoverFigure.jpg',
          'category': 10,
          'categoryText': 'LifeSciences',
          'num': 24,
          'cover2': 'https://www.youbaobao.xyz/book/res/img/LifeSciences/978-3-319-69539-6_CoverFigure.jpg'
        },
        {
          'cover': 'https://www.youbaobao.xyz/book/res/img/Literature/2010_Book_CyborgsInLatinAmerica.jpeg',
          'category': 11,
          'categoryText': 'Literature',
          'num': 6,
          'cover2': 'https://www.youbaobao.xyz/book/res/img/Literature/2010_Book_HistoryAndCulturalMemoryInNeo-.jpeg'
        },
        {
          'cover': 'https://www.youbaobao.xyz/book/res/img/MaterialsScience/978-981-10-7617-6_CoverFigure.jpg',
          'category': 15,
          'categoryText': 'MaterialsScience',
          'num': 2,
          'cover2': 'https://www.youbaobao.xyz/book/res/img/MaterialsScience/2018_Book_ProceedingsOfTheScientific-Pra.jpeg'
        },
        {
          'cover': 'https://www.youbaobao.xyz/book/res/img/Mathematics/978-3-319-29439-1_CoverFigure.jpg',
          'category': 16,
          'categoryText': 'Mathematics',
          'num': 9,
          'cover2': 'https://www.youbaobao.xyz/book/res/img/Mathematics/2015_Book_InnovationsInQuantitativeRiskM.jpeg'
        },
        {
          'cover': 'https://www.youbaobao.xyz/book/res/img/MedicineAndPublicHealth/978-3-319-28624-2_CoverFigure.jpg',
          'category': 17,
          'categoryText': 'MedicineAndPublicHealth',
          'num': 20,
          'cover2': 'https://www.youbaobao.xyz/book/res/img/MedicineAndPublicHealth/978-3-319-75019-4_CoverFigure.jpg'
        },
        {
          'cover': 'https://www.youbaobao.xyz/book/res/img/Philosophy/978-3-319-26300-7_CoverFigure.jpg',
          'category': 18,
          'categoryText': 'Philosophy',
          'num': 16,
          'cover2': 'https://www.youbaobao.xyz/book/res/img/Philosophy/978-3-319-94610-8_CoverFigure.jpg'
        },
        {
          'cover': 'https://www.youbaobao.xyz/book/res/img/Physics/978-3-319-42424-8_CoverFigure.jpg',
          'category': 19,
          'categoryText': 'Physics',
          'num': 10,
          'cover2': 'https://www.youbaobao.xyz/book/res/img/Physics/978-3-662-57366-2_CoverFigure.jpg'
        },
        {
          'cover': 'https://www.youbaobao.xyz/book/res/img/PoliticalScienceAndInternationalRelations/978-3-319-69929-5_CoverFigure.jpg',
          'category': 20,
          'categoryText': 'PoliticalScienceAndInternationalRelations',
          'num': 26,
          'cover2': 'https://www.youbaobao.xyz/book/res/img/PoliticalScienceAndInternationalRelations/978-981-10-7182-9_CoverFigure.jpg'
        },
        {
          'cover': 'https://www.youbaobao.xyz/book/res/img/Psychology/978-3-319-78160-0_CoverFigure.jpg',
          'category': 21,
          'categoryText': 'Psychology',
          'num': 3,
          'cover2': 'https://www.youbaobao.xyz/book/res/img/Psychology/2015_Book_PromotingSocialDialogueInEurop.jpeg'
        },
        {
          'cover': 'https://www.youbaobao.xyz/book/res/img/SocialSciences/978-3-319-72356-3_CoverFigure.jpg',
          'category': 2,
          'categoryText': 'SocialSciences',
          'num': 51,
          'cover2': 'https://www.youbaobao.xyz/book/res/img/SocialSciences/978-3-319-77991-1_CoverFigure.jpg'
        },
        {
          'cover': 'https://www.youbaobao.xyz/book/res/img/Statistics/2013_Book_ShipAndOffshoreStructureDesign.jpeg',
          'category': 22,
          'categoryText': 'Statistics',
          'num': 1,
          'cover2': 'https://www.youbaobao.xyz/book/res/img/Statistics/2013_Book_ShipAndOffshoreStructureDesign.jpeg'
        }
      ],
    }
  },
  methods: {
    onSearchBarClick() {
      //  跳转到搜索页
    },
    onBannerClick() {
      console.log('click///')
    },
    onMoreClick() {
      console.log('onMore click')
    },
    onBookClick() {
      console.log('onBook Click')
    }
  }
}
</script>

<style lang="scss" scoped>
.home-book {
  margin-top: 23px;
}
</style>
