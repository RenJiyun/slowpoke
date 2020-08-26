<template>
  <a-scene>
    <a-box
      position="0 2 -5"
      rotation="0 45 45"
      scale="1 1 1"
      animation="property: object3D.position.y; to: 2.2; dir: alternate; dur: 2000; loop: true"
      scale-on-mouseenter
    ></a-box>

    <a-camera position="0 7 5">
      <a-cursor color="#FF0000"></a-cursor>
    </a-camera>
  </a-scene>
</template>

<script>
export default {
  beforeCreate() {
    AFRAME.registerComponent("scale-on-mouseenter", {
      schema: {
        to: { default: "2.5 2.5 2.5", type: "vec3" }
      },

      init: function() {
        var data = this.data;
        var el = this.el;
        this.el.addEventListener("click", function() {
          console.log("=====");
          el.object3D.scale.copy(data.to);
        });
      }
    });
  },
  methods: {}
};
</script>
