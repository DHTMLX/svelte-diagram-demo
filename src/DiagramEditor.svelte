<script>
  import { onMount, onDestroy } from "svelte";
  import { DiagramEditor } from "@dhx/trial-diagram";
  import "@dhx/trial-diagram/codebase/diagram.min.css";
  
  export let data;

  let container;
  let diagram_editor;

  onMount(() => {
    diagram_editor = new DiagramEditor(container, {
      type: "default"
    });
    diagram_editor.parse(data);
  });

    onDestroy(() => {
      diagram_editor.destructor();
    });
</script>

<div bind:this={container} class="widget"></div>
