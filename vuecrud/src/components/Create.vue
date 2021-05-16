<template>
  <div class="container" >
        <div class="card">
            <div class="card-header" style="background-color: grey;">
                <h3 >New Bike</h3>
            </div>
            <div class="card-body">
                <form v-on:submit.prevent="addItem">
                    <div class="form-group">
                        <label>Bike Manufacturer:</label>
                        <input type="text" class="form-control" v-model="item.name"/>
                    </div>
                    <div class="form-group">
                        <label>Model:</label>
                        <input type="text" class="form-control" v-model="item.price"/>
                    </div>
                    <div class="form-group">
                        <br>
                        <input type="submit" class="btn btn-primary" value="Add"/>
                    </div>
                </form>               
            </div>
        </div>
        <div>
            <br><br>
            <h3 style="text-align: center;">Featured Bike</h3>
            <img src="https://www.bikebug.com/assets/full/BP_59256.jpg" style="background-color: grey;display: block; margin-left: auto; margin-right: auto;width:90%;">
        </div>
    </div>
</template>


<script>
export default {
  components: {
      name: 'AddItem'
  },
  data() {
      return {
          item: {}
      }
  },
  methods: {
      addItem() {
           let uri = 'http://localhost:4000/items/add';
            this.axios.post(uri, this.item).then((response) => {
                console.log(response.data)
            });
        }
    }
}
</script>

<!--
Tan, Geoferson Owen P.
WD-202
-->