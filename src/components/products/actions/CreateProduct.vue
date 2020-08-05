<template>
    <div class="createProduct">
        <modal :header="'Create Product'" :isShow="showModal" v-if="showModal" @close="showModal = false">
            <product-form :product="product" v-on:submit-form="productAction"/>
       </modal>
    </div>
</template>
<script>
import Modal from '../../shared/Modal.vue'
import axios from 'axios'
import ProductForm from './ProductForm'
import { errorToaster, successToaster } from '../components/shared/service/ErrorHandler.js'
export default {
  name: 'createProduct',
  components: { Modal, ProductForm },
  data () {
    return {
      product: {},
      showModal: false
    }
  },
  methods: {
    showModalForm: function () {
      this.showModal = true
    },

    productAction: function (product) {
      console.log('Creating new Product', product)
      // Create new product
      axios
        .post(`${process.env.VUE_APP_BASE_URL}/Products`, product)
        .then((response) => {
          this.showModal = false
          successToaster(
            'Product Is Now Added',
            'Product Is Now Added'
          )
          this.$emit('close')
        })
        .catch((error) => {
          this.showLoader = false
          errorToaster(' Failed', 'Please try again after sometime')
          console.log(error)
        })
    }
  }
}
</script>
<style lang="scss">
</style>
