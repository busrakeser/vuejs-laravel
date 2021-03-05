<template>
    <div align="center">
        <!-- <p>İf-Else kullanımı</p>
        Merhaba {{ isim }} <span v-html="soyisim"></span>
         Yaşınız {{ yas }}
         <h5 v-if="yas>=18">Reşitsiniz</h5>
         <h5 v-else>Reşit değilsiniz</h5>
         <hr> -->

        <p>Dizi yazdırma</p>
         {{ meyveler}}
         <hr>

        <p>For ile dizinin elemanlarını yazdırma</p>
         <li :key="meyve" v-for="meyve in meyveler">
             {{meyve}}

         </li>
         <hr>

        <p>For ile dizinin indis numaralarını ve elemanlarını yazdırma</p>
         <li :key="meyve" v-for="(meyve,key) in meyveler">
             {{key+"-"+meyve}}

         </li>
         <hr>

        <p>Object yazdırma</p>
         <li :key="user" v-for="(user) in users">
             {{user}}
         </li>
         <hr>

        <p>Object içerisindeki elemanlara erişme</p>
         <li :key="user" v-for="(user) in users">
             {{user.name}}
         </li>
         <hr>

        <p>Objectin içerisindeki objectin elemanlarına erişme</p>
         <li :key="user" v-for="(user) in users2">
             {{user.name.firstName}}
         </li>
         <hr>

         <!-- <p>Butona tıklandığğında yaşı bir artırma uygulaması</p>
         Merhaba {{ isim }} <span v-html="soyisim"></span>
         Yaşınız {{ yas }}
         <button @click="ageCounter" class="btn btn-primary">Yaş Arttır</button>
         <h5 v-if="yas>=18">Reşitsiniz</h5>
         <h5 v-else>Reşit değilsiniz</h5>
        <hr> -->

        <!-- <p>Butona tıklandığğında yaşı bir artırma uygulaması</p>
         Merhaba {{ isim }} <span v-html="soyisim"></span>
         Yaşınız {{ yas }}
         <button @click="ageCounter(1)" class="btn btn-primary">1 Yaş Arttır</button>
         <button @click="ageCounter(5)" class="btn btn-primary">5 Yaş Arttır</button>
         <h5 v-if="yas>=18">Reşitsiniz</h5>
         <h5 v-else>Reşit değilsiniz</h5>
        <hr> -->

        <p>Butona tıklandığğında yaşı bir artırma uygulaması</p>
         Merhaba {{ isim }} <span v-html="soyisim"></span>
         Yaşınız {{ yas }}
         <button @click="ageCounter('+',1)" class="btn btn-primary">1 Yaş Arttır</button>
         <button @click="ageCounter('-',5)" class="btn btn-primary">5 Yaş Azalt</button>
         <h5 v-if="yas>=18">Reşitsiniz</h5>
         <h5 v-else>Reşit değilsiniz</h5>
        <hr>

        

    </div>
</template>
<script>
export default {
    data() {
        return {
            isim:'Büşra',
            soyisim:'<strong>Keser</strong>',
            yas:16,
            meyveler:['armut', 'elma', 'kiraz'],
            users:[
                {name:'Büşra',age:'25',gender:'female'},
                {name:'Elif',age:'20',gender:'female'},
                {name:'Ali',age:'35',gender:'male'}

            ],
            
            users2:[
                {
                    name:{
                        firstName:'Büşra',
                        lastName:'Keser'
                    },
                    age:'30',
                    gender:'female'
                },
                {
                    name:{
                        firstName:'Ahmet',
                        lastName:'Uğur'
                    },
                    age:'18',
                    gender:'male'
                }

            ]
        }
    },
    methods: {
        ageCounter(command,count){
            //alert(this.yas)
            if(command=='+'){
                this.yas+=count
            }
            else if(command=='-'){
                this.yas-=count
            }
        }
    },
    //vuejs yaşam döngüsü
    beforeCreate() {
        //değişkenler oluşturulmadan önce çalışır
        //methodlar burada çalışmaz çünkü yüklenmemiştir
        console.log('beforeCreate')
    },
    created() {
        //değişkenler ve methodlar oluşturulduktan sonra yapılacak işlemler
        console.log('created')
    },
    beforeMount() {
        console.log('beforeMount')
    },
    mounted() {
        //tüm yüklemeler bittiğinde çalışır jquery ready gibi sayfa yüklendikten sonra 
        this.ageCounter('+',2)
    },

}
</script>
<style lang="stylus">

</style>