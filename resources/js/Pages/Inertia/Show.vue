<script setup>
import { Inertia } from '@inertiajs/inertia'
import { router } from '@inertiajs/vue3'

defineProps({
    id : String,
    blog: Object
})

const deleteConfirm = id => {
    // console.log(id)
    router.delete(`/inertia/${id}`, {
        onBefore: () => confirm('本当に削除しますか？')
    })
    // router.post('/inertia', form)
}
</script>

<template>
{{ id }}<br>
{{ blog.title }}<br>
<button @click="deleteConfirm(blog.id)">削除</button>
</template>