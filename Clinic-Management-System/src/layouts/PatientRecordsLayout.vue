<template>
  <q-layout view="lHh Lpr lFf" class="bg-secondary">
    <q-header reveal elevated>
      <q-toolbar class="row glossy bg-primary items-center justify-center">
        <div class="col">
            <q-btn outline rounded style="width: 105px" color="secondary" label="Back" icon="mdi-arrow-left"/>
        </div>
        <q-toolbar-title class="col" style="padding: .25em;">
            Patient Records
        </q-toolbar-title>
        <div class="text-h5"> Best<span class="text-accent ">Byte</span> <q-img src="icons\logo_white.png" alt="company logo"
          style="width:2em;height:2em;"/>
        </div>
      </q-toolbar>
    </q-header>



    <q-drawer
        v-model="drawer" show-if-above :width="200" :breakpoint="400">
        <q-scroll-area style="height: calc(100% - 150px); margin-top: 150px; border-right: 1px solid #ddd">
          <q-list padding>
            <q-item v-ripple clickable to="/system">
              <q-item-section avatar>
                <q-icon name="mdi-home" />
              </q-item-section>

              <q-item-section>
                Home Page
              </q-item-section>
            </q-item>

            <q-item v-ripple clickable to="/profilesettings">
              <q-item-section avatar>
                <q-icon name="mdi-account" />
              </q-item-section>

              <q-item-section>
                Profile 
              </q-item-section>
            </q-item>

            <q-item v-ripple clickable>
              <q-item-section avatar>
                <q-icon name="mdi-timetable" />
              </q-item-section>

              <q-item-section>
                Appointments
              </q-item-section>
            </q-item>

            <q-item v-ripple clickable to="/patientrecords">
              <q-item-section avatar>
                <q-icon name="mdi-medical-bag" />
              </q-item-section>

              <q-item-section>
                Patient Records
              </q-item-section>
            </q-item>

            <q-item v-ripple clickable>
              <q-item-section avatar>
                <q-icon name="mdi-cog" />
              </q-item-section>

              <q-item-section>
                Settings
              </q-item-section>
            </q-item>
          </q-list>
        </q-scroll-area>

        <q-img class="absolute-top" src="https://cdn.quasar.dev/img/material.png" style="height: 150px">
          <div class="absolute-bottom bg-transparent">
            <q-avatar size="80px" class="q-mb-sm">
              <img src="icons\logo_black.png">
            </q-avatar>
            <div class="text-weight-bold">Profile Name</div>
            <div>@bestbyte</div>
          </div>
        </q-img>
      </q-drawer>

    <q-page-container>
      <!-- This is where pages get injected -->
      <router-view />
    </q-page-container>

  </q-layout>
</template>

<script>
import { ref } from 'vue'

export default {
   name: 'SystemLayout',

  setup () {
    return {
      drawer: ref(false)
    }
  }
}
</script>
