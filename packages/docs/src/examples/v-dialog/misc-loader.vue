<template>
  <div class="text-center">
    <v-btn
      :disabled="dialog"
      :loading="dialog"
      color="purple-darken-2"
      @click="dialog = true"
    >
      Start loading
    </v-btn>
    <v-dialog
      v-model="dialog"
      :scrim="false"
      persistent
    >
      <v-card
        color="primary"
      >
        <v-card-text>
          Please stand by
          <v-progress-linear
            indeterminate
            color="white"
            class="mb-0"
          ></v-progress-linear>
        </v-card-text>
      </v-card>
    </v-dialog>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        dialog: false,
      }
    },

    watch: {
      dialog (val) {
        if (!val) return

        setTimeout(() => (this.dialog = false), 4000)
      },
    },
  }
</script>
