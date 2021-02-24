<template>
    <div>
        <h3>Customer Reviews</h3>
        <div v-if="!$fetchState.pending">
            <ReviewCard 
                v-for="reviewer in reveiwers.results"
                :key="reviewer.login.uuid"
                :review="reviewer"
            />
        </div>
        <div v-else>
            loading...
        </div>
    </div>
</template>

<script>
    export default {
        data(){
            return {
                reveiwers:[]
            }
        },
        async fetch() {
            this.reveiwers = await fetch(
                'https://randomuser.me/api/?resultes=2'
            ).then(res => res.json())
            
        }
    }
</script>

<style lang="scss" scoped>

</style>