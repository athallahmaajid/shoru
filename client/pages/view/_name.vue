<template>
  <div>
    <link
      href="https://cdn.jsdelivr.net/npm/tailwindcss@2.1.2/dist/tailwind.min.css"
      rel="stylesheet"
    />
    <div class="max-w-4xl mx-auto sm:px-6 lg:px-8">
      <v-card class="mt-8 overflow-hidden shadow sm:rounded-lg p-6 text-center">
        <h1 v-if="error" class="text-4xl mt-10 leading-7 font-semibold">
          {{ message }}
        </h1>

        <h1 v-if="found" class="text-4xl mt-10 leading-7 font-semibold">
          Shoru - View Url
        </h1>
        <h1 v-else class="text-4xl mt-10 leading-7 font-semibold">
          We Are Sorry the Url is not found :(
        </h1>

        <p v-if="found" class="mt-4 text-gray-600 pb-5">
          See info about <span class="font-bold">{{ url_name }}</span> url name
        </p>
        
        <p v-if="found" class="mt-4 text-gray-600 pb-5">
          This url will direct you to <span class="font-bold">{{ url }}</span>
        </p>

        <p v-if="found" class="mt-4 text-gray-600 pb-5">
          You can visit <span class="font-bold">https://shoru.vercel.app/{{ url_name }}</span> for shortcut
        </p>

        <v-col v-if="found" cols="12">
          <a :href="'https://shoru.vercel.app/' + url_name">
            <v-btn type="submit" tile style="width: 100%"> Open Url </v-btn>
          </a>
        </v-col>

        <p
          :class="
            found
              ? 'py-5 mt-10 text-gray-600 pb-5 border-t border-dashed'
              : 'py-5 mt-5 text-gray-600 pb-5'
          "
        >
          Wanna shorten your url? Just use
          <NuxtLink to="/">Shoru</NuxtLink>, no need to sign up!
        </p>
      </v-card>
      <div class="flex justify-center pt-4 space-x-2">
        <a href="https://github.com/aldhanekaa/shoru" target="_blank"
          ><svg
            class="w-6 h-6 text-gray-600 hover:text-gray-800"
            xmlns="http://www.w3.org/2000/svg"
            xmlns:xlink="http://www.w3.org/1999/xlink"
            aria-hidden="true"
            role="img"
            width="32"
            height="32"
            preserveAspectRatio="xMidYMid meet"
            viewBox="0 0 24 24"
          >
            <path
              d="M12 2.247a10 10 0 0 0-3.162 19.487c.5.088.687-.212.687-.475c0-.237-.012-1.025-.012-1.862c-2.513.462-3.163-.613-3.363-1.175a3.636 3.636 0 0 0-1.025-1.413c-.35-.187-.85-.65-.013-.662a2.001 2.001 0 0 1 1.538 1.025a2.137 2.137 0 0 0 2.912.825a2.104 2.104 0 0 1 .638-1.338c-2.225-.25-4.55-1.112-4.55-4.937a3.892 3.892 0 0 1 1.025-2.688a3.594 3.594 0 0 1 .1-2.65s.837-.262 2.75 1.025a9.427 9.427 0 0 1 5 0c1.912-1.3 2.75-1.025 2.75-1.025a3.593 3.593 0 0 1 .1 2.65a3.869 3.869 0 0 1 1.025 2.688c0 3.837-2.338 4.687-4.563 4.937a2.368 2.368 0 0 1 .675 1.85c0 1.338-.012 2.413-.012 2.75c0 .263.187.575.687.475A10.005 10.005 0 0 0 12 2.247z"
              fill="currentColor"
            /></svg
        ></a>
        <p class="text-gray-500">
          Made with luv by
          <a href="https://github.com/aldhanekaa">Aldhaneka</a>
        </p>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import viewPage from './view.page'

export default viewPage
</script>
