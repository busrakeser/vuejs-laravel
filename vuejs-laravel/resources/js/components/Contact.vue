<template>
  <div v-if="users.length>0" class="card mt-5">
                  <div class="card-header">
                      Üye Listesi
                  </div>
                  <div class="card-body">
                      <li :key="u" v-for="(user,u) in users">
                          {{user}}
                          <button class="btn btn-danger btn-sm" @click="$emit('deleteUser',u)">Sil</button>
                      </li>
                      
                  </div>

              </div>
</template>

<script>
export default {
    //gönderilen dataların yakalandığı kısım
    props:['users']

}
</script>

<style>

</style>