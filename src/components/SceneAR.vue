<template>
  <div id="ar-scene">
    <a-scene
        vr-mode-ui="enabled: false"
        embedded
        arjs="trackingMethod: best; sourceType: webcam; debugUIEnabled: false;">

      <a-marker type="pattern" url="/public/pattern-marker.patt">
        <a-entity
            gltf-model="/coin.glb"
            scale="0.5 0.5 0.5"
            position="0 0 0"
            animation-mixer>
        </a-entity>
      </a-marker>

      <a-entity camera></a-entity>
    </a-scene>
  </div>
</template>

<style scoped>
#ar-scene {
  width: 100vw;
  height: 100vh;
  overflow: hidden;
}

a-scene {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
</style>
