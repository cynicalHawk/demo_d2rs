<template>
    <v-card
        max-width="500"
    >
        <v-img
            width="500"
            src='kf_symbols/kf_symbol1.jpg'
        ></v-img>
    </v-card>
</template>

<script>
export default {
    props: ['id', 'location', 'img', 'description']
}
</script>

