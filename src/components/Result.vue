<template>
    <h1 class="results">Result : {{ result }}.</h1>
</template>

<script>
export default {
    props: ['result'],
    data() {
        return  {
            rank: {
                name: "Mohamad Kholid Kamali"
            }
        }
    }
}
</script>

<style>
    .results { 
        text-align: center;
        margin-top: 50px;
    }
</style>