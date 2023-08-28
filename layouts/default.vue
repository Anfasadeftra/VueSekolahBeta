<template>
    <div id="app">
    <bagian-atas/>
    <Nuxt />
    <bagian-bawah />
    </div>
</template>

<script>
import BagianAtas from "~/components/BagianAtas.vue"
import BagianBawah from "~/components/BagianBawah.vue"

export default {
    components: {
        BagianAtas,
        BagianBawah,
    }
}

</script>
