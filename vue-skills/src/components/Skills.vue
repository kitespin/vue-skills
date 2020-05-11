<template>
    <div class="hello">
        <div class="holder">
            <!-- prevents the page from reloading and calls the method addSkill on submission -->
            <form @submit.prevent="addSkill">
                <!-- v-model allows 2 way data binding allows communication between template and logic and viceversa -->
                <input type="text" placeholder="Enter a skill you have..." v-model="skill">
                
               <!-- <input type="checkbox" id="checkbox" v-model="checked"> -->
               
            </form>
            <ul>
                <transition-group name="list" enter-active-class="animated bounceInUp" leave-active-class="animated bouceOutDown">
                    <li v-for="data in skills" :key="data.skill"> {{ data.skill }}</li>
                </transition-group>
            </ul>

            <p>These are the skills that you possess.</p>
        </div>
    </div>
</template>

<script>
export default {
    name: "Skills",
    data() {
        return {
            //checked: false,
            skill: "",
            skills: [
                {"skill": "vue.js"},
                {"skill": "Frontend development"},
            ],
        }
    },
    methods: {
        addSkill(){
            this.skills.push({skill: this.skill})
            //emptys out the skill once submitted
            this.skill = "";
            //console.log('This checkbox value is : '+this.checked);
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import "https://cdn.jsdelivr.net/npm/animate.css@3.5.1";

.holder{
    background: #fff;
}

ul{
    margin: 0;
    padding: 0;
    list-style-type: none;
}

ul li{
    padding: 20px;
    font-size: 1.3em;
    background-color: #E0EDF4;
    border-left: 5px solid #3EB3F6;
    margin-bottom: 2px;
    color: #3E5252;
}

p{
    text-align: center;
    padding: 30px 0;
    color: gray;
}

.container{
    box-shadow: 0px 0px 40px lightslategray;
}

input{
    width: calc(100% - 40px);
    border: 0;
    padding: 20px;
    font-size: 1.3em;
    background-color: #323333;
    color: #687F7F;
}

</style>





