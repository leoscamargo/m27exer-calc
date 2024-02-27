<script>
export default {
    data() {
        return {
            num1: '',
            num2: '',
            operator: '',
            resultado: '0',
        };
    },
    methods: {
        calcula() {
            const value1 = parseFloat(this.num1);
            const value2 = parseFloat(this.num2);
            switch (this.operator) {
                case 'adicao':
                    this.resultado = value1 + value2;
                    break;
                case 'subtracao':
                    this.resultado = value1 - value2;
                    break;
                case 'multiplicacao':
                    this.resultado = value1 * value2;
                    break;
                case 'divisao':
                    this.resultado = value1 / value2;
                    break;
            }
        },
    },
};
</script>
<template>
    <form>
        <div class="row">
            <div class="col">
                <input v-model="num1" @input="calcula" required type="text" placeholder="Digite o número 1"
                    class="form-control">
            </div>
            <div class="col-md-2">
                <p class="mt-1">Escolha o tipo da operação:</p>
            </div>
            <div class="col-md-2">
                <select class="form-control" v-model="operator" @change="calcula">
                    <option value="adicao">Somar</option>
                    <option value="subtracao">Subtrair</option>
                    <option value="multiplicacao">Multiplicar</option>
                    <option value="divisao">Dividir</option>
                </select>
            </div>
            <div class="col">
                <input v-model="num2" @input="calcula" required type="text" placeholder="Digite o número 2"
                    class="form-control">
                </div>
            <h5 class="mt-5">Resultado: {{ resultado }}</h5>
        </div>
    </form>
</template>