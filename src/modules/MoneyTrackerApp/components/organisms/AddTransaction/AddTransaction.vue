<template>
    <div>
        <form-transaction 
            @save-data="onSaveTransaction"
            data-testid="form-transaction"
        />
    </div>
</template>

<script>
import FormTransaction from './FormTransaction';
import types from './../../../../../store/modules/money-tracker/types';
export default {
    name: 'AddTransaction',

    components: {
        FormTransaction
    },
    methods: {
        onSaveTransaction(data){
            this.$store.dispatch(`moneyTracker/${types.createTransaction}`, data)
        }
    }
}
</script>

<style scoped>
    div {
        margin-top: 3rem;
    }
</style>