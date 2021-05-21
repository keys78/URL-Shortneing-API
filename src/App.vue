<template>
  <section class="xl:w-9/12 lg:w-10/12 w-11/12 mx-auto mt-8">
    <Header />

    <section class="sm:mb-52 mb-10">
      <Showcase />
      <div class="overflow-x-hidden absolute sm:top-32 top-28 right-0">
        <img class="kpokoto zufiii relative lg:-right-14 sm:-right-80 -right-8" src="./assets/images/illustration-working.svg" />
      </div>
    </section>
    
    <div class="enactus relative w-full sm:h-36 h-48 dark-violet sm:mt-20 mt-0 -mb-20 rounded-t-2xl rounded-b-2xl border-black mb-60">
      <form @submit.prevent="enactUrl" class="mputa relative flex sm:flex-row flex-col justify-between w-11/12 gap-4 mx-auto pt-12">
          <input v-model="formus" type="text" class="focus:outline-none mputa py-3 px-2 w-full rounded-t-xl rounded-b-xl bg-white" placeholder="Shorten a link here..."/>
          <div v-if="inputError" class="error text-red-500 poppins italic absolute sm:top-28 top-5 left-0">{{ inputError }}</div>
          <input type="submit" value="Shorten It!" class="md:w-2/12 sm:w-3/12 w-full font-medium subito mputa py-3 px-2 rounded-t-xl rounded-b-xl"/>
      </form>
        <img class="sm:block hidden zufi rounded-t-2xl rounded-b-2xl absolute top-0 left-0 w-full h-36" src="./assets/images/bg-shorten-desktop.svg" />
        <img class="sm:hidden block zufi rounded-t-2xl rounded-b-2xl absolute top-0 left-0 w-full h-48" src="./assets/images/bg-shorten-mobile.svg" />
    </div>

  </section>

   
  <section class="w-full grayhsll pt-16 overflow-x-hidden maload">

     <div v-if="load" class="loader pt-10 w-2/12 mx-auto">
      <img class="w-16 mx-auto" src="https://upload.wikimedia.org/wikipedia/commons/7/7a/Ajax_loader_metal_512.gif"/>
    </div>

       <div v-if="block" class="sm:flex-row flex-col flex justify-between sm:items-center py-3 mt-10 bg-white px-2 rounded xl:w-9/12 lg:w-10/12 w-11/12 mx-auto">
            <div class="sm:pl-6 sm:border-b-0 sm:py-0 py-1 border-b-2 text-left font-medium text-lg text-black">{{ formus }}</div>

            <div class="flex sm:flex-row flex-col items-center sm:gap-16 gap-2">
              <div class="sm:w-6/12 w-full lagon text-lg text-left sm:py-0 py-1 pt-1 font-medium text-white"> {{ full_short_link }} </div>
              <div @click.prevent="copyUp" class="sm:w-9/12 w-full">
                  <p v-if="!copy" class="w-full mx-auto cursor-pointer py-1 rounded sm:pr-4 text-center subito px-4">Copy</p>
                 <p v-if="copy" class="w-full mx-auto borontu text-lg py-1 rounded sm:pr-4 text-center text-white px-4 cursor-pointer">Copied!</p>
              </div>
            </div>
        </div>

    <div class="xl:w-4/12 lg:w-5/12 md:w-7/12 w-11/12 mx-auto pt-36 text-center">
      <h1 class="text-3xl font-bold poppins">Advanced Statistics</h1>
      <p class="grayh3 poppins mt-3 font-medium">Track how your links are performing across the web with our advanced statistics dashboard.</p>
    </div>



    <div class="xl:w-9/12 w-11/12 mx-auto lg:mt-60 mt-40 pb-32">
       <h1 class="lg:block hidden -mb-40 w-full h-3 subito"></h1>
       <h1 class="lg:hidden block adjustive mx-auto w-3 h-screen subito"></h1>
      <div class="flex lg:flex-row flex-col gap-7 lg:w-full md:w-6/12 sm:w-7/12 w-11/12 mx-auto">

      <div class=" bg-white sm:h-64 h-72 lg:w-4/12 w-full mx-auto sm:px-8 px-2 text-center pb-20 pt-16 rounded">
        <div class="-mt-24 mb-10 rounded-full dark-blue w-3/12 lg:mx-0 mx-auto p-4">
           <img src="./assets/images/icon-brand-recognition.svg" />
        </div>
        <h1 class="text-xl font-semibold poppins pb-3">Brand Recognition</h1>
        <p class="advstats poppins">Boost your brand recognition with each click. Generic links don’t 
          mean a thing. Branded links help instil confidence in your content.
        </p>
      </div>
      
      <div class=" bg-white sm:h-64 h-72 lg:w-4/12 w-full mx-auto sm:px-8 px-2 text-center pb-20 pt-16 rounded mt-10">
        <div class="-mt-24 mb-10 rounded-full dark-blue w-3/12 lg:mx-0 mx-auto p-4">
           <img src="./assets/images/icon-detailed-records.svg" />
        </div>
        <h1 class="text-xl font-semibold poppins pb-3">Detailed Records</h1>
        <p class="advstats poppins">Gain insights into who is clicking your links. Knowing when and where 
          people engage with your content helps inform better decisions.
        </p>
      </div>
      
      <div class=" bg-white sm:h-64 h-72 lg:w-4/12 w-full mx-auto sm:px-8 px-2 text-center pb-20 pt-16 rounded mt-20">
        <div class="-mt-24 mb-10 rounded-full dark-blue w-3/12 lg:mx-0 mx-auto p-4">
           <img src="./assets/images/icon-fully-customizable.svg" />
        </div>
        <h1 class="text-xl font-semibold poppins pb-3">Fully Customizable</h1>
        <p class="advstats poppins">Improve brand awareness and content discoverability through customizable 
          links, supercharging audience engagement.
        </p>
      </div>
      
      </div>
      <!--end of flex--->
       
    </div>

  </section>

  <section class="relative w-full h-72 dark-blue border-black lexo">
          <div class="text-center pt-24">
            <h1 class="sm:text-4xl text-3xl tracking-wide font-bold text-white">Boost your links today</h1>
             <Button class="mt-6 cursor-pointer px-8 py-3 font-semibold subito poppins" text="Get Started" color="hsl(180, 66%, 49%)" textcolor="white"/>
          </div>
        <img class="sm:block hidden zufiii absolute top-0 left-0 w-full h-72" src="./assets/images/bg-boost-desktop.svg" />
        <img class="sm:hidden block zufiii absolute top-0 left-0 w-full h-72" src="./assets/images/bg-boost-mobile.svg" />
  </section>
  
  <footer class="w-full borontu pb-16">
    <section class="lg:w-9/12 w-11/12 gap-10 pt-16 mx-auto flex md:flex-row flex-col text-center justify-between items-start">

      <div class="logoi sm:text-3xl text-4xl sm:mx-left mx-auto">
        Shortly
      </div>

      <div class="poppins sm:mx-left mx-auto">
        <h1 class="font-bold sm:text-base text-2xl text-white pb-5">Features</h1>
        <p class="foot text-white">Link Shortening</p>
        <p class="foot sm:py-6 py-3 text-white">Branded Links</p>
        <p class="foot text-white">Analytics</p>
      </div>
    
      <div class="poppins sm:mx-left mx-auto">
        <h1 class="font-bold sm:text-base text-2xl text-white pb-5">Resources</h1>
        <p class="foot text-white">Blog</p>
        <p class="foot sm:py-6 py-3 text-white">  Developers</p>
        <p class="foot text-white">Support</p>
      </div>
    
      <div class="poppins sm:mx-left mx-auto">
        <h1 class="font-bold sm:text-base text-2xl text-white pb-5">Company</h1>
        <p class="foot text-white">About</p>
        <p class="foot sm:py-6 py-3 text-white">Our Team</p>
        <p class="foot pb-6 text-white">Careers</p>
        <p class="foot text-white">Contact</p>
      </div>
    
      <div class="flex justify-between gap-6 items-start sm:mx-left mx-auto">
       <img class="foot" src="./assets/images/icon-facebook.svg" />
       <img class="foot" src="./assets/images/icon-twitter.svg" />
       <img class="foot" src="./assets/images/icon-pinterest.svg" />
       <img class="foot" src="./assets/images/icon-instagram.svg" />
      </div>
    
    </section>
  </footer>
  <audio id="beep">
        <source src="water-droplet-drip.mp3" type="audio/mp3">
      </audio>
  
</template>

<script>
import Header from './components/Header.vue'
import Showcase from './components/Showcase.vue'
import Button from './components/Button.vue'

export default {
  name: 'App',

  data() {
    return {
      formus: '',
      inputError: '',
      full_short_link:'',
      block: false,
      copy:false,
      load:false,
      
    }
  },

  components: {
   Header,
   Showcase,
   Button,
  
  },

  methods: {
    enactUrl() {
       document.getElementById("beep").play();
      this.inputError = this.formus.length > 1 ? '' : 'Please add a link'
      this.load = this.formus.length > 1 ? true : false

        fetch(`https://api.shrtco.de/v2/shorten?url=` + this.formus) 
        .then((res) => {
            return res.json();
        })
        .then((data) => {
          console.log(data)
            this.full_short_link = data.result.full_short_link
       
        })
        
        .finally(() => {
          this.block = true
          this.load = false;
        
        })

           .catch((err) => {
            this.inputError = "unable to fetch short link; try again"
            this.block = false
        })
        
    //otimando
    },

       copyUp(e) {
         e.preventDefault();
        this.copy = !this.copy;
        var inputc = document.body.appendChild(document.createElement("input"));
        inputc.value = this.full_short_link; inputc.focus();inputc.select();document.execCommand('copy');inputc.parentNode.removeChild(inputc);

    }


  }
}
</script>

<style>
.poppins{
  font-family: 'Poppins', sans-serif;
}

.dark-violet{
  background: hsl(255, 11%, 22%)
}
.dark-blue{
  background: hsl(257, 27%, 26%)
}
.mputa{
  z-index:999;
}

.lexo{
  z-index: -2;
}

.enactus{
  z-index:1;
} 


.zufi{
  z-index: -99;
}

.zufiii{
  z-index: -99;
}
.subito{
  background: hsl(180, 66%, 49%);
  color:white;
  cursor: pointer;
  font-size: 18px;
}
.subito:focus{ outline:none;}.subito:hover{transform:scale(0.98)}

.grayhsll {
    background:hsla(258, 29%, 64%, 0.116)
}

.grayh3{
        color:hsl(249, 3%, 59%);
        font:18px;
}
.advstats{
        color:hsl(249, 3%, 59%);
        font:12px;
        font-weight:500;
}
.borontu{
  background: hsl(260, 8%, 14%);
}
.logoi{
    font-weight:700;
    color:aliceblue;
}
.foot:hover{
  color: hsl(180, 66%, 49%);
  cursor: pointer;
}
.lagon{
  color: hsl(180, 66%, 49%);
  cursor: pointer;
}

.adjustive{
  margin-bottom: -800px;
}

</style>
