<script>
  import Provider from "../src/Provider.svelte";
  import Text from "../src/Text.svelte";

  let name = "Jonatan";
  let locale = "en";
  $: config = {
    locale,
    catalogs: {
      en: {
        messages: {
          "Hello world": "Hello world"
        }
      },
      sv: {
        messages: {
          "Hello world": "Hej världen",
          "Hello {name}": "Hej {name}"
        }
      }
    }
  };
</script>

<label>
  Language:
  <select bind:value={locale}>
    <option value="en">English</option>
    <option value="sv">Svenska</option>
  </select>
</label>

<Provider {config}>
  <h1>
    <Text message={'Hello world'} />
  </h1>
  <p>
    <Text message={'Hello {name}'} props={{ name }} />
  </p>
</Provider>
