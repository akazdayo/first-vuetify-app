<template>
    <v-parallax src="https://cdn.vuetifyjs.com/images/parallax/material2.jpg">
        <div class="d-flex flex-column fill-height justify-center align-center text-white">
            <h1 class="text-h4 font-weight-thin mb-4">
                Beef
            </h1>
            <h4 class="subheading">
                Very tasty beef
            </h4>
            <v-rating v-model="rating" bg-color="orange-lighten-1" color="white"></v-rating>
            <v-card class="mx-auto" max-width="425">
                <v-list lines="two">
                    <v-list-subheader>Review</v-list-subheader>

                    <v-list-item prepend-avatar="https://cdn.vuetifyjs.com/images/lists/1.jpg" title="Very bad beef">
                        <template v-slot:subtitle>
                            I think it is very good beef.The price is cheap and I would like to go back.
                        </template>
                    </v-list-item>

                    <v-divider inset></v-divider>

                    <v-list-item prepend-avatar="https://cdn.vuetifyjs.com/images/lists/2.jpg">
                        <template v-slot:title>
                            The above review is fake. <span class="text-grey-lighten-1"></span>
                        </template>

                        <template v-slot:subtitle>
                            The above review is fake. Please don't be fooled. This review may also be a fake.
                        </template>
                    </v-list-item>

                    <v-divider inset></v-divider>

                    <v-list-item prepend-avatar="https://cdn.vuetifyjs.com/images/lists/3.jpg" title="Very good!">
                        <template v-slot:subtitle>
                            I find this pork very tasty.I like it very much.
                        </template>
                    </v-list-item>
                </v-list>
            </v-card>
            <v-container>
                <v-row justify="center">
                    <v-btn color="red-darken-2" @click="snackbar = true">
                        Good
                    </v-btn>

                    <v-snackbar v-model="snackbar" :timeout="timeout" multi-line>
                        {{ good }}

                        <template v-slot:actions>
                            <v-btn color="red" variant="text" @click="snackbar = false">
                                Close
                            </v-btn>
                        </template>
                    </v-snackbar>

                </v-row>
            </v-container>


        </div>
    </v-parallax>


    <v-responsive class="overflow-y-auto" max-height="550">
        <div class="pa-6 text-center position-sticky">
            Scroll down
        </div>

        <v-responsive min-height="50vh"></v-responsive>

        <div class="text-center text-body-2 mb-12">
            The card will appear below:
        </div>

        <v-lazy v-model="isActive" :options="{
            threshold: .5
        }" min-height="200" transition="fade-transition">
            <v-card class="mx-auto" max-width="336">
                <v-card-title>Card title</v-card-title>

                <v-card-text>
                    Phasellus magna. Quisque rutrum. Nunc egestas, augue at pellentesque laoreet, felis eros vehicula
                    leo, at
                    malesuada velit leo quis pede. Aliquam lobortis. Quisque libero metus, condimentum nec, tempor a,
                    commodo
                    mollis, magna.

                    In turpis. In dui magna, posuere eget, vestibulum et, tempor auctor, justo. In turpis. Pellentesque
                    dapibus
                    hendrerit tortor. Ut varius tincidunt libero.
                </v-card-text>
            </v-card>
        </v-lazy>
    </v-responsive>

</template>


<script lang="ts">
export default {
    data: () => ({
        rating: 1,
        isActive: false,
        snackbar: false,
        timeout: 2000,
        good: `あなたはGoodを送信しました👍`,
        bad: `あなたはBadを送信しました👎`

    }),
    methods: {
        onpressed: function (_: any) {
            alert("nyaa")
        }
    }
}
</script>