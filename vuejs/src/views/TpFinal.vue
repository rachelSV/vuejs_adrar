<script setup>
    import TPactiveUser from '@/components/TPactiveUser.vue';
    import TPuserData from '@/components/TPuserData.vue';

//datas
const user = {
  name: 'Michel',
  age: 30,
};

//methods
function majUserData(majData) {
  user.name = majData.name;
  user.age = majData.age;
}
</script>

<template>
    <TPactiveUser v-bind:name="user.name" v-bind:age="user.age"/>
    <TPuserData @maj-user="majUserData"/>

</template>