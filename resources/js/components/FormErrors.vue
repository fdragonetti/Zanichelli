<template> 
</template>

<script>
export default {
    name: 'FormErrors',
    data(){
        return{
            errors: {},

        }
    },
    methods: {
        setErrors(errors){
            this.errors = errors;
        },

        hasError(fieldName){
            return (fieldName in this.errors);
        },

        getError(fieldName){
            return this.errors[fieldName][0];
        },

        clearError(event){
            Vue.delete(this.errors, event.target.name);
        },

        clearAllErrors(){
            this.errors = {};
        }
    },
    computed:{
        hasAnyError(){
            return Object.keys(this.errors).length > 0;
        }
    }
}
</script>