<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8 mt-5">
                <div class="card">
                    <div class="card-header">
                        Watch Proporties
                    </div>
                    <div class="card-body">
                        <h1 v-if="alert">Sayı {{counter}}'a ulaştı</h1>
                        Sayı: {{counter}}
                        <button @click="counter++">Arttır</button>
                        <button @click="counter--">Azalt</button>

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
            counter:0,
            alert:false
        }
    },
    methods: {
        artir(){
            this.alert=true
        }
    },
    watch:{
        counter(val,oldval){
            console.log('sayı arttı'),//butona her tıklandığında consola yazar
            console.log(val),// ilk parametre butona her tıklandığında counter değerini yazar
            console.log(val,oldval)// ilk ve ikinci parametre butona her tıklandığında counter değerini ve önceki değerini yazar
            console.log(val>oldval ?'Sayı arttırıldı' : 'Sayı Azaltıldı')
            //sayı arttırıldığında bir method çağırılabilir
            if(val>oldval){
                if(val>9){
                    this.artir();
                }
            }        
        }
    }

}
</script>

<style>

</style>