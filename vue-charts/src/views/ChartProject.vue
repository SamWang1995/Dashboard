<template>
    <div class="chartproject">
        <v-container class="my-5">
            <v-layout row wrap>
                <v-flex xs3>
                        <v-card class="pa-3 ma-3">
                        <v-container>
                            <v-card-text>
                                <div class="subheading">Toggle Regular and option income</div>
                                
                                <div class="grey--text">Your payable taxes from option exercise are addition to the
                                    regular income tax you owe. Toggle to include or exclude items from your tax breakdown.
                                </div>
                                
                            </v-card-text>
                            <v-checkbox v-model="checkbox1" :label="`Checkbox 1: ${checkbox1.toString()}`"></v-checkbox>
                            <v-checkbox v-model="checkbox2" :label="`Checkbox 2: ${checkbox2.toString()}`"></v-checkbox>
                            <v-spacer></v-spacer>
                            <div class="subheading ml-3 mt-3 mb-5">Toggle option grants</div>
                            <v-checkbox v-model="checkbox3" :label="`Checkbox 3: ${checkbox3.toString()}`"></v-checkbox>
                            <v-checkbox v-model="checkbox4" :label="`Checkbox 4: ${checkbox4.toString()}`"></v-checkbox>
                            <v-checkbox v-model="checkbox5" :label="`Checkbox 5: ${checkbox5.toString()}`"></v-checkbox>
                        </v-container>
                    </v-card>
                </v-flex>
                <v-flex xs9>
                    <v-card class="pa-3 ma-3">
                        <Barchart :height="242"/>
                    </v-card>
                </v-flex>
            </v-layout>
        </v-container>
    </div>
</template>
<script>
import Barchart from "@/components/Barchart"
export default {
    components: { Barchart },
    data () {
    return {
      checkbox1: true,
      checkbox2: false,
      checkbox3: false,
      checkbox4: false,
      checkbox5: false
    }
  }
}
</script>
