<template>

    <h2>Tipo de Cuenta: {{cuenta}}</h2>
    <h2>Saldo: {{saldo}}</h2>
    <h2>Cuenta: {{ estado ? 'Activa' : 'Desactivada'}}</h2>
    <div v-for="(servicio,index) in servicios" :key="index">
       {{ index + 1 }} -  {{ servicio }}
    </div>
    <AccionSaldo 
        texto="Aumentar Saldo"
        @accion="aumentar"
    />
    <AccionSaldo 
        texto="Disminuir Saldo"
        @accion="disminuir"
        :desactivar="desactivar"
    />
    <AccionSaldo 
        texto="Multiplicar por 2 el Saldo"
        @accion="multiplicar"
    />
    <AccionSaldo
        texto="Dividir el saldo en 2"
        @accion="dividir"
    />

</template>

<script >
import AccionSaldo from './AccionSaldo.vue'


export default {
    components: {
        AccionSaldo
    },
    data() {
        return {
            saldo: 1000,
            cuenta: 'Visa',
            estado: true,
            cuenta: 'Visa',
            servicios: ['giro','abono','transferencia'],
            desactivar: false
        }
    },
    methods: {

        aumentar() {
            this.saldo = this.saldo + 100
            this.desactivar = false
        },

        disminuir() {
            if(this.saldo === 0){
                this.desactivar = true
                alert('Saldo Agotado')
                return 
            }
            this.saldo = this.saldo - 100
        },

        multiplicar() {
            this.saldo = this.saldo * 2
        },

        dividir() {
            this.saldo = this.saldo / 2
        }
    }
}
</script>

<style>

</style>