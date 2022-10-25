<template>
  <div id="modifiers">
    <!-- capture를 먼저 실행한후 버블링 실행 -->
    <!-- <div @click.capture="clickDiv"> -->
    <!-- self는 클릭한 요소가 나 자신일때 이벤트를 실행한다.  -->
    <div @click.self="clickDiv">
      DIV 영역
      <p @click="clickP">
        <!-- 버블링 -->
        <!-- p 영역 <span @click.stop="clickSpan">span영역</span> -->
        p 영역 <span @click="clickSpan">span영역</span>
      </p>
    </div>
    <!-- 한 번만 실행한다. -->
    <button @click.once="clickDiv">once</button>
  </div>
  <!-- preventDefault : 기본기능막음 -->
  <a href="https://www.naver.com" @click.prevent="clickA">a 영역</a>
</template>

<script>
export default {
  setup() {
    const clickDiv = () => {
      console.log("clickDiv");
      // location.href = "https://naver.com";
    };
    const clickP = () => {
      console.log("clickP");
    };
    const clickSpan = () => {
      console.log("clickSpan");
      // alert("좋아요");
    };
    const clickA = () => {
      console.log("clickA");
      alert("어떤기능");
    };
    return { clickDiv, clickP, clickSpan, clickA };
  },
};
</script>

<style scoped>
#modifers div,
#modifiers p,
#modifiers span {
  padding: 40px;
}

#modifiers div {
  background-color: #ccc;
}

#modifiers p {
  background-color: #999;
}
#modifiers span {
  display: block;
  background-color: #666;
}
</style>
