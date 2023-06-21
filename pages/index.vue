<template>
  <div class="container">
    <div><h2>##Form , Even Handling dan List rendering##</h2></div>
    <br>
    <FormSiswa @siswa-added="addSiswa" /><br>
    <DaftarSiswa :siswa-list="siswaList" />
  </div>
</template>

<script>
import "bootstrap/dist/css/bootstrap.css";
import "bootstrap-vue/dist/bootstrap-vue.css";
import FormSiswa from "@/components/FormSiswa.vue";
import DaftarSiswa from "@/components/DaftarSiswa.vue";


export default {
  components: {
    FormSiswa,
    DaftarSiswa
  },
  data() {
    return {
      siswaList: []
    };
  },
  methods: {
    addSiswa(siswa) {
      this.siswaList.push(siswa);
    }
  }
};
</script>

