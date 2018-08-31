<template>
        <div>
            <h1>{{titulo}}</h1>
            <ul  class="list-group">
                <li class="list-group-item">
                        <input type="text" placeholder="Buscar" class="form-control" v-model="nombre">
                    </li>
                <li class="list-group-item"  v-for="item in prueba" :key="item.algo">{{item.nombre}}</li>              
            </ul>
        </div>
</template>
<script>
export default {
    name:'tabla',
      props: ['titulo','prueba'],
         
}
</script>

