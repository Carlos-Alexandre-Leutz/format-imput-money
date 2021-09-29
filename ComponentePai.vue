<template>
    <div>
        <format-imput-money
            :ViewModel="ViewModel"
            :atualizaTab="true"
            :config="config"
            @reactRealTime="reactRealTime"
        ></format-imput-money>
        {{ ViewModel }}
        
    </div>
</template>
 
<script>
import AutoNumericInput from "./formatImputMoney.vue";
import { ref } from "vue";
export default {
    components: {
        formatImputMoney
    },
    setup() {
        let ViewModel = ref(0);
        let config = ref({
            masked: false,
            prefix: "$",
            suffix: "",
            thousands: ",",
            decimal: ".",
            precision: 2,
            disableNegative: false,
            disabled: false,
            min: null,
            max: null,
            allowBlank: false,
            minimumNumberOfCharacters: 0,
        });
        const reactRealTime = (e) => {
            ViewModel.value = e;
        };
        return {
            ViewModel,
            reactRealTime,
            config,
        };
    },
};
</script> 
