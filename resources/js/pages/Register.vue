<template>

    <Head title="Cadastro de Usuário" />
    <AppLayout>
        <h1 class="text-2xl font-bold">Cadastro de Usuário</h1>
        <form class="flex flex-col gap-3 w-50" @submit.prevent="save">
            <div class="flex flex-col">
                <label for="name">Nome:</label>
                <input class="border-2 rounded p-1" type="text" id="name" v-model="form.name">
                <span class="text-red-500"> {{ form.errors.name }}</span>
            </div class="flex flex-col">
            <div>
                <label for="email">Email</label>
                <input class="border-2 rounded p-1" type="email" id="email" v-model="form.email">
                <span class="text-red-500"> {{ form.errors.email }}</span>
            </div>
            <button type="submit" class="bg-blue-500 text-white p-2 rounded w-fit">Cadastrar</button>
        </form>
    </AppLayout>
</template>

<script setup lang='ts'>
import AppLayout from "@/layouts/AppLayout.vue"
import { Head, useForm } from '@inertiajs/vue3'

const form = useForm({
    name: '',
    email: ''
});

const save = () => {
    form.post(route('register.store'), {
        onSuccess() {
            alert('cadastrado com sucesso');
        }
    });
}
</script>