<script lang="ts">
   import { invoke } from "@tauri-apps/api/tauri"
   import TitleBar from "../components/TitleBar.svelte";
   import Editor from "../components/Editor.svelte";
   import FileExplorer from "../components/FileExplorer.svelte";

   let name: string
   let output: string
   async function greet() {
      output = await invoke('greet', { name: 'Jean-Pierre' })
   }
</script>

<style>

   main {
      margin: 50px;
      width: 100%;
      height: 100%;
   }
</style>

<header>
   <TitleBar />
</header>


<main>
   <FileExplorer />
   <Editor />
</main>


