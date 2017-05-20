<template>
    <svg class="" viewBox="0 0 284 284" version="1.1" xmlns="http://www.w3.org/2000/svg">
        <g>
            <linearGradient id="SVGID_1_" gradientUnits="userSpaceOnUse" x1="141.73" y1="3.9387" x2="141.73" y2="1245.944">
                <stop  offset="0" style="stop-color:#000000"/>
              <stop  offset="1" style="stop-color:#ffffff;stop-opacity:0"/>
            </linearGradient>
            <path style="fill:url(#SVGID_1_);" d="M137.4,279.1l-133-133c-2.4-2.4-2.4-6.3,0-8.7l133-133c2.4-2.4,6.3-2.4,8.7,0l133,133
		c2.4,2.4,2.4,6.3,0,8.7l-133,133C143.7,281.5,139.8,281.5,137.4,279.1z"/>
        </g>
    </svg>
</template>

<style>
.VueToNuxtLogo
{
  display: inline-block;
  animation: turn 2s linear forwards 1s;
  transform: rotateX(180deg);
  position: relative;
  overflow: hidden;
  height: 180px;
  width: 245px;
}
.Triangle
{
  position: absolute;
  top: 0;
  left: 0;
  width: 0;
  height: 0;
}
.Triangle--one
{
  border-left: 105px solid transparent;
  border-right: 105px solid transparent;
  border-bottom: 180px solid #41B883;
}
.Triangle--two
{
  top: 30px;
  left: 35px;
  animation: goright 0.5s linear forwards 3.5s;
  border-left: 87.5px solid transparent;
  border-right: 87.5px solid transparent;
  border-bottom: 150px solid #3B8070;
}
.Triangle--three
{
  top: 60px;
  left: 35px;
  animation: goright 0.5s linear forwards 3.5s;
  border-left: 70px solid transparent;
  border-right: 70px solid transparent;
  border-bottom: 120px solid #35495E;
}
.Triangle--four
{
  top: 120px;
  left: 70px;
  animation: godown 0.5s linear forwards 3s;
  border-left: 35px solid transparent;
  border-right: 35px solid transparent;
  border-bottom: 60px solid #fff;
}

@keyframes turn {
  100% {
    transform: rotateX(0deg);
  }
}
@keyframes godown {
  100% {
    top: 180px;
  }
}
@keyframes goright {
  100% {
    left: 70px;
  }
}
</style>
