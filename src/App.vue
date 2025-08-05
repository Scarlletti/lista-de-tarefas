<template>
    <div class='bg-[#ABA1C6] h-screen w-screen place-items-center place-content-center'>
        <div class='grid text-center gap-[1rem] items-center'>
            <div
                class='bg-[#DFDDF2] flex flex-col border-[0.2rem] rounded-[2rem] text-[#FFF5F6] border-[#FFF5F6] w-[12rem] h-[12rem] justify-center items-center text-3xl'>
                <p class='text-[#ABA1C6]'>DATA</p>
                <p>{{ dia }}</p>
                <p class='bg-amber-200 w-[3rem] h-[3rem] rounded-[2rem] place-content-center'>{{ mes }}</p>
                <p>{{ ano }}</p>
            </div>
            <div
                class='bg-[#DFDDF2] p-[1rem] flex flex-row gap-[2rem] rounded-[2.5rem] border-[0.2rem] border-[#FFF5F6] justify-center text-2xl items-center text-center'>
                <input type="text" v-model="newTask"
                    class='bg-[#FFF5F6] rounded-[2rem] outline-none p-[0.2rem] text-[#ABA1C6] text-center border-none'
                    placeholder='Digite uma tarefa...'>
                <button @click="addTask"
                    class='bg-[#ABA1C6] rounded-[2rem] text-[#FFF5F6] outline-none text-center p-[0.6rem] '>Adicionar</button>
            </div>
            <div
                class='bg-[#DFDDF2] flex flex-col gap-[1rem] p-[2rem] w-[41rem] h-[30rem] text-[#FFF5F6] border-[0.2rem] border-[#FFF5F6] text-center rounded-[2rem] text-3xl overflow-y-auto transparent-scrollbar col-span-2'>
                <h1 class='text-[#ABA1C6]'>TAREFAS DO DIA</h1>
                <div v-for="(t) in tasks" :key="t.id" class='flex flex-row gap-[1rem] text-center p-[0.4rem] rounded-[2rem] bg-[#ABA1C6] min-w-0 max-w-full break-words'>
                    <input type="checkbox" v-model="t.completed" class='cursor-pointer accent-amber-200 w-[1rem]'/>
                    <label :class="[{ 'line-through': t.completed }]">{{ t.title }}</label>
                    <button @click="removeTask(t.id)" class='text-amber-200'>x</button>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref, onMounted, watch } from 'vue';

const data = ref(new Date());
const dia = ref((data.value.getDate()).toString().padStart(2, '0'));
const mes = ref((data.value.getMonth() + 1).toString().padStart(2, '0'));
const ano = ref(data.value.getFullYear());

const tasks = ref([])
const newTask = ref('')

function addTask() {
    if (newTask.value.trim() !== '') {
        tasks.value.push({ title: newTask.value, completed: false, id: newTask.value.length })
        newTask.value = ''
    }
}

function removeTask(id) {
    tasks.value = tasks.value.filter((t) => t.id !== id)
}

watch(tasks, (newTasks) => {
    localStorage.setItem('tasks', JSON.stringify(newTasks))
}, { deep: true })

onMounted(() => {
    const savedTasks = localStorage.getItem('tasks')
    if (savedTasks) {
        tasks.value = JSON.parse(savedTasks)
    }
})

</script>