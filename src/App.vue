<template>
<div>
 <header v-show="seeHeader" class="header">
   <div class="header_container">
       <span class="header_logo">logo</span>
     <div>
       <img src="./photo/person.png">
       <img class="header_icon" src="./photo/like.png">
       <img src="./photo/basket.png">
       <a 
      @click="openMenu"
       href="#" class="burger-menu" />
     </div>
   </div>
 </header>


   <div v-show="showMenu" class="mobile-menu">
     <div @click="closeMenu" class="close-button">
       <img src="./photo/close-menu.png">
     </div>
     <div class="todo">
     <span class="todo_item">постельное белье</span>
     <span class="todo_item">одежда для дома</span>
     <span class="todo_item">одежда для улицы</span>
     <span class="todo_item">выход</span>
     </div>
   </div>


 <div @click="closeMenu" class="container">
   <div class="main_photo-wrapper">
     <div class="miniatures">
       <div @click='changePhoto(1)' class="miniature_wrapper">
         <img  src="./photo/1.png">
         <div class="miniature_fon"></div>
       </div>
       <div @click='changePhoto(2)' class="miniature_wrapper">
         <img  src="./photo/suit.png">
         <div class="miniature_fon"></div>
       </div>
       <div @click='changePhoto(3)' class="miniature_wrapper">
         <img  src="./photo/suit_1.png">
         <div class="miniature_fon"></div>
       </div>
       <div @click='changePhoto(4)' class="miniature_wrapper">
         <img  src="./photo/suit_2.png">
         <div class="miniature_fon"></div>
       </div>
       <div @click='changePhoto(5)' class="miniature_wrapper">
         <img  src="./photo/suit_3.png">
         <div class="miniature_fon"></div>
       </div>


       </div>
          <img class="main_photo" :src="currentPhoto">
      </div>


  <div class="description">
   <div class="description_main">
     <h4 class="description_title">{{titleItem}}</h4>
     <div class="description_art">Арт. 02765/46</div>
     <div>
       <span class="description_reviews">Отзывы</span>
       <span>
       <img src="./photo/star.png">
       <img src="./photo/star.png">
       <img src="./photo/star.png">
       <img src="./photo/star.png">
       <img src="./photo/star1.png">
       </span>
       <span class=" description_rewiew">14 отзывов</span>
       <img class="description_arrow" src="./photo/Line15.png">
     </div>
   </div>

   <div class="price">
     <span class="price_main">800 ₽</span>
     <span class="price_discount">1 500 ₽</span>
     <img src="./photo/Line15.png">
   </div>

   <div class="discount">
     <div class="discount_sale">скидка -36%</div>
     <div class="discount_sale">акция -20%</div>
   </div>

  <div>
    <select class="choose_size" id="size">
    <option class="choose_your-size" value="hide">Выбрать размер</option>
    <option value="s">small</option>
    <option value="m">medium</option>
    </select> 
    <a class="item-link" href='#'>Определить размер</a>
  </div>

  <div>
    <div class="count-selector">
      <div class="count_all">
      <button class="button_increase"
              @click="increment">+</button>
              <input type="number"  
                     class="count"
                     :value="number" disabled>
      <button class="button_decrease"
              @click="decrement">-</button>
      </div>
      <div class="count_buttons">
      <button class="button_add-to-card"
              @click='addToCart'>Добавить в корзину</button>
      <button class="button_like"
              @click='addToLike'></button></div>
    </div>
      <a class="item-link" href="#">Купить в 1 клик</a>
  </div>

  <div v-show='showModal' 
        @click="closeModal"
        class="modal">
    <div class="modal_text">{{modalMessage}}</div>
      <div class="" >
       <img class="modal_icon" src="./photo/close-menu.png">
     </div>
  </div>

  <div class="line">
  </div>
  <div class="line-mobile"></div>

  <div class="links">
    <a class="item-link item-link_icon item-link_icon_t-shirt " href="#">Описание товара</a>
    <a class="item-link item-link_icon item-link_icon_clock" href="#">Доставка и возврат</a>
    <a class="item-link item-link_icon item-link_icon_bag" href="#">Способы оплаты</a>
  </div>

  </div>
 </div>

<div class="container_gallery">
  <a href="#" class="item-link item_style ">Посмотреть все стили</a>
  <div class="gallery-main">
    <div class="gallery_photo-big">
      <img src="./photo/gallery_big.png">
    </div>
    <div class="gallery_photos">
      <div class="gallery_row">
        <div class="gallery_cell">
          <div class="hidden-item">
            <div class="hidden-item_icon"></div>
            <div class="hidden-item_like">
              67
            </div>
            <div class="hidden-item_shopper">
              <span>Узнай, что на мне</span>
            </div>


          </div>
          <img class="" src="./photo/gallery_1.png">
          </div> 
        <div class="gallery_cell">
          <div class="hidden-item">
            <div class="hidden-item_icon"></div>
            <div class="hidden-item_like">
              98
            </div>
            <div class="hidden-item_shopper">
              <span>Узнай, что на мне</span>
            </div>


          </div>
          <img class="" src="./photo/gallery_2.png"> 
          </div>
      </div>
      <div class="gallery_row"> 
        <div class="gallery_cell">
          <div class="hidden-item">
            <div class="hidden-item_icon"></div>
            <div class="hidden-item_like">
              200
            </div>
            <div class="hidden-item_shopper">
              <span>Узнай, что на мне</span>
            </div>


          </div>
          <img class="" src="./photo/gallery_3.png">
          </div> 
        <div class="gallery_cell">
          <div class="hidden-item">
            <div class="hidden-item_icon"></div>
            <div class="hidden-item_like">
              5
            </div>
            <div class="hidden-item_shopper">
              <span>Узнай, что на мне</span>
            </div>


          </div>
          <img class="" src="./photo/gallery_4.png">
          </div>

        </div>
      
      </div>

    </div>
  </div>

<footer class="container_footer">
  <div class="footer_row">
  <div class="footer_customers">
    <span class="footer_title">Покупателям</span>
    <span class="footer_blocks">Каталог</span>
    <span class="footer_blocks">Акции</span>
    <span class="footer_blocks">Бренды</span>
  </div>
  <div class="footer_customers">
    <span class="footer_title">О нас</span>
    <span class="footer_blocks">О компании</span>
    <span class="footer_blocks">Новости</span>
    <span class="footer_blocks">Команда</span>
  </div>
  </div>
  <div class="footer_customers footer_feedback">
    <span class="footer_title footer_news">Узнайте первыми о новинках</span>
    <div>
    <input class="footer_email" type="email" placeholder="Адрес электронной почты">
    <!-- <img src="./photo/close.png"> -->
    </div>
    <button class="button_subscribe" >Подписаться</button>
  </div>
</footer>

</div>

</template>

<script>
export default {

  created () {
    window.addEventListener('scroll', this.handleScroll);
  },
  unmounted () {
    window.removeEventListener('scroll', this.handleScroll);
  },

  data() {
    return {
      titleItem: 'Пижама для девочек',
      number: 1,
      modalMessage: '',
      showModal: false,
      showMenu: false,
      currentPhoto: '../../static/1.png',
      direction: false,
      startY: 0,
      seeHeader: true,
     
    };
  },
  methods: {

    handleScroll () {
      let scrollY = window.scrollY
      if (scrollY > this.startY) {
        this.direction = false;
      } else {
        this.direction = true;
      }
      this.startY = scrollY;
      console.log(this.direction)

      if (!this.direction ){
        this.seeHeader = false
      } else {
        this.seeHeader = true
    }
    },

    changePhoto(photo){
      this.currentPhoto = '../../static/'+photo+'.png'
      console.log(photo);
    },

    increment() {
      this.number++;
    },

    decrement() {
       // eslint-disable-next-line
      if (this.number == 0){
      }
      else {
        this.number--;
      }
    },

    addToCart() {
      // eslint-disable-next-line
      if (this.number === 0){

      }
      else {
        this.showModal = true
        this.modalMessage = 'Товар '+this.titleItem+' в количестве '+this.number+' ед. добавлен в корзину'
      }
    },

    addToLike() {
      this.showModal = true
      this.modalMessage = 'Товар '+this.titleItem+' добавлен в избранное'
    },

    closeModal(){
      this.showModal = false
    },

    openMenu(){
      this.showMenu = true
    },

    closeMenu(){
      this.showMenu = false
    },

    
  },
};


</script>

<style lang='css'>
body{
  font-family: "Open Sans";
  margin: 0;
}
#app {

}

p{
  margin: 0;
}

.modal{
  border-bottom: 1px solid #C4C4C4; 
  width: auto; 
  position: fixed; 
  right: 50px; 
  bottom: 10px;
  display: flex;
  z-index: 4;
  justify-content: space-evenly;
    z-index: 4;
    background: white;
}
@media screen and (max-width: 800px){
.modal{
  width: auto;
  left: 10px;
  right: 10px;
}}

.modal_text{
  font-size: 12px;
  color: #828282;
  letter-spacing: 0.04em;
  font-weight: 400;
  line-height: 16px;
  cursor: pointer;
  
}

.modal_icon{
  width: 14px;
  margin-left: 10px;
  cursor: pointer;
}

.mobile-menu{
  background-color: white;
  display: none;
  position: fixed;
  z-index: 3;
  top: 0;
  right: 0;
  left: 0;
}
@media screen and (max-width: 415px){
  .mobile-menu{
    display: block;
  }
}

.close-button{
  position: absolute;
  right: 25px;
  top: 23px;
  
}


.todo{
  display: flex;
  flex-direction: column;
  padding-left: 30px;

}

.todo_item{
  font-weight: 400;
  font-size: 12px;
  line-height: 16px;
  letter-spacing: 0.04em;
  text-transform: uppercase;
  margin-bottom: 30px;
}

.todo_item:last-child{
  margin-bottom: 43px;
}

.todo_item:first-child{
  margin-top: 80px;
}

.miniature_fon{
  background: rgba(255, 255, 255, 0.3);
  height: 91px;
  position: relative;
  z-index: 2;
}
@media screen and (max-width: 500px){
.miniature_fon{
  height: 52px;
}}

.miniatures{
  position: absolute;
  top: 26px;
  left: 24px;
  
}

.miniatures img{
  position: absolute;
  display: block;
  width: 100%;
  z-index: 1;
}

.miniature_wrapper{
  width: 70px;
  height: 91px;
  margin-bottom: 7px;
  position: relative;
}

@media screen and (max-width: 500px){
.miniature_wrapper{
  width: 40px;
  height: 52px;
}}

.item_style{
  display: block;
  margin: 35px 0 40px;
}
@media screen and (max-width: 800px){
.item_style{
  margin: 58px 0;
}}

@media screen and (max-width: 415px){
.burger-menu{
  background-image: url("./photo/menu.png");
  background-repeat: no-repeat;
  width: 24px;
  height: 14px;
  display: inline-block;
  margin-left: 33px;
}}


.header{
 height: 40px;
  box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);
  margin-bottom: 24px;
  position: fixed;
    top: 0;
    left: 0;
    right: 0;
    z-index: 2;
    background: white;
}
@media screen and (max-width: 415px){
  .header{
    height: 66px;
    box-shadow: none;
  }}


.header_icon{
  margin: 0 33px ;
}

.header_container{
  display: flex;
  justify-content: space-between;
  max-width: 1390px;
  margin: 0 auto;
  padding-top: 12px;

}

@media screen and (max-width: 1390px){
  .header_container{
    padding-left: 12px;
    padding-right: 12px ;
  }}

  @media screen and (max-width: 415px){
  .header_container{
    padding-top: 22px;

  }}

.header_logo{
  font-family: 'Open Sans';
  font-weight: 700;
  font-size: 22px;
  line-height: 16px;
  letter-spacing: 0.04em;
  text-transform: uppercase;
  color: #000000;
}






.footer_title{
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  font-family: 'Open Sans';
  letter-spacing: 0.04em;
  text-transform: uppercase;
  color: #333333;
  margin-bottom: 16px;
}

.footer_news{
  margin-bottom: 37px;
}

.footer_blocks{
  font-family: 'Open Sans';
  font-weight: 400;
  font-size: 14px;
  line-height: 20px;
  letter-spacing: 0.04em;
  color: #333333;
  margin-bottom: 8px;
}

.footer_email{
  border: none;
  border-bottom: 1px solid #C4C4C4;
  padding-right: 24px;
  background-image: url("./photo/close.png");
  background-repeat: no-repeat;
  background-position: right 4px;
  padding-bottom: 12px;
  width: 100%;

}

.footer_customers{
    display: flex;
    flex-direction: column;
    width: auto;
}
 @media screen and (max-width: 800px){
  .footer_customers{
    width: 50%;

  }}


.footer_customers:first-child{
  padding-left: 16px;
}

.footer_feedback{
  width: 50%;
  padding: 0 10%;
  box-sizing: border-box;
}
@media screen and (max-width: 800px){
  .footer_feedback{
    padding: 0 4%; 
    padding-left: 16px;
}
}
.footer_row{
  display: flex;
  justify-content: space-around;
  width: 50%;
}


@media screen and (max-width: 800px){
  .footer_row{
    margin-bottom: 58px !important; 
}
}

@media screen and (max-width: 800px){
  .footer_feedback, .footer_row{
    margin: 0 auto;
    width: 100%;
}

.footer_email{
      background-repeat: no-repeat;
    background-position: right 4px;
    padding-bottom: 12px;
    width: 100%;
    padding-right: 0;
    box-sizing: border-box;
}
}






.button_subscribe{
  width: 150px;
  height: 36px;
  border: 1px solid #333333;
  align-items: center;
  padding: 8px 28px;
  font-weight: 400;
  font-size: 14px;
  line-height: 20px;
  font-family: 'Open Sans';
  letter-spacing: 0.04em;
  margin: 35px 0 0 auto;
  background-color: white;
}

.gallery-main{
  display: flex;
  justify-content: center;
}
@media screen and (max-width: 415px){
  .gallery-main{
    flex-direction: column;
  }
}


.gallery_photo-big {
  margin-right: 16px;
  /* margin-top: 35px; */
}
@media screen and (max-width: 415px){
  .gallery_photo-big{
    margin-right: 0;
  }
}
.gallery_photo-big img{
  width: 100%;
  display: block;
      margin-bottom: 16px;
}
@media screen and (max-width: 415px){
  .gallery_photo-big img{
    margin-bottom: 10px;
  }
}


.gallery_photo-margin{
  margin-right: 16px;
}

.gallery_row{
  display: flex;
  flex-direction: row;
  width: 100%;
}
.gallery_row:first-child{
  margin-bottom: 16px;
}
@media screen and (max-width: 415px){
  .gallery_row:first-child{
    margin-bottom: 10px;
  }
}

.gallery_dark::after{
  content: '';
  width: 100%;
  height: 100%;
  position: absolute;
  top: 0; left: 0;
  background-color: rgba(0,0,0,1);
   
}

.line{
  border-bottom: 0.5px solid #C4C4C4;
  margin: 29px 0 29px 0;
  padding: 0;
  position: relative;
  left: -21px;
}
@media screen and (max-width: 800px){
  .line{
    display: none;
  }
}

.line-mobile{
  display: none;
}

@media screen and (max-width: 800px){
.line-mobile{
  display: block;
  border-bottom: 0.5px solid #C4C4C4;
  margin: 29px 0 29px 0;
  position: relative;
  left: -21px;
}
}



.button_increase, .button_decrease{
  font-weight: 400;
font-size: 14px;
line-height: 20px;
}

.button_decrease{
  margin-right: 12px;
}

.button_add-to-card{
  font-weight: 400;
font-size: 14px;
line-height: 20px;
letter-spacing: 0.04em;
margin-right: 4px;
}


.count-selector{
  margin-top: 40px;
  margin-bottom: 12px;
  display: flex;
}
.count_all, .count_buttons{
  display: flex;
}
@media screen and (max-width: 415px){
  .count_all, .count-selector{
    display: block;
    margin-bottom: 15px;
  }
}

.choose_size{
  width: 315px;
  height: 44px;
  display:block;
  margin-top: 33px;
  appearance: none;
  background-image: url("./photo/Line15_1.png");
  background-repeat: no-repeat;
  background-position: 287px center;
  padding-left: 15px;
  font-weight: 400;
  font-size: 14px;
  line-height: 20px;
  font-family: "Open Sans";
  margin-bottom: 10px;
  border: 1px solid #333333;
}


.choose_your-size{
  font-weight: 400;
  font-size: 14px;
  line-height: 20px;
  color: #333333;
  border: none;  
}

.discount_sale{
  border: 1px solid #333333;
  padding: 3px 9px;
  display: inline-block;
  font-weight: 400;
  font-size: 12px;
  line-height: 16px;
  margin-top: 10px;
  margin-right: 10px;
}

.price{
  margin-top: 46px;
}

.price_main{
  letter-spacing: 0.04em;
  color: #333333;
  margin-right: 8px;
  font-family: 'Open Sans';
  font-style: normal;
  font-weight: 700;
  font-size: 24px;
  line-height: 24px;
}

.price_discount{
  font-weight: 400;
  font-size: 14px;
  line-height: 20px;
  text-decoration: line-through;
  color: #828282;
  margin-right: 20px;
  letter-spacing: 0.04em;
}

.description{
  width: 50%;
  padding-left: 36px;
  box-sizing: border-box;
}
@media screen and (max-width: 800px){
  .description{
    width: 100%;
   
  }}


  
.gallery_photos, .gallery_photo-big{
  width: 50%;
}
@media screen and (max-width: 415px){
  .gallery_photos, .gallery_photo-big{
    width: 100%;
 
  }}

  

.gallery_cell{
  width: 50%;
  position: relative;
}

.gallery_cell:hover .hidden-item{
  display: block;
  cursor: pointer;
}

.hidden-item{
  display: none;
  background: rgba(51, 51, 51, 0.7);
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
} 

.hidden-item_icon, .hidden-item_like, .hidden-item_shopper{
  position: absolute;
}

.hidden-item_shopper{
  background: url("./photo/icon-shopper.png") no-repeat 0 0;
  width: 32px;
  height: 35px;
  left: 50%;
  top: 50%;
  margin-left: -16px;
  margin-top: -16px;
}

.hidden-item_shopper span{
  position: absolute;
  width: 142px;
  margin-left: -71px;
  bottom: -23px;
  color: white;
  font-weight: 400;
  font-size: 14px;
  line-height: 20px;
  letter-spacing: 0.04em;
  font-family: 'Open Sans';
}

.hidden-item_icon{
  background: url("./photo/icon-gallery.png") no-repeat 0 0;
  width: 16px;
  height: 16px;
  top: 16px;
  right: 16px;
}

.hidden-item_like{
  background: url("./photo/icon-like.png") no-repeat 0 4px;

  bottom: 20px;
  left: 50%;
  color: white;
  width: 50px;
  height: 20px;
  padding-left: 10px;
  margin-left: -25px;
  font-weight: 400;
  font-size: 14px;
  line-height: 20px;
  letter-spacing: 0.04em;
}



.gallery_cell:first-child{
  margin-right: 16px;
}
@media screen and (max-width: 415px){
  .gallery_cell:first-child{
    margin-right: 10px;
 
  }}

.gallery_photos{
  display: flex;
  flex-direction: column;
}

.gallery_photos img{
  width: 100%;
  display: block;
}

.main_photo-wrapper{
  width: 50%;

  position: relative;
}
@media screen and (max-width: 800px){
  .main_photo-wrapper{
    width: 100%;
  }}

.main_photo{

width: 100%;
}  
@media screen and (max-width: 800px){
  .main_photo{
    margin-bottom: 0;
  }}  
.description_title{
  font-size: 18px;
  color: #333333;
  margin-bottom: 8px;
  font-weight: 600;
  line-height: 24px;
}

.description_arrow{
  position: relative;
    top: 2px;
}

.description_reviews{
  letter-spacing: 0.04em;
  font-weight: 400;
  font-size: 14px;
  line-height: 20px;
  color: #333333;
  margin-right: 13px;
}

.description_rewiew{
  margin-left: 5px;
  margin-right: 8px;
  letter-spacing: 0.04em;
  font-weight: 400;
  font-size: 14px;
  line-height: 20px;
  color: #333333;
}



.description_art{
  font-size: 12px;
  color: #828282;
  letter-spacing: 0.04em;
  margin-bottom: 18px;
  font-weight: 400;
  line-height: 16px;
}



.links{
  display: flex;
  flex-direction: column;
}



.item-link_icon::before {
  content:"";
  background-repeat: no-repeat;
  background-position: 0 0 ;
  display: inline-block;
  width: 15px;
  height: 15px;
  position: relative;
  top: 3px;
  
}
.item-link_icon_t-shirt::before{
  background-image: url("./photo/icon-t-shirt.png");
  width: 16px;
  height: 16px;
      margin-right: 6.5px;
      top: 4px;
}

.item-link_icon_clock::before{
  background-image: url("./photo/icon-clock.png");
  width: 18px;
  height: 18px;
      margin-right: 4.5px;
      top: 5px;
      left: -1px;

}

.item-link_icon_bag::before{
  background-image: url("./photo/icon-bag.png");
    width: 14px;
    height: 10px;
        margin-right: 8.5px;
        top: 1px;
        left: 1px
}
@media screen and (max-width: 415px){
  .item-link_icon_bag{
    margin-bottom: 58px;
  }}

.item-link{
  font-weight: 400;
  font-size: 14px;
  line-height: 20px;
  letter-spacing: 0.04em; 
  color:  #333333;
  text-decoration: none;
  /* border-bottom: 1px solid s#333333; */
  text-decoration-line: underline;

}
.links .item-link{
    margin-bottom: 12px;
}
.button_like{
  background-image: url("./photo/heart.png");
  background-repeat: no-repeat;
  background-position: center center;
  width: 44px;
  height: 44px;
  background-color: #333333;
  border: none;
  padding: 0;
}

.button_add-to-card{
  width: 203px;
  height: 44px;
  background-color: #333333;
  color: white;
  font-size: 14px;
  border: none;
  padding: 0;

}

.button_increase, .button_decrease{
  width: 44px;
  height: 44px;
  border: none;
  background-color: #F2F2F2;
  font-size: 14px;
  padding: 0;
}

.count{
  width: 44px;
  height: 44px;
  background-color: #F2F2F2;
  border: none;
  font-size: 14px;
  padding: 0;
  text-align: center;
  
  font-weight: 400;
  line-height: 20px;
}



.container_footer{
  max-width: 1390px;
  margin: 142px auto 70px;
  display: flex;
  justify-content: space-around;
}
@media screen and (max-width: 800px){
  .container_footer{
    flex-direction: column;
    margin-top: 40px
  }}


.container_gallery{
  max-width: 1390px;
  margin: 0 auto;
  text-align: center;
}

.container{
  max-width: 1390px;
  margin: 0 auto;
  display: flex;
  flex-direction: row;
  justify-content: center;
    margin-top: 64px;
  
}
@media screen and (max-width: 800px){
  .container{
    flex-direction: column;
  }}
</style>
