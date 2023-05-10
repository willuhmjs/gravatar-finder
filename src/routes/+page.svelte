<script lang="ts">
    let email: string = "";
    $: hashedEmail = CryptoJS.MD5(email.replace(/\s/g, "").toLowerCase());
</script>

<input type="email" bind:value={email}/>
<input type="text" disabled value="ttps://www.gravatar.com/avatar/{hashedEmail}"/>
<img src="https://www.gravatar.com/avatar/{hashedEmail}?s=300" alt="gravatar preview"/>

