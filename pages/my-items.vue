<template>
    <div>
        <MyItem 
            v-for="(rental,index) in myRentals" 
            :key="index" 
            :item="rental"
        />
    </div>
</template>

<script>
    import { mapState } from 'vuex';

    export default {
        layout:"no-nav",
        computed: {
            ...mapState([
                'myRentals',
            ])
        },
    }
</script>

<style lang="scss" scoped>

</style>