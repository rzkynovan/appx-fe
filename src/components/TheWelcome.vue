<template>
  <div class="container mt-5 ">
        <!-- Button trigger modal -->
        <h2 class="text-center">Data Siswa</h2>
        <p class="text-muted text-center">From Site A</p>
<button type="button" class="btn btn-primary float-left mb-3" data-bs-toggle="modal" data-bs-target="#studentInput">
  Buat Baru!
</button>

    <table class="table table-bordered text-white text-center">
    <thead>
      <tr>
        <th>Id</th>
        <th>Nama</th>
        <th>Kelas</th>
        <th>Action</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="post,k in formData" :key="k">
        <th class="" scope="row">{{ post.id }}</th>
        <td>{{ post.nama }}</td>
        <td>{{ post.kelas }}</td>
        <td class="d-flex gap-2">
          <button @click="editData(post.id)">Edit</button>
          <a href="" class="btn btn-sm btn-danger">Delete</a>
        </td>
      </tr>
    </tbody>
  </table>



<!-- Modal Create -->
<div class="modal fade" id="studentInput" tabindex="-1" aria-labelledby="studentInputLabel" aria-hidden="true">
  <div class="modal-dialog">
    <div class="modal-content bg-dark">
      <div class="modal-header">
        <h1 class="modal-title fs-5" id="studentInputLabel">Modal title</h1>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
        <form @submit.prevent="submitForm">
          <div class="modal-body">
              <div class="mb-3">
                <label for="nama">Nama</label>
                <input type="text" name="nama" id="nama" v-model="formData.nama" class="form-control">
              </div>
              <div class="mb-3">
                <label for="kelas">Kelas</label>
                <input type="text" name="kelas" id="kelas" v-model="formData.kelas" class="form-control">
              </div>
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
            <button type="submit" class="btn btn-primary" onclick="return confirm('Yakin dek?')" >Save changes</button>
          </div>
        </form>
    </div>
  </div>
</div>
<!-- End Modal Create -->
<!-- Button trigger modal -->


<!-- Modal Udate -->
<div v-if="showModal">
      <div>
        <label for="editName">Name:</label>
        <input type="text" id="editName" v-model="editFormData.nama" required >
        <br><br>
        <label for="editEmail">Email:</label>
        <input type="text" id="editEmail" v-model="editFormData.kelas" required>
        <br><br>
        <button @click="updateData">Update</button>
        <button @click="closeModal">Cancel</button>
      </div>
    </div>

</div>
<hr class="mx-4">
  <div class="container mt-5 ">
        <!-- Button trigger modal -->
        <h2 class="text-center">Data Guru</h2>
        <p class="text-muted text-center">From Site A</p>
      <button type="button" class="btn btn-primary float-left mb-3" data-bs-toggle="modal" data-bs-target="#teachersInput">
        Buat Baru!
      </button>

    <table class="table table-bordered text-white text-center">
    <thead>
      <tr>
        <th>Id</th>
        <th>Nama</th>
        <th>Kelas</th>
        <th>Action</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="post,k in formData" :key="k">
        <th class="" scope="row">{{ post.id }}</th>
        <td>{{ post.nama }}</td>
        <td>{{ post.kelas }}</td>
        <td class="d-flex gap-2">
          <button @click="editData(post.id)">Edit</button>
          <a href="" class="btn btn-sm btn-danger">Delete</a>
        </td>
      </tr>
    </tbody>
  </table>



<!-- Modal Create -->
<div class="modal fade" id="teachersInput" tabindex="-1" aria-labelledby="teachersInputLabel" aria-hidden="true">
  <div class="modal-dialog">
    <div class="modal-content bg-dark">
      <div class="modal-header">
        <h1 class="modal-title fs-5" id="teachersInputLabel">Modal title</h1>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
        <form @submit.prevent="submitForm">
          <div class="modal-body">
              <div class="mb-3">
                <label for="nama">Nama</label>
                <input type="text" name="nama" id="nama" v-model="formData.nama" class="form-control">
              </div>
              <div class="mb-3">
                <label for="kelas">Kelas</label>
                <input type="text" name="kelas" id="kelas" v-model="formData.kelas" class="form-control">
              </div>
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
            <button type="submit" class="btn btn-primary" onclick="return confirm('Yakin dek?')" >Save changes</button>
          </div>
        </form>
    </div>
  </div>
</div>
<!-- End Modal Create -->
<!-- Button trigger modal -->


<!-- Modal Udate -->
<div v-if="showModal">
      <div>
        <label for="editName">Name:</label>
        <input type="text" id="editName" v-model="editFormData.nama" required >
        <br><br>
        <label for="editEmail">Email:</label>
        <input type="text" id="editEmail" v-model="editFormData.kelas" required>
        <br><br>
        <button @click="updateData">Update</button>
        <button @click="closeModal">Cancel</button>
      </div>
    </div>

</div>
<hr class="mx-4">
  <div class="container mt-5 ">
        <!-- Button trigger modal -->
        <h2 class="text-center">Data Staff</h2>
        <p class="text-muted text-center">From Site B</p>
      <button type="button" class="btn btn-primary float-left mb-3" data-bs-toggle="modal" data-bs-target="#teachersInput">
        Buat Baru!
      </button>

    <table class="table table-bordered text-white text-center">
    <thead>
      <tr>
        <th>Id</th>
        <th>Nama</th>
        <th>Kelas</th>
        <th>Action</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="post,k in formData" :key="k">
        <th class="" scope="row">{{ post.id }}</th>
        <td>{{ post.nama }}</td>
        <td>{{ post.kelas }}</td>
        <td class="d-flex gap-2">
          <button @click="editData(post.id)">Edit</button>
          <a href="" class="btn btn-sm btn-danger">Delete</a>
        </td>
      </tr>
    </tbody>
  </table>



<!-- Modal Create -->
<div class="modal fade" id="teachersInput" tabindex="-1" aria-labelledby="teachersInputLabel" aria-hidden="true">
  <div class="modal-dialog">
    <div class="modal-content bg-dark">
      <div class="modal-header">
        <h1 class="modal-title fs-5" id="teachersInputLabel">Modal title</h1>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
        <form @submit.prevent="submitForm">
          <div class="modal-body">
              <div class="mb-3">
                <label for="nama">Nama</label>
                <input type="text" name="nama" id="nama" v-model="formData.nama" class="form-control">
              </div>
              <div class="mb-3">
                <label for="kelas">Kelas</label>
                <input type="text" name="kelas" id="kelas" v-model="formData.kelas" class="form-control">
              </div>
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
            <button type="submit" class="btn btn-primary" onclick="return confirm('Yakin dek?')" >Save changes</button>
          </div>
        </form>
    </div>
  </div>
</div>
<!-- End Modal Create -->
<!-- Button trigger modal -->


<!-- Modal Udate -->
<div v-if="showModal">
      <div>
        <label for="editName">Name:</label>
        <input type="text" id="editName" v-model="editFormData.nama" required >
        <br><br>
        <label for="editEmail">Email:</label>
        <input type="text" id="editEmail" v-model="editFormData.kelas" required>
        <br><br>
        <button @click="updateData">Update</button>
        <button @click="closeModal">Cancel</button>
      </div>
    </div>

</div>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      formData: [],
        editFormData: {
          nama: '',
          kelas: ''
        },
        editIndex: null,
        showModal: false



    }
  },
  mounted() {
    // axios
    //   .get('http://belajarapi.local/api/students')
    //   .then((response) => {
    //     this.posts = response.data.data
    //   });
    this.getData();
  },
  methods: {
      async submitForm() {
        try {
          const response = await axios.post('http://localhost:5051/api/students-store', this.formStudent);
          console.log(response);
          alert('Add new data Success!')
        } catch (error) {
          console.error(error);
        }
      },
      async getData() {
        try {
          const response = await axios.get('http://localhost:5051/api/students');
          this.formData = response.data.data;
        } catch (error) {
          console.error(error);
        }
      },
      async updateData() {
        try {
          const response = await axios.put('http://localhost:5051/api/students/' + this.editIndex, this.editFormData);
          console.log(response);
          this.closeModal();
          this.getData();
        } catch (error) {
          console.error(error);
        }
      },
      editData(index) {
        this.editIndex = index;
        this.editFormData = { ...this.formData[index-1] };
        this.showModal = true;
      },
      closeModal() {
        this.showModal = false;
        this.editIndex = null;
        this.editFormData = { nama: '', kelas: '' };
      }
   }

}
</script>