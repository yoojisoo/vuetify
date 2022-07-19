<template>
    <v-container>
        <div class="home">
            <!-- <v-btn @click="start"></v-btn> -->
            <v-btn>
                Click Me
            </v-btn>
            
            <FdelEditCard :cardInfo="cardInfo"/>
            <breakpoints />
            <DataTable />
            <DateForm />
            <TextFields />
            <TextFieldsSubmit />
        </div>
    </v-container>
</template>

<script>
// @ is an alias to /src
import { FdelEditCard, Breakpoints, DataTable, DateForm, TextFields, TextFieldsSubmit } from '@/assets/importFile.js'
export default {
    name: 'HomeView',
    components: {
        FdelEditCard,
        Breakpoints,
        DataTable,
        DateForm,
        TextFields,
        TextFieldsSubmit
    },
    data() {
        return {
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
            dbDataBase: {            //하드코딩 데이터
                addrList: [{ name: '유지수',type: '우리집', detail: '정자동 6-17번지', etc: '302호', phone1: '01079977521', phone2: '01045189681' }],
                userId: 's_plus7@naver.com',
                userNm: '유지수',
                group: 'ROLE_MANAGER',
            }
        }
    },
    methods: {
        start() {
            for (const addr in dbDataBase.addrList) {
                // if (Object.hasOwnProperty.call(object, key)) {
                    // const element = object[key];
                    // console.log('addr');
                    // console.log(addr.name + ' ' + 'addr.type');
                    // console.log('object, element, key ------------------------->');
                    // console.log(object);
                    // console.log(element);
                    // console.log(key);
                // }
            }
        }
    }
}
</script>
