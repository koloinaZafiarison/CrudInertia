<template>
    <div class="post__edit">
        <form class="max-w-md mx-auto mt-6" action="" @submit.prevent="form.put(`/post/update/${post.id}`)">
            <div class="mb-6">
                <label class="block mb-2 uppercase font-bold text-xs text-gray-700">Title</label>
                <input class="border border-gray-400 p-2 w-full" type="text" name="title" v-model="form.title">
                <div v-if="form.errors.title" v-text="form.errors.title" class="text-red-500 text-xs mt-1"></div>
            </div>
            <div class="mb-6">
                <label class="block mb-2 uppercase font-bold text-xs text-gray-700">Author</label>
                <input class="border border-gray-400 p-2 w-full" type="text" name="author" v-model="form.author">
                <div v-if="form.errors.author" v-text="form.errors.author" class="text-red-500 text-xs mt-1"></div>
            </div>
            <div class="mb-6">
                <label class="block mb-2 uppercase font-bold text-xs text-gray-700">Content</label>
                <textarea  class="border border-gray-400 p-2 w-full" type="textarea" name="content" v-model="form.content"></textarea>
                <div v-if="form.errors.content" v-text="form.errors.content" class="text-red-500 text-xs mt-1"></div>
            </div>
            <div>
                <button class="border bg-blue-400 p-2 rounded w-full cursor-pointer text-white" type="submit" value="Update post">update post</button>
            </div>
        </form>
    </div>
</template>

<script setup>
    import { useForm } from '@inertiajs/vue3';
    import {defineProps} from 'vue';

    let props = defineProps({
        post : Object
    })

    const form = useForm({
        title : props.post.title,
        author : props.post.author,
        content : props.post.content,
    })

</script>
