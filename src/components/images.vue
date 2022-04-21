<template>
  <div class="map-main">
    <div class="container">
      <div class="carousel">
        <div class="deneme">
          <div class="items"><div class="rotate-image"><img class="image" src="@/assets/temp.jpg" alt=""></div></div>
          <div class="items"><div class="rotate-image"><img class="image" src="@/assets/temp.jpg" alt=""></div></div>
          <div class="items"><div class="rotate-image"><img class="image" src="@/assets/temp.jpg" alt=""></div></div>
          <div class="items"><div class="rotate-image"><img class="image" src="@/assets/temp.jpg" alt=""></div></div>
          <div class="items"><div class="rotate-image"><img class="image" src="@/assets/temp.jpg" alt=""></div></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  data(){
    return{
      black:null,
      startBlackX:null,
      startBlackY:null,
      isStart:false,
      isMinus:false,
      isPlus:false
    }
  },
}
</script>

<style lang="scss">
@import url(https://fonts.googleapis.com/css?family=Anaheim);
@import '@/scss/mixins.scss';

*{
  margin: 0;
  padding: 0;
  outline: none;
  border: none;
	box-sizing: border-box;
}
html,body{
  height: 100%;
  background-image: radial-gradient(mintcream 0%, lightgray 100%);
}

.map-main{
  height: 100%;
  @include d-flex-center;
  .container{
    width: 210px;
    height: 140px;
    position: relative;
    perspective: 1000px;
    .carousel{
      width: 100%;
      height: 100%;
      transform-style: preserve-3d;
      transform: rotateX(-30deg)!important;
      
      .deneme{
        width: 100%;
        height: 100%;
        transform-style: preserve-3d;
        animation: rotation 20s infinite linear;
        @include d-flex-center;
        .items{
          position: absolute;
          width: 186px;
          height: 116px;
          left: 10px;
          top: 10px;
          .rotate-image{
            width: 100%;
            height: 100%;
            .image{
              width: 100%;
            }
          }
          
          &:nth-child(1){
            transform: rotateY(0deg) translateZ(200px);
            transform-style: preserve-3d;
            
            .rotate-image{
              width: 100%;
              height: 100%;
              animation: item1 300s infinite linear;
              .image{
                position: absolute;
                
              }
            }
          }
          &:nth-child(2){
            transform: rotateY(90deg) translateZ(200px);
            transform-style: preserve-3d;
            .rotate-image{
              width: 100%;
              height: 100%;
              animation: item2 20s infinite linear;
              .image{
                position: absolute;
                
              }
            }
          }
          &:nth-child(3){
            transform: rotateY(180deg) translateZ(200px);
            transform-style: preserve-3d;
            .rotate-image{
              width: 100%;
              height: 100%;
              animation: item3 20s infinite linear;
              .image{
                position: absolute;
                
              }
            }
          }
          &:nth-child(4){
            transform: rotateY(270deg) translateZ(200px);
            transform-style: preserve-3d;
            .rotate-image{
              width: 100%;
              height: 100%;
              animation: item4 20s infinite linear;
              .image{
                position: absolute;
                
              }
            }
          }
          &:nth-child(5){
            transform-style: preserve-3d;
            .rotate-image{
              width: 100%;
              height: 100%;
              animation: item1 20s infinite linear;
              .image{
                position: absolute;
                
              }
            }
          }
        }
      }
    }
  }
}


@keyframes item1{
  from{
		transform: rotateY(0deg);
	}
	to{
		transform: rotateY(-360deg);
	}
}
@keyframes item2{
  from{
		transform: rotateY(90deg);
	}
	to{
		transform: rotateY(-270deg);
	}
}
@keyframes item3{
  from{
		transform: rotateY(180deg);
	}
	to{
		transform: rotateY(-180deg);
	}
}
@keyframes item4{
  from{
		transform: rotateY(270deg);
	}
	to{
		transform: rotateY(-90deg);
	}
}

@keyframes rotation{
	from{
		transform: rotateY(0);
	}
	to{
		transform: rotateY(360deg);
	}
}
</style>
