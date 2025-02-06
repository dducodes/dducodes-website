<template>
  <div class="px-5 py-5 md:px-12 md:py-5 text-left text-amber-50 mx-3">
      <article data-page="about">
        <header>
          <div
            class="text-2xl font-bold text-blue-300 mb-10 fadein-bot title-section flex items-center justify-center flex-col">
            <h4>My Certificates</h4>
            <p class="text-base font-normal text-white">  
                The certifications I have gained throughout the years</p>
          </div>
        </header>
  
        <section>
          <div>
            <!-- Horizontal Scrollable Container -->
            <div 
              class="flex overflow-x-auto gap-4 pb-8 fade-zoom-in scrollbar-thin scrollbar-thumb-purple-300 scrollbar-track-purple-300"
            >
              <!-- Each Certificate Card -->
              <div
                v-for="item in items"
                :key="item.id"
                class="item-card flex flex-col items-center gap-2 rounded bg-[#1e1e1f] hover:bg-[#282828] border border-[#383838] rounded-xl text-blue-300 px-5 py-5 lg:px-5 shrink-0 w-80"
              >
                <div class="w-full h-[75%] flex items-center justify-center overflow-hidden m-0 p-0">
                  <img
                    alt="HTML"
                    loading="lazy"
                    decoding="async"
                    data-nimg="1"
                    class="w-full h-full flex object-cover rounded-xl"
                    :src="'/certificate logo/' + item.imageUrl + '.svg'"
                  />
                </div>

                <div class="w-full flex flex-col gap-2 items-center text-sm md:text-base lg:text-lg">
                  <p></p>
                  <div class="title-text font-medium text-secondary">{{ item.name }}</div>
                  <div class="w-full text-left text-[10px] text-[#c1c1c1] md:text-xs lg:text-sm">
                    <p>Topic: {{ item.tech }}</p>
                  </div>
                  <div class="w-full text-left text-[10px] text-[#c1c1c1] md:text-xs lg:text-sm">
                    {{ item.status }}
                  </div>
                </div>

                <!-- Link to certificate -->
                <div class="w-full flex justify-end flex cursor-pointer items-end gap-2 text-primary ">
                  <a v-if="item.link !== 'null'" :href= "item.link" target="_blank" rel="noreferrer"
                        title="View Certificate" class="transition-all">
                        <svg stroke="white"
                          fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round"
                          height="18" width="18" xmlns="http://www.w3.org/2000/svg">
                          <path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"></path>
                          <polyline points="15 3 21 3 21 9"></polyline>
                        <line x1="10" y1="14" x2="21" y2="3"></line>
                </svg></a></div>
              </div>
            </div>
          </div>
        </section>
      </article>
    </div>
  </template>
  

<script>
import Certficates from "../api/CertificateViewAPI";

export default {
  name: "CertificateViewAPI",
  mixins: [Certficates],
};
</script>