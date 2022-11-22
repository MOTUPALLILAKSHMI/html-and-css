# html-and-css
<title> How to Drag and Drop Images using HTML5 ? </title>
<style>
	#div1 {
		width: 350px;
		height: 70px;
		padding: 10px;
		border: 1px solid #aaaaaa;
	}
</style>
Drag and Drop option to change the position of the sequnce of the image

<div id="div1" ondrop="drop(event)"
	ondragover="allowDrop(event)">
</div>
<br>

<img id="drag1" src=
"assets/images/mortarboard.png" draggable="true" ondragstart="drag(event)" width="336" height="69">

<script>
	function allowDrop(ev) {
		ev.preventDefault();
	}

	function drag(ev) {
		ev.dataTransfer.setData("text", ev.target.id);
	}

	function drop(ev) {
		ev.preventDefault();
		var data = ev.dataTransfer.getData("text");
		ev.target.appendChild(document.getElementById(data));
	}
</script>
