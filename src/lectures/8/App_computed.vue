<template>
  <div>
    <h2>{{ teacher.name }}</h2>
    <h3>강의가 있습니까?</h3>
    <!-- <p>{{ teacher.lectures.length > 0 ? "있음" : "없음" }}</p> -->
    <p>{{ hasLecture }}</p>
    <p>{{ existLecture() }}</p>
    <p>{{ hasLecture }}</p>
    <p>{{ existLecture() }}</p>
    <button @click="counter++">{{ counter }}</button>
    <h2>name</h2>
    <p>{{ fullName }}</p>
  </div>
</template>

<script>
import { computed, reactive, ref } from "vue";

export default {
  setup() {
    const teacher = reactive({
      name: "짐코딩",
      lectures: ["HTML/CSS", "JavaScript", "Vue3"],
    });

    // 보관하고있다가 계산된 결과값 cash한 데이터를 돌려준다. => cash가 다시 계산되는 시점 : 반응형 데이터가 변경될 때
    // 성능면에서 엄청나게 유리하다.
    const hasLecture = computed(() => {
      console.log("computed");
      return teacher.lectures.length > 0 ? "있음" : "없음";
    });

    const existLecture = () => {
      console.log("method");
      return teacher.lectures.length > 0 ? "있음" : "없음";
    };

    const counter = ref(0);

    const firstName = ref("홍");
    const lastName = ref("길동");

    // computed readonly 사용하기
    // const fullName = computed(() => firstName.value + " " + lastName.value);
    // console.log("Console출력:", fullName.value);

    // computed를 쓰기가능한 함수로 사용하기.
    const fullName = computed({
      get() {
        return firstName.value + " " + lastName.value;
      },
      set(value) {
        [firstName.value, lastName.value] = value.split(" ");
      },
    });
    fullName.value = "짐 코딩";
    return {
      fullName,
      teacher,
      hasLecture,
      existLecture,
      counter,
    };
  },
};
</script>

<style></style>
