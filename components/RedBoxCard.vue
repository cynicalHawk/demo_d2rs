<template>
    <v-card class="mx-auto text-left" max-width="500">
        <v-img
            height="200px"
            :src=img
        ></v-img>
        <v-card-title>{{location}}</v-card-title>
        <v-card-subtitle v-if="isComplete">
            <v-icon small color="green">fas fa-check</v-icon>
            Completed!
        </v-card-subtitle>
        <v-card-subtitle v-if="!isComplete">Not Complete</v-card-subtitle>
        <v-card-text class="text-left">{{description}}</v-card-text>
        <v-card-actions>
            <v-btn
                v-if="!active"
                color="primary"
                @click="clickActivate(id)"
            >
                Activate
            </v-btn>
            <v-btn
                v-if="active"
                color="primary"
                @click="clickDeactivate(id)"
            >
                Deactivate
            </v-btn>
            <v-btn
                color="primary"
                :disabled="!active"
                @click="clickComplete()"
            >
                Toggle Complete
            </v-btn>
        </v-card-actions>
    </v-card>
</template>

<script>
export default {
    props: ['id', 'location', 'img', 'description', 'active'],
    data: function() {
        return {
            isComplete: false,
        }
    },
    methods: {
        clickActivate(id) { 
            this.$emit('activate', id);
        },
        clickDeactivate(id) { 
            this.$emit('deactivate', id);
        },
        clickComplete() { 
            this.isComplete = !this.isComplete
        }
    }
}
</script>

