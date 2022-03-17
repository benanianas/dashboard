<template>
<div class='cnt'>
  <div class="top d-flex justify-content-between mb-3">
    <div class=" h4">Up Time:00:11:39</div>
    <img width="40" height="40" src="@/static/settings.png" />
  </div>
  <div class="row" style="max-width: 1500px; margin: auto;">
    <div class="col-md-6 d-flex justify-content-center align-items-center">
      <div style="position: relative; width: 350px;height: 350px; border-radius: 50%; border: solid #fff 1px;">
        <div class="circle-txt" style="top: 45%;font-size: 1.8rem; opacity: .5; font-weight: 600;">STATUS</div>
        <div class="circle-txt" style="top: 55%;font-size: 1.3rem; font-weight: 600;">OP START</div>
      </div>
    </div>
    <div class="col-md-6 cards pt-5" style="color: #363636;">
      <div v-for="(elm, i) in cards" :key="i" class="crd row mb-5" :style="`border: solid ${elm.color} 2px;`">
        <div class="col-9 d-flex justify-content-center align-items-center" style="position: relative;">
          <div class="display-3" style="font-weight: 400;"> {{elm.value}} {{elm.unit}}</div>
          <div style="position: absolute; bottom: 5px; left: 20px; font-weight: 600; font-size: 1.2rem;">{{elm.text}}</div>
        </div>
        <div class="col-3 d-flex  justify-content-center align-items-center" :style="`background-color: ${elm.color};`">
          <img width="90" height="90" :src="elm.icon" />
        </div>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'IndexPage',
  data(){
    return {
      cards: [
        {
          color: "#ff3434",
          text: "Temperature",
          icon: require('@/static/temperature.png') ,
          unit: '°C',
          value: '499'
        },
         {
          color: "#ffaa3b",
          text: "Cycle Time",
          icon: require('@/static/cycle.png'),
          unit: 's',
          value: '09.5'
        },
         {
          color: "#04a780;",
          text: "Cycle Count",
          icon: require('@/static/counter.png'),
          unit: '',
          value: '4'
        },
      ]
    }
  }
}
</script>

<style>
.html, body{
  width: 100vw;
  height: 100vh;
  background: radial-gradient(#0d4881,#0f336b);
  padding: 30px;
  color: #fff;
}
.crd{
  background: #fff;
  width: 100%;
  height: 180px;
  border-radius: 8px;
}
.circle-txt{
  position: absolute;
  transform: translate(-50%, -50%);
  left: 50%;
}
</style>
