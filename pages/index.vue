<template>
  <div class="flex justify-center">
    <div class="container ma-auto p-8 break-normal inline-block">
      <div
        class="
          font-bold
          text-black-600 text-lg
          m-3
          p-3
          bg-gray-300
          inline-block
          mb-8
        "
        v-for="(item, index) in showPageData"
        :key="index"
      >
        {{ item }}
      </div>

      <div class="flex justify-center">
        <button
          class="
            bg-gray-500
            hover:bg-gray-700
            text-white
            font-bold
            py-2
            px-4
            rounded-full
            mx-2
            my-2
            hidden
            md:inline-flex
          "
          v-for="index in totalPages"
          :key="index"
          @click="changePage(index)"
        >
          {{ index }}
        </button>
      </div>
      <div class="mb-8">
        <p class="font-bold text-black-600 text-lg">
          Current page : {{ currentPage }}
        </p>
        <p class="font-bold text-black-600 text-lg">
          data range: {{ (currentPage - 1) * entryPerPage + 1 }} -
          {{ currentPage * entryPerPage }}
        </p>
        <button
          class="
            bg-blue-500
            hover:bg-blue-700
            text-white
            font-bold
            py-2
            px-4
            rounded
            block
            md:hidden
          "
          @click="loadMoreData"
        >
          load More
        </button>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  data() {
    return {
      fullApiData: [
        "environmental",
        "establishment",
        "extraordinary",
        "functionality",
        "illustrations",
        "inappropriate",
        "independently",
        "informational",
        "installations",
        "institutional",
        "instructional",
        "international",
        "interventions",
        "investigation",
        "investigators",
        "liechtenstein",
        "manufacturers",
        "manufacturing",
        "massachusetts",
        "mediterranean",
        "miscellaneous",
        "modifications",
        "notifications",
        "opportunities",
        "organisations",
        "organizations",
        "parliamentary",
        "participating",
        "participation",
        "photographers",
        "possibilities",
        "practitioners",
        "precipitation",
        "presentations",
        "professionals",
        "psychological",
        "qualification",
        "questionnaire",
        "relationships",
        "restructuring",
        "revolutionary",
        "semiconductor",
        "significantly",
        "sophisticated",
        "specification",
        "starsmerchant",
        "strengthening",
        "subscriptions",
        "substantially",
        "technological",
        "transcription",
        "undergraduate",
        "understanding",
        "unfortunately",
        "vulnerability",
        "accommodations",
        "accountability",
        "administration",
        "administrative",
        "administrators",
        "advertisements",
        "appropriations",
        "authentication",
        "cardiovascular",
        "characteristic",
        "classification",
        "communications",
        "concentrations",
        "considerations",
        "constitutional",
        "correspondence",
        "discrimination",
        "identification",
        "implementation",
        "infrastructure",
        "interpretation",
        "investigations",
        "knowledgestorm",
        "organizational",
        "pharmaceutical",
        "qualifications",
        "recommendation",
        "reconstruction",
        "rehabilitation",
        "representation",
        "representative",
        "responsibility",
        "simultaneously",
        "specifications",
        "superintendent",
        "sustainability",
        "transformation",
        "transportation",
        "characteristics",
        "confidentiality",
        "congratulations",
        "instrumentation",
        "internationally",
        "pharmaceuticals",
        "recommendations",
        "representations",
        "representatives",
        "troubleshooting",
        "characterization",
        "responsibilities",
        "sublimedirectory",
        "telecommunications",
        "documentcreatetextnode",
      ],
      currentPage: 1,
      entryPerPage: 10,
      showPageData: [],
    };
  },
  computed: {
    totalPages: function () {
      return this.fullApiData.length % 10 === 0
        ? this.fullApiData.length / 10
        : Math.floor(this.fullApiData.length / 10) + 1;
    },
  },
  methods: {
    changePage: function (pageNumber) {
      this.currentPage = pageNumber;
      this.pageData();
    },
    pageData: function () {
      const start =
        this.currentPage === 1
          ? 0
          : (this.currentPage - 1) * this.entryPerPage + 1;
      const end =
        this.currentPage === 1
          ? this.currentPage * this.entryPerPage
          : this.currentPage * this.entryPerPage + 1;
      this.showPageData = this.fullApiData.slice(start, end);
    },
    loadMoreData: function () {
      this.currentPage++;
      const start = 0;
      const end =
        this.currentPage === 1
          ? this.currentPage * this.entryPerPage
          : this.currentPage * this.entryPerPage + 1;
      this.showPageData = this.fullApiData.slice(start, end);
    },
  },
  mounted() {
    this.pageData();
  },
};
</script>


12

353
