<template>
    <div class="image-container">
        <img v-for="(image, index) in images" :key="index" :src="image.src" :style="{ height: image.height, width: image.width, opacity: 0 }"
            :class="[image.class, { 'fade-in': image.visible }]" />
    </div>
</template>
  
<script>
export default {
    data() {
        return {
            images: [
                {
                    src: "/media/papers/1.png",
                    height: "200px",
                    visible: false,
                    class: "absolute top-18 left-20"
                },
                {
                    src: "/media/papers/2.png",
                    height: "200px",
                    visible: false,
                    class: "absolute top-18 left-60"
                },
                {
                    src: "/media/papers/3.png",
                    height: "200px",
                    visible: false,
                    class: "absolute top-18 left-100"
                },
                {
                    src: "/media/papers/4.png",
                    height: "200px",
                    visible: false,
                    class: "absolute top-18 left-140"
                },
                {
                    src: "/media/papers/5.png",
                    height: "200px",
                    visible: false,
                    class: "absolute top-18 left-180"
                },
                {
                    src: "/media/papers/7.png",
                    height: "200px",
                    visible: false,
                    class: "absolute top-42 left-160"
                },
                {
                    src: "/media/papers/8.png",
                    height: "150px",
                    visible: false,
                    class: "absolute top-52 left-120"
                },
                {
                    src: "/media/papers/6.png",
                    height: "200px",
                    visible: false,
                    class: "absolute top-58 left-100"
                },
                {
                    src: "/media/papers/9.png",
                    height: "200px",
                    visible: false,
                    class: "absolute top-66 left-60"
                },
                {
                    src: "/media/papers/10.png",
                    height: "200px",
                    visible: false,
                    class: "absolute top-71 left-40"
                },
                {
                    src: "/media/papers/11.png",
                    width: "350px",
                    visible: false,
                    class: "absolute top-81 left-10"
                },
                {
                    src: "/media/papers/13.png",
                    width: "350px",
                    visible: false,
                    class: "absolute top-81 left-10"
                },
                {
                    src: "/media/papers/12.png",
                    width: "350px",
                    visible: false,
                    class: "absolute top-91 right-180"
                },
                {
                    src: "/media/papers/6.png",
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
  