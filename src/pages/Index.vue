<template>
<div class="q-pa-md">
  <app-header :title='msg' @changeTitle="updateTitle($event)"></app-header>
  <!-- <q-input v-model="searchItem"></q-input> -->
  <q-input label="first name" v-model="firstName"></q-input>
  <q-input label="last name" v-model="lastName"></q-input>
  {{ fullName }}
  <q-list></q-list>
  <app-footer></app-footer>
</div>
</template>

<script>
import Header from '../components/Header.vue'
import Footer from '../components/Footer.vue'
import api from '../boot/axios'

export default {
  name: 'PageIndex',
  
  components: {
    appHeader: Header,
    appFooter: Footer
  },

  watch: {
    searchItem(newVal, oldVal) {
      this.msg = newVal.toUpperCase() 
      // this.msg.toLowerCase()
    },

    firstName: function(newVal, oldVal) {
      this.fullName = `${newVal.toUpperCase()} ${this.lastName.toLowerCase()}` 
    },

    lastName: function(newVal, oldVal) {
      this.fullName = `${this.firstName.toUpperCase()} ${newVal.toLowerCase()}` 
    }
  },

  data() {
    return{
      msg:'Hello world!',
      searchItem: '',
      data: [],
      firstName: '',
      lastName: '',
      fullName: ''
    }
  },

  created() {
    for(let i = 0; i < 100; i++) {
      let result = {
        name: `angka ${i}`,
      }
      this.data.push(result)
    }

    console.log(api);
  },
  
  methods: {
    updateTitle(updatedTitle) {
      console.log(updatedTitle);
      this.msg = updatedTitle
    }
  }
}
</script>
