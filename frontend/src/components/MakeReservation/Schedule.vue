<template>
  <div style="background-color: white;">
    <v-layout column>
      <div class="blank-4"></div>
      <v-flex>
        <img src="@/assets/makeReservation/make_schedule_guide.png">
      </v-flex>
      <div class="blank-4"></div>
      <div class="blank-4"></div>

      <v-flex ml-3 mr-3>
        <p class="tags">예약 일정 선택</p>
      </v-flex>

      <v-layout row ml-3 mr-3>
        <v-flex style="width:135px;">
          <v-select :items="items_date" label="날짜" solo flat></v-select>
        </v-flex>
        <v-spacer></v-spacer>
        <v-flex style="width:165px;">
          <v-select :items="items_time" label="시간대" solo flat></v-select>
        </v-flex>
      </v-layout>
      <div class="blank-4"></div>

      <v-layout mt-4 justify-center>
        <v-btn class="mainBtn" color="#1675fa" outline @click="pressNext">
          <div class="btnDiv">
            <p>다음</p>
          </div>
        </v-btn>
      </v-layout>
      <div class="blank-4"></div>
      <div class="blank-4"></div>
      <div class="blank-4"></div>
    </v-layout>
  </div>
</template>



<script>
export default {
  data: () => ({
    items_date: [
      "12/16(일)",
      "12/17(월)",
      "12/18(화)",
      "12/19(수)",
      "12/20(목)",
      "12/21(금)",
      "12/22(토)"
    ],
    items_time: [
      "오전 7:00-7:30",
      "오전 7:30-8:00",
      "오전 8:00-8:30",
      "오전 8:30-9:00",
      "오전 9:00-9:30",
      "오전 9:30-10:00",
      "오전 10:00-10:30",
      "오전 10:30-11:00",
      "오전 11:00-11:30",
      "오전 11:30-12:00"
    ]
  }),
  methods: {
    navigateTo(route) {
      this.$router.push(route);
    },
    pressNext() {
      this.navigateTo({ name: "make_select_nurse" });
    }
  }
};
</script>

<style scoped>
.blank-4 {
  height: 40px;
}
.v-text-field {
  border: 1px solid currentColor;
  border-color: #999999;
  height: 50px;
}
.v-textarea {
  border: 1px solid currentColor;
  border-color: #999999;
  height: 100px;
}
.tags {
  text-align: left;
}

p {
  font-size: 18px;
}
img {
  max-width: 100%;
  object-fit: cover;
}

.mainBtn {
  font-size: 17px;
  font-weight: bolder;

  padding-top: 10px;
  padding-left: 26px;
  padding-right: 26px;
  padding-bottom: 10px;

  height: 47px;
  width: 150px;
  border-radius: 13px;
  border-width: 2px;
}
.btnDiv {
  transform: translateX(5%);
}
</style>