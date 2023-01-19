<template>
    <div>
        <div class="d-flex align-center text-center justify-center">
            <!--                  Bool              True               False -->
            <v-avatar :color="isIntersecting ? 'green-lighten-1' : 'red-darken-2'" variant="flat"
                class="mr-3 swing-transition" :size="isIntersecting ? '64' : '32'"></v-avatar>

        </div>


        <v-sheet class="overflow-y-auto" max-height="1080">
            <v-sheet height="300vh" class="d-flex align-center text-center pa-2">
                <v-col justify="center">
                    <div v-if="isIntersecting == true"> あいうえお
                        <v-img :aspect-ratio="aspectRatio" :width="width"
                            src="https://1.bp.blogspot.com/-uP8BFlcRFgU/X1CK7XOwFDI/AAAAAAABaww/2UhCSOzFA1gfzVh7HT6pbPo6StFy2iMBgCNcBGAsYHQ/s1600/hakase1_smile.png"
                            cover></v-img>
                    </div>
                    <div v-else>
                        <v-img :aspect-ratio="aspectRatio" :width="width"
                            src="https://cdn.vuetifyjs.com/images/parallax/material.jpg" cover></v-img>
                    </div>
                    <br>
                    <br>
                    <br>
                    <br>
                    <br>
                    <br>
                    <br>
                    <br>
                    <br>
                    <v-icon icon="fa:fas fa-lock" v-intersect="onIntersect"></v-icon>
                </v-col>
            </v-sheet>
        </v-sheet>
    </div>
</template>

<script>
export default {
    data: () => ({
        isIntersecting: false,
    }),

    methods: {
        onIntersect(isIntersecting, entries, observer) {
            // More information about these options
            // is located here: https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API
            this.isIntersecting = isIntersecting
        },
    },
}
</script>