<template>
  <div id="main" class="container">
        <div class="row">
            
            <div class="col-sm-4">
                <h1>hoteles</h1>
                <tabla :titulo="hoteles.nombre" :prueba="hoteles">  </tabla>
            </div>

        </div>
    </div>
</template>
<script>
import Vue from 'vue'
import tabla from '@/components/tabla'

 var urlhoteles = 'https://decameronback.herokuapp.com/mostarH.php';
 Vue.component('common-list', {
            props: ['lists'],
            template: `<ul class="list-group"> 
            <li v-for = "item in lists" class = "list-group-item" > 
            {{ item.nombre }} 
            </li> </ul>`,
        });

export default {
    name: 'listhoteles',
     created: function() {
                this.getHotel()
     },
    data () {
    return {
      hoteles: [],
       mititulo:'Titulo a tavla.vue',
    }
  },
  methods: {
                getHotel: function() {
                    axios.get(urlhoteles).then(response => {
                        this.hoteles = response.data
                    });
                },

},
components:{
        tabla
    },
     computed: {
                searchUser: function() {
                    return this.lists.filter((item) => item.hoteles.includes(this.hoteles));
                }
            }
}
</script>
