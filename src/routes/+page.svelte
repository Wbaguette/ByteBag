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
   
   .container {
      display: flex;
      flex-direction: row;
      margin-top: 30px;
      margin-left: -8px;
      padding-left: 0px;
      margin-right: -8px;
      padding-right: 0px;
      height: 100vh;
   }

</style>

<header>
   <TitleBar />
</header>

<div class="container">
   <FileExplorer />
   <Editor />
</div>
   

