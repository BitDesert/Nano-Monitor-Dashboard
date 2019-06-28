<template>
  <div class="home">
    <mdb-container>
      <mdb-row>
        <Monitor
          v-for="(item, index) in monitors"
          v-bind:index="index"
          v-bind:key="item.url"
          :url="item.url"
        />
      </mdb-row>
    </mdb-container>
  </div>
</template>

<script>
// @ is an alias to /src
import Monitor from "@/components/Monitor.vue";

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
  name: "home",
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
    mdbIcon,
    Monitor
  },
  data() {
    return {
      monitors: [
        { url: "https://monitor-beta.mynano.ninja/api.php" },
        { url: "https://beta.nanoskynode.com/api.php" },
        { url: "https://benna.just-dmitry.ru/api.php" },
        //{ url: "https://b.repnode.org/api.php" },
        { url: "http://beta.nanode.cc/api.php" }
      ]
    };
  }
};
</script>
