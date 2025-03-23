<template>
  <div class="container py-4">
    <h1 class="mb-4">Stories</h1>
    <div v-for="story in stories" :key="story.id" class="card mb-3">
      <a :href="`https://kontinentalist.com/stories/${story.slug}`" target="_blank"> 
        <img 
          :src="story.hero_image.url" 
          class="card-img-top" 
          alt="Hero Image"
          style="width: 100%; object-fit: cover;"
        />
      </a>

      <div class="card-body">
        <h5 class="card-title">{{ story.title }}</h5>
        <div class="card-text" v-html="story.dek"></div>
      </div>
    </div>
    <button class="btn btn-primary mt-3" @click="loadMore">Load More</button>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const stories = ref([])
const page = ref(1)

const loadStories = async () => {
  const res = await fetch(`https://cryptodire.kontinentalist.com/api/v1/stories?page=${page.value}`)
  const data = await res.json()

//  Debugging: see which stories are mising 'dek'
//  data.data.forEach(story => {
//  if (!story.dek) {
//    console.log(`No dek for: ${story.title}`)
//    }
//  })

  stories.value.push(...data.data)
}

const loadMore = () => {
  page.value++
  loadStories()
}

loadStories()
</script>