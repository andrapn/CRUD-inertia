<script setup>
  import {useForm, Head} from "@inertiajs/inertia-vue3";

  const props = defineProps({
    user: Object,
  });

  const form = useForm({
    name: props.user.name,
    email: props.user.email
  })
</script>

<template>
<Head title="Edit User"/>
  <div class="max-w-7xl m-auto mt-10">

  <form @submit.prevent="form.put(`/user/${user.id}`)">
      <div class="form-control w-full max-w-xs mb-4">
      <label class="label">
        <span class="label-text">Name</span>
      </label>
    <input type="text" v-model="form.name" name="name" placeholder="Andra Putra" class="input input-bordered w-full max-w-xs" />
    </div>

    <div class="form-control w-full max-w-xs mb-5">
      <label class="label">
        <span class="label-text">Email</span>
      </label>
    <input type="email" v-model="form.email" name="email" placeholder="andra.putra@kodingworks.io" class="input input-bordered w-full max-w-xs" />
    </div>

    <input type="submit" value="Save" class="btn btn-active btn-accent">
    <a href="/user" class="btn btn-error ml-2">Back</a>
  </form>

  </div>
</template>