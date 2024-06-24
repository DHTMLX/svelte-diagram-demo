<script>
    import { onMount } from "svelte";
    
    import "@dhx/trial-diagram/codebase/diagram.min.css";
    import { DiagramEditor } from "@dhx/trial-diagram";
    
    export let data;

    let diagram;
    let container;
    onMount(() => {
        diagram = new DiagramEditor(container, {type: "default"  });
        
        return () => {
            diagram.destructor();
        };
    });
    $: diagram?.parse(data);
</script>

<div bind:this={container} style="width: 100%; height: 100%;"></div>

