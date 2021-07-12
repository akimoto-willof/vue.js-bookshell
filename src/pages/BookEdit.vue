<template>
    <div>
        {{ books }}
    </div>
</template>

<script>
export default {
    name: "BookEdit",
    props: {
        books: Array
    },
    beforeRouteEnter (to, from, next) {
        // vueはすべて非同期のため、処理を遅延させるコード
        // next内ではthisが使えないためvmで代用
        next( vm => {
            vm.$nextTick( () => {
                vm.book = vm.books[vm.$route.params.id]
            })
        })
    }

}
</script>

<style>

</style>