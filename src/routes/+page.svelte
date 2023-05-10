<script lang="ts">
    let email: string = "";
    $: hashedEmail = `https://www.gravatar.com/avatar/${CryptoJS.MD5(email.replace(/\s/g, "").toLowerCase())}?s=250`;
</script>

<img src={hashedEmail} alt="gravatar preview"/>
<div>
<p>Enter an email address to get their Gravatar URL.</p>
<input type="email" placeholder="Gravatar Email" bind:value={email}/>
<a href={hashedEmail} target="_blank">{hashedEmail}</a>
</div>
<style>
    * {
        margin: 0.5rem 0;
    }

    img {
        border: 1px solid #f5f5f5;
    }

    input {
        width: 100%;
        padding: 0.5rem;
        margin: 0.5rem 0;
        border: 1px solid #ccc;
        background-color: #f5f5f5;
        border: 0;
        border-bottom: 1px solid #ccc;
        max-width: 500px;
        font-size: 1rem;
    }

    div {
        max-width: 600px;
        text-align: center;
    }
</style>