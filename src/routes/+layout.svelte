<script lang="ts">
	import "../app.css";
	import ViewTransition from "../lib/components/view-transition.svelte";
	import { ModeWatcher } from "mode-watcher";
	let { children } = $props();
</script>

<ModeWatcher />
<ViewTransition />
{@render children()}
