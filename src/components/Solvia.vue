<template>
    <div>
        <img alt="Solvia" src="../assets/logo.png">
        <h1 class="text-center text-xl">{{ msg }}</h1>
    </div>
</template>

<script>
export default {
    name: 'Solvia',
    props: {
        msg: String
    }
}
</script>