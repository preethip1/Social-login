<script>
  import { GoogleAuth } from "@beyonk/svelte-social-auth";
  let name;
  let login = false;
  function onSignIn(e) {
    login = true;
    let user = e.detail.user;
    let profile = user.getBasicProfile();
    name = profile.getName();
  }
</script>

<div class = "mt-2">
  {#if login == false}
    <GoogleAuth
      clientId="518788113732-7m6gullvbi4phr8el7tari1s3lge27i4.apps.googleusercontent.com"
      on:auth-success={onSignIn} />
      {:else}
      <div>{name} is logged in </div>
  {/if}
</div>
