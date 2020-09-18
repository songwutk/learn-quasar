<!-- ไฟล์ pages/Index.vue -->

<template>
  <!-- ส่วนแสดง -->
  <q-page padding>
    <input v-model="message" @keyup="handleKeyUp" />
    <!-- แค่ใส่ input ก็ได้ input box แล้ว พอใส่ v-model มันก็จะผูก field เข้ากับ message ให้เอง ต่อด้วย @keyup ให้ผูก method handleKeyUp -->
    <button @click="clearMessage">Clear</button>
    <!-- ใส่ button ได้ปุ่ม ถ้าใส่ @click ให้เรียก method clearMessage -->
    <h5>{{ message }}</h5>
    <!-- แสดงค่า message -->
  </q-page>
</template>

<!-- ส่วน script -->
<script>
export default {
  data() {
    return {
      message: "I love Vue.js ", // นิยามค่า I love vue.js ลงในตัวแปร message
    };
  },
  methods: {
    clearMessage() {
      this.message = ""; // ล้างค่าตัวแปร message
    },
    handleKeyUp(e) {
      // จับค่าคีย์บอร์ดที่กด ลงในตัวแปร e
      console.log(e); // log ตัวแปรใน console
      if (e.keyCode == 27) {
        // รหัส ascii 27 คือปุ่ม esc
        this.clearMessage(); // เรียก method clearMessage
      } else if (e.keyCode == 13) {
        // รหัส ascii 13 คือปุ่ม enter
        this.alertMessage(); // เรียก method alertMessage
      }
    },
    alertMessage() {
      alert(this.message); // ขึ้น Dialog alert ด้วยข้อความใน ตัวแปร  message
    },
  },
};
</script>
