<template>
  <div class="demo-frame">
    <div class="header bg-success">
      <p>My order</p>
    </div>
    <div ref="tabSlick" class="slick slick-tab">
      <div>All Orders</div>
      <div>Waiting for Payment</div>
      <div>Processing</div>
      <div>Shipped</div>
      <div>Cancelled</div>
    </div>
    <div ref="contentSlick" class="slick slick-content">
      <div>
        <Items />
        <Items />
      </div>
      <div>
        <Items />
        <Items />
        <Items />
      </div>
      <div>
        <Items />
        <Items />
        <Items />
      </div>
      <div>
        <Items />
      </div>
      <div>
        <Items />
        <Items />
        <Items />
      </div>
    </div>
  </div>
</template>

<script>
import 'slick-carousel/slick/slick.css';
import 'slick-carousel/slick/slick-theme.css';
import 'slick-carousel';
import $ from 'jquery';
import Items from './components/Items.vue';

export default {
  name: 'App',
  components: {
    Items,
  },
  mounted() {
    this.initializeSlick();
  },
  methods: {
    initializeSlick() {
      $(this.$refs.tabSlick).slick({
        slidesToShow: 1,
        slidesToScroll: 1,
        asNavFor: this.$refs.contentSlick,
        dots: true,
        focusOnSelect: true,
        infinite: false,
        variableWidth: true,
      });

      $(this.$refs.contentSlick).slick({
        slidesToShow: 1,
        slidesToScroll: 1,
        arrows: false,
        fade: true,
        asNavFor: this.$refs.tabSlick,
        infinite: false,
      });
    },
  },
};
</script>

<style>
*{
  padding: 0;
  margin: 0;
}
body{
  font-family: Arial;
  font-size: 15px;
}
.slick-slider .slick-arrow,
.slick-slider .slick-dots{
  display:none !important
}

.slick-tab .slick-slide{
  padding:5px 15px;
  text-align: center;
}
.slick-tab .slick-current{
  border-bottom:solid 2px #28a745
}

.slick-content .slick-slide{
  background:#ddd;
  padding:15px;
  min-height: 200px;
}

.slick-slider
{
    position: relative;
    display: block;
    box-sizing: border-box;
    -webkit-user-select: none;
       -moz-user-select: none;
        -ms-user-select: none;
            user-select: none;
    -webkit-touch-callout: none;
    -khtml-user-select: none;
    -ms-touch-action: pan-y;
        touch-action: pan-y;
    -webkit-tap-highlight-color: transparent;
}

.slick-list
{
    position: relative;
    display: block;
    overflow: hidden;
    margin: 0;
    padding: 0;
}
.slick-list:focus
{
    outline: none;
}
.slick-list.dragging
{
    cursor: pointer;
    cursor: hand;
}

.slick-slider .slick-track,
.slick-slider .slick-list
{
    -webkit-transform: translate3d(0, 0, 0);
       -moz-transform: translate3d(0, 0, 0);
        -ms-transform: translate3d(0, 0, 0);
         -o-transform: translate3d(0, 0, 0);
            transform: translate3d(0, 0, 0);
}

.slick-track
{
    position: relative;
    top: 0;
    left: 0;

    display: block;
    margin-left: auto;
    margin-right: auto;
}
.slick-track:before,
.slick-track:after
{
    display: table;

    content: '';
}
.slick-track:after
{
    clear: both;
}
.slick-loading .slick-track
{
    visibility: hidden;
}

.slick-slide
{
    display: none;
    float: left;

    height: 100%;
    min-height: 1px;
}
[dir='rtl'] .slick-slide
{
    float: right;
}
.slick-slide img
{
    display: block;
}
.slick-slide.slick-loading img
{
    display: none;
}
.slick-slide.dragging img
{
    pointer-events: none;
}
.slick-initialized .slick-slide
{
    display: block;
}
.slick-loading .slick-slide
{
    visibility: hidden;
}
.slick-vertical .slick-slide
{
    display: block;

    height: auto;

    border: 1px solid transparent;
}
.slick-arrow.slick-hidden {
    display: none;
}
.header{
  width: 100%;
  height: 40px;
}
.header > p{
  text-align: center;
  line-height: 40px;
  color: white;
}
.slick-initialized .slick-slide{
  padding: 10px;
}
.slick-dotted.slick-slider{
  margin-bottom: 0px;
}

.slick-content .slick-slide{
    padding: 0px;
    height: 100vh;
}
*{
    padding: 0;
    margin: 0;
}
.fz-90{
    font-size: 90%;
}
.image-thumb{
    width: 80px;
    height: 80px;
    border-radius: 4px;
    border: 0.5px solid rgb(238, 238, 238);
    background-repeat: no-repeat;
    background-size: 90%;
    background-position: center center;
    position: relative;
    float: left;
    background-image: url(https://images.macrumors.com/t/9r84bU_ZTOTrUixxwhjHUFsAvD4=/800x0/smart/article-new/2017/09/iphonexdesign.jpg?lossy);
    flex-shrink: 0;
}
.status{
    width: calc(100% - 90px);height: 90px;margin-top: 5px;float: right;
}

</style>
