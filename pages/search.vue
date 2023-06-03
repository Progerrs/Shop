<template>
  <MainSection title="Test" :loading="false">
      <div class="max-w-lg mx-auto">
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
          <div v-for="comic in comics" :key="comic.id" :class="getComicCardClasses">
            <img :src="comic.image" alt="Comic Image" class="w-full h-40 object-cover mb-4 rounded-lg">
            <h2 :class="getComicTitleClasses">{{ comic.title }}</h2>
            <p :class="getComicDescriptionClasses">{{ comic.description }}</p>
            <div class="flex items-center justify-between">
              <span class="text-sm text-gray-500">Issue #{{ comic.issueNumber }}</span>
              <span class="text-sm text-gray-500">Published on {{ comic.publishedDate }}</span>
            </div>
          </div>
        </div>
      </div>
  </MainSection>
</template>

<script>
export default {
  data() {
    return {
      darkMode: true,
      comics: [
        {
          id: 1,
          title: "Comic 1",
          description: "Description of Comic 1",
          image: "https://cdn.marvel.com/content/1x/marvsmposterbk_intdesign.jpg",
          issueNumber: 1,
          publishedDate: "May 1, 2023",
        },
        {
          id: 2,
          title: "Comic 2",
          description: "Description of Comic 2",
          image: "https://cdn.marvel.com/content/1x/marvsmposterbk_intdesign.jpg",
          issueNumber: 2,
          publishedDate: "May 8, 2023",
        },

        {
          id: 2,
          title: "Comic 2",
          description: "Description of Comic 2",
          image: "https://cdn.marvel.com/content/1x/marvsmposterbk_intdesign.jpg",
          issueNumber: 2,
          publishedDate: "May 8, 2023",
        },

        {
          id: 2,
          title: "Comic 2",
          description: "Description of Comic 2",
          image: "https://cdn.marvel.com/content/1x/marvsmposterbk_intdesign.jpg",
          issueNumber: 2,
          publishedDate: "May 8, 2023",
        },

        {
          id: 2,
          title: "Comic 2",
          description: "Description of Comic 2",
          image: "https://cdn.marvel.com/content/1x/marvsmposterbk_intdesign.jpg",
          issueNumber: 2,
          publishedDate: "May 8, 2023",
        },

        {
          id: 2,
          title: "Comic 2",
          description: "Description of Comic 2",
          image: "https://cdn.marvel.com/content/1x/marvsmposterbk_intdesign.jpg",
          issueNumber: 2,
          publishedDate: "May 8, 2023",
        },
      ],
    };
  },
  computed: {
    getComicCardClasses() {
      return this.darkMode
          ? "bg-gray-800 rounded-lg shadow-md p-4 text-white"
          : "bg-white rounded-lg shadow-md p-4";
    },
    getComicTitleClasses() {
      return this.darkMode ? "text-xl font-semibold mb-2 text-white" : "text-xl font-semibold mb-2";
    },
    getComicDescriptionClasses() {
      return this.darkMode ? "text-gray-400 mb-4 text-white" : "text-gray-600 mb-4";
    },
  },
};
</script>