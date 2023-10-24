<script lang="ts">
    interface $$Props {
      obrazek: string;
    }
  </script>
  
  <div class="karticka">
    <svelte:element this={"div"} class={`okenko}`}>
      <svelte:element this={"h2"} class={`nadpis}`}>
        <slot />
      </svelte:element>
      <svelte:element this={"img"} src={obrazek} class={`img`} />
    </svelte:element>
  </div>

<style lang="stylus">

</style>