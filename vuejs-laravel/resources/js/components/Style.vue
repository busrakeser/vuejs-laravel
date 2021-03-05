<template>
  <div class="container">
      <div class="row justify-content-center">
          <div class="col-md-8 mt-5">
              <div class="card">
                  <div class="card-header">
                      Class&Style İşlemleri
                  </div>
                  <div class="card-body">
                      <!-- <p v-bind:class="{'text-danger':red}">Merhaba ben Büşra</p> -->
                      <p v-bind:class="{kirmizi:red, buyut:size}">Merhaba ben Büşra</p>
                      <!-- <button @click="red=true">Kırmızı</button> -->
                      <button @click="red=!red">Renk Değiştir</button>
                      <button @click="size=!size">Boyut Değiştir</button>

                        <hr>
                      <!-- belirlenen kurallara göre veri girişini sağlama -->
                      <!-- girilen inputun uzunluğu 3 ten küçük olduğu sürece kırmızı olacak -->
                      <!-- 3 ve 3ten büyük karakter girildiğinde yeşil olacak -->
                      <label>Ad Soyad</label>
                      <!-- <input type="text" class="form-control" v-bind:class="{'is-invalid':name.length<3, 'is-valid':name.lenght>2}" v-model="name"> -->
                          <!-- yukarıdaki işlemleri if ile yapma -->
                          <input type="text" class="form-control" v-model="name" v-bind:class="[name.length>3 ? 'is-valid' : 'is-invalid']">
                  
                        <hr>
                      <p v-bind:style="myStyle">Lorem ipsum dolor sit amet consectetur adipisicing elit. Beatae eligendi repellendus quidem! Placeat aperiam obcaecati itaque delectus quae similique temporibus dignissimos doloribus, quis ipsa corporis rem commodi sed fugiat nesciunt alias minima provident maxime odio. Assumenda, voluptatibus rem! Odio veniam suscipit saepe accusantium optio placeat iure sint assumenda. Laborum, hic.</p>

                  </div>
              </div>
          </div>
      </div>
  </div>
</template>

<script>
export default {
    data() {
        return {
            red:false,
            size:false,
            name:'',
            myStyle:{
                color:'red',
                fontSize:'30px',
            }
        }
    },

}
</script>

<style>
.kirmizi{
    color: red;
}
.buyut{
    font-size:50px ;
}
</style>