<script setup lang="ts">
const supabase = useSupabaseClient();
const { auth } = useSupabaseClient();

const doLogin = async () => {
  const redirectTo = `${location.origin}/confirm`;
  await auth.signInWithOAuth({
    provider: "twitter",
    options: {
      redirectTo,
    },
  });
};
</script>

<template>
  <div>
    <button @click="doLogin">Sign in with Twitter</button>
  </div>
</template>
