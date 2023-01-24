<template>
    <div>
        <v-row justify="center" align="center">
            <v-col class="text-center">
                <div class="text-subtitle-2">Offset Top</div>
                {{ offsetTop }}
            </v-col>
        </v-row>
        <v-container id="scroll-target" style="max-height: 400px" class="overflow-y-auto">
            <v-row v-scroll:#scroll-target="onScroll" align="center" justify="center" style="height: 2000px;">
                <v-img :aspect-ratio="aspectRatio" :width="width"
                    src="https://1.bp.blogspot.com/-uP8BFlcRFgU/X1CK7XOwFDI/AAAAAAABaww/2UhCSOzFA1gfzVh7HT6pbPo6StFy2iMBgCNcBGAsYHQ/s1600/hakase1_smile.png"
                    cover v-if="offsetTop >= 200"></v-img>
                <h1 v-if="offsetTop >= 1000">hello</h1>
            </v-row>
        </v-container>
    </div>
</template>

<script>
export default {
    data: () => ({
        offsetTop: 0,
    }),

    methods: {
        onScroll(e) {
            this.offsetTop = e.target.scrollTop
        },
    },
}
</script>