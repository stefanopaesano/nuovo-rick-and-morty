<script>
export default {
    data() {
        return {

        };
    },
    methods: {

    },
    props: {
        Character: Object
    }

}
</script>

<template>

    <div class="single-character">                 
        <div class="imge">
            <img :src="Character.image" alt="">
        </div>

        <div>
            <h3>
                {{ Character.name }}
            </h3>
        </div>

        <div>
            <h3>
                {{ Character.status }}
            </h3>
        </div>
    </div>

</template>

<style lang="scss" scoped>
</style>
