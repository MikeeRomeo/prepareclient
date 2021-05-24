<template>
    <div>
        <div class="form-row">
            <div class="form-input">
                <div class="form-row form-header">
                    <h4 class="title">Beleid:</h4>
                </div>
                <textarea name="beleid" v-model="Beleid" class="diagnose">
                </textarea>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "DiagnoseTab",
    props:['index'],
    computed:{
        Beleid:{
            get(){
                return this.$store.state.patientFiles.cases[this.index].beleid;
            },
            set(value){
                this.$store.commit('updateBeleid', {"contents":value, "index":this.index})
            }
        },
    }
}
</script>

<style lang="scss" scoped>
    .diagnose{
        height: 500px;
    }
</style>