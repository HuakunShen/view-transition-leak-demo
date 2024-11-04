<script lang="ts">
  import { goto } from "$app/navigation";
  import User from "lucide-svelte/icons/user";
  import { page } from "$app/stores";
  import { Button } from "@kksh/svelte";
</script>

<Button on:click={() => goto("/")}>Back</Button>
<div class="p-4">
  <h1>Detail Page for {$page.params.id}</h1>
  <span class="logo" style:--logo="logo-{$page.params.id}">
    <User class="mr-2 size-10" />
  </span>
</div>

<style>
  .logo {
    view-transition-name: var(--logo);
    /* clip-path: inset(0 0 0 0); */
  }
</style>
