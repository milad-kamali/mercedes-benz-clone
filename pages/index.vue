<template>
  <div>
    <h2 class="text-3xl text-center font-Gelasio mt-5">
      {{ $t('welcomeMessage') }}
    </h2>
    <p
      class="w-2/4 text-center whitespace-pre-wrap mx-auto my-5"
    >
      {{ $t('exclusiveReports') }}
      <a href="www.mbusa.com">www.mbusa.com.</a>
    </p>
    <div class="flex justify-center mt-10">
      <a
        href="http://forward.mercedes-benz.com/homepage"
        class="hover:bg-blue-400 text-blue-400 hover:text-white border-2 border-blue-400 rounded mx-auto p-2.5 duration-200"
      >
        {{ $t('bringMeToMyLocalWebsite') }}
      </a>
    </div>
    <!-- benz links -->
    <div class="grid grid-cols-3 w-3/4 gap-x-2 mx-auto my-16">
      <a
        v-for="(item, i) in benzLinks"
        :key="i"
        :href="item.link"
        class="relative flex justify-center items-center hover"
      >
        <img
          :src="'/images/' + item.picture"
          class="w-60"
          :alt="item.title"
        >
      </a>
    </div>
    <!-- gallery -->
    <div>
      <ul class="flex text-xl gap-x-10 justify-center">
        <li
          v-for="(item, i) in galleryTabs"
          :key="i"
          class="cursor-pointer"
          :class="currentGalleryTab == item ? 'text-blue-400 underline underline-offset-8' : null"
          @click="currentGalleryTab = item"
        >
          {{ $t(item) }}
        </li>
      </ul>
      <div class="grid grid-rows-4 grid-cols-3 gap-1 -mx-5 mt-6 overflow-hidden">
        <a
          v-for="(item, i) in news"
          :key="i"
          href="#"
          class="relative showDes"
          :class="item.isBig ? 'row-span-2 col-span-2' : 'row-span-1 col-span-1'"
        >
          <img
            :src="'/images/' + item.image"
            :alt="item.title"
            class="h-full"
          >
          <div class="absolute w-full h-14 bottom-0 bg-black bg-opacity-40 text-white px-6 py-4 transition-all duration-300 info">
            <div class="font-Gelasio text-xl">{{ item.title }}</div>
            <p class="text-sm opacity-0 transition-opacity duration-500">{{ item.des }}</p>
          </div>
        </a>
      </div>
    </div>
    <!-- features -->
    <div class="grid grid-cols-3 my-8">
      <div class="text-center">
        <span class="material-icons text-4xl text-orange-400">local_gas_station</span>
        <div class="text-xl underline underline-offset-4">
          {{ $t('features[0]') }}
        </div>
      </div>
      <div class="text-center">
        <span class="material-icons text-4xl text-green-400">compost</span>
        <div class="text-xl underline underline-offset-4">
          {{ $t('features[1]') }}
        </div>
      </div>
      <div class="text-center">
        <span class="material-icons text-4xl text-blue-400">ev_station</span>
        <div class="text-xl underline underline-offset-4">
          {{ $t('features[1]') }}
        </div>
      </div>
    </div>
    <!-- description -->
    <p class="whitespace-pre-line">
      {{ $t('description') }}
    </p>
    <!-- other links -->
    <div class="grid grid-cols-4 mt-8">
      <div v-for="section in otherLinks" :key="section">
        <h4 class="font-Gelasio text-2xl pb-4 border-b">
          {{ $t(section)[0] }}
        </h4>
        <a v-for="(link, j) in 7" :key="j" href="#" class="block text-gray-600 my-0.5">
          {{ $t('moreTopics[' + (link) + ']') }}
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'MainPage',
  layout: 'main',
  data () {
    return {
      benzLinks: [
        {
          title: 'Mercedes Benz Museum',
          picture: 'museum-channel-tile.webp',
          link: 'https://www.mercedes-benz.com/en/classic/museum/'
        },
        {
          title: 'Mercedes Me',
          picture: 'me-channel-tile_new.png',
          link: 'https://www.mercedes-benz.com/en/mercedes-me/'
        },
        {
          title: 'Mercedes Me',
          picture: 'she-channel-tile.webp',
          link: 'https://www.mercedes-benz.com/en/mercedes-me/'
        }
      ],
      galleryTabs: ['new', 'popular', 'videos'],
      currentGalleryTab: 'new',
      news: [
        {
          image: '00-mercedes-benz-vision-eqxx-2022-2560x1440.webp',
          title: 'VISION EQXX: The new benchmark of efficiency.',
          des: 'The VISION EQXX sets new standards for aerodynamics and enables an electric range of over 1,000 km.',
          isBig: true
        },
        {
          image: '00-design-the-big-small-world-of-mercedes-benz-2560x1440.webp',
          title: 'The big small world of Mercedes-Benz.',
          des: 'From classics to the AMG – the Mercedes-Benz model cars are true-to-the-original miniatures of their bigger...',
          isBig: false
        },
        {
          image: '01-mercedes-benz-classic-h-number-plate-2022-2560x1440.webp',
          title: '“H” as in “Happy New Year”.',
          des: 'In 2022, fascinating young classics from Mercedes-Benz will be able to obtain the H number plate for the fi...',
          isBig: false
        },
        {
          image: 'mercedes-eq-formula-e-team-stoffel-vandoorne-2022_V2jpeg.jpeg',
          title: 'Stoffel Vandoorne',
          des: 'Our driver Stoffel Vandoorne is part of the Mercedes-EQ Formula E Team. get to know him.',
          isBig: false
        },
        {
          image: 'mercedes-eq-formula-e-team-nyck-de-vries-2022_V2jpeg.webp',
          title: 'Nyck de Vries',
          des: 'Our driver Nyck de Vries is part of the Mercedes-Benz EQ Formula E Team. Get to know him.',
          isBig: false
        },
        {
          image: 'Mercedes-Benz-EQ-Formula_E_Team_santiago_teserjpeg.webp',
          title: 'Mercedes-EQ Formula E Team',
          des: 'Welcome to the Mercedes-EQ Formula E Team. Discover all about racing and our drive for lifestyle, sustainab...',
          isBig: false
        },
        {
          image: 'Studio-Odeonsplatz-The-Design-Edit-EQS-450-2560x1440.webp',
          title: 'The Design Edit at Studio Odeonsplatz by Mercedes-Benz.',
          des: 'Explore the cooperations with Heron Preston & Proenza Schouler.',
          isBig: true
        },
        {
          image: 'mercedes-eq-formula-e-team-ian-james-review-16-9jpeg.jpeg',
          title: 'Valencia Review with Ian James',
          des: 'Learn more about how Mercedes-EQ envisions the future of mobility, the special impact team spirit will have...',
          isBig: false
        },
        {
          image: '01-mercedes-benz-driving-events-overview-2560x1440.webp',
          title: 'Driving Events.',
          des: 'The Driving Events are always a source of thrills and adventure: improve your driving skills, on and offroa...',
          isBig: false
        }
      ],
      otherLinks: ['moreTopics', 'shopping', 'allAboutCars', 'discoverMore']
    }
  }
}
</script>

<style scoped>
  .hover::after {
    content: '';
    display: block;
    width: 100%;
    height: 0;
    background-color: rgb(44, 146, 230);
    position: absolute;
    bottom: 0;
    transition: height 0.10s;
  }
  .hover:hover::after {
    height: 0.4rem;
  }
  .showDes:hover .info {
    height: 7rem;
    background-color: rgba(0, 0, 0, 0.7);
  }
  .showDes:hover p {
    opacity: 1;
  }
</style>
