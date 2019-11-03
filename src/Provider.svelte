<script>
  import { setContext } from "svelte";
  import { writable } from 'svelte/store'
  import lingui from "@lingui/core";
  export let config;

  const store = writable()

  $: {
    let i18n = lingui.setupI18n(config);
    store.set(i18n)
  }

  setContext("i18n", { subscribe: store.subscribe });
</script>

<slot />
