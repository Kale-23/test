<script>
    export let src;
    export let color;
    export let description;
</script>

<div class="card" data-color={color}>
    <img class="card-front-image card-image" src={src} alt={description}>
    <div class="card-faders">
        <img class="card-fader card-image" src={src} alt="">
        <img class="card-fader card-image" src={src} alt="">
        <img class="card-fader card-image" src={src} alt="">
        <img class="card-fader card-image" src={src} alt="">
        <img class="card-fader card-image" src={src} alt="">
        <img class="card-fader card-image" src={src} alt="">
        <img class="card-fader card-image" src={src} alt="">
        <img class="card-fader card-image" src={src} alt="">
    </div>
</div>

<style>
.card {
    background-size: cover;
    background-position: center;
    position: relative;
    cursor: pointer;
    outline: none;
    transition: scale 100ms;
}
.card .card-front-image {
  position: relative;
  z-index: 2;
}

.card .card-image {
  width: clamp(300px, 10vw, 300px);
  border-radius: clamp(0.5rem, 0.75vw, 2rem);
}
.card-faders {
  height: 100%;
  width: 100%;
  position: absolute;
  left: 0px;
  top: 0px;
  z-index: 1;
  opacity: 0;
  transition: opacity 1500ms;
  pointer-events: none;
}
.card:hover .card-faders {
  opacity: 1;
}
.card:active {
  scale: 0.98;
}
.card-fader {
  position: absolute;
  left: 0px;
  top: 0px;
}
.card-fader:nth-child(odd) {
  animation: fade-left 3s linear infinite;
}

.card-fader:nth-child(even) {
  animation: fade-right 3s linear infinite;
}

.card-fader:is(:nth-child(3), :nth-child(4)) {
  animation-delay: 750ms;
}

.card-fader:is(:nth-child(5), :nth-child(6)) {
  animation-delay: 1500ms;
}

.card-fader:is(:nth-child(7), :nth-child(8)) {
  animation-delay: 2250ms;
}

@keyframes fade-left {
  from {
    scale: 1;
    translate: 0%;
    opacity: 1;
  }
  
  to {
    scale: 0.8;
    translate: -30%;
    opacity: 0;
  }
}

@keyframes fade-right {
  from {
    scale: 1;
    translate: 0%;
    opacity: 1;
  }
  
  to {
    scale: 0.8;
    translate: 30%;
    opacity: 0;
  }
}
</style>
