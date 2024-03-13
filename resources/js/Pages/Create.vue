<template>
    <div class="post__create">
        <form action="" @submit.prevent="form.post('/post')">
            <div class="">
                <label>Title</label>
                <input class="ml-3" type="text" v-model="form.title">
            </div>
            <div>
                <label>Author</label>
                <input class="ml-3" type="text" v-model="form.author">
            </div>
            <div>
                <label>Content</label>
                <textarea  class="ml-3" type="textarea" v-model="form.content"></textarea>
            </div>
            <div>
                <input class="ml-3" type="submit" value="Create a new post"/>
            </div>
        </form>
    </div>
</template>

<script setup>
    import { useForm } from '@inertiajs/vue3';

    const form = useForm({
        title : '',
        author:'',
        content:'',
    })

</script>

