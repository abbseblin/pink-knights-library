<template>
  <div>
    <div class="container">
      <b-form @submit="onSubmit" @reset="onReset" v-if="showForm">
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

        <b-button type="submit" variant="primary">{{
          isTableDataVisible ? "Submit" : "Update"
        }}</b-button>
        <b-button type="reset" variant="danger">Reset</b-button>
      </b-form>

      <div class="mt-10 container" v-if="isTableDataVisible">
        <table class="table table-responsive">
          <tbody>
            <tr>
              <th>Id</th>
              <th>Name</th>
              <th>Address</th>
              <th>Email</th>
              <th>Contact</th>
              <th>IsActive</th>
              <th></th>
              <th>Actions</th>
            </tr>
            <tr v-for="item in form.employeeData" :key="item.id">
              <td>{{ item.id }}</td>
              <td>{{ item.name }}</td>
              <td>{{ item.address }}</td>
              <td>{{ item.email }}</td>
              <td>{{ item.contact }}</td>
              <td>
                <div class="switch">
                  <label>
                    <input type="checkbox" :checked="item.isActive" />
                    <span class="lever"></span>
                  </label>
                </div>
              </td>
              <td>
                <Editemployee :id="item.id" />
              </td>
              <td>
                <div>
                  <button class="btn btn-danger" @click="onDelete(item.id)">
                    Delete
                  </button>
                </div>
              </td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    isTableDataVisible: {
      type: Boolean,
      default: true
    },
    showForm: {
      type: Boolean,
      default: true
    }
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
    };
  },
  mounted() {
    this.getData();
     this.$eventBus.on('get-data',this.getData);
  },
  methods: {
    onSubmit(event) {
      event.preventDefault();
      var params = {
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
            this.getData();
            this.$notify({
              text: "Record Inserted Successfully!"
            });
          }
        })
        .catch(error => {
          console.log(error);
        });

    },
    onDelete(id) {

      this.$store.dispatch("deleteEmployee", id).then(res => {
        if (res.data.isSuccess) {
          this.getData();
          this.$notify({
            text: "Record Deleted Successfully!"
          });
        }
      });
    },
    getData() {
      this.$store.dispatch("getEmployees").then(res => {
        if (res.data.isSuccess) {
          this.form.employeeData = res.data.responseData;
        }
      });

    },
    onReset(event) {
      event.preventDefault();
      // Reset our form values
      this.form.email = "";
      this.form.name = "";
      this.form.address = "";
      this.form.contact = "";
      // Trick to reset/clear native browser form validation state
    }
  }
};
</script>
