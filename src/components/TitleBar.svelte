<style>
   .titlebar {
      height: 30px;
      background-color: #333063;
      user-select: none;
      display: flex;
      justify-content: flex-start;
      position: fixed;
      align-items: center;
      top: 0;
      left: 0;
      right: 0;
   }

   .titlebar button {
      display: inline-flex;
      justify-content: center;
      align-items: center;
      width: 40px;
      height: 20px;
      cursor: pointer;
      font-family: Arial, Helvetica, sans-serif;

      margin: 0.4%;      
      background-color: #333063;
      border: none;
      color: #e9e7e7;
   }

   .titlebar button:hover {
      background-color: #391389
   }
</style>

<div data-tauri-drag-region class="titlebar">
   <!-- Put an image of the logo here -->
   
   <button>
      File
   </button>

   <button>
      Edit
   </button>

   <button>
      New
   </button>

   <button id="title-minimize" on:click={appWindow.minimize}>
      <img src="https://api.iconify.design/mdi:window-minimize.svg?color=%23ffff" alt="minimize">
   </button>

   <button id="title-maximize" on:click={async () => {
      if (await appWindow.isMaximized()) { appWindow.unmaximize() } else { appWindow.maximize() }
   }}>
      <img src="https://api.iconify.design/mdi:window-maximize.svg?color=%23ffff" alt="maximize">
   </button>

   <button id="title-close" on:click={appWindow.close}>
      <img src="https://api.iconify.design/mdi:close.svg?color=%23ffff" alt="close">
   </button>
</div>

<script lang="ts">
   import { appWindow } from "@tauri-apps/api/window"
</script>
