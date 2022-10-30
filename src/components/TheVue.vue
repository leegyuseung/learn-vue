<template>
  <main>
    <div class="container py-4">
      <!-- @click="sayHello" -->
      <MyButton class="my-button" id="my-button" @click="sayHello"></MyButton>
      <LabelInput label="이름" data-id="id입니다." />
      <hr />
      <FancyButton>Click!!!<span style="color: red">@@@</span></FancyButton>
      <!-- <FancyButton v-slot="{ fancyMessage }">{{ fancyMessage }}</FancyButton> -->
      <FancyButton
        ><template v-slot="{ fancyMessage }">{{
          fancyMessage
        }}</template></FancyButton
      >

      <hr />
      <AppCard>
        <!-- v-on v-bind v-slot 은 동적으로 가능하다. -->
        <!-- <template #[slotArgs]> 제목입니다. </template> -->
        <!-- <template #default> 내용입니다. </template> -->
        <!-- 암시적으로 default 슬롯입니다.! -->
        <!-- <template #footer> 푸터입니다. </template> -->

        <template #default="{ childMessage, helloMessage }"
          >default입니다. {{ message }} {{ childMessage }}{{ helloMessage }}
        </template>
        <template #header="{ headerMessage }"
          >default입니다. {{ headerMessage }}
        </template>
        <template #footer="{ footerMessage }"
          >default입니다. {{ footerMessage }}
        </template>
      </AppCard>
      <AppCard>게시글입니다.</AppCard>
    </div>
  </main>
</template>

<script>
import { ref } from "vue";
import AppCard from "./AppCard.vue";
import FancyButton from "./FancyButton.vue";
import LabelInput from "./LabelInput.vue";
import MyButton from "./MyButton.vue";

export default {
  components: { MyButton, LabelInput, FancyButton, AppCard },
  setup() {
    const sayHello = () => {
      alert("안녕");
    };
    const slotArgs = ref("header");
    const message = ref("Hi");
    return { sayHello, slotArgs, message };
  },
};
</script>

<style></style>
