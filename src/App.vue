<template>
  <div v-text="name"></div>
  <div v-html="lastname"></div>
  <div v-html="download"></div>
  <div v-bind:id="headingId">Head</div>
  <button v-bind:disabled="isDisabled">Connect</button>
  <h2 class="underline">GO GO GO</h2>
  <h2 class="underline" v-bind:class="status">*Status*</h2>
<h2 v-bind:class="isPromoted && 'promoted'">Promoted Movie</h2>
<h2 v-bind:class="isSoldout ?'sold-out' : 'new'">Soldout ? Movie(red=out/green=yet)</h2>
<h2 v-bind:class="['new','promoted']">Newly Promotion Movie</h2>
<h2 v-bind:class="[isPromoted && 'promoted', isSoldout ? 'sold-out' : 'new']">Array Condition movie(red=not/green=avaraible)</h2>
<h2 v-bind:class="{
  promoted: isPromoted,
  new: !isSoldout,
  'sold-out': isSoldout
}">Object conditional movie</h2>

<h2 v-bind:style="{
color: highlightColor,
fontSize: headerSize + 'px',
padding: '10x'
}">Inline Stlye</h2>

<h2 v-bind:style="headerStyleOpject">Stlye Object</h2>

<h2 v-bind:style="[baseStyleOpject, successStyleOpject]">Success Stlye</h2>

</template>

<script>


export default {
  name: 'App',
  data() {
    return {
      name: "Supachai",
      lastname: "<b>Sakupan</b>",
      download: '<a href="#" onclick="alert(\'You have been downloading\')">Download</a>',
      headingId: 'heading',
      isDisabled: false,
      status: 'finish',
      isPromoted: true,
      isSoldout: false,
      highlightColor: 'orange',
      headerSize: 40,
      headerStyleOpject: {
        color: 'orange',
        fontSize: '50px',
        padding: '10px'
      },
      baseStyleOpject: {
        fontSize: '50px',
        padding: '10px'
      },
      successStyleOpject: {
        color: 'green',
        backgroundColor: 'lightgreen',
        border: '1px soild green',
        padding: '20px'
      }
    };
  }
  
}
</script>

<style>
#app {
  font-family: 'Agdasima', sans-serif;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.underline {
text-decoration: underline;
}

.promoted {
  font-family:'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
  font-style: italic;
  text-decoration: underline;
}

.new {
  color: olivedrab;
}

.sold-out {
  color: red;
}
</style>
