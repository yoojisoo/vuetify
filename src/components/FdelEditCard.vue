<!--
	cardInfo: {
		title:       [],     //제목
		content:     [],     //출력할 내용
		index:       0,      //List index
		mainColor:   '',     //사용하는 색상
		css:         '',     //사용하는 css 폼 (font, font-size etc...)
		chip: {         
			text:    '',     //칩 value
			isColor: '',     //칩 색상이 있다면 -> main color 사용
		},
	},
-->
<template>
	<v-card>
		<v-card-title v-if="cardInfo.title">
			<span v-for="title in cardInfo.title" :key="title">
				카드타이틀 : {{ cardInfo.title }}
			</span> 
		</v-card-title>
		<v-card-text v-if="cardInfo.content">
			<span v-for="content in cardInfo.content" :key="content">
				카트콘텐트 : {{ cardInfo.content }}
			</span>
		</v-card-text>
		<!-- <v-card-subtitle>
			<p> {{ cardInfo.index }} </p>
			<p> {{ cardInfo.mainColor }} </p>
			<p> {{ cardInfo.chip.text }} </p>
			<p> {{ cardInfo.chip.isColor }} </p>
		</v-card-subtitle> -->
	</v-card>
</template>


<script>
export default {
	props: ['cardInfo'],
}
</script>

<style>

</style>