<script setup lang="ts">
  const title = ref('Hello World')
  const route = useRoute()
  useHead({
    meta: [{property: 'og:title', content: `App Name - ${route.meta.title}`}],
    script: [
      {
        src: 'https://third-party-script.com',
        // valid options are: 'head' | 'bodyClose' | 'bodyOpen'
        tagPosition: 'bodyClose',
      },
    ],
    link: [
      {
        rel: 'preconnect',
        href: 'https://fonts.googleapis.com',
      },
    ],
  })
</script>
<template>
  <div>
    <Head>
      <Title>{{ title }}</Title>
      <Meta name="description" :content="title" />
      <Style type="text/css" children="body { background-color: green; }" />
      <Link
        href="https://fonts.bunny.net/css?family=figtree:400,500,600&display=swap"
        rel="stylesheet"
        type="text/css" />
      <Link
        rel="stylesheet"
        href="https://fonts.googleapis.com/css2?family=Roboto&display=swap"
        crossorigin="" />
    </Head>

    <h1>{{ title }}</h1>
  </div>
</template>
