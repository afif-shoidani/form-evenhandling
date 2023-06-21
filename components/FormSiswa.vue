<script>
export default {
  data() {
    return {
      noInduk: '',
      nama: '',
      nilai: null
    };
  },
  methods: {
    addSiswa() {
      const siswa = {
        noInduk: this.noInduk,
        nama: this.nama,
        nilai: this.nilai
      };
      this.$emit('siswa-added', siswa);
      this.noInduk = '';
      this.nama = '';
      this.nilai = null;
    }
  }
};
</script>
<template>
   <div class="container">
    <h3>Form Nilai Tugas Siswa</h3>
    <form @submit.prevent="addSiswa" class="mt-3">
      <div class="form-group">
        <label for="noInduk">No Induk Siswa:</label>
        <input type="text" id="noInduk" v-model="noInduk" required class="form-control col-sm-6">
      </div>
      <div class="form-group">
        <label for="nama">Nama Siswa:</label>
        <input type="text" id="nama" v-model="nama" required class="form-control col-sm-6">
      </div>
      <div class="form-group">
        <label for="nilai">Nilai Tugas:</label>
        <input type="number" id="nilai" v-model="nilai" required class="form-control col-sm-6">
      </div>
      <button type="submit" class="btn btn-primary col-sm-3">Tambah</button>
    </form>
  </div>
</template>


