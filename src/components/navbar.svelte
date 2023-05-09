<script>
  import { onMount } from "svelte";
  let menuOpen = false;

  function toggleMenu() {
    menuOpen = !menuOpen;
  }

  onMount(() => {
    const handleResize = () => {
      if (window.innerWidth >= 768) {
        menuOpen = false;
      }
    };
    window.addEventListener("resize", handleResize);
    return () => {
      window.removeEventListener("resize", handleResize);
    };
  });
</script>

<nav class="bg-red-800 p-4">
  <div class="container mx-auto flex justify-between items-center">
    <a href="/" class="text-white text-lg font-bold">CJRu TheCru...PA!</a>
    <button class="text-white lg:hidden" on:click={toggleMenu}>
      {menuOpen ? '✕' : '☰'}
    </button>
    <div class={`${menuOpen ? "block" : "hidden"} lg:flex space-x-4`}>
      <a href="/" class="text-white">Home</a>
      <a href="./src/routes/login/index.svelte" class="text-white">Login</a>
      <a href="./src/routes/contact/index.svelte" class="text-white">Contact</a>
    </div>
  </div>
</nav>

<style>
  .text-bar {
    color: #F59E0B;
    animation: blinking 2s infinite;
  }
  @keyframes blinking {
    0% {
      opacity: 0;
    }
    50% {
      opacity: 1;
    }
    100% {
      opacity: 0;
    }
  }
</style>
