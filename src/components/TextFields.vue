<template>
<!-- 이것도 v-form이긴 하네...? -->
  <v-form>
    <v-container>
      <v-row>
        <v-col cols="12">
          <v-text-field
            v-model="message"
            :append-icon="marker ? 'mdi-map-marker' : 'mdi-map-marker-off'"
            :append-outer-icon="message ? 'mdi-send' : 'mdi-microphone'"
            :prepend-icon="icon"
            filled
            clear-icon="mdi-close-circle"
            clearable
            label="Message"
            type="text"
            @click:append="toggleMarker"
            @click:append-outer="sendMessage"
            @click:prepend="changeIcon"
            @click:clear="clearMessage"
          ></v-text-field>
		  <!-- 
			v-model="message"
				-> 메세지를 보고있는데... 이게 있어야 append-outer-icon이 의미가 있는 것.
            :append-icon="marker ? 'mdi-map-marker' : 'mdi-map-marker-off'"
				-> append한 아이콘이 true ? true : false
            :append-outer-icon="message ? 'mdi-send' : 'mdi-microphone'"
				-> text-fields 밖의 아이콘을 누를 때(보내기), 메세지가 있으면 ? true : false
            :prepend-icon="icon"
				-> text-fields 앞에 아이콘 데이터 icons배열 넣어줌.
            filled
				-> field 색깔 채우기 (디자인)
            clear-icon="mdi-close-circle"
				-> 없으면 기본, 기본 말고 다른 디자인을 적어 준 것.
            clearable
				-> 메세지가 있을 때, 없애주는 것.
            label="Message"
				-> 라벨
            type="text"
            @click:append="toggleMarker"
				-> 지도모양 아이콘 클릭 시 true / false 상태 변경, false 시 아이콘에 X 자 표시됨.
            @click:append-outer="sendMessage"
				-> 메세지 보내주기 : this.resetIcon()와 this.clearMessage() 함수 실행
				   여기서 text-field에 적은 메세지 어디로 보내줘야 하는거 같은데.............
            @click:prepend="changeIcon"
				-> 앞에 감정표현 하는 아이콘 변화
            @click:clear="clearMessage"
				-> 버튼 눌러서 메세지 지울 때, 메세지 지워 주는 것.
		   -->
        </v-col>
      </v-row>
    </v-container>
  </v-form>
</template>

<script>
  export default {
    data: () => ({
      password: 'Password',
      show: false,
      message: 'Hey!',
      marker: true,
      iconIndex: 0,
      icons: [
        'mdi-emoticon',
        'mdi-emoticon-cool',
        'mdi-emoticon-dead',
        'mdi-emoticon-excited',
        'mdi-emoticon-happy',
        'mdi-emoticon-neutral',
        'mdi-emoticon-sad',
        'mdi-emoticon-tongue',
      ],
    }),

    computed: {
      icon () {
        return this.icons[this.iconIndex]
      },
    },

    // mounted() {
    //   console.log('텍스트필드 ~~~~~~~~~~~~~~~~~~~~');
    // },

    methods: {
      toggleMarker () {
        this.marker = !this.marker
      },
      sendMessage () {
        this.resetIcon()
        this.clearMessage()
      },
      clearMessage () {
        this.message = ''
      },
      resetIcon () {
        this.iconIndex = 0
      },
      changeIcon () {
        this.iconIndex === this.icons.length - 1 //마지막 아이콘이면 ~
          ? this.iconIndex = 0
          : this.iconIndex++
      },
    },

  }
</script>

<style>

</style>