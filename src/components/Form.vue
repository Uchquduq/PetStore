<template>
  <div>
  <my-header :cartItemCount="cartItemCount"></my-header>
    <div class="mt-5">
      <div class="container">
        <div class="row">
           <h2 class="text-center ml-3 col-12"><strong>Pet Depot Checkout</strong></h2>
           <h5 class="text-center ml-3 col-12"><strong>Enter Your Information</strong></h5>

          <div class="col-6">
            <div class="form-group">

            </div>
            <div class="form-group">
              <div class="col-md-12">
                <strong>First Name:</strong>
                <input v-model.trim="order.firstName" class="form-control" />
              </div>
              <div class="col-md-12">
                <strong>Last Name:</strong>
                <input v-model.trim="order.lastName" class="form-control" />
              </div>
            </div>
            <div class="form-group">
              <div class="col-md-12"><strong>Address:</strong></div>
              <div class="col-md-12">
                <input   v-model.trim="order.address" class="form-control" />
              </div>
            </div>
            <div class="form-group">
              <div class="col-md-12"><strong>City:</strong></div>
              <div class="col-md-12">
                <input v-model.trim="order.city" class="form-control" />
              </div>
            </div>
            <div class="form-group">
              <div class="col-md-6">
                <strong>State:</strong>
                <select v-model="order.state" class="form-control">
                  <option disabled value="">State</option>
                  <option v-for="(state, key) in states" v-bind:value="state" :key="key">
                  {{key}}
                  </option>
                </select>
              </div>
            </div>
            <div class="form-group">
              <div class="col-md-6 col-md-offset-4">
                <strong>Zip / Postal Code:</strong>
                <input v-model.number="order.zip"
                   class="form-control"
                   type="number"/>
              </div>
            </div>
            <div class="form-group">
              <div class="col-md-6 boxes">
                <input type="checkbox"
                       id="gift" value="true"
                                 v-bind:true-value="order.sendGift"
                                 v-bind:false-value="order.dontSendGift"
                                 v-model="order.gift">
                <label for="gift">Ship As Gift?</label>
              </div>
            </div><!-- end of form-group -->
            <div class="form-group">
              <div class="col-md-6 boxes">
                <input type="radio"
                       id="home"
                       v-bind:value="order.home"
                       v-model="order.method">
                <label for="home">Home</label>
                <input type="radio"
                       id="business"
                       v-bind:value="order.business"
                       v-model="order.method">
                <label for="business">Business</label>
              </div>
            </div><!-- end of form-group-->




          </div><!--end of panel-body-->
          <div class="col-6 verify">
              <pre class="mt-3">
              First Name: {{order.firstName}}
              Last Name: {{order.lastName}}
              Address: {{order.address}}
              City: {{order.city}}
              Zip: {{order.zip}}
              State: {{order.state}}
              Method: {{order.method}}
              Gift: {{order.gift}}
              </pre>
              <div class="form-group">
              <div class="col-md-6">
                <button type="submit" class="btn btn-primary submit" v-on:click="submitForm">Place Order</button>
              </div><!-- end of col-md-6-->
            </div>
            </div>
            <!-- end of col-md-12 verify-->

            <!-- end of form-group-->
        </div><!--end of panel panel-info-->


      </div><!--end of col-md-10 col-md-offset-1-->
    </div><!--end of row-->
  </div>
</template>
<script>
import MyHeader from './Header.vue';
export default {
  name: 'Form',
  props: ['cartItemCount'],
  data () {
    return {
      states: {
        AL: 'Alabama',
        AK: 'Alaska',
        AR: 'Arizona',
        CA: 'California',
        NV: 'Nevada'
      },
      order: {
        firstName: '',
        lastName: '',
        address: '',
        city: '',
        zip: '',
        state: '',
        method: 'Home Address',
        business: 'Business Address',
        home: 'Home Address',
        gift:'',
        sendGift: 'Send As A Gift',
        dontSendGift: 'Do Not Send As A Gift'
      }

    }
  },
  components: { MyHeader },
  methods: {
    submitForm() {
      alert('Submitted');
    }
  }
}
</script>
<style>
</style>
