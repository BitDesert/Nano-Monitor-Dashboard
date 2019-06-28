<template>
        <mdb-col sm="4">
  <mdb-card>
    <mdb-card-body>
      <mdb-card-title>{{ monitor.nanoNodeName }}</mdb-card-title>
      <hr>
      <p class="font-small grey-dark-text mb-0">{{ monitor.version }}</p>
    </mdb-card-body>
    <mdb-card-footer color="mdb-color" class="lighten-3 p-0 text-center">
      <ul class="list-unstyled list-inline font-small mt-3">
        <li class="list-inline-item pr-2 white-text">
          <mdb-icon icon="th" />
          {{ monitor.currentBlock }}
        </li>
        <li class="list-inline-item pr-2">
          <a href="#" class="white-text">
            <mdb-icon icon="th-large" />
            {{ monitor.uncheckedBlocks }}
          </a>
        </li>
        <li class="list-inline-item pr-2">
          <a href="#" class="white-text">
            <mdb-icon icon="network-wired" />
            {{ monitor.numPeers }}
          </a>
        </li>
      </ul>
    </mdb-card-footer>
  </mdb-card>
        </mdb-col>
</template>

<script>
import axios from "axios";

import {
  mdbContainer,
  mdbRow,
  mdbCol,
  mdbCard,
  mdbCardImage,
  mdbCardHeader,
  mdbCardBody,
  mdbCardTitle,
  mdbCardText,
  mdbCardFooter,
  mdbCardUp,
  mdbCardAvatar,
  mdbCardGroup,
  mdbBtn,
  mdbView,
  mdbMask,
  mdbIcon
} from "mdbvue";

export default {
  name: "CardProPage",
  props: ['url'],
  components: {
    mdbContainer,
    mdbRow,
    mdbCol,
    mdbCard,
    mdbCardImage,
    mdbCardHeader,
    mdbCardBody,
    mdbCardTitle,
    mdbCardText,
    mdbCardFooter,
    mdbCardUp,
    mdbCardAvatar,
    mdbCardGroup,
    mdbBtn,
    mdbView,
    mdbMask,
    mdbIcon
  },
  data() {
    return {
      monitor: {
        nanoNodeName: null,
        currentBlock: null,
        uncheckedBlocks: null,
        version: null,
        numPeers: null
      }
    };
  },
  mounted() {
    axios.get(this.url)
    .then(response => (this.monitor = response.data))
    .catch(error => (console.error(error)));
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
