<template>
    <section>
        <div class=" sm:pt-24 pt-2 lg:w-7/12 sm:w-9/12 w-full sm:mt-0 mt-96 sm:text-left text-center">
            <div>
                <h1 class="md:text-7xl text-5xl font-semibold text-black poppins tracking-wide"> More than just shorter links</h1>
                <h4 class="grayh2 poppins lg:w-7/12 sm:w-9/12 w-full fontie mt-3 font-medium">Build your brand’s recognition and get detailed insights 
                    on how your links are performing.
                </h4>

                <Button class="mt-10 px-8 py-3 font-semibold poppins" text="Get Started" color="hsl(180, 66%, 49%)" textcolor="white"/>
            </div>

        
        </div>

    </section>
</template>

<script>
import Button from './Button.vue'

    export default {
        name: 'Showcase',
        components: {
        Button,
        }
    }
</script>


<style>
    .grayh2{
        color:hsl(0, 0%, 75%);
        font:18px;
    }
    .fontie{
        font-size: 18px;
    }
</style>