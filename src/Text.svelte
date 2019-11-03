<script>
  import { getContext } from "svelte";
  const i18n = getContext("i18n");
  export let message, props;
</script>

{$i18n._(message, props)}
