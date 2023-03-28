<template>
  <v-app id="inspire">

    <v-app-bar>

      <v-toolbar-title class="mx-12">Consultorio Juridico </v-toolbar-title>

      <v-btn prepend-icon="mdi-login" variant="outlined"> <NuxtLink to="/login"> Iniciar Sesion  </NuxtLink></v-btn>
    </v-app-bar>

    <v-main>


      <div class="d-flex flex-column ma-16">
  
        <v-sheet width="300" class="mx-auto">

      <v-form fast-fail @submit.prevent>
        <v-text-field
          v-model="firstName"
          prepend-inner-icon="mdi-account"
          label="Usuario"
          :rules="[rules.required]"
        ></v-text-field>
  
        <v-text-field
              v-model="password"
              prepend-inner-icon="mdi-lock"
              :rules="[rules.required, rules.min]"
              :type="show1 ? 'text' : 'password'"
              name="input-10-1"
              label="Contraseña"
        
            ></v-text-field>

        <v-select
          v-model="select"
          :items="items"
          label="Rol"
          :rules="[rules.required]"
        ></v-select>
  
        <v-btn type="submit" block class="mt-2"><NuxtLink to="/dashboard">Submit</NuxtLink></v-btn>
      </v-form>
    </v-sheet>

      </div>


    </v-main>
  </v-app>
</template>

<script>
export default {
   data(){
    return {

      show1: false,
      show2: true,
      password: 'Password',
      rules: {
        required: value => !!value || 'Required.',
        min: v => v.length >= 8 || 'Min 8 characters',
        emailMatch: () => (`The email and password you entered don't match`),
      },
    
    valid: true,
    name: '',
    nameRules: [
      v => !!v || 'Name is required',
      v => (v && v.length <= 10) || 'Name must be less than 10 characters',
    ],
    select: null,
    items: [
      'Estudiante',
      'Monitor',
      'Asesor',
      'Director',
    ],
    checkbox: false,
  }
},
  methods: {
    async validate () {
      const { valid } = await this.$refs.form.validate()

      if (valid) alert('Form is valid')
    },
    reset () {
      this.$refs.form.reset()
    },
    resetValidation () {
      this.$refs.form.resetValidation()
    },
  },
}
</script>