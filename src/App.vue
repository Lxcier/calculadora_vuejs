<script setup>
import { reactive } from 'vue';
import Cabecalho from './components/Header.vue';
import Calculadora from './components/Inputs.vue';

const estado = reactive({
    operacao: "adicao",
    valor1: 0,
    valor2: 0,
});

const somar = ({valor1, valor2} = estado) => valor1 + valor2;

const subtrair = ({valor1, valor2} = estado) => valor1 - valor2;

const multiplicar =  ({valor1, valor2} = estado) => valor1 * valor2;

const dividir = ({valor1, valor2} = estado) => valor1 / valor2;

const calculador = () => {
    const {valor1, valor2, operacao} = estado;

    if (valor1, valor2) {
        switch(operacao) {
            case 'adicao':
                return somar();
            case 'subtracao':
                return subtrair();
            case 'multiplicacao':
                return multiplicar();
            case 'divisao':
                return dividir();       
        }   
    }
}

</script>

<template>
    <div class="container">
       <Cabecalho />
       <Calculadora :troca-operacao="evento => estado.operacao = evento.target.value"
       :valor-1="evento => estado.valor1 = Number(evento.target.value)" 
       :valor-2="evento => estado.valor2 = Number(evento.target.value)"/> 
       <div class="resultado mt-0 m-4">
            <p class="text-dark p-2">O resultado é: {{ calculador() }}</p>
        </div>
    </div>
</template>

<style>
    .resultado {
        background-color: #58DF71;
        max-width: calc(40rem + 6px);
    }
</style>