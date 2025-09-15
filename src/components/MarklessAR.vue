<template>
  <div class="ar-wrapper">
    <div class="ar-box">
      <a-scene
          renderer="colorManagement: true; physicallyCorrectLights: true; antialias: true"
          webxr="mode: ar; optionalFeatures: local-floor"
          xr-mode-ui="enabled: false"
          vr-mode-ui="enabled: false"
          embedded
      >
        <!-- Luci per migliorare la resa del modello -->
        <a-entity light="type: ambient; intensity: 0.6"></a-entity>
        <a-entity light="type: directional; intensity: 1" position="0 2 1"></a-entity>

        <!-- Modello senza marker, davanti alla camera -->
        <a-entity
            gltf-model="/coin.glb"
            scale="0.1 0.1 0.1"
            position="0 0 -1"
            rotation="0 90 0"
            animation-mixer
        ></a-entity>

        <a-entity camera></a-entity>
      </a-scene>
    </div>
  </div>
</template>

<style scoped>
.ar-wrapper {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}

.ar-box {
  width: min(90vw, 420px);
  aspect-ratio: 9 / 16;
  position: relative;
  overflow: hidden;
  border-radius: 12px;
  box-shadow: 0 6px 24px rgba(0, 0, 0, 0.25);
  background: #000;
}

.ar-box a-scene {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
}
</style>