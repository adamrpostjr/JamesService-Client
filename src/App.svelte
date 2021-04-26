<script>
	import Titlebar from './titleBar.svelte'
	import ServerInfo from './serverInfo.svelte';
	import Message from './message.svelte';
	import Wallpaper from './wallpaper.svelte';
	import Typing from './typing.svelte';
	import { io } from "socket.io-client"; 

	var tab
	var sid

	function activeTab(event){
		for (let i = 0; i < document.getElementsByTagName('tab').length; i++) {
			document.getElementsByTagName('tab')[i].classList.remove('active')
		}
		document.getElementById(event.target.id).classList.add('active')
		tab = event.target.id
	}
    const socket = io("ws://127.0.0.1:6969");
    

</script>


<main>
	<Titlebar/>
	<ServerInfo socket={socket}/>
	<div class="body-parts">
		<div>
			<tab class="active" id="mouse-movement" on:click="{activeTab}">Mouse Movments</tab>
			<tab class="" id="typing" on:click="{activeTab}">Typing</tab>
			<tab class="" id="message" on:click="{activeTab}">Message</tab>
			<tab class="" id="wallpaper" on:click="{activeTab}">Wallpaper</tab>
			<tab class="" id="email" on:click="{activeTab}">Email</tab>
			<tab class="" id="start-app" on:click="{activeTab}">Start Application</tab>
			<tab class="" id="download" on:click="{activeTab}">Download</tab>
		</div>
			{ #if tab == 'mouse-movement' || tab === undefined}
				mouse-movement
			{ :else if tab == 'typing'}
				<Typing socket={socket}/>
			{ :else if tab == 'message'}
				<Message socket={socket}/>
			{ :else if tab == 'wallpaper'}
				<Wallpaper socket={socket}/>
			{ :else if tab == 'email'}
				email
			{ :else if tab == 'start-app'}
				start-app
			{ :else if tab == 'download'}
				download
			{/if }

	</div>
</main>

<style>
	.body-parts{
		width: 98%;
		height: 85%;
		padding: 1%;
		-webkit-user-select: none;
	}
	tab{
		background: black;
		padding: 0 14px;
		border-radius: 5px 5px 0 0;
		cursor: pointer;
		-webkit-user-select: none;
	}
	tab.active{
		color: black;
		background: white;
	}
</style>