<template>
    <div class="grid grid-cols-2">
        <div class="font-bold text-xl">
            {{ selected.name }} Chat
        </div>
        <div>
            <select
                v-model='selected'
                @change='$emit("roomChanged", selected)'
                class="float-right"
            >
                <option
                    v-for='(room, index) in rooms'
                    :key='index'
                    :value='room'
                >
                    {{ room.name }}
                </option>
            </select>
        </div>
    </div>
</template>

<script>
export default {
    name: 'selectionView',
    props: ['rooms', 'currentRoom'],
    data: () => ({
        selected: '',
    }),
    created() {
        this.selected = this.currentRoom;
    }
}
</script>