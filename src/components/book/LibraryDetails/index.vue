<template>
  <div class="library-details" v-if="loanHistory.length > 0">
    <v-tabs v-model="tab">
      <v-tab
        v-for="({ text, value }, index) in tabs"
        :key="index"
        :href="`#${value}`"
      >
        {{ text }}
      </v-tab>
      <v-tab-item value="check-in">
        <CheckIn :records="checkIn" />
      </v-tab-item>
      <v-tab-item value="check-out">
        <CheckOut :records="checkOut" />
      </v-tab-item>
    </v-tabs>
  </div>
</template>
<script>
import CheckIn from "./CheckIn";
import CheckOut from "./CheckOut";
export default {
  name: "LibraryDetails",
  components: {
    CheckIn,
    CheckOut
  },
  props: {
    loanHistory: Array
  },
  data: function() {
    return {
      tab: "",
      tabs: [
        {
          text: "Check In",
          value: "check-in"
        },
        {
          text: "Check Out",
          value: "check-out"
        }
      ],
      checkIn: [],
      checkOut: []
    };
  },
  mounted() {
    this.checkIn = this.loanHistory
      .filter(history => !!history.check_in)
      .map(history => history.check_in);
    this.checkOut = this.loanHistory
      .filter(history => !!history.check_out)
      .map(history => history.check_out);
  }
};
</script>
<style lang="scss" scoped></style>
