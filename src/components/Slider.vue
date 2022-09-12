<script>
export default {

    props: {
        sliderData: Array
    },

    data() {
        return {
            currentSlide: 0,
            
            //Declaring interval to change slide automatically every 5s
            inter: setInterval(() => {
                if (this.currentSlide == this.sliderData.length - 1) {
                    this.changeSlide(0);
                }
                else {
                    this.changeSlide(this.currentSlide + 1)
                }
            }, 5000)
        }
    },

    methods: {
        changeSlide(index) {

            //Cancel last interval
            clearInterval(this.inter);

            //Change current index and current background image.
            this.currentSlide = index;
            this.$refs.backgroundImage.style.backgroundImage = `url(${this.sliderData[this.currentSlide].Image})`;
            document.getElementById("sliderBtn" + this.currentSlide).focus();

            this.resetAnimation();

            //Set interval to change slide automatically.
            this.inter = setInterval(() => {
                if (this.currentSlide == this.sliderData.length - 1) {
                    this.changeSlide(0);
                }
                else {
                    this.changeSlide(this.currentSlide + 1);
                }
            }, 5000);

        },

        resetAnimation(){
            this.$refs.loadingBar.style.animationName = "none";
            requestAnimationFrame(() => {
                this.$refs.loadingBar.style.animationName = ""
            }, 0);
        }
    },

    mounted() {
        this.changeSlide(0);
    }

}

</script>


<template>
    <div class="SliderDiv" ref="backgroundImage">
        <div class="SliderContent">

            <div class="SliderBtnWrapper">
                <button class="SliderBtn" v-for="(item, index) in sliderData" @click="changeSlide(index)"
                    :id="'sliderBtn' + index"></button>
            </div>

            <div class="TitleWrapper">
                <h1> {{ this.sliderData[currentSlide].Title }} </h1>
                <h2> {{ this.sliderData[currentSlide].SubTitle }} </h2>
            </div>

            <div class="LoadingBarDiv">
                <div id="loadingBar" ref="loadingBar"></div>
            </div>

            <div class="ContentDiv">
                <p> {{ this.sliderData[currentSlide].Content }} </p>
            </div>

            <div class="BottomBtnWrapper">
                <button class="BottomBtn" id="bottomBtn1"> {{ this.sliderData[currentSlide].Btn1Val }} </button>
                <button class="BottomBtn" id="bottomBtn2"> {{ this.sliderData[currentSlide].Btn2Val }} </button>
            </div>

        </div>

        <div class="FooterDiv">
            <div class="FooterBorder">
                <p>Lorem ipsum dolor sit amet</p>
            </div>
        </div>
    </div>
</template>

<style>
@import "../css/slider/sliderBtns.css";
@import "../css/slider/loadingBar.css";
@import "../css/slider/bottomBtns.css";
@import "../css/slider/titleWrapper.css";
@import "../css/slider/content.css";
@import "../css/slider/footer.css";

.SliderDiv {
    height: calc(100vh - var(--menuHeight));
    width: 100vw;

    background-color: #fdfdfd;

    transition-property: background-image;
    transition-duration: 300ms;
    transition-timing-function: ease-in;

    background-size: cover;
    background-position: center;

    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    flex-direction: column;
}

.SliderContent {
    height: 100%;
    padding-left: 15%;

    background-color: rgba(0, 0, 0, 0.5);

    color: #fff;

    display: flex;
    align-items: flex-start;
    justify-content: center;
    flex-direction: column;
    row-gap: 3%;
}

@media screen and (max-width: 750px) {
    .SliderContent {
        height: 100%;
        padding-left: 10%;

        background-color: rgba(0, 0, 0, 0.5);

        color: #fff;

        display: flex;
        align-items: flex-start;
        justify-content: center;
        flex-direction: column;
        row-gap: 3%;

        padding-top: 10%;
        padding-bottom: 10%;
    }
}
</style>