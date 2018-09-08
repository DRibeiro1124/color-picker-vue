<template>
    <div class="main-container">
        <div class="color-box" :style="boxStyle">
            <section class="sliders">
                <div class="color-prop">Hue</div>
                <input
                type="range"
                min="0"
                max="360"
                v-on:input="this.updateHueValue"
                :value="this.hue" />
                <div class="color-prop">Saturation</div>
                <input
                type="range"
                min="0"
                max="100"
                v-on:input="this.updateSaturationValue"
                :value="this.hue" />
                <div class="color-prop">Lightness</div>
                <input
                type="range"
                min="0"
                max="100"
                v-on:input="this.updateLightnessValue"
                :value="this.hue" />
                <div class="color-prop">Alpha</div>
                <input
                type="range"
                min="0"
                max="100"
                v-on:input="this.updateAlphaValue"
                :value="this.hue" />
            </section>
        </div>    

        <section class="display-colors">
            <div class="add-colors">
                <h3>hsla ({{this.hue}}, {{this.saturation}}, {{this.lightness}}, {{this.newAlpha}})</h3>
            </div>
        </section>
    </div>
</template>

<script>
export default {
    name: "ColorPicker",
    data: function () {
        return {
            hue: 180, 
            saturation: 50, 
            lightness: 50, 
            alpha: 100
        }
    },
    methods: {
        updateHueValue: function (event) {
            return this.hue = event.target.value
        },
        updateSaturationValue: function (event) {
            return this.saturation = event.target.value
        },
        updateLightnessValue: function (event) {
            return this.lightness = event.target.value
        },
        updateAlphaValue: function (event) {
            return this.alpha = event.target.value
        }
    },
    computed: {
        newAlpha: function () {
            return this.alpha / 100
        },
        boxStyle: function () {
            return {
                "background-color": "HSLA(" + this.hue + ", " + this. saturation + "%, " + this.lightness + "%, " + this.newAlpha +" )",
            };
        },
        
    }
};
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Merriweather|Montserrat');
/* font-family: 'Merriweather', serif;
font-family: 'Montserrat', sans-serif; */

.main-container {
    display: flex;
    justify-content: center;
    flex-direction: column;
    padding-top: 3em;
}

.color-box {
    font-family: 'Montserrat', sans-serif;
    border: 2px solid #222;
    border-radius: 1em;
    height: auto;
    width: auto;
    display: flex;
    justify-content: flex-start;
}

.color-prop {
    font-size: 12px;
    font-family: 'Merriweather', serif;
}

.sliders {
    padding: 10px;
}

.add-colors {
    margin-top: 0.8em;
    margin-left: auto;
    margin-right: auto;
    width: 15em;
    border: 1px solid #222;
    border-radius: 4px;
}

.display-colors {
    padding-top: 3em;

}
</style>
