<template>
  <div class="App">
    <DefaultHeader/>
    <div class="Contents">
      <p v-if="msg.length > 0">
        {{ msg }}
      </p>
      <p v-else>
        no text
      </p>
      <input type="text" v-model="msg">
      <button @click="clear()">clear</button>
    </div>
  </div>
</template>
<script>
import DefaultHeader from './components/DefaultHeader';

export default {
  components: {
    DefaultHeader,
  },
  data() {
    return {
      msg: 'input something.',
    };
  },
  methods: {
    clear() {
      this.msg = '';
    },
  },
  created() {
    const that = this;
    $.getJSON('http://www.geonames.org/postalCodeLookupJSON?postalcode=10504&country=US&callback=?', {}, (json) => {
      that.msg = json.postalcodes[0].adminName1;
    });
  },
};
</script>

<style>
html, body, div, span, applet, object, iframe,
h1, h2, h3, h4, h5, h6, p, blockquote, pre,
a, abbr, acronym, address, big, cite, code,
del, dfn, em, img, ins, kbd, q, s, samp,
small, strike, strong, sub, sup, tt, var,
b, u, i, center,
dl, dt, dd, ol, ul, li,
fieldset, form, label, legend,
table, caption, tbody, tfoot, thead, tr, th, td,
article, aside, canvas, details, embed,
figure, figcaption, footer, header, hgroup,
menu, nav, output, ruby, section, summary,
time, mark, audio, video {
  margin: 0;
  padding: 0;
  border: 0;
  font-size: 100%;
  font: inherit;
  vertical-align: baseline;
}
/* HTML5 display-role reset for older browsers */
article, aside, details, figcaption, figure,
footer, header, hgroup, menu, nav, section {
  display: block;
}
body {
  line-height: 1;
}
ol, ul {
  list-style: none;
}
blockquote, q {
  quotes: none;
}
blockquote:before, blockquote:after,
q:before, q:after {
  content: '';
  content: none;
}
table {
  border-collapse: collapse;
  border-spacing: 0;
}
.Contents {
  padding-top: 60px;
}
</style>
