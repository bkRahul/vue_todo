<template>
    <header class="header">
        <section class="hero is-medium is-primary is-bold">
        <div class="hero-body">
            <div class="container">
                <h1 class="title">Todo List</h1>
            </div>
            <div id="nav">
                <router-link to="/">Home</router-link> |
                <router-link to="/about">About</router-link>
            </div>            
        </div>
        </section>
    </header>
</template>

<script>
export default {
    name: "Header"
}
</script>