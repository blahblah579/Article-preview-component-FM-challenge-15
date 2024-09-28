<template>
  <v-container>
    <v-row class="main-row d-flex flex-column flex-sm-row justify-center my-10">
      <v-col cols="10" sm="4" class="left pa-0 d-flex">
        <img class="img" src="/src/assets/drawers.jpg" alt="" />
      </v-col>
      <v-col cols="10" sm="6" class="right px-0">
        <v-col cols="12" class="text1 px-8">
          Shift the overall look and feel by adding these wonderful touches to
          furniture in your home
        </v-col>

        <v-col cols="12" class="text2">
          Ever been in a room and felt like something was missing? Perhaps it
          felt slightly bare and uninviting. I've got some simple tips to help
          you make any room feel complete.
        </v-col>

        <v-col cols="12" v-if="isScreenLarge" class="lowest1 d-flex px-8">
          <v-col cols="9" class="d-flex align-center pa-0">
            <v-avatar>
              <v-img alt="" src="/src/assets/avatar-michelle.png"></v-img>
            </v-avatar>
            <v-col class="d-flex flex-column">
              <div class="name">Abhishek Negi</div>
              <div class="date">25 Sept 2024</div>
            </v-col>
          </v-col>
          <v-spacer></v-spacer>
          <v-col cols="3" class="pa-0 d-flex align-center justify-center">
            <v-btn
              flat
              @click="showRectangle = !showRectangle"
              size="small"
              class="btn"
              density="comfortable"
              icon="mdi-share"
            ></v-btn>

            <div
              v-if="showRectangle && isScreenLarge"
              class="chat-box-container d-flex justify-center"
            >
              <v-sheet class="chat-box d-flex align-center justify-center px-0">
                <v-col
                  class="d-flex links justify-space-around px-5 align-center"
                >
                  <div class="share">S H A R E</div>
                  <div>
                    <img
                      class="link"
                      src="/src/assets/icon-facebook.svg"
                      alt="Facebook"
                      @click="openLink('https://www.facebook.com')"
                    />
                  </div>
                  <div>
                    <img
                      class="link"
                      src="/src/assets/icon-twitter.svg"
                      alt=""
                      @click="openLink('https://www.x.com')"
                    />
                  </div>
                  <div>
                    <img
                      class="link"
                      src="/src/assets/icon-pinterest.svg"
                      alt=""
                      @click="openLink('https://www.pinterest.com')"
                    />
                  </div>
                </v-col>
              </v-sheet>
              <div class="triangle"></div>
            </div>
          </v-col>
        </v-col>

        <v-col
          cols="12"
          v-if="!isScreenLarge && !showRectangle"
          class="lowest2 d-flex px-10 align-center"
          :class="{
            'lowest2-dark': showRectangle,
            'lowest2-light': !showRectangle,
          }"
        >
          <v-col cols="9" class="d-flex align-center pa-0">
            <v-avatar>
              <v-img alt="John" src="/src/assets/avatar-michelle.png"></v-img>
            </v-avatar>
            <v-col class="d-flex flex-column">
              <div class="name">Abhishek Negi</div>
              <div class="date">25 Sept 2024</div>
            </v-col>
          </v-col>
          <v-spacer></v-spacer>
          <v-col cols="3" class="d-flex justify-center mb-2 ml-6 pl-2">
            <v-btn
              flat
              @click="showRectangle = !showRectangle"
              size="small"
              class="btn"
              density="comfortable"
              icon="mdi-share"
            ></v-btn>

            <div
              v-if="showRectangle && isScreenLarge"
              class="chat-box-container d-flex justify-center"
            >
              <v-sheet class="chat-box d-flex align-center justify-center px-0">
                <v-col
                  class="d-flex links justify-space-around px-5 align-center"
                >
                  <div class="share">S H A R E</div>
                  <div>
                    <img
                      class="link"
                      src="/src/assets/icon-facebook.svg"
                      alt=""
                      @click="openLink('https://www.facebook.com')"
                    />
                  </div>
                  <div>
                    <img
                      class="link"
                      src="/src/assets/icon-twitter.svg"
                      alt=""
                      @click="openLink('https://www.x.com')"
                    />
                  </div>
                  <div>
                    <img
                      class="link"
                      src="/src/assets/icon-pinterest.svg"
                      alt=""
                      @click="openLink('https://www.pinterest.com')"
                    />
                  </div>
                </v-col>
              </v-sheet>
              <div class="triangle"></div>
            </div>
          </v-col>
        </v-col>

        <v-col
          cols="12"
          v-if="!isScreenLarge && showRectangle"
          class="lowest2 d-flex"
          :class="{
            'lowest2-dark': showRectangle,
            'lowest2-light': !showRectangle,
          }"
        >
          <v-col cols="9" class="d-flex align-center pa-0">
            <v-col class="d-flex links justify-space-around px-5 align-center">
              <div class="share">S H A R E</div>
              <div>
                <img
                  class="link"
                  src="/src/assets/icon-facebook.svg"
                  alt=""
                  @click="openLink('https://www.facebook.com')"
                />
              </div>
              <div>
                <img
                  class="link"
                  src="/src/assets/icon-twitter.svg"
                  alt=""
                  @click="openLink('https://www.x.com')"
                />
              </div>
              <div>
                <img
                  class="link"
                  src="/src/assets/icon-pinterest.svg"
                  alt=""
                  @click="openLink('https://www.pinterest.com')"
                />
              </div>
            </v-col>
          </v-col>
          <v-col cols="3" class="d-flex justify-center mb-2">
            <v-btn
              flat
              @click="showRectangle = !showRectangle"
              size="small"
              class="btn"
              density="comfortable"
              icon="mdi-share"
            ></v-btn>
          </v-col>
        </v-col>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
import { ref, computed, onMounted, onUnmounted } from "vue";

// Variable to toggle the visibility of the chat box
const showRectangle = ref(false);

// Computed property to detect if the screen is large enough
const isScreenLarge = ref(window.innerWidth > 599.5);

// Function to update screen size dynamically
const updateScreenSize = () => {
  isScreenLarge.value = window.innerWidth > 599.5;
};

// Attach event listener to detect window resize
onMounted(() => {
  window.addEventListener("resize", updateScreenSize);
});

// Cleanup the event listener on component unmount
onUnmounted(() => {
  window.removeEventListener("resize", updateScreenSize);
});

const openLink = (url) => {
  window.open(url, "_blank");
};
</script>
  
  <style scoped>
@font-face {
  font-family: f1;
  src: url(/src/assets/Manrope-Regular.ttf);
}
@font-face {
  font-family: f2;
  src: url(/src/assets/Manrope-Bold.ttf);
}
@font-face {
  font-family: f3;
  src: url(/src/assets/Manrope-Light.ttf);
}
.share {
  font-family: f3;
  color: hsl(212, 23%, 69%);
  font-size: 13px;
  word-spacing: 2px;
}
.right {
  background-color: #fff;
}

.text1 {
  color: hsl(217, 19%, 35%);
  font-weight: bold;
  font-family: f1;
  padding-right: 35px;
  padding-left: 35px;
  padding-bottom: 0px;
  padding-top: 20px;
}
.text2 {
  color: hsl(214, 17%, 51%);
  font-size: 13px;
  padding-right: 55px;
  padding-left: 35px;
}
.name {
  font-family: f2;
  font-size: 12px;
  color: hsl(214, 17%, 51%);
}
.date {
  font-family: f1;
  font-size: 12px;
  color: hsl(214, 31%, 69%);
}
.btn {
  background-color: hsl(213, 44%, 95%);
  color: hsl(214, 16%, 51%);
  position: relative;
}
/* Container to hold the chat-box and the triangle */
.chat-box-container {
  position: absolute;
  top: 47%; /* Adjust this to keep the box above the button */
  left: 73.3%;
  transform: translateX(-50%);
  width: 230px; /* Fixed width as per design */
  z-index: 10;
  display: flex; /* Flex layout to handle content */
  justify-content: center;
}

/* Rectangle (chat-box) style */
.chat-box {
  width: 100%; /* Ensure the chat box takes the full container width */
  background-color: hsl(219, 19%, 35%);
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  font-size: 10px;
  font-weight: bold;
  position: relative;
  z-index: 11;
  padding: 8px 0;
}

/* Triangle style */
.triangle {
  position: absolute;
  top: 100%; /* Positioned directly under the chat box */
  left: 50%;
  transform: translateX(-50%);
  width: 0;
  height: 0;
  border-left: 10px solid transparent;
  border-right: 10px solid transparent;
  border-top: 10px solid hsl(219, 19%, 35%);
}

.link {
  cursor: pointer;
}
.img {
  width: 100%; /* Makes the image take up the full width of the container */
  height: 100%;
  object-fit: cover; /* Scales the image to cover the container */
  border-top-left-radius: 10px;
  border-bottom-left-radius: 10px;
}
.right {
  border-top-right-radius: 10px;
  border-bottom-right-radius: 10px;
}
.lowest2-dark {
  background-color: hsl(219, 19%, 35%);
}
.lowest2-light {
  background-color: hsl(0, 0%, 98%);
}

/* Responsive styling for smaller screens */
@media (max-width: 920px) {
  .chat-box-container {
    top: 47.6%; /* Adjust this to keep the box above the button */
    left: 82.4%;
  }
}
@media (max-width: 599.5px) {
  .chat-box-container {
    top: -140%; /* Adjust top value for smaller screens */
    width: 180px; /* Adjust width for smaller screens */
  }
  .img {
    object-fit: cover; /* Ensure the image covers the container */
    height: auto; /* Set height to auto to maintain aspect ratio */
    border-top-left-radius: 10px;
    border-bottom-left-radius: 0px;
    border-top-right-radius: 10px;
  }

  .right {
    background-color: #f9f9f9; /* Change background color for smaller screens */
    padding-right: 0px;
    padding-left: 0px;
    padding-bottom: 0px;
  }
  .lowest2 {
    border-bottom-left-radius: 10px;
    border-bottom-right-radius: 10px;
  }
  .main-row {
    align-items: center;
  }
  .text1 {
    color: hsl(217, 19%, 35%);
    font-weight: bold;
    font-family: f1;
    padding-right: 35px;
    padding-left: 35px;
    padding-bottom: 0px;
    padding-top: 20px;
  }
  .text2 {
    color: hsl(214, 17%, 51%);
    font-size: 13px;
    padding-right: 55px;
    padding-left: 35px;
  }
}
</style>
  