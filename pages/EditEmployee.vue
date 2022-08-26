<template>
  <div>
    <b-button id="show-btn" @click="showModal(id)">Edit</b-button>

    <b-modal :id="id" hide-footer>
      <template #modal-title>
        Edit Employee Info
      </template>
      <div class="d-block">
        <b-form @submit="onUpdate">
          <b-form-group id="input-group-1" label="Name:" label-for="input-1">
            <b-form-input
              id="input-1"
              v-model="form.name"
              type="text"
              placeholder="Enter Name"
              required
            ></b-form-input>
          </b-form-group>

          <b-form-group id="input-group-2" label="Address:" label-for="input-2">
            <b-form-input
              id="input-2"
              v-model="form.address"
              type="text"
              placeholder="Enter Address"
              required
            ></b-form-input>
          </b-form-group>

          <b-form-group
            id="input-group-3"
            label="Email address:"
            label-for="input-3"
            description="We'll never share your email with anyone else."
          >
            <b-form-input
              id="input-3"
              v-model="form.email"
              type="email"
              placeholder="Enter email"
              required
            ></b-form-input>
          </b-form-group>

          <b-form-group id="input-group-4" label="Contact:" label-for="input-4">
            <b-form-input
              id="input-4"
              v-model="form.contact"
              type="number"
              placeholder="Enter Contact"
              required
            ></b-form-input>
          </b-form-group>
          <input type="text" v-model="hiddenId" hidden />
          <b-button type="submit" variant="primary">
            Update
          </b-button>
          <b-button type="reset" variant="danger">Reset</b-button>
        </b-form>
      </div>
      <b-button class="mt-3" block @click="$bvModal.hide(id)">Close</b-button>
    </b-modal>
  </div>
</template>
<script>
import Registration from "@/components/Registration";
export default {
  components: {
    Registration
  },
  props: {
    id: String,
  },
  data() {
    return {
      form: {
        email: "",
        name: "",
        address: "",
        contact: "",
        employeeData: []
      },
      hiddenId: ""
    };
  },

  mounted() {
  },
  methods: {
    showModal(id) {
      this.$bvModal.show(id);
      this.getEmployeeDetailsById(id);
    },
    onUpdate(event) {
      this.$bvModal.hide(this.id);
      event.preventDefault();
      var params = {
        Id: this.hiddenId,
        Name: this.form.name,
        Address: this.form.address,
        email: this.form.email,
        contact: this.form.contact,
        isActive: true
      };
      this.$store
        .dispatch("createOrUpdateEmployee", params)
        .then(res => {
          if (res.data != null) {
            this.$notify({
              text: "Record Updated Successfully!"
            });
            this.$eventBus.emit('get-data');
          }
        })
        .catch(error => {
          console.log(error);
        });
    },

    getEmployeeDetailsById(id) {
      this.$store.dispatch("getEmployeeByID", id).then(res => {
        if (res.data.isSuccess) {
          this.hiddenId = res.data.responseData.id;
          this.form.name = res.data.responseData.name;
          this.form.email = res.data.responseData.email;
          this.form.address = res.data.responseData.address;
          this.form.contact = res.data.responseData.contact;
        }
      });
    }
  },

  name: "Editemployee"
};
</script>
<style scoped></style>
