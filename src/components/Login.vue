<script setup>
import axios from "axios";
import { ref } from "vue";
import { toast } from "vue3-toastify";
import "vue3-toastify/dist/index.css";
import Multiselect from "@vueform/multiselect";
import "@vueform/multiselect/themes/default.css";
import { vMaska } from "maska";

const text = ref("");
const phone = ref("+998");
const value = ref(null);
const value1 = ref(null);
const lessons = ref([
  "IT kurslar",
  "Matematika",
  "Ingliz tili",
  "Arab tili",
  "Rus tili",
  "Arab tili kids",
  "IELST",
  "Turk tili",
  "Kimyo-Biologiya",
  "Maktabgacha tayyo'rlov darslari",
  "Почемучка",
  "Mental arifmetika",
]);
const times = ref(["08:00-14:00", "14:00-18:00", "18:00-21:00"]);

const handleForm = () => {
  axios.post(
    "https://api.telegram.org/bot6312458538:AAEntEagx0B-xJmmK8hluU9g82M5xu6tnJI/sendMessage",
    {
      chat_id: -1001989077847,
      text: `<b>Ismi:</b> ${text.value}\n<b>Telofon Raqami:</b> ${phone.value}\n<b>Tanlagan Fani:</b> ${value.value}\n<b>Tanlagan Vaqti:</b> ${value1.value}`,
      parse_mode: "HTML",
    }
  );

  text.value = undefined;
  phone.value = "+998";
  value.value = undefined;
  value1.value = undefined;

  toast.success("Xabaringiz yuborildi tez orada siz bilan bo'g'lanishadi.", {
    autoClose: 5000,
  });
};
</script>

<template>
  <div
    class="w-full mx-auto max-w-7xl px-5 sm:px-8 md:px-14 lg:px-5"
    id="login"
  >
    <div class="mt-10 w-full flex mx-auto lg:mx-0">
      <div
        class="flex sm:flex-row flex-col gap-5 w-full lg:h-[400px] sm:h-full h-[600px]"
      >
        <form
          @submit.prevent="handleForm"
          class="py-1 pl-6 w-full flex-col pr-6 flex gap-3 items-center text-heading-3 shadow-lg shadow-box-shadow border border-box-border bg-box-bg rounded-lg ease-linear focus-within:bg-body focus-within:border-primary"
        >
          <h1
            class="mt-10 text-2xl/tight text-center sm:text-4xl/tight md:text-4xl/tight xl:text-5xl/tight font-bold text-heading-1"
          >
            O’zbekistondagi Sifatli Ta’lim markazi!
          </h1>
          <p class="md:text-lg text-heading-3 text-center">
            O'quv markazimizga siz ham qo’shiling va biz bilan yuqori
            natijalarga erishing!
          </p>
          <div class="flex lg:flex-row flex-col gap-6 mt-5 sm:w-[80%] w-[100%]">
            <div class="flex items-center sm:flex-row gap-4 w-full">
              <div
                class="py-1 pl-6 w-full pr-1 flex gap-3 items-center text-heading-3 shadow-lg shadow-box-shadow border border-box-border bg-box-bg rounded-full ease-linear focus-within:bg-body focus-within:border-primary"
              >
                <span class="min-w-max pr-2 border-r border-box-border">
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    width="20"
                    fill="none"
                    viewBox="0 0 16 16"
                    stroke-width="1.5"
                    stroke="currentColor"
                    class="w-5 h-5 opacity-100 dark:text-white text-black"
                  >
                    <path
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      d="M8 8a3 3 0 1 0 0-6 3 3 0 0 0 0 6zm2-3a2 2 0 1 1-4 0 2 2 0 0 1 4 0zm4 8c0 1-1 1-1 1H3s-1 0-1-1 1-4 6-4 6 3 6 4zm-1-.004c-.001-.246-.154-.986-.832-1.664C11.516 10.68 10.289 10 8 10c-2.29 0-3.516.68-4.168 1.332-.678.678-.83 1.418-.832 1.664h10z"
                    ></path>
                  </svg>
                </span>

                <input
                  type="text"
                  id="text"
                  v-model="text"
                  autocomplete="off"
                  required
                  placeholder="Ismingiz"
                  class="w-full py-3 outline-none rounded-full bg-box-bg pl-2"
                />
              </div>
            </div>

            <div class="flex items-center sm:flex-row gap-4 w-full">
              <div
                class="py-1 pl-6 w-full pr-1 flex gap-3 items-center text-heading-3 shadow-lg shadow-box-shadow border border-box-border bg-box-bg rounded-full ease-linear focus-within:bg-body focus-within:border-primary"
              >
                <span class="min-w-max pr-2 border-r border-box-border">
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    width="20"
                    fill="none"
                    viewBox="0 0 16 16"
                    stroke-width="1.5"
                    stroke="currentColor"
                    class="w-5 h-5 opacity-100 dark:text-white text-black"
                  >
                    <path
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      d="M3.654 1.328a.678.678 0 0 0-1.015-.063L1.605 2.3c-.483.484-.661 1.169-.45 1.77a17.568 17.568 0 0 0 4.168 6.608 17.569 17.569 0 0 0 6.608 4.168c.601.211 1.286.033 1.77-.45l1.034-1.034a.678.678 0 0 0-.063-1.015l-2.307-1.794a.678.678 0 0 0-.58-.122l-2.19.547a1.745 1.745 0 0 1-1.657-.459L5.482 8.062a1.745 1.745 0 0 1-.46-1.657l.548-2.19a.678.678 0 0 0-.122-.58L3.654 1.328zM1.884.511a1.745 1.745 0 0 1 2.612.163L6.29 2.98c.329.423.445.974.315 1.494l-.547 2.19a.678.678 0 0 0 .178.643l2.457 2.457a.678.678 0 0 0 .644.178l2.189-.547a1.745 1.745 0 0 1 1.494.315l2.306 1.794c.829.645.905 1.87.163 2.611l-1.034 1.034c-.74.74-1.846 1.065-2.877.702a18.634 18.634 0 0 1-7.01-4.42 18.634 18.634 0 0 1-4.42-7.009c-.362-1.03-.037-2.137.703-2.877L1.885.511z"
                    ></path>
                  </svg>
                </span>

                <input
                  type="phone"
                  name="phone"
                  required
                  autocomplete="off"
                  v-maska
                  data-maska="+998 (##) ###-##-##"
                  v-model="phone"
                  id="phone"
                  placeholder="Telefon raqamingiz"
                  class="w-full py-3 outline-none bg-box-bg rounded-full pl-2"
                />
              </div>
            </div>

            <div class="flex items-center sm:flex-row gap-4 w-full">
              <div
                class="py-1 pl-6 w-full pr-1 flex gap-3 items-center text-heading-3 shadow-lg shadow-box-shadow border border-box-border bg-box-bg rounded-full ease-linear focus-within:bg-body focus-within:border-primary"
              >
                <span class="min-w-max pr-2 border-r border-box-border">
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    width="20"
                    fill="none"
                    viewBox="0 0 16 16"
                    stroke-width="1.5"
                    stroke="currentColor"
                    class="w-5 h-5 opacity-100 dark:text-white text-black"
                  >
                    <path
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      d="M1 2.828c.885-.37 2.154-.769 3.388-.893 1.33-.134 2.458.063 3.112.752v9.746c-.935-.53-2.12-.603-3.213-.493-1.18.12-2.37.461-3.287.811V2.828zm7.5-.141c.654-.689 1.782-.886 3.112-.752 1.234.124 2.503.523 3.388.893v9.923c-.918-.35-2.107-.692-3.287-.81-1.094-.111-2.278-.039-3.213.492V2.687zM8 1.783C7.015.936 5.587.81 4.287.94c-1.514.153-3.042.672-3.994 1.105A.5.5 0 0 0 0 2.5v11a.5.5 0 0 0 .707.455c.882-.4 2.303-.881 3.68-1.02 1.409-.142 2.59.087 3.223.877a.5.5 0 0 0 .78 0c.633-.79 1.814-1.019 3.222-.877 1.378.139 2.8.62 3.681 1.02A.5.5 0 0 0 16 13.5v-11a.5.5 0 0 0-.293-.455c-.952-.433-2.48-.952-3.994-1.105C10.413.809 8.985.936 8 1.783z"
                    ></path>
                  </svg>
                </span>

                <Multiselect
                  placeholder="Fanlar"
                  required
                  v-model="value"
                  :options="lessons"
                  class="whitespace-nowrap bg-box-bg dark:text-white text-black h-full rounded-full w-[100%] z-50 py-1 bg-none border-none"
                />
              </div>
            </div>

            <div class="flex items-center sm:flex-row gap-4 w-full">
              <div
                class="py-1 pl-6 w-full pr-1 flex gap-3 items-center text-heading-3 shadow-lg shadow-box-shadow border border-box-border bg-box-bg rounded-full ease-linear focus-within:bg-body focus-within:border-primary"
              >
                <span class="min-w-max pr-2 border-r border-box-border">
                  <svg
                    width="20"
                    viewBox="0 0 24 24"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                    stroke="#f7f2f2"
                  >
                    <path
                      d="M23 12C23 18.0751 18.0751 23 12 23C5.92487 23 1 18.0751 1 12C1 5.92487 5.92487 1 12 1C18.0751 1 23 5.92487 23 12ZM3.00683 12C3.00683 16.9668 7.03321 20.9932 12 20.9932C16.9668 20.9932 20.9932 16.9668 20.9932 12C20.9932 7.03321 16.9668 3.00683 12 3.00683C7.03321 3.00683 3.00683 7.03321 3.00683 12Z"
                      fill="#e3e3e3"
                    ></path>
                    <path
                      d="M12 5C11.4477 5 11 5.44771 11 6V12.4667C11 12.4667 11 12.7274 11.1267 12.9235C11.2115 13.0898 11.3437 13.2343 11.5174 13.3346L16.1372 16.0019C16.6155 16.278 17.2271 16.1141 17.5032 15.6358C17.7793 15.1575 17.6155 14.5459 17.1372 14.2698L13 11.8812V6C13 5.44772 12.5523 5 12 5Z"
                      fill="#e3e3e3"
                    ></path>
                  </svg>
                </span>

                <Multiselect
                  placeholder="Qulay vaqt"
                  required
                  v-model="value1"
                  :options="times"
                  class="whitespace-nowrap bg-box-bg dark:text-white text-black h-full rounded-full w-[100%] z-40 py-1 bg-none border-none"
                />
              </div>
            </div>
          </div>
          <button
            type="submit"
            class="px-6 py-3 mt-10 mb-5 w-[60%] sm:w-[35%] md:w-[25%] flex justify-center rounded-full bg-[#1d4ed8] outline-none overflow-hidden border duration-300 ease-linear after:absolute after:inset-x-0 after:aspect-square after:scale-0 after:opacity-70 after:origin-center after:duration-300 after:ease-linear after:rounded-full after:top-0 after:left-0 hover:after:opacity-100 hover:after:scale-[2.5] border-transparent relative after:bg-[#43e20e] hover:border-[#43e20e]"
          >
            <span class="flex relative z-[5] text-white"> Yuborish </span>
            <!-- <span class="flex sm:hidden relative z-[5]">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke-width="1.5"
                stroke="currentColor"
                class="w-5 h-5"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  d="M6 12L3.269 3.126A59.768 59.768 0 0121.485 12 59.77 59.77 0 013.27 20.876L5.999 12zm0 0h7.5"
                ></path>
              </svg>
            </span> -->
          </button>
        </form>
      </div>
    </div>
  </div>
</template>

<style>
.multiselect {
  background: none !important;
  border-radius: inherit !important;
  z-index: 100% !important;
  border: none !important;
}
.multiselect .multiselect-dropdown {
  background-color: rgb(var(--color-box));
  border-radius: 8px !important ;
  border: transparent !important;
  margin-top: 5rem !important;
  border: none !important;
  /* top: 30px; */
  bottom: -10px;
  height: 10rem;
}

.multiselect .multiselect-dropdown::-webkit-scrollbar {
  width: 0;
}
.multiselect .multiselect-fake-input {
  background: transparent !important;
  border-radius: 8px !important;
  border: none !important;
  z-index: 100% !important;
}
input:focus {
  background-color: none !important;
  -webkit-appearance: none;
  outline: none !important;
}

.is-active:focus {
  background-color: none !important;
  -webkit-appearance: none;
  outline: none !important;
}
/* .multiselect:focus {
  background-color: none !important;
  -webkit-appearance: none;
  outline: none !important;
}
.multiselect .multiselect-dropdown:focus {
  background-color: none !important;
  -webkit-appearance: none;
  outline: none !important;
}
.multiselect .multiselect-dropdown::-webkit-scrollbar:focus {
  background-color: none !important;
  -webkit-appearance: none;
  outline: none !important;
}
.multiselect .multiselect-fake-input:focus {
  background-color: none !important;
  -webkit-appearance: none;
  outline: none !important;
} */
</style>
