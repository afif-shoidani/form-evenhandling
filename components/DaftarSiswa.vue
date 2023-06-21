<script>
export default {
  props: {
    siswaList: {
      type: Array,
      required: true
    }
  },
  computed: {
    rataRataNilai() {
     if (this.siswaList.length === 0) {
      return 0;
    }
    
    const totalNilai = this.siswaList.reduce((sum, siswa) => {
      return sum + parseInt(siswa.nilai);
    }, 0);
    
    const rataRata = totalNilai / this.siswaList.length;
    
    return isNaN(rataRata) ? 0 : parseFloat(rataRata.toFixed(2));
  }
  }
};
</script>
<template>
  <div class="container">
    <h3>Daftar Siswa</h3>
    <table class="table mt-3">
      <thead>
        <tr>
          <th>No Induk</th>
          <th>Nama Siswa</th>
          <th>Nilai Tugas</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(siswa, index) in siswaList" :key="index">
          <td>{{ siswa.noInduk }}</td>
          <td>{{ siswa.nama }}</td>
          <td>{{ siswa.nilai }}</td>
        </tr>
      </tbody>
    </table>
    
    <p class="mt-10"><h5>Rata-rata Nilai Tugas :  {{ rataRataNilai }} </h5></p>
    
  </div>
</template>


