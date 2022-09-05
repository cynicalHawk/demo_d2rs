<template>
    <v-container>
        <h1>Test</h1>
        <v-layout row wrap justify-space-between>
                <RedBoxCard
                    class="pa-6 ma-2"
                    v-for="k in cardData"
                    :key="k.id"
                    :id="k.id"
                    :location="k.location"
                    :img="k.img"
                    :description="k.description"
                />
        </v-layout>
    </v-container>
</template>

<script>
import RedBoxCard from './RedBoxCard.vue'

export default {
    // props: ['data'],
    data() {
        return {
            cardData: [
                {id: 0, location: "Opening Encounter", img: "/kf_symbols/kf_symbol1.jpg", description: "After completing the opening encounter and going through the portal, jump on the first swinging lamp and turn around. The circle is directly below the platform below you"},
                {id: 1, location: "Opening Encounter", img: "/kf_symbols/kf_symbol2.jpg", description: "This circle can be found on the wall directly behind the first secret chest. After riding the tombship across the chasm (second part of the jumping puzzle), jump off early and head left up the wall, then head through a hole in the wall to find the chest and circle"},
                {id: 2, location: "Totems Encounter", img: "/kf_symbols/kf_symbol3.jpg", description: "After completing the totems encounter, head into the left side room. The circle is on the wall behind the balcony where the knights spawn, towards the right side"},
                {id: 3, location: "Warpriest Encounter", img: "/kf_symbols/kf_symbol4.jpg", description: "After defeating the warpriest, this circle can be found on the wall by the right side balcony"},
            ]
        }
    },
    components: { RedBoxCard }
}
</script>
