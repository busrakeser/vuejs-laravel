<template>
  <div class="container">
      <div class="row justify-content-center">
          <div class="col-md-8 mt-5">
              <div class="card">
                  <div class="card-header">
                      Örnek uygulama
                  </div>
                  <div class="card-body">
                      <div class="form-group">
                          <label>Ad Soyad</label>
                          <input type="text" v-model="name" class="form-control" v-bind:class="{'is-invalid':errors.length>0, 'is-valid':errors.length==0 && name!=''}">
                          <div class="invalid-feedback">
                              <span :key="ky" v-for="(error,ky) in errors">
                                  {{error}}
                              </span>
                          </div>
                      </div>
                      <button :disabled="errors.length>0 || name==''" @click="create" class="btn btn-primary">Oluştur</button>
                  </div>

              </div>
              <!-- :users değişkeni ile dataları Contact sayfasına gönderdik -->
              <!-- @deleteUser ile gelen emit i dinleyp deleteUsers methoduna gönderdik -->
              <user-list @deleteUser="deleteUsers" :users="users"></user-list>
          </div>
      </div>
  </div>
</template>

<script>
//contact kısını projeye çağırma işlemi
import userList from './Contact.vue'
export default {
    components:{
        //userlist e erişim ve kullanım alanı
        userList

    },
    data() {
        return {
            name:'',
            errors:[],
            users:[],
        }
    },
    
    watch:{
        name(val){
            this.errors=[]
            //console.log(val)
            //console.log(this.name.length)
            if(this.name.length==''){
                this.errors.push('Alan boş bırakılamaz')
                return 
            }
            if(val[0]!=val[0].toUpperCase()){
                this.errors.push('Ad büyük harfle başlamalıdır')
                return;
            }
            if(this.name.length<4){
            
                this.errors.push('Ad Soyad alanı minimum 6 karakter olmalıdır.')
                return;
            }
            if(this.name.length>25){
                this.errors.push('Ad Soyad alanı maximum 24 karater olmalıdır.')
                return
            }
            
            
        }
    },
    methods: {
        create(){
            this.users.push(this.name);
        },
        //silme işlemi contact(child) sayfasından gelen istek doğrultusunda parentta gerçekleşti
        deleteUsers(key){
            this.$delete(this.users,key);

        }
    
    },


}
</script>

<style>

</style>