<titleBar id="titlebar">
	<span class="left"><img src="./favicon.png" alt=""> JamesService</span>
	<appControll class="right"><span class="left-internal" id="min">&#128469;&#xFE0E;</span><span class="right-internal" id="max">&#128473;&#xFE0E;</span></appControll>
</titleBar>

<style>
	img{
		height: 25px;
		width: auto;
		padding-right: 30px;
	}
	
	appControll > span{
		cursor: pointer;
	}
	.left{
		width: 80%;
		margin: unset;
		padding: unset;
		float: left;
		text-align: center;
	}
	.right{
		width: 20%;
		margin: unset;
		padding: unset;
		float: right;
	}
	.left-internal{
		width: 50%;
		margin: unset;
		padding: unset;
		float: left;
		text-align: center;
	}
	.right-internal{
		width: 50%;
		margin: unset;
		padding: unset;
		float: right;
		text-align: center;
	}
	.left-internal:hover, .right-internal:hover{
		color:white;
		text-shadow: 2px 2px 3px white;
	}
</style>