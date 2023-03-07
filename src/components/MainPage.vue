<template>
  <div class="main_container">
    <div class="otp_genrator_box">
      <div class="new_otp">
        {{ this.otp.length === 0 ? "generate otp" : this.otp }}
      </div>
      <button class="otp_generator_btn" @click="generateOtp">
        Generate Otp
      </button>
    </div>
    <div class="otp_verifier_box">
      <div class="new_otp">
        <input type="text" class="otpInput" v-model="verifyOtp" />
      </div>
      <button class="otp_generator_btn" id="otp_verifier" @click="checkOtp">
        Verify Otp
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return { otp: [], verifyOtp: "", otpSize: 7 };
  },
  methods: {
    generateOtp() {
      if (this.otp != null) {
        this.otp = "";
      }
      for (let i = 0; i < this.otpSize; i++) {
        this.otp += Math.floor(Math.random() * 10);
      }
      return this.otp;
    },
    checkOtp() {
      if (this.otp === this.verifyOtp) {
        alert("otp is verfied");
        this.verifyOtp = "";
      } else {
        alert("please check your otp ");
      }
    },
  },
};
</script>

<style>
.main_container {
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  border: 1px solid black;
  width: 100%;
  height: 100vh;
}
.otp_genrator_box {
  border: none;
  height: 35%;
  width: 22%;
  border-radius: 6px;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  background-color: whitesmoke;
  box-shadow: 0px 0px 10px 0px;
}
.new_otp {
  border: 1px solid black;
  height: 12%;
  width: 73%;
  display: flex;
  justify-content: center;
  align-items: center;
}
.otp_generator_btn {
  margin-top: 6%;
  height: 11%;
  border: 1px solid black;
  border-radius: 3px;
  color: white;
  background-color: royalblue;
  font-size: 15px;
  font-family: helvetica;
}
.otp_generator_btn:active {
  background-color: red;
  color: white;
}
.otp_verifier_box {
  border: none;
  height: 35%;
  width: 22%;
  border-radius: 6px;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  background-color: whitesmoke;
  box-shadow: 0px 0px 10px 0px;
}
.otpInput {
  border: none;
  width: 100%;
  height: 93%;
  overflow: hidden;
}
</style>
