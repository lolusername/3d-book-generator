<template>
  <section class="book container d-flex flex-column ">
    <transition>
          <BookForm v-bind:title="title"/>
    </transition>

    <div class="book-wrapper d-flex justify-content-center align-items-center">
      <div id="tridiv">
      <div class="scene" style="-webkit-transform:rotateX(178deg) rotateY(-112deg); -moz-transform:rotateX(178deg) rotateY(-112deg); -ms-transform:rotateX(178deg) rotateY(-112deg); transform:rotateX(178deg) rotateY(-112deg); ">
        <div class="shape cuboid-1 cub-1">
          <div class="face ft">
            <h1 class="main-copy">
              {{title.title}}
            </h1>
            <p class="author">
              {{title.author}}
            </p>
            <ul class="points-list">
              <li>{{title.point1}}</li>
              <li>{{title.point2}}</li>
              <li>{{title.point3}}</li>
            </ul>
            <img v-bind:src="title.imgUrl" alt="" id="logo">
            <div class="photon-shader" style="background-color: rgba(0, 0, 0, 0.15);"></div>
          </div>
          <div class="face bk">
            <div class="photon-shader" style="background-color: rgba(0, 0, 0, 0.3);"></div>
          </div>
          <div class="face rt">
            <div class="photon-shader" style="background-color: rgba(0, 0, 0, 0.3);"></div>
          </div>
          <div class="face lt">
            <div class="photon-shader" style="background-color: rgba(0, 0, 0, 0.3);"></div>
          </div>
          <div class="face bm">
            <div class="photon-shader" style="background-color: rgba(0, 0, 0, 0.3);"></div>
          </div>
          <div class="face tp">
            <div class="photon-shader" style="background-color: rgba(0, 0, 0, 0.3);"></div>
          </div>
        </div>
      </div>
     
    </div>
    
    </div>
  </section>
</template>

<script>

import BookForm from "./BookForm.vue";

export default {
  name: "Book",
    data: function() {
      return  {
        title:{
          title:"",
          author:"",
          point1:"",
          point2:"",
          point3:"",
          imgUrl:""
        }
      } 
  },
  components: {
    BookForm

  },
  props: {
    version: Boolean
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
$book-color: #000a12;

body {
  background:#f5f5f5;
}

#logo {
    max-height: 53px;
    object-fit: contain;
    float: right;
    margin-right: 20px;
    position: relative;
    position: absolute;
    right: 0;
    top: 381px;
}


.logo {
  width:120px;
  height:120px;
  background-image:url(https://www.festisite.com/static/partylogo/img/logos/google.png);
}

.main-copy {
  
    color: #fff;
    margin-top: 140px;
    margin-left: 20px;
    font-size: 40px;
}
#tridiv {
  perspective: 800px;
  // position: absolute;
  overflow: hidden;
  width: 100%;
  height: 100%;
  background: transparent;
  font-size: 100%;
      width: 400px;
    height: 600px;
}
.face {
  box-shadow: inset 0 0 0 1px rgba(0, 0, 0, 0.21);
}
.face .author {
  color:#fff;
  margin-left:23px;
}
.scene, .shape, .face, .face-wrapper, .cr {
  position: absolute;
  transform-style: preserve-3d;
}
.scene {
  width: 80em;
  height: 80em;
  top: 50%;
  left: 50%;
  margin: -40em 0 0 -40em;
}
.shape {
  top: 50%;
  left: 50%;
  width: 0;
  height: 0;
  transform-origin: 50%;
}
.face, .face-wrapper {
  overflow: hidden;
  transform-origin: 0 0;
  backface-visibility: hidden;
  /* hidden by default, prevent blinking and other weird rendering glitchs */
}
.face {
  background-size: 100% 100%!important;
  background-position: center;
}
.face-wrapper .face {
  left: 100%;
  width: 100%;
  height: 100%
}
.photon-shader {
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%
}
.side {
  left: 50%;
}
.cr, .cr .side {
  height: 100%;
}
[class*="cuboid"] .ft, [class*="cuboid"] .bk {
  width: 100%;
  height: 100%;
}
[class*="cuboid"] .bk {
  left: 100%;
}
[class*="cuboid"] .rt {
  transform: rotateY(-90deg) translateX(-50%);
}
[class*="cuboid"] .lt {
  transform: rotateY(90deg) translateX(-50%);
}
[class*="cuboid"] .tp {
  transform: rotateX(90deg) translateY(-50%);
}
[class*="cuboid"] .bm {
  transform: rotateX(-90deg) translateY(-50%);
}
[class*="cuboid"] .lt {
  left: 100%;
}
[class*="cuboid"] .bm {
  top: 100%;
}
/* .cub-1 styles */
.cub-1 {
  transform:translate3D(0em, -0.125em, -0.125em) rotateX(0deg) rotateY(-90deg) rotateZ(-180deg);
  opacity:1;
  width:20em;
  height:28em;
      width: 289px;
    height: 448px;
  margin:-14em 0 0 -10em;
}
.cub-1 .ft {
  transform:translateZ(3em);
}
.cub-1 .bk {
  transform:translateZ(-3em) rotateY(180deg);
}
.cub-1 .rt, .cub-1 .lt {
  width:6em;
  height:28em;
}
.cub-1 .tp, .cub-1 .bm {
  width:20em;
  height:6em;
}
.cub-1 .face {
  background-color:$book-color;
}
.cub-1 .ft {
  background-color:$book-color;
}
.cub-1 .bk {
  background-color:$book-color;
}
.cub-1 .tp {
  background-color:$book-color;
}
.cub-1 .bm {
  background-color:$book-color;
}
.cub-1 .lt {
  background-color:$book-color;
}
.cub-1 .rt {
  background-color:$book-color;
}
.cub-1 .ft {
  background-color:$book-color;
  background-image: url(../assets/Blank-GG-cover_1200x1855.png);
  background-size:cover !important;
  background-repeat:no-repeat;


}
.points-list {
      margin-left: 0;
    padding-left: 0;
    list-style-position: inside;
        margin-top: 80px;
}
.points-list>li {
    color: #fff;
    position: relative;
    margin-left: 20px;

    font-size: 14px;
}
</style>
