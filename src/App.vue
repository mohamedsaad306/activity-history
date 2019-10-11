<template>
  <div id="app">
   
    

<ul id="progress">
    <li v-for="(stage,index) in stages" v-bind:key="stage.name" :id="stage.name" :title="stage.title" v-on:click="StageSelected"  >
      <span>({{index+1}}) </span>
      {{stage.name}}

    </li>
    <!-- <li class="active">Step 2</li>
    <li>Step 3</li> -->
</ul>
  </div>
</template>
<script>
export default {
  data() {
    return {
      selectedIndex:-1, 
      stages: [
        { name: "Stage1 ", active: false  , isSelected : false , title : "Alt Message "},
        { name: "Stage2 ", active: true },
        { name: "Stage3 ", active: false },
        { name: "Stage4 ", active: false },
        { name: "Stage5 ", active: false },
        { name: "Stage6 ", active: false },
        { name: "Stage7 ", active: false },
        { name: "Stage8 ", active: false }
      ]
    };
  }, 
  methods:{
    StageSelected(arg,el){
      console.log('Selected this', this)
      console.log('Selected args ', arg)
      console.log('Selected el ', el)

    },
  }
};
</script>

<style> 
 

 
#progress {
    padding: 0;
    list-style-type: none;
    font-family: arial;
    font-size: 12px;
    clear: both;
    line-height: 1em;
    margin: 0 -1px;
    text-align: center;
}

#progress li:hover{
    background: #98ca9d;

}
 #progress li span{
   float: left;
 }

#progress li {
    float: left;
    padding: 10px 30px 10px 40px;
    background: #d4ead7;
    color: black;
    position: relative;
    border-top: 1px solid #d4ead7;
    border-bottom: 1px solid #d4ead7;
    width: 10%;
    margin: 3px;
    
}

#progress li:before {
    content: '';
    border-left: 16px solid #fff;
    border-top: 16px solid transparent;
    border-bottom: 16px solid transparent;
    position: absolute;
    top: 0;
    left: 0;
    
}
#progress li:hover:after {
    border-left-color: #98ca9d;

}
#progress li:after {
    content: '';
    border-left: 16px solid #d4ead7;
    border-top: 16px solid transparent;
    border-bottom: 16px solid transparent;
    position: absolute;
    top: 0;
    left: 100%;
    z-index: 20;
    
}

#progress li.active {
    background: #98ca9d;
}

#progress li.active:after {
    border-left-color: #98ca9d;
}
</style>
