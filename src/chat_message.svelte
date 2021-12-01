<script>
    export let message;
    export let sender;

    const msgClass = message.who === sender ? 'sent': 'recieved';

    const ts = new Date(message.when);

</script>

<div class={`message ${msgClass}`}>

    <div class="message-text">
        <p>{message.what}</p>
        <time>{ts.toLocaleDateString()}</time>
    </div>

</div>