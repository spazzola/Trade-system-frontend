<template>
    <div class="add-supplier-content">
        <div class="form-group">
            <label>Nazwa sprzedawcy</label>
            <input type="text" id="date" class="form-control" v-model="supplier.name"/>
            <button 
                    class="btn btn-success btn-sm" 
                    style="margin-top: 0.5%;"
                    @click="createSupplier">Dodaj
            </button>
        </div>
    </div>
</template>

<script>
import axios from '../../axios-auth'
import { eventBus } from '../../main'

export default {
    data() {
        return {
            supplier : {
                name: ''
            }
        }
    },
    methods: {
        createSupplier() {
            axios.post("/supplier/create", this.supplier, {
                headers: {
                    'Authorization': 'Bearer ' + this.$store.state.jwt
          }
            }).then(resp => {
                if (resp.status == 200) {
                    alert('Dodano sprzedawce')
                }
            }).catch((error) => {alert('Nie dodano sprzedawcy')})
            .then(this.$store.commit('getAllBuyers'))
            setTimeout(()=>{
                this.supplier.name = ''
                },100);
        }
    }
}
</script>

<style scoped>
.add-supplier-content {
  position: relative;
  width: 100%;
  height: 100%;
  border-radius: 0px 5px 5px 5px;
  margin: 0.5%;
  float: left;
}

.form-control {
  width: 15%;
  height: 25px;
  font-size: 0.9vw;
}

button {
    opacity: 1;
    display: inline;
    font-size: 0.9vw;
}

label {
    font-size: 0.9vw;
}
</style>