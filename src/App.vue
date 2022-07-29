<script setup>
import Bid from './components/Bid.vue'
</script>

<template>
    <div class="container">
        <nav class="navbar pb-4"
             role="navigation"
             aria-label="main navigation">
            <div class="navbar-brand">
                <a class="navbar-item is-size-1" href="#">
                    Labid
                </a>
            </div>
        </nav>

        <main>
            <Bid />
        </main>
    </div>
</template>
