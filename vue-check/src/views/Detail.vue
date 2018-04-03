<template>
    <div>
    <div>楼盘详情页</div>
    楼盘名称：{{state.name}}
    </div>
    
</template>
<script>
    export default {
        name:"Detail",
        data(){
            return {
                state:{}
            }
        },
        created(){
            this.$http.post("http://localhost:3000/detail",{id:this.$route.params.id},{emulateJSON:true}).then(e=>this.state=e.body[0])
        }
    }
</script>