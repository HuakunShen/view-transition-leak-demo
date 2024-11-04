<script lang="ts">
  import { goto } from "$app/navigation";
  import User from "lucide-svelte/icons/user";
  import { Command } from "@kksh/svelte";

  const randomKeys = Array.from({ length: 100 }, (_, idx) => idx);
</script>

<Command.Root class="max-w-[450px] h-[30em] rounded-lg border shadow-md">
  <Command.Input placeholder="Type a command or search..." class="h-36" />
  <Command.List class="max-h-full overflow-hidden">
    <Command.Empty>No results found.</Command.Empty>
    {#each randomKeys as key}
      <Command.Item onSelect={() => goto(`/detail/${key}`)}>
        <span class="logo" style:--logo="logo-{key}">
          <User class="mr-2 size-4" />
        </span>
        <span>{key}</span>
      </Command.Item>
    {/each}
  </Command.List>
</Command.Root>

<style>
  .logo {
    view-transition-name: var(--logo);
  }
</style>
