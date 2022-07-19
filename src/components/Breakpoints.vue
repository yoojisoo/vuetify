<template>
    <v-container>
        <!-- :fullscreen = "$vuetify.breakpoint.mobile" 모바일 일때만 풀스크린 적용하겠다 -->
        <div class="text-center">
        <v-dialog
        v-model="dialog"
        width="500"
        :fullscreen = "$vuetify.breakpoint.mobile"
        >
            <template v-slot:activator="{ on, attrs }">
                <v-btn
                color="red lighten-2"
                dark
                v-bind="attrs"
                v-on="on"
                >
                Click Me
                </v-btn>
            </template>

            <v-card>
                <v-card-title class="text-h5 grey lighten-2">
                카드 타이플
                </v-card-title>

                <v-card-text>
                카드 본문
                </v-card-text>

                <v-divider></v-divider>

                <v-card-actions>
                    <v-spacer></v-spacer>
                    <v-btn
                        color="primary"
                        text
                        @click="dialog = false"
                    >
                        동의
                    </v-btn>
                </v-card-actions>
            </v-card>
        </v-dialog>
    </div>

        <v-card>
            <!-- name으로 접근 시, 현재 뷰포트가 어떤 코드에 위치하는지 알 수 있다. -->
            <v-card-title>
                $vuetify.breakpoint.name: {{ $vuetify.breakpoint.name }}
            </v-card-title>
                <v-card
                class="pa-3"
                outlined
                :height="height"
                >
                    콘텐츠1
                </v-card>
                <v-card
                class="pa-3"
                outlined
                :height="height"
                >
                    <!-- 1264 이상일 경우 false(모바일이 아님) -->
                    <v-card-title>
                        $vuetify.breakpoint.mobile:
                        {{ $vuetify.breakpoint.mobile }}
                        {{ $vuetify.breakpoint.mobileBreakpoint }}
                    </v-card-title>
                    콘텐츠2
                </v-card>
        </v-card>

    
    </v-container>
</template>

<script>
    export default {
        data : () => ({
            dialog: false,
        }),
        computed: {
            height () {
                switch (this.$vuetify.breakpoint.name) {
                    case 'xs' : return 100
                    case 'sm' : return 150
                    case 'md' : return 200
                    case 'lg' : return 250
                    default: return 300
                }
            }
        }
    }
</script>

<style>

</style>