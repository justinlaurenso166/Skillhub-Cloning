<script setup>
    let sliderContainer = ref()
    let slider = ref()
    let cards = ref()
    let elementsToShow = ref()
    let sliderContainerWidth = ref()
    let cardWidth = ref()

    const carousel = ()=>{
        if(document.body.clientWidth < 640){
            elementsToShow.value = 1
        }else{
            elementsToShow.value = 3
        }
        sliderContainer.value = document.getElementById('sliderContainer')
        slider.value = document.getElementById('slider')
        cards.value = slider.value.getElementsByTagName('li')

        sliderContainerWidth.value = sliderContainer.value.clientWidth;

        cardWidth.value = sliderContainerWidth.value/elementsToShow.value;

        slider.value.style.width = cards.value.length*cardWidth.value+'px';
        slider.value.style.transition = 'margin'
        slider.value.style.transitionDuration = '1s'

        for(let index = 0; index < cards.value.length; index++){
            const element = cards.value[index];
            element.style.width = cardWidth.value+'px';
        }
    }

    const next = ()=>{
        if(+slider.value.style.marginLeft.slice(0,-2) != -cardWidth.value * (cards.value.length - elementsToShow.value)){
            slider.value.style.marginLeft = ((+slider.value.style.marginLeft.slice(0,-2)) - cardWidth.value) + 'px'
        }
    }

    const prev = ()=>{
        if(+slider.value.style.marginLeft.slice(0,-2) !== 0){
            slider.value.style.marginLeft = ((+slider.value.style.marginLeft.slice(0,-2)) + cardWidth.value) + 'px'
        }
    }

    onMounted(()=>{
        carousel();
    })
</script>

<template>
    <div>
        <section class="pt-32">
            <div class="text-center">
                <h3 class="text-5xl font-semibold tracking-wide">Our popular courses</h3>
                <p class="text-lg font-light mt-5 tracking-wide">Non-disclosure agreement seed round seed <br> money accelerator influencer.</p>
            </div>
            <div class="flex gap-2 mt-14">
                <div class="flex items-center w-1/12 justify-center">
                    <button @click="prev" class="rounded-full w-14 h-14 flex justify-center items-center shadow-gray-300 shadow-md"><img src="@/assets/prev.png"></button>
                </div>
                <div class="sliderContainer w-10/12 overflow-hidden" id="sliderContainer">
                    <ul id="slider" class="flex w-full gap-10">
                        <li class="border w-1/3 border-gray-300 p-4 rounded-md">
                            <div class="w-full">
                                <img src="@/assets/course1.png" width="100%">
                            </div>
                            <h4 class="font-semibold text-md mt-5">Graphic Design Course</h4>
                            <div class="flex justify-between mt-7">
                                <div>
                                    <img src="@/assets/8.png">
                                </div>
                                <div>
                                    <span class="text-[#3fba96] tracking-wider">
                                        $119.99
                                    </span>
                                </div>
                            </div>
                            <div class="flex items-center gap-2 mt-4">
                                <img src="@/assets/9.png">
                                <span class="font-extralight text-xs text-gray-400 -mt-1">25K+ Students</span>
                            </div>
                        </li>
                        <li class="border w-1/3 border-gray-300 p-4 rounded-md">
                            <div class="w-full">
                                <img src="@/assets/course3.png" width="100%">
                            </div>
                            <h4 class="font-semibold text-md mt-5">Illustration design course</h4>
                            <div class="flex justify-between mt-7">
                                <div>
                                    <img src="@/assets/8.png">
                                </div>
                                <div>
                                    <span class="text-[#3fba96] tracking-wider">
                                        $119.99
                                    </span>
                                </div>
                            </div>
                            <div class="flex items-center gap-2 mt-4">
                                <img src="@/assets/9.png">
                                <span class="font-extralight text-xs text-gray-400 -mt-1">25K+ Students</span>
                            </div>
                        </li>
                        <li class="border w-1/3 border-gray-300 p-4 rounded-md">
                            <div class="w-full">
                                <img src="@/assets/course2.png" width="100%">
                            </div>
                            <h4 class="font-semibold text-md mt-5">UI/UX design course</h4>
                            <div class="flex justify-between mt-7">
                                <div>
                                    <img src="@/assets/8.png">
                                </div>
                                <div>
                                    <span class="text-[#3fba96] tracking-wider">
                                        $119.99
                                    </span>
                                </div>
                            </div>
                            <div class="flex items-center gap-2 mt-4">
                                <img src="@/assets/9.png">
                                <span class="font-extralight text-xs text-gray-400 -mt-1">25K+ Students</span>
                            </div>
                        </li>
                        <li class="border w-1/3 border-gray-300 p-4 rounded-md">
                            <div class="w-full">
                                <img src="@/assets/course4.png" width="100%">
                            </div>
                            <h4 class="font-semibold text-md mt-5">Web Development</h4>
                            <div class="flex justify-between mt-7">
                                <div>
                                    <img src="@/assets/8.png">
                                </div>
                                <div>
                                    <span class="text-[#3fba96] tracking-wider">
                                        $119.99
                                    </span>
                                </div>
                            </div>
                            <div class="flex items-center gap-2 mt-4">
                                <img src="@/assets/9.png">
                                <span class="font-extralight text-xs text-gray-400 -mt-1">25K+ Students</span>
                            </div>
                        </li>
                    </ul>
                </div>
                <div class="flex items-center w-1/12 justify-center">
                    <button @click="next" class="rounded-full w-14 h-14 flex justify-center items-center shadow-gray-300 shadow-md"><img src="@/assets/next.png"></button>
                </div>
            </div>
        </section>
    </div>
</template>