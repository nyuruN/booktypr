<script setup lang="ts">
let props = defineProps<{
    options: readonly string[]
}>()

let model = defineModel()
</script>

<template>
    <div class="button-group">
        <template v-for="option in props.options">
            <div class="group-button" @click="model = (model == option) ? undefined : option"
                :class="{ active: model == option }">
                {{ option }}
            </div>
        </template>
    </div>
</template>

<style scoped>
.button-group {
    display: flex;
    background-color: #3b3b3b;
    border-radius: 8px;
    min-width: 10rem;
    overflow: clip;
    user-select: none;
}

.group-button {
    padding: 0.7rem;
    font-weight: bold;
    font-size: 0.9rem;
}

.group-button:hover {
    background-color: #555555;
    cursor: pointer;
}

.group-button.active {
    background-color: rgb(152, 192, 88);
}

.group-button:not(:last-child) {
    border-right: 2px solid #4b4b4b;
}
</style>