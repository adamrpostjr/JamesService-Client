<script>
	export let socket;
    let img = null
    function previewWallpaper() {
        img = document.getElementById('img-url').value 
        if (img.length == 0) {
            img = null
        }
    }
    function defaultThePreview() {
        img = null
    }
    function setWallpaper() {
        console.log(img.length)
        if (img.length != 0) {
            socket.emit('wallpaper', img)
        }
        
    }
</script>

<wallpaper>
    { #if img == null }
        <img src="/placeholder.jpg" alt="">
    { :else }
        <img src="{img}" on:error="{defaultThePreview}" alt="">
    {/if}
    <input type="text" id="img-url" on:blur="{previewWallpaper}" placeholder="Image to Set as James Wallpaper">
    <button on:click="{setWallpaper}">SEND</button>
</wallpaper>

<style>
    img{
        display: block;
        margin: auto;
        margin-top: 10px;
        max-height: 360px;
        min-height: 360px;
        max-width: 80%;
    }
    input{
        display: block;
        width: 80%;
        margin: auto;
        margin-top: 25px;
    }
    input:focus{
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