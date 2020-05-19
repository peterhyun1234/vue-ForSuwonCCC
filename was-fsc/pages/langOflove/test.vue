

<template>
  <v-app id="inspire">
    <v-container>
      <v-row>
        <v-col>
          <v-card>
            <v-expansion-panels 
              class="mb-6"
              v-model="panel"
              multiple
            >
              <v-expansion-panel>
                <v-expansion-panel-header expand-icon="mdi-menu-down">
                  질문 1
                  <template v-slot:actions>
                    <v-icon color="primary">$expand</v-icon>
                  </template>
                </v-expansion-panel-header>
                <v-expansion-panel-content>
                  Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                  <v-switch v-model="accordion" class="ma-2" label="Accordion"></v-switch>
                  <v-switch v-model="accordion" class="ma-2" label="Accordion"></v-switch>
                </v-expansion-panel-content>
              </v-expansion-panel>
              <v-expansion-panel>
                <v-expansion-panel-header expand-icon="mdi-menu-down">
                  질문 1
                  <template v-slot:actions>
                    <v-icon color="primary">$expand</v-icon>
                  </template>
                </v-expansion-panel-header>
                <v-expansion-panel-content>
                  Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                  <v-switch v-model="accordion" class="ma-2" label="Accordion"></v-switch>
                </v-expansion-panel-content>
              </v-expansion-panel>
              <v-expansion-panel>
                <v-expansion-panel-header expand-icon="mdi-menu-down">
                  질문 1
                  <template v-slot:actions>
                    <v-icon color="primary">$expand</v-icon>
                  </template>
                </v-expansion-panel-header>
                <v-expansion-panel-content>
                  Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                  <v-switch v-model="accordion" class="ma-2" label="Accordion"></v-switch>
                </v-expansion-panel-content>
              </v-expansion-panel>
              <v-expansion-panel>
                <v-expansion-panel-header expand-icon="mdi-menu-down">
                  질문 1
                  <template v-slot:actions>
                    <v-icon color="primary">$expand</v-icon>
                  </template>
                </v-expansion-panel-header>
                <v-expansion-panel-content>
                  Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                  <v-switch v-model="accordion" class="ma-2" label="Accordion"></v-switch>
                </v-expansion-panel-content>
              </v-expansion-panel>
            </v-expansion-panels>
                <!-- <div>
      <v-expansion-panels>
        <v-expansion-panel>
          <v-expansion-panel-header>
            Item
            <template v-slot:actions>
              <v-icon color="primary">$expand</v-icon>
            </template>
          </v-expansion-panel-header>
        </v-expansion-panel>
  
        <v-expansion-panel>
          <v-expansion-panel-header disable-icon-rotate>
            Item
            <template v-slot:actions>
              <v-icon color="teal">mdi-check</v-icon>
            </template>
          </v-expansion-panel-header>
          <v-expansion-panel-content>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
          </v-expansion-panel-content>
        </v-expansion-panel>
  
        <v-expansion-panel>
          <v-expansion-panel-header disable-icon-rotate>
            Item
            <template v-slot:actions>
              <v-icon color="error">mdi-alert-circle</v-icon>
            </template>
          </v-expansion-panel-header>
          <v-expansion-panel-content>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
          </v-expansion-panel-content>
        </v-expansion-panel>
      </v-expansion-panels>
    </div> -->
          </v-card>
        </v-col>
      </v-row>
      <v-row>
        <v-col>
          <v-card>
            One of two columns
          </v-card>
        </v-col>
        <v-col>
          <v-card>
            One of two columns
          </v-card>
        </v-col>
        <v-col>
          <v-card>
            One of two columns
          </v-card>
        </v-col>
      </v-row>
      <v-row>
        <v-col
          v-for="n in 3"
          :key="n"
          cols="sm"
        >
          <v-card
            class="pa-2"
            outlined
            tile
          >
            col
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-app>
</template>


<script>

export default {
  components: {
  },
  data () {
    return {
      accordion: false,
      panel: [0, 1, 2],
    }
  },
}
</script>

