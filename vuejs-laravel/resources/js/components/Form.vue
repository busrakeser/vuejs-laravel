<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-6 mt-5">
                <div class="card">
                    <div class="card-header">
                        Form işlemleri
                    </div>
                    <div class="card-body">
                        

                        <div class="form-group">
                            <!-- {{name}} -->
                            <!-- js deki name yerine v-model tanımlayıp name yi onun içerisinie atıyoruz data kısmında eklenilen değer default değeri -->
                            <label>Text</label>
                            <input class="form-control" type="text" v-model="name">
                        </div>


                        <div class="form-group">
                            <!-- {{name}} -->
                            <!-- js deki name yerine v-model tanımlayıp name yi onun içerisinie atıyoruz data kısmında eklenilen değer default değeri -->
                            <!-- <label>Select Box</label>
                            <select class="form-control" v-model="select">
                                <option value="0">Seçenek 1</option>
                                <option value="1">Seçenek 2</option>
                            </select> -->
                            <label>Select Box Arrayden Listeleme</label>
                            <select class="form-control" v-model="select">
                                <option :value="option.value" :key="key" v-for="(option,key) in options">
                                    {{option.name}}
                                </option>
                                
                            </select>
                        </div>


                        <div class="form-group">
                            <label>Radio Button</label><br>
                            Seçilen {{radio}} <br>
                            <input type="radio" id="bir" v-model="radio" value="ELMA">
                             <label for="bir">Elma</label><br>
                            
                            <input type="radio" id="iki" v-model="radio" value="ARMUT">
                            <label for="iki">Armut</label>
                        </div>


                        
                        <!-- <div class="form-group">
                            <label>CheckBox</label><br>
                            {{checkbox}}
                            <input type="checkbox" v-model="checkbox">
                             
                        </div> -->


                        <div class="form-group">
                            <label>CheckBox</label><br>
                            {{checkbox}} <br>
                            <input type="checkbox" id="elma" value="Elma" v-model="checkbox">
                            <label for="elma">Elma</label> <br>
                            <input type="checkbox" id="armut" value="Armut" v-model="checkbox">
                            <label for="armut">Armut</label> <br>
                            <input type="checkbox" id="kiraz" value="Kiraz" v-model="checkbox">
                            <label for="kiraz">Kiraz</label> <br>
                             
                        </div>
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
            name:null,
            //name:'Büşra' default değer 
            options:[
                {name:'Belirtmek istemiyorum' , value:0},
                {name:'Erkek', value:1},
                {name:'Kadın', value:2}
            ],
            select:null,
            //select:1 bir option nın seçili gelmesi için kullanılır
            radio:null,
            //checkbox:false,
            checkbox:[],
        }
    },
}
</script>


<style>

</style>