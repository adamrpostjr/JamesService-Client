<script>
	export let socket;
    function sendKeyStrokes(){
        var ks = document.getElementById('system-keystrokes').value
        if(ks != null){
            socket.emit('tsws', ks)
            document.getElementById('system-keystrokes').value = null
        }
    }
</script>

<message>
    <textarea name="system-keystrokes" id="system-keystrokes" placeholder="Keystrokes to Sent to James"></textarea>
    <button on:click="{sendKeyStrokes}">SEND</button>
</message>

<style>
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