

<script setup lang="ts">
  import { defineProps, defineEmits } from 'vue'; 
  import { message } from 'ant-design-vue';
  const [messageApi, contextHolder] = message.useMessage();

  const emit = defineEmits(['submit', 'backStep'])

  const _props = defineProps<{
    skills: string[]
  }>()

  let skills = ref(_props.skills ? useCloneDeep(_props.skills) : []);

  const state = reactive({ skill: '' });

  const nextStep = () => {
    if (skills.value.length === 0) {
      console.log(11111)
      messageApi.info('Cần thêm ít nhất 1 kỹ năng');
    } else {
      emit('submit', { skills: skills.value })
    }
  }

  const backStep = () => {
    emit('backStep')
  }

  const addSkill = () => {
    if(state.skill !== '') {
      state.skill.split(',').forEach((_skill : any) => {
        skills.value.push(_skill.trim());
      })
      state.skill = ''
    }
  }

  const removeSkill = (__skill : any) => {
    skills.value = skills.value.filter((_skill : any) => _skill !== __skill);
    console.log(skills.value)
  }
</script>

<template>
    <div class="mb-8">
      <context-holder />
      <h6 class="!text-black font-[700] text-[16px]">Kỹ năng</h6>
      <div class="mt-4">
        <a-input :disabled="skills.length === 20" v-model:value="state.skill" placeholder="Thêm tối đa 20 kỹ năng (Các kỹ năng cách nhau bằng dấu phẩy)" @pressEnter="addSkill" />
        <div class="mt-3 flex gap-3 flex-wrap items-center">
          <div v-for="_skill, index in skills" :key="index" class="inline-flex items-center gap-1 border-[1px] border-solid text-[#00237d] border-[#00237d] py-[2px] pl-2 pr-1 rounded-[999px]">
            <span>{{ _skill }}</span>
            <span class="relative font-bold -top-[1px] text-[16px] block cursor-pointer px-2" @click="() => removeSkill(_skill)">x</span>
          </div>
        </div>
      </div>
      <div class="flex items-center justify-end gap-6 mt-6">
        <a-button class="!text-[#00237d] !border-none" @click="backStep">Hủy</a-button>
        <a-button class="!text-[#00237d] !border-[#00237d] !rounded-3xl !w-[130px] !p-0 !flex !items-center justify-center" @click="nextStep">Lưu</a-button>
      </div>
    </div>
</template>
