<template>
    <header class="flex justify-between bg-blue-500 h-25 items-center px-5">
        <h1 class="text-white text-2xl font-bold">Gerenciamento de tarefas</h1>
        <nav class="flex gap-4 text-white">
            <Link href="#">Cadastro de Usuario</Link>
            <Link href="#">Cadastro de Tarefas</Link>
            <Link href="#">Gerenciar Tarefas</Link>
        </nav>
    </header>
    <main class="w-11/12 mx-auto">
        <slot>

        </slot>
    </main>
</template>

<script setup lang='ts'>
import { Link } from '@inertiajs/vue3'
</script>

<style></style>