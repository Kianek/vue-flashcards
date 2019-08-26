<template>
  <v-container>
    <v-row justify="center">
      <v-col align="center" cols="4">
        <h2>Log In</h2>
        <v-form>
          <v-text-field
            v-model="username"
            label="Username"
            :rules="usernameRules"
            :error="valid"
            :error-messages="usernameErrors"
          ></v-text-field>
          <v-text-field
            type="password"
            v-model="password"
            :rules="passwordRules"
            label="Password"
            :error="valid"
            :error-messages="passwordErrors"
          ></v-text-field>
          <v-btn depressed color="primary" class="mt-4" @click="submit" :loading="isLoading">log in</v-btn>
          <v-spacer></v-spacer>
          <v-divider class="my-4"></v-divider>
          <router-link to="/register">No account? Sign up now!</router-link>
        </v-form>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      valid: false,
      username: "",
      usernameErrors: [],
      usernameRules: [
        v => v.length < 20 || "Username must be less than 20 characters"
      ],
      password: "",
      passwordErrors: [],
      passwordRules: [
        v => v.length <= 6 || "Password must be at least 6 characters"
      ],
      isLoading: false
    };
  },
  methods: {
    submit() {
      if (this.username.length <= 0 && this.password.length <= 0) {
        const isRequired = "is required";
        this.usernameErrors.push(`Username ${isRequired}`);
        this.passwordErrors.push(`Password ${isRequired}`);
        this.valid = false;
        return;
      }

      this.username = this.password = "";
      // Send credentials to the server
      this.isLoading = true;
    }
  }
};
</script>