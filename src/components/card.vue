<template>
  <div class="map-main">
    <div class="card-main">
        <div @mousedown="moveCard" id="card" class="card">
            <div id="item" class="item"></div>
        </div>
        
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  data(){
    return{
      card:null,
      startMouse:null,
      rotateY:null,
      itemStartX:null,
      item:null,
    }
  },
  methods:{
      removeMouse(){
          window.removeEventListener('mousemove',this.listenMouse)
          window.removeEventListener('mouseup',this.removeMouse)
      },
      listenMouse(res){
        if(!this.startMouse)
            this.startMouse = res.clientX;
        
        
        this.rotateY= res.clientX/10-this.startMouse/10
        this.item.style.left = `${this.itemStartX - (res.clientX/2 - this.startMouse/2)}px`
        this.card.style.transform=`rotateY(${this.rotateY}deg)`
      },
      moveCard(){
          this.card = document.getElementById('card');
          this.itemStartX = document.getElementById('item').offsetLeft
          this.item = document.getElementById('item')
          window.addEventListener('mousemove',this.listenMouse)
          window.addEventListener('mouseup',this.removeMouse)
      },
  }
}
</script>

<style lang="scss">
// @import url(https://fonts.googleapis.com/css?family=Anaheim);
// @import '@/scss/mixins.scss';

// *{
//   margin: 0;
//   padding: 0;
//   outline: none;
//   border: none;
// 	box-sizing: border-box;
// }
// html,body{
//   height: 100%;
//   background-image: radial-gradient(mintcream 0%, lightgray 100%);
// }

// .map-main{
//   height: 100%;
//   @include d-flex-center;
//   background-color: rgb(27, 27, 27);
//   .card-main{
//     width: 450px;
//     height: 600px;
//     perspective: 1000px;
//     .card{
//         overflow: hidden;
//         background-color: #fff;
//         width: 100%;
//         height: 100%;
//         transform-style: preserve-3d;
//         position: relative;
//         -webkit-box-shadow: inset 0px 0px 195px -60px rgba(0,0,0,0.75);
// -moz-box-shadow: inset 0px 0px 195px -60px rgba(0,0,0,0.75);
// box-shadow: inset 0px 0px 195px -60px rgba(0,0,0,0.75);
//         .item{
//             top: 50%;
//             left: 50%;
//             transform: translate(-50%,-50%);
//             position: absolute;
//             background-color: #000;
//             width: 150px;
//             height: 200px;
//         }
//     }
//   }
//   .container{
//     width: 210px;
//     height: 140px;
//     position: relative;
//     perspective: 1000px;
//     .carousel{
//       width: 100%;
//       height: 100%;
//       transform-style: preserve-3d;
//       transform: rotateX(-30deg)!important;
      
//     }
//   }
// }


// @keyframes item1{
//   from{
// 		transform: rotateY(0deg);
// 	}
// 	to{
// 		transform: rotateY(-360deg);
// 	}
// }
// @keyframes item2{
//   from{
// 		transform: rotateY(90deg);
// 	}
// 	to{
// 		transform: rotateY(-270deg);
// 	}
// }
// @keyframes item3{
//   from{
// 		transform: rotateY(180deg);
// 	}
// 	to{
// 		transform: rotateY(-180deg);
// 	}
// }
// @keyframes item4{
//   from{
// 		transform: rotateY(270deg);
// 	}
// 	to{
// 		transform: rotateY(-90deg);
// 	}
// }

// @keyframes rotation{
// 	from{
// 		transform: rotateY(0);
// 	}
// 	to{
// 		transform: rotateY(360deg);
// 	}
// }

</style>
