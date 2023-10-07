<template>
<v-carousel show-arrows="hover" :height="250">
    <v-carousel-item src="https://cdn.vuetifyjs.com/images/cards/docks.jpg" cover></v-carousel-item>
    <v-carousel-item src="https://cdn.vuetifyjs.com/images/cards/hotel.jpg" cover></v-carousel-item>
    <v-carousel-item src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg" cover></v-carousel-item>
</v-carousel>
<v-container>
    <v-layout class="overflow-visible" style="height: 56px;">
        <v-bottom-navigation v-model="value" :bg-color="color" mode="shift">
            <v-btn :onclick="enableFood">
                <v-icon>mdi mdi-food</v-icon>
                <span>Indian</span>
            </v-btn>
            <v-btn :onclick="enableFood1">
                <v-icon>mdi mdi-noodles</v-icon>
                <span>Chinese</span>
            </v-btn>
            <v-btn :onclick="enableFood2">
                <v-icon>mdi mdi-food-turkey</v-icon>
                <span>Chiken</span>
            </v-btn>
            <v-btn :onclick="enableFood3">
                <v-icon>mdi mdi-food-fork-drink</v-icon>
                <span>Soft Drinks</span>
            </v-btn>
        </v-bottom-navigation>
    </v-layout>
    <v-divider :thickness="12"></v-divider>
    <div v-if="indFood">
        <v-container fluid class="bg-blue-grey-lighten-2 mb-6 pa-5">
            <v-row no-gutters>
                <v-col v-for="n in 3" :key="n">
                    <v-sheet class="pa-16 ma-5">
                        Dynamic Images
                    </v-sheet>
                </v-col>
            </v-row>
        </v-container>
    </div>
    <div v-if="indFood1">
        <v-container fluid class="bg-teal mb-6">
            <v-row no-gutters>
                <v-col v-for="n in 3" :key="n">
                    <v-sheet class="pa-16 ma-5">
                        Dynamic Images
                    </v-sheet>
                </v-col>
            </v-row>
        </v-container>
    </div>
    <div v-if="indFood2">
        <v-container fluid class="bg-brown mb-6">
            <v-row no-gutters>
                <v-col v-for="n in 3" :key="n">
                    <v-sheet class="pa-16 ma-5">
                        Dynamic Images
                    </v-sheet>
                </v-col>
            </v-row>
        </v-container>
    </div>
    <div v-if="indFood3">
        <v-container fluid class="bg-indigo mb-6">
            <v-row no-gutters>
                <v-col v-for="n in 3" :key="n">
                    <v-sheet class="pa-16 ma-5">
                        Dynamic Images
                    </v-sheet>
                </v-col>
            </v-row>
        </v-container>
    </div>
</v-container>
</template>

<script>
export default {
    name: 'CarosualComponent',
    data: () => ({
        value: 0,
        indFood: true,
        indFood1: false,
        indFood2: false,
        indFood3: false,
    }),
    methods:{
        enableFood(){
            console.log("click event");
            this.indFood = true;
            this.indFood1 = false;
            this.indFood2 = false;
            this.indFood3 = false;
        },
        enableFood1(){
            console.log("click event1");
            this.indFood = false;
            this.indFood2 = false;
            this.indFood3 = false;
            this.indFood1 = true;
        },
        enableFood2(){
            console.log("click event2");
            this.indFood = false;
            this.indFood1 = false;
            this.indFood3 = false;
            this.indFood2 = true;
        },
        enableFood3(){
            console.log("click event2");
            this.indFood = false;
            this.indFood1 = false;
            this.indFood2 = false;
            this.indFood3 = true;     
        },
    },
    computed: {
        color() {
            switch (this.value) {
                case 0:
                    return 'blue-grey'
                case 1:
                    return 'teal'
                case 2:
                    return 'brown'
                case 3:
                    return 'indigo'
                default:
                    return 'blue-grey'
            }
        },
    },
}
</script>
