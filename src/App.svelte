<script>
  import DiagramEditor from "./DiagramEditor.svelte";
  import { getData } from "./data.js";

  const data = getData();
</script>

<DiagramEditor  data={data}/>
