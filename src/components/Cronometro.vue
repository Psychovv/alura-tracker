<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
    name: 'CronometroFix',
    props: {
        tempoEmSegundos: {
            type: Number,
            required: true
        }
    },
    computed: {
        tempoDecorrido(): string {
            return new Date(this.tempoEmSegundos * 1000).toISOString().substr(11, 8)
        }
    }
})
</script>

<template>
    <section>
        <strong>
            {{ tempoDecorrido }}
        </strong>
    </section>
</template>

<style scoped></style>