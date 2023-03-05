<script>
    import { invoke } from "@tauri-apps/api/tauri";

    let name = "";
    export let greeting = "";

    async function greet() {
        greeting = await invoke("welcome to your Tauri invocation, ", { name });
    }
</script>

<div>
    <input
        type="text"
        placeholder="Enter a name..."
        bind:value={name}
        id="greet-input" />
    <button on:click={greet}>Greet</button>
    <p>{greeting}</p>
</div>
