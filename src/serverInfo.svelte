<script>
   export let socket;
    var sid
    var time = 0

   socket.on('connect', connect =>{
        sid = socket.id
    })
    socket.on('disconnect', disconnect =>{
        sid = null
    })




</script>

<server>
    { #if sid == null || sid === undefined }
        <socketId class="in-active">
            <span>Socket ID: </span><id id="id"></id>
        </socketId>
    { :else }
        <socketId class="active">
            <span>Socket ID: </span><id id="id">{sid}</id> -- {time}
        </socketId>
    { /if }
</server>

<style>
    server{
        font-size: small;
        display: inline-block;
        width: 100%;
    }
    socketId{
        padding: 0 20px;
        border-radius: 25px;
        color: #3b4252;
        margin: 0 0 0 10px;
    }
    .active{
        background: #a3be8c;
    }
    .in-active{
        background: #bf616a;
    }
    #id{
        font-weight: 600;
    }
</style>