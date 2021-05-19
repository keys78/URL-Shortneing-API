<template>
    <header>
        <div class="xl:w-5/12 lg:w-6/12 md:w-7/12 md:flex hidden flex  justify-between font-semibold items-center poppins">
            <h1 class="logos">Shortly</h1>
            <h2 class="cursor-pointer grayhsl">Features</h2>
            <h2 class="cursor-pointer grayhsl">Pricing</h2>
            <h2 class="cursor-pointer grayhsl">Resources</h2>
        </div>
        
        <div class="flex justify-between md:flex hidden items-center font-semibold poppins gap-4">
            <h2 class="grayhsl">Login</h2>
            <Button class="font-medium" text="Sign Up" color="hsl(180, 66%, 49%)" textcolor="white"/>
        </div>

        
    </header>
    <div class="flex justify-between items-center md:hidden flex">
             <div class="logos">Shortly</div>
             <div @click="toggleBar">
                 <i v-if="!showBar" class=" text-2xl hover:text-green-400 fas fa-bars cursor-pointer"></i>
                 <i v-if="showBar" class="text-3xl hover:text-red-400 fas fa-times cursor-pointer"></i>
             </div>
        </div>

        <div v-if="showBar" class="animate__animated animate__faster animate__slideInDown -mb-96 text-center md:hidden block w-11/12 mx-auto rounded-t-3xl rounded-b-3xl dark-blue p-8 z-index-100">
        
            <h2 class="cursor-pointer text-white font-bold">Features</h2>
            <h2 class="cursor-pointer py-6 text-white font-bold">Pricing</h2>
            <h2 class="cursor-pointer text-white font-bold">Resources</h2>
        
            <h1 class="border-b border-white py-6 opacity-30"></h1>

              <h2 class="cursor-pointer text-white font-bold py-6">Login</h2>
            <Button class="font-medium w-11/12 mx-auto py-3" text="Sign Up" color="hsl(180, 66%, 49%)" textcolor="white"/>
        
        </div>
</template>

<script>
import Button from './Button'


export default {
    name: 'Header',
    
    data() {

        return {
            showBar: true,
        }

    },

    components: {
    Button,
},
    methods: {
        toggleBar() {
            this.showBar = !this.showBar
        }
    }
}


</script>



<style scoped>
 Header{
    display: flex;
    justify-content:space-between;
    align-items: center;
 }
.logos{
    font-weight:700;
    font-size: 32px;
}
h2{
    font-size:18px;
}
.grayhsl{
    color:hsl(257, 7%, 63%);
}

.grayhsl:hover{
    color:black;
}
</style>
