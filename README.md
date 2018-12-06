# Keras to tensorflow.js


index.html 
	<script type="text/javascript" src="/js/imagenet_classes.js"></script> 
	<script src="https://cdn.jsdelivr.net/npm/@tensorflow/tfjs@latest"></script>
	<script type="text/javascript" src="https://code.jquery.com/jquery-2.1.1.min.js"></script> 

Once you load all the above three scripts, you can open up a new file named mobile-net.js that will have all the functionality needed to make Keras MobileNet model work in a web browser.

The user interface that I made at the start of the tutorial has HTML, CSS and JavaScript code combined. We will look into model specific part instead of looking into every single line of code.

let model;
async function loadModel() {
  console.log("model loading..");

  // display model loading progress box
  loader = document.getElementById("progress-box");
  load_button = document.getElementById("load-button");
  loader.style.display = "block";

  // model name is "mobilenet"
  modelName = "mobilenet";
  
  // clear the model variable
  model = undefined;
  
  // load the model using a HTTPS request (where you have stored your model files)
  model = await tf.loadModel('https://gogul09.github.io/models/mobilenet/model.json');
  
  // hide model loading progress box
  loader.style.display = "none";
  load_button.disabled = true;
  load_button.innerHTML = "Loaded Model";
  console.log("model loaded..");
}
