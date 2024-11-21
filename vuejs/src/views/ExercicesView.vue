<script setup>
import NewAmi from '../components/NewAmi.vue'
import UnAmiEmitObjet from '../components/UnAmiEmitObjet.vue'
import UnAmiPropsEmit from '../components/UnAmiPropsEmit.vue'
import UnAmiProps1 from '../components/UnAmiProps1.vue'
import ExoDynamicStyle from '../components/ExoDynamicStyle.vue'
import ExoListVifVfor from '../components/ExoListVifVfor.vue'
import ExoDataBiding from '../components/ExoDataBiding.vue'
import ExoCompteur from '../components/Compteur.vue'
import TaskList from '../components/TaskList.vue'
import FormEvent from '../components/FormEvent.vue'
import VModel from '../components/VModel.vue'
import StyleDynamic from '../components/StyleDynamic.vue'
import JeuCompteur from '../components/JeuCompteur.vue'

//datas
const lesAmis = [
    {
        id: 'lasticot',
        name: 'COCO L ASTICOT',
        phone: '01234 5678 991',
        email: 'coco@lasticot.com',
        premium: true
    },
    {
        id: 'janine',
        name: 'Janine DeLavega',
        phone: '09876 543 221',
        email: 'janine@delavega.com',
        premium: true
    },
    {
        id: 'jojo',
        name:"jojoLeBarjo",
        phone:'123 12346 24',
        email:'jojo@barjo.com',
        premium: true
    },
    {
        id:'kimonoSurUnFrigo',
        name:"Steven Seagal",
        phone:'+338765477',
        email:'steven@seagal.com',
        premium: true
    }
];

// Methods
function afficherStatusPremium(leIdDansUnAmi) {
    // alert("Je comprend rien");
    const unAmiIdentified = lesAmis.find(unAmiATrouver => unAmiATrouver.id === leIdDansUnAmi)
    unAmiIdentified.premium = !unAmiIdentified.premium;
    console.log(unAmiIdentified)
}
function ajouterAmi(name, phone, email){
    console.log("Nouvel ami ajouté :");
    const newAmiContact = {
        id: new Date().toISOString(),
        name : name,
        phone : phone,
        email : email,
        premium : false
    };
    lesAmis.push(newAmiContact);
    console.log("Nouvel ami ajouté :", lesAmis);
}
</script>

<template>
  <div>
    <h1>Exercices</h1>
    <NewAmi @add-ami="ajouterAmi" />
    <UnAmiEmitObjet v-for="ami in lesAmis" :key="ami.id" v-bind:leId="ami.id" v-bind:leNom="ami.name" v-bind:lePhone="ami.phone" v-bind:leMail="ami.email" v-bind:premium="ami.premium" @mon-event-premium="afficherStatusPremium"/>
    <UnAmiPropsEmit v-for="ami in lesAmis" :key="ami.id" v-bind:leId="ami.id" v-bind:leNom="ami.name" v-bind:lePhone="ami.phone" v-bind:leMail="ami.email" @mon-event-premium="afficherStatusPremium"/>
    <UnAmiPropsEmit leNom="Jacqueline" lePhone="22.22.22" leMail="jacqueline@jj.com" premium="1"/>
    <UnAmiProps1 leNom="Michel" lePhone="00.00.00" leMail="michel@michel.com" premium="1"/>
    <UnAmiProps1 leNom="Jean Jacques" lePhone="11.11.11" leMail="JJ@jacquy.com" premium="0"/>
    <StyleDynamic />
    <JeuCompteur />
    <VModel />
    <FormEvent />
    <TaskList />
    <ExoListVifVfor />
    <ExoDynamicStyle />
    <ExoCompteur />
    <ExoDataBiding />
  </div>
</template>
