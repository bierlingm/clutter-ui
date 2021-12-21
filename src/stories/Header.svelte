<script>
  import './header.css';
  import Button from './Button.svelte';

  import { createEventDispatcher } from 'svelte';

  export let user = null;

  const dispatch = createEventDispatcher();

  function onLogin(event) {
    dispatch('login', event);
  }
  function onLogout(event) {
    dispatch('logout', event);
  }
  function onCreateAccount(event) {
    dispatch('createAccount', event);
  }
</script>

<header>
  <div class="wrapper">
    <div>
      <img src="favicon.png" alt="Clutter Favicon">
      <h1>Clutter</h1>
    </div>
    <div>
      {#if user}
        <Button size="small" on:click={onLogout} label="Log out" />
      {/if}
      {#if !user}
        <Button size="small" on:click={onLogin} label="Log in" />
        <Button primary size="small" on:click={onCreateAccount} label="Sign up" />
      {/if}
    </div>
  </div>
</header>

<style>
  img {
    width: 30px;
    height: 30px;
  }
</style>