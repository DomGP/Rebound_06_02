<template>
    <div>

        <form class="form-style" action="">
            <label for="">Ingrese su nombre</label>
            <input type="text" v-model="name" required>
            <label for="">Ingrese su apellido</label>
            <input type="text" v-model="lastName" required>
            <label for="">Ingrese su correo</label>
            <input type="email" v-model="email" required>
            <input class="btn-style" type="submit" @click.prevent="sendForm">
        </form>
        <br>
        <form action="">
            <label for="">Ingrese su edad</label>
            <input type="number" v-model="edad">
            <!-- <input type="submit" @click.prevent="sendAge"> -->
        </form>
        <div v-if="edad>0 && edad < 14">Tu edad es niñez</div>
        <div v-else-if="edad>13 && edad < 18">Tu edad es adolecencia</div>
        <div v-else-if="edad>17 && edad < 35">Tu edad es adulto joven</div>
        <div v-else-if="edad>35 && edad < 65">Tu edad es adulto</div>
        <div v-else-if="edad>64">Tu edad es tercera edad</div>

    </div>
</template>

<script>
export default {
    name: 'component-name',
    // props: {},
    data: function(){
        return {
            name:"",
            lastName:"",
            email:"",
            edad:"",
        }
    },
    // computed: {},
    methods: {
        sendForm(){
            alert(`Saludos ${this.name} ${this.lastName}, tu correo es ${this.email}`)
            this.name=""
            this.lastName=""
            this.email=""
            this.edad=""
        },
    }
    // watch: {},
    // components: {},
    // mixins: [],
    // filters: {},
    // -- Lifecycle Methods
    // -- End Lifecycle Methods
}
</script>

<style scoped>
.form-style{
    display: flex;
    flex-direction: column;
    width: 10%;
    justify-content: center;
    align-content: center;
    text-align: center;
}
.btn-style{
    margin-top: 10px;
}
    
</style>