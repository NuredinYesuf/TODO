<nav></nav>
    <router-link to="/">Home</router-link>
</nav>
<template>
    <div class="hello">
        <h1>{{ msg }}</h1>
        <p>
            Welcome to your Vue.js app!
        </p>
        <button @click="sayHello">Click me</button>
        <p>{{ greeting }}</p>
    </div>
</template>

<script>
export default {
    name: 'HelloWorld',
    props: {
        msg: String
    },
    data() {
        return {
            greeting: ''
        };
    },
    methods: {
        sayHello() {
            this.greeting = 'Hello from HelloWorld component!';
        }
    }
};
</script>

<style scoped>
.hello {
    text-align: center;
    margin-top: 40px;
}
button {
    margin-top: 20px;
    padding: 10px 20px;
    font-size: 16px;
}
</style>