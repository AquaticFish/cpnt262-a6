<!-- LightSwitch.svelte -->
<script>
  let isOn = false;
  let isLoading = false;

  const toggleSwitch = () => {
    isLoading = true;

    // Simulate an asynchronous operation (e.g., fetching data)
    setTimeout(() => {
      isOn = !isOn;
      isLoading = false;
    }, 1000);
  };
</script>

<style>
  .switch {
    width: 60px;
    height: 30px;
    border-radius: 15px;
    background: #ddd;
    position: relative;
    cursor: pointer;
  }

  .toggle {
    width: 30px;
    height: 30px;
    border-radius: 50%;
    background: #fff;
    position: absolute;
    transition: transform 0.3s;
    transform: translateX(0);
  }

  .on {
    transform: translateX(30px);
  }

  /* Skeleton loading effect */
  .skeleton {
    animation: loading 1.5s infinite;
    background: linear-gradient(90deg, #f0f0f0 25%, #e0e0e0 50%, #f0f0f0 75%);
    background-size: 200% 100%;
    border-radius: 15px;
  }

  @keyframes loading {
    to {
      background-position: -200% 0;
    }
  }
</style>

<div on:click={toggleSwitch} class="switch">
  {#if isLoading}
    <div class="toggle skeleton"></div>
  {:else}
    <div class="toggle" class:{{ on: isOn }}></div>
  {/if}
</div>
