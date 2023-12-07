<script setup>
import { ref } from 'vue'
import CCASlotsTodoItem from './CCASlotsTodoItem.vue'
import CCASlotsTodoItem2 from './CCASlotsTodoItem2.vue'
import CCBSlotsProps from './CCBSlotsProps.vue'
const gegevensinparent = "dit is in de parent"
const slotswitcher = ref("vierde")
function naaranderslot(){
    slotswitcher.value = "deene"
}
</script>
<template>
    <div>
        <CCASlotsTodoItem>
            ABC
            <input>
            {{ gegevensinparent }}
        </CCASlotsTodoItem>
        <hr>
        <CCASlotsTodoItem2>
            ABC
            <input>
            {{ gegevensinparent }}
        </CCASlotsTodoItem2>
        <hr>
        
        <CCASlotsTodoItem2>

        </CCASlotsTodoItem2>
        <CCASlotsTodoItem2/>
        <CCASlotsTodoItem2>
            en dit in de zondernaam
            <template v-slot:deene>Dit komt in de ene</template>
            <template v-slot:deandere>Dit komt in de andere</template>
            <template #derde>de derde inhoud</template>
            <template #[slotswitcher]>dit zit nu in vierde</template>
            <button @click="naaranderslot()">switch naar de ene</button>
        </CCASlotsTodoItem2>
        <CCBSlotsProps v-slot="slotProps">
            {{ slotProps.autonaam }}
        </CCBSlotsProps>
        <CCBSlotsProps v-slot="qq">
            {{ qq.autonaam }}
        </CCBSlotsProps>
        <CCBSlotsProps v-slot="{autonaam,ikhebnogmeer }">
            {{ autonaam }} en {{ ikhebnogmeer }}
        </CCBSlotsProps>
        <CCBSlotsProps #weereennaam="zomaar">
            {{ zomaar.zomaar }}
        </CCBSlotsProps>
        <CCBSlotsProps #weereennaam="zomaar">
            {{ zomaar }}
        </CCBSlotsProps>
    </div>
</template>