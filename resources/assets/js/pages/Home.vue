<style>

</style>

<template>
    <div id="cafes" class="page">
        <cafe-map v-show="cafesView === 'map'"></cafe-map>
        <cafe-list v-show="cafesView === 'list'"></cafe-list>

        <add-cafe-button></add-cafe-button>
        <toggle-cafes-view></toggle-cafes-view>
        <map-legend></map-legend>

        <router-view></router-view>
    </div>
</template>

<script>
    import CafeMap from '../components/cafes/CafeMap.vue';
    import CafeList from '../components/cafes/CafeList.vue';
    import AddCafeButton from '../components/cafes/AddCafeButton.vue';
    import ToggleCafesView from '../components/cafes/ToggleCafesView.vue';
    import MapLegend from '../components/cafes/MapLegend.vue';

    export default {
        components: {
            CafeMap,
            CafeList,
            AddCafeButton,
            ToggleCafesView,
            MapLegend
        },

        computed: {
            cafesView() {
                return this.$store.getters.getCafesView;
            }
        }
    }
</script>