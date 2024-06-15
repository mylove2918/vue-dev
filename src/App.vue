<script setup>
import { ref } from "vue";
const userAgent = navigator.userAgent;

let isActive = ref(false);

const toggleActive = () => {
  isActive.value = !isActive.value;
};
</script>

<template>
  <div class="inner-1440">
    <p class="tit">[User Agent 확인]</p>
    <div class="user-agent">
      <p>
        당신의 접속 디바이스 userAgent 정보를 확인하시고 싶으시면 button을
        클릭하세요.
      </p>
      <button @click="toggleActive">확인하기</button>
    </div>
    <p v-if="isActive" class="info-txt">
      당신의 userAgent 정보는
      <span class="fc-red fw-bold">{{ userAgent }}</span> 입니다.
    </p>
  </div>
</template>

<style scoped lang="scss">
* {
  list-style: none;
  text-decoration: none;
  margin: 0;
  padding: 0;
}

.fc-red {
  color: red;
}

.fw-bold {
  font-weight: 700;
}

.inner-1440 {
  max-width: 1440px;
  margin: 0 auto;
  padding-top: 30px;

  .tit {
    font-weight: 700;
  }
}

.user-agent {
  display: flex;
  padding: 10px 0;
  button {
    margin-left: 30px;
    padding: 0 5px;
  }
}
</style>
