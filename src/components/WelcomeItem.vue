<template>
  <div>
    <header class="header">
      <nav class="navbar navbar-expand-lg bg-body bg-md-transpernt" id="header">
        <div class="container-fluid px-2 px-md-5 d-flex w-100">
          <a class="navbar-brand" href="#"
            ><img src="../assets/img/nav-brand.png" alt="" class="" width="70"
          /></a>
          <button
            class="navbar-toggler"
            type="button"
            data-bs-toggle="collapse"
            data-bs-target="#navbarText"
            aria-controls="navbarText"
            aria-expanded="false"
            aria-label="Toggle navigation"
          >
            <span class="navbar-toggler-icon"></span>
          </button>
          <div class="collapse navbar-collapse" id="navbarText">
            <ul
              class="navbar-nav mb-2 mb-lg-0 w-100 mx-auto justify-content-center gap-2"
            >
              <li class="nav-item">
                <a class="nav-link active" aria-current="page" href="#"
                  >Tentang</a
                >
              </li>
              <li class="nav-item">
                <a class="nav-link" href="#">Panduan</a>
              </li>
              <li class="nav-item">
                <a class="nav-link" href="#">Fitur</a>
              </li>
            </ul>
            <div class="button-compaund">
              <a href="" class="btn btn-success btn-sm">Masuk</a>
            </div>
          </div>
        </div>
      </nav>
    </header>

    <main>
      <section class="hero-section" id="hero">
        <div
          class="container mt-5 d-flex align-items-center justify-items-center flex-column"
        >
          <h1 class="text-start title text-md-center mt-5">
            <b
              >Hi Tarea Students! Selamat Datang <br />Di Learning Management
              <span style="color: #3fce28">Tarea</span></b
            >
          </h1>
          <a href="" class="btn btn-success btn-hero mt-4 py-2 px-sm-5"
            >Mulai Belajar</a
          >
        </div>
      </section>

      <section class="guru" id="guru">
        <div class="container">
          <h1 class="text-center mb-3"><b>Data Guru</b></h1>
          <div class="card-wrapper row row-cols-4 gap-4 justify-content-center">
            <div v-for="item in teachers" :key="item.id">
              <div class="card col">
                <div class="card-body">
                  <img src="../assets/img/Buku1.png" alt="" class="img-fluid" />
                </div>
              </div>
              <div class="card-footer">
                <div
                  class="data d-flex justify-content-between align-items-center"
                >
                  <p>Nama</p>
                  <p class="p-0 m-0">{{ item.nama }}</p>
                </div>
                <div
                  class="data d-flex justify-content-between align-items-center"
                >
                  <p>NIP</p>
                  <p class="p-0 m-0">{{ item.nip }}</p>
                </div>
              </div>
            </div>
          </div>
          <h1 class="text-center mb-3 mt-5"><b>Data Siswa</b></h1>
          <div class="card-wrapper row row-cols-4 gap-4 justify-content-center">
            <div v-for="item in students" :key="item.id">
              <div class="card col">
                <div class="card-body">
                  <img src="../assets/img/Buku1.png" alt="" class="img-fluid" />
                </div>
              </div>
              <div class="card-footer">
                <div
                  class="data d-flex justify-content-between align-items-center"
                >
                  <p>Nama</p>
                  <p class="p-0 m-0">{{ item.nama }}</p>
                </div>
                <div
                  class="data d-flex justify-content-between align-items-center"
                >
                  <p>Kelas</p>
                  <p class="p-0 m-0">{{ item.kelas }}</p>
                </div>
              </div>
            </div>
          </div>
          <h1 class="text-center mb-3 mt-5"><b>Data Karyawan</b></h1>
          <div class="card-wrapper row row-cols-4 gap-4 justify-content-center">
            <div v-for="item in karyawan" :key="item.id">
              <div class="card col">
                <div class="card-body">
                  <img src="../assets/img/Buku1.png" alt="" class="img-fluid" />
                </div>
              </div>
              <div class="card-footer">
                <div
                  class="data d-flex justify-content-between align-items-center"
                >
                  <p>Nama</p>
                  <p class="p-0 m-0">{{ item.nama }}</p>
                </div>
                <div
                  class="data d-flex justify-content-between align-items-center"
                >
                  <p>Jabatan</p>
                  <p class="p-0 m-0">{{ item.jabatan }}</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
    </main>
  </div>
</template>

<style>
@import "../assets/css/styles.css";
</style>

<script>
import axios from "axios";
export default {
  data() {
    return {
      teachers: [],
      students: [],
      karyawan: [],
    };
  },
  mounted() {
    this.getDataTeachers();
    this.getDataStudents();
    this.getDataKaryawan();
  },
  methods: {
    async getDataTeachers() {
      try {
        const response = await axios.get("http://13.213.0.182:4000/teachers");
        this.teachers = response.data.data;
      } catch (error) {
        console.error(error);
      }
    },
    async getDataStudents() {
      try {
        const response = await axios.get("http://13.213.0.182:4000/students");
        this.students = response.data.data;
      } catch (error) {
        console.error(error);
      }
    },
    async getDataKaryawan() {
      try {
        const response = await axios.get("http://13.213.0.182:4000/karyawan");
        this.karyawan = response.data.data;
      } catch (error) {
        console.error(error);
      }
    },
  },
};
</script>
