<template>
  <aside class="lg-side">
    <div class="inbox-head">
     
    </div>
    <keep-alive>
      <component :is="currentView.tag"></component>
    </keep-alive>
  </aside>
</template>

<script>
  import Personal from './Personal.vue';
  import Allergies from './Allergies.vue';
  import Medications from './Medications.vue';
  import MedicalHistory from './MedicalHistory.vue';
  import Procedures from './Procedures.vue';
  import FamilyHistory from './FamilyHistory.vue';
  import Questions from './Questions.vue';
  import Pharmacy from './Pharmacy.vue';
  import Payment from './Payment.vue';
  import Doctors from './Doctors.vue';
  import Settings from './Settings.vue';
  import { eventBus } from './main';

  export default {
    created() {
      eventBus.$on('changeView', (data) => {
        let temp = [{
          tag: data.tag,
          title: data.title
        }];
        this.history = temp.concat(this.history.splice(0));
      });
    },
    data() {
      return {
        history: [
          {
            tag: 'app-personal',
            title: 'Personal'
          }
        ]
      };
    },
    computed: {
      currentView() {
        return this.history[0];
      }
    },
    components: {
      appPersonal: Personal,
      appAllergies: Allergies,
      appMedications: Medications,
      appMedicalHistory: MedicalHistory,
      appProcedures: Procedures,
      appFamilyHistory: FamilyHistory,
      appQuestions: Questions,
      appPharmacy: Pharmacy,
      appPayment: Payment,
      appDoctors: Doctors,
      appSettings: Settings
    }
  }
</script>
