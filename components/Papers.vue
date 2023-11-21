
<template>
    <div class="image-container">
        <img v-for="(image, index) in images" :key="index" :src="image.src" :style="{ height: image.height, width: image.width, opacity: 0 }"
            :class="[image.class, { 'fade-in': image.visible }]" />
    </div>
</template>
  
<script>
import paper1 from '/media/papers/1.png';
import paper10 from '/media/papers/10.png';
import paper11 from '/media/papers/11.png';
import paper12 from '/media/papers/12.png';
import paper13 from '/media/papers/13.png';
import paper2 from '/media/papers/2.png';
import paper3 from '/media/papers/3.png';
import paper4 from '/media/papers/4.png';
import paper5 from '/media/papers/5.png';
import paper6 from '/media/papers/6.png';
import paper7 from '/media/papers/7.png';
import paper8 from '/media/papers/8.png';
import paper9 from '/media/papers/9.png';
export default {
    data() {
        return {
            images: [
                {
                    src: paper1,
                    height: "200px",
                    visible: false,
                    class: "absolute top-18 left-20"
                },
                {
                    src: paper2,
                    height: "200px",
                    visible: false,
                    class: "absolute top-18 left-60"
                },
                {
                    src: paper3,
                    height: "200px",
                    visible: false,
                    class: "absolute top-18 left-100"
                },
                {
                    src: paper4,
                    height: "200px",
                    visible: false,
                    class: "absolute top-18 left-140"
                },
                {
                    src: paper5,
                    height: "200px",
                    visible: false,
                    class: "absolute top-18 left-180"
                },
                {
                    src: paper7,
                    height: "200px",
                    visible: false,
                    class: "absolute top-42 left-160"
                },
                {
                    src: paper8,
                    height: "150px",
                    visible: false,
                    class: "absolute top-52 left-120"
                },
                {
                    src: paper6,
                    height: "200px",
                    visible: false,
                    class: "absolute top-58 left-100"
                },
                {
                    src: paper9,
                    height: "200px",
                    visible: false,
                    class: "absolute top-66 left-60"
                },
                {
                    src: paper10,
                    height: "200px",
                    visible: false,
                    class: "absolute top-71 left-40"
                },
                {
                    src: paper11,
                    width: "350px",
                    visible: false,
                    class: "absolute top-81 left-10"
                },
                {
                    src: paper12,
                    width: "350px",
                    visible: false,
                    class: "absolute top-81 left-10"
                },
                {
                    src: paper13,
                    width: "350px",
                    visible: false,
                    class: "absolute top-91 right-180"
                },
                {
                    src: paper6,
                    width: "350px",
                    visible: false,
                    class: "absolute top-101 right-220"
                }
            ],
        };
    },
    mounted() {
        this.images.forEach((image, index) => {
            setTimeout(() => {
                image.visible = true;
            }, 300 * index);
        });
    },
};
</script>
  
<style>
.fade-in {
    animation: fadeIn 0.75s ease-in-out forwards; 
}

@keyframes fadeIn {
    from { opacity: 0; }
    to { opacity: 1; }
}
</style>
  