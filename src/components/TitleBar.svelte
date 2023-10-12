<script lang="ts">
   import { appWindow } from "@tauri-apps/api/window"
</script>

<style>
   .titlebar {
      height: 30px;
      background-color: rgb(13, 13, 13);
      user-select: none;
      display: flex;
      justify-content: space-between;
      position: fixed;
      align-items: center;
      top: 0;
      left: 0;
      right: 0;
   }

   .titlebar-left {
      display: flex;
      align-items: center;
      margin: 0.4%;
   }

   .titlebar-right {
      display: flex;
      align-items: center;
      margin: 0.4%;
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
      background-color: black;
      border: none;
      color: #bab8b8;
   }

   .titlebar button:hover {
      background-color: rgb(46, 46, 46);
   }
</style>

<div data-tauri-drag-region class="titlebar">
   <!-- Put an image of the logo here -->
   <div class="titlebar-left">
      <button>
         File
      </button>
   
      <button>
         Edit
      </button>
   
      <button>
         New
      </button>
   </div>

   <div class="titlebar-right">
      <button id="title-minimize" on:click={appWindow.minimize}>
         <img src="https://api.iconify.design/mdi:window-minimize.svg?color=%23bab8b8" alt="minimize">
      </button>
   
      <button id="title-maximize" on:click={async () => {
         if (await appWindow.isMaximized()) { appWindow.unmaximize() } else { appWindow.maximize() }
      }}>
         <img src="https://api.iconify.design/mdi:window-maximize.svg?color=%23bab8b8" alt="maximize">
      </button>
   
      <button id="title-close" on:click={appWindow.close}>
         <img src="https://api.iconify.design/mdi:close.svg?color=%23bab8b8" alt="close">
      </button>
   </div>

</div>
