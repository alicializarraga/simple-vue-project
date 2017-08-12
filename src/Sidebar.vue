<template>
  <aside class="sm-side">
      <div class="user-head">
          <img src="src/assets/images/DialDoc.png">
      </div>

      <ul class="inbox-nav">
          <li>
              <a href="#" @click.prevent="navigate('app-Personal', 'Personal')">
                  1. Personal
              </a>
          </li>

          <li>
              <a href="#" @click.prevent="navigate('app-Allergies', 'Allergies')">
                  2. Allergies
              </a>
          </li>

          <li>
              <a href="#" @click.prevent="navigate('app-Medications', 'Medications')">
                  3. Medications
              </a>
          </li>

          <li>
              <a href="#" @click.prevent="navigate('app-MedicalHistory', 'Medical History')">
                  4.- Medical History</a>
          </li>

          <li>
              <a href="#" @click.prevent="navigate('app-Procedures', 'Procedures')">
                  5.- Procedures</a>
          </li>

          <li>
              <a href="#" @click.prevent="navigate('app-FamilyHistory', 'Family History')">
                  6.- Family History</a>
          </li>

          <li>
              <a href="#" @click.prevent="navigate('app-Questions', 'Questions')">
                  7.- Questions</a>
          </li>

          <li>
              <a href="#" @click.prevent="navigate('app-Pharmacy', 'Pharmacy')">
                  8.- Pharmacy</a>
          </li>

          <li>
              <a href="#" @click.prevent="navigate('app-Payment', 'Payment')">
                  9.- Payment</a>
          </li>

          <li>
              <a href="#" @click.prevent="navigate('app-Doctors', 'Doctors')">
                  10.- Doctors</a>
          </li>

          <li>
              <a href="#" @click.prevent="navigate('app-Settings', 'Settings')">
                  11.- Settings </a>
          </li>
      </ul>
  </aside>
</template>

<script>
  import { eventBus } from './main';
  export default {
    methods: {
      navigate(newView, title) {
        eventBus.$emit('changeView', {
          tag: newView,
          title: title
          });
        }
    }
  }
</script>
