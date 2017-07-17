<template>
  <div class="natofier">
    <input type="text" v-model="sourceText" class="form-control" :placeholder="sourcePlaceholder">
    <div v-if="natofiedText" class="panel panel-default">
      <div class="panel-heading">
        <h3 class="panel-title">Natofied</h3>
      </div>
      <div class="panel-body">{{ natofiedText }}</div>
    </div>
    <div v-if="morseText" class="panel panel-default">
      <div class="panel-heading">
        <h3 class="panel-title">Morse</h3>
      </div>
      <div class="panel-body">{{ morseText }}</div>
    </div>
  </div>
</template>

<script>
  import encodify from 'encodify';

  export default {
    name: 'Natofier',
    data: () => ({
      sourceText: '',
      sourcePlaceholder: 'type some words',
    }),
    computed: {
      natofiedText() {
        return encodify.toNATOCode(this.sourceText);
      },
      morseText() {
        return encodify.toMorseCode(this.sourceText);
      },
    },
  };
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h1, h2 {
    font-weight: normal;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }

  li {
    display: inline-block;
    margin: 0 10px;
  }

  a {
    color: #42b983;
  }
</style>
