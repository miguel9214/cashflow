<template lang="">
    <header>
        <img class="logoHeader"
        @click="reload()"
        src="@/assets/logo.svg" alt="logo">
        <h1><span>Track</span>Cash</h1>
        <span></span>
    </header>
</template>
<script>
export default {
    methods:{
        reload(){
            location.reload();
        }

    }
    
}
</script>
<style>

header{
    display: flex;
  justify-content: space-around;
  align-items: center;
  width: 100vw;

}
.logoHeader, span{
    width: 48px;
}

h1 {
    font-size: 1.4rem;
  color: var(--brand-blue);
}
h1 span {
  color: var(--brand-green);
}
    
    
</style>