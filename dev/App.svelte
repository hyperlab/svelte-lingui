<script>
  import Provider from "../src/Provider.svelte";
  import Text from "../src/Text.svelte";

  let name = "Jonatan";
  let config = {
    locale: "sv",
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

<Provider {config}>
  <h1>
    <Text message={'Hello {name}'} props={{ name }} />
  </h1>
</Provider>
