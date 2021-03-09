# screen-Recorder-with-JavaScript

<!DOCTYPE html>
<html>
<head>
	<style type="text/css">
		#video{
			width: 90%;
			border:1px solid black;
		}
	</style>
</head>
<body>
<button id="start">start capture</button>
<button id="stop">stop capture</button>
<video id="video" autoplay></video>
<script type="text/javascript">
	var video=document.getElementById("video")
	var start=document.getElementById("start")
	var stop=document.getElementById("stop")
	start.addEventListener("click",async ()=>{
		try{
			video.srcObject=await navigator.mediaDevices.getDisplayMedia({
				video:true
			})
		}
		catch(error){
			console.log(error)
		}
	})
	stop.addEventListener("click",()=>{
		video.srcObject=null
	})
</script>
</body>
</html>
