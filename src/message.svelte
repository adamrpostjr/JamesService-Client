<script>
	export let socket;
    function sendMessage(){
        var msg = {}
        msg.titleText = document.getElementById('system-title').value
        msg.bodyText = document.getElementById('system-message').value
        if(msg.titleText != null && msg.bodyText != null){
            console.log(msg)
            socket.emit('message', msg)
            msg.titleText = null
            msg.bodyText = null
        }
    }
</script>

<message>
    <input type="text" id="system-title" placeholder="Title of the Message to Send to James">
    <textarea name="system-message" id="system-message" placeholder="Body of the Message to Send to James"></textarea>
    <button on:click="{sendMessage}">SEND</button>
</message>

<style>
    input{
        width: 80%;
        display: block;
        margin: auto;
        margin-top: 17px;
    }
    input:focus{
        outline-color: transparent;
    }
    textarea{
        width: 80%;
        height: 35%;
        resize: none;
        display: block;
        margin: auto;
        margin-top: 17px;
    }
    textarea:focus{
        outline-color: transparent;
    }
    button{
        float: right;
        width: 105px;
        margin: 10px;
        border-radius: 20px;
        font-weight: bold;
    }
</style>