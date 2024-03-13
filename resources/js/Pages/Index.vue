<template>
    <div class="flex justify-center">
        <Link href="/post/create" class="rounded border-2 bg-gray-400 h-10 w-40" as="button">Create a new post</Link>

    </div>
    <div v-if="true" class="text-blue-600 mb-3 flex justify-center">{{ $page.props.flash.message }}</div>
    <div class="flex justify-center container mx-auto pt-5">
        <table class="border-separate border-spacing-2 border-2 border-slate-500">
            <thead>
                <tr class="font-bold">
                    <th>Title</th>
                    <th>Author</th>
                    <th>Content</th>
                    <th>Edit</th>
                    <th>Update</th>
                </tr>
            </thead>
            <tbody>
                <tr class="post__block" v-for="post in posts" :key="post.id">
                    <td>
                        {{ post.title }}
                    </td>
                    <td>
                        {{post.author}}
                    </td>
                    <td>
                        <Link :href="`/post/${post.id}`">Read more</Link>
                    </td>
                    <td>
                        <Link :href="`/post/edit/${post.id}`">Edit post</Link>
                    </td>
                    <td>
                        <Link :href="`/post/delete/${post.id}`" method="DELETE" as="button">Delete post</Link>
                    </td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script setup>
import { Link } from '@inertiajs/vue3';

    defineProps({
        posts :Object,

    })
</script>

