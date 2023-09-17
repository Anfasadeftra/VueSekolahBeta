<template>
  <div class="py-4">
    <div a style="font-family: arial;" class="container">
      <div class="title border-bottom d-flex align-items-center justify-content-between py-2">
        <h3>SEWAKU</h3>
        <div class="d-flex align-items-center my-4">
          <input
            type="text"
            class="form-control"
            placeholder="Cari Jasa"
            v-model="searchQuery"
          />
            <span class="me-2 mx-4">Tampilkan Sebagai</span>
            <button
              class="btn btn-outline-dark"
              @click="isGrid=!isGrid"
            >
              {{ isGrid ? 'Grid' : 'List' }}
            </button>
            <span class="me-2 mx-4">Kategori</span>
            <select class="form-select-sm py-2" aria-label=".form-select-lg example" v-model="selectedCategory">
              <option value="">Semua</option>
              <option value="Desain">Jasa Desain</option>
              <option value="Video">Jasa Video</option>
              <option value="Foto">Jasa Foto</option>
            </select>
        </div>
      </div>
      <div class="list-task row">
        <CardData
          v-for="(task, i) in filteredTasks"
          :key="i"
          :task="task"
          :isGrid="isGrid"
        />
      </div>
      <div class="action py-2">
        <a
          v-if="!isCreating"
          href="#"
          class="add-button"
          @click="isCreating=!isCreating"
        >
        Add Task
        </a>
        <div v-else class="add-card">
          <form @submit.prevent="addTask">
            <div class="card mb-2">
              <div class="card-body d-flex flex-column p-0">
                <input v-model="newTask.title" class="form-control border-0 mb-2" placeholder="Title" type="text" />
                <textarea 
                v-model="newTask.description" 
                class="form-control border-0 small" 
                placeholder="Description" rows="3"
                ></textarea>
                <select v-model="newTask.category" class="form-select border-0 mb-2">
                  <option value="">Pilih Kategori</option>
                  <option value="Desain">Jasa Desain</option>
                  <option value="Video">Jasa Video</option>
                  <option value="Foto">Jasa Foto</option>
                </select>
              </div>
            </div>
            <div class="button-wrapper d-flex">
              <button class="btn btn-primary me-2">Save</button>
              <button class="btn btn-outline-secondary" @click="isCreating = !isCreating">Cancel</button>
            </div>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import CardData from '../components/Card/CardData.vue';
export default {
  layout(context) {
    return 'custom';
  },
  components: {
    CardData,
  },
  data() {
    return {
      searchQuery: '',
      isGrid: true,
      isCreating: false,
      selectedCategory: '',
      tasks: [
        {
          title: 'Desain 1',
          description: 'ini deskripsi desain',
          isDone: false,
          category: 'Desain',
        },
        {
          title: 'Video 1',
          description: 'ini deskripsi video',
          isDone: false,
          category: 'Video',
        },
        {
          title: 'Foto 1',
          description: 'ini deskripsi foto',
          isDone: false,
          category: 'Foto',
        },
        {
          title: 'Desain 2',
          description: 'ini deskripsi desain',
          isDone: false,
          category: 'Desain',
        },
        {
          title: 'Video 2',
          description: 'ini deskripsi video',
          isDone: false,
          category: 'Video',
        },
        {
          title: 'Foto 2',
          description: 'ini deskripsi foto',
          isDone: false,
          category: 'Foto',
        },
      ],
      newTask: {
          title: '',
          description: '',
          isDone: false,
          category: '',
      },
    };
  },

  methods: {
    addTask() {
      if (this.newTask.title && this.newTask.description && this.newTask.category) {
        const newTaskObject = {
          title: this.newTask.title,
          description: this.newTask.description,
          isDone: this.newTask.isDone,
          category: this.newTask.category,
        };

        this.tasks.push(newTaskObject);
        this.resetForm();
        this.isCreating = false;

      } else {
        alert('Semua field perlu diisi');
      }
    },
    resetForm() {
      this.newTask.title = '';
      this.newTask.description = '';
      this.newTask.isDone = false;
      this.newTask.category = '';
    },
  },

  computed: {
    filteredTasks() {
      let filteredByCategory = [];
      if (this.selectedCategory === '') {
        filteredByCategory = this.tasks;
      } else {
        filteredByCategory = this.tasks.filter((task) => task.category === this.selectedCategory);
      }
      if (this.searchQuery === '') {
        return filteredByCategory;
      } else {
        return filteredByCategory.filter((task) =>
          task.title.toLowerCase().includes(this.searchQuery.toLowerCase())
        );
      }
    },
  },
};
</script>