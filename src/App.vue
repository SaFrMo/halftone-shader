<template>
    <div id="app">
        <FragmentShader class="shader" :key="Date.now()">
            <script type="shader/fragment">
                precision mediump float;
                uniform vec2 uResolution;
                uniform float uTime;
                void main() {
                    vec2 uv = gl_FragCoord.xy / uResolution.xy;
                    gl_FragColor = vec4(uv.x, 0.2, 0.2, 1.);
                }
            </script>
        </FragmentShader>
    </div>
</template>

<script>
import FragmentShader from '@fuzzco/fragment-shader'

export default {
    name: 'app',
    components: {
        FragmentShader
    }
}
</script>

<style lang="scss">
#app {
    display: flex;
    align-items: center;
    justify-content: center;
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;

    .shader {
        width: 66vw;
        height: 66vh;
        position: relative;
    }
}
</style>
