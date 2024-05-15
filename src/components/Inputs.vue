<script setup>
    const props = defineProps(['valor1', 'valor2', 'trocaOperacao'])
</script>

<template>
    <form class="p-4">
        <h5 class="text-white">Qual tipo de operação gostaria de fazer?</h5>
        <select @change="props.trocaOperacao" class="seletor form-control mt-3">
            <option value="adicao">Adição +</option>
            <option value="subtracao">Subtração -</option>
            <option value="multiplicacao">Multiplicação *</option>
            <option value="divisao">Divisão /</option>
        </select>
        <div class="inputs d-flex mt-2 gap-2">
            <input @keyup="props.valor1" type="number" class="form-control" placeholder="Digite o primeiro valor">
            <input @keyup="props.valor2" type="number" class="form-control" placeholder="Digite o segundo valor">
        </div>
        
    </form>
</template>

<style>
    .seletor {
        max-width: 25%;
    }

    input {
        max-width: 20rem;
    }

    @media screen and (max-width: 430px){
        .seletor {
            max-width: 40%;
        }
        .seletor option{
            font-size: 12px;
        }
        .inputs {
            flex-direction: column;
        }
    }
</style>