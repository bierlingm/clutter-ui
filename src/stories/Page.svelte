<script>
  import './page.css';
  import Header from './Header.svelte';

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

<article>
  <Header {user} on:login={onLogin} on:logout={onLogout} on:createAccount={onCreateAccount} />
</article>
