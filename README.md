# cartoon-ai-website
Free AI Cartoon Photo Maker
<!DOCTYPE html>
<html>
<head>
    <title>Free AI Cartoon Photo Maker</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        body{
            font-family: Arial, sans-serif;
            text-align: center;
            background: #f2f2f2;
            padding: 20px;
        }
        img{
            max-width: 90%;
            margin-top: 20px;
            filter: contrast(120%) saturate(150%);
            border-radius: 10px;
        }
        input, button{
            margin-top: 15px;
            padding: 10px 20px;
            font-size: 16px;
            border-radius: 5px;
        }
        button{
            background-color: #4CAF50;
            color: white;
            border: none;
        }
        button:hover{
            background-color: #45a049;
        }
    </style>
</head>
<body>

<h1>Free AI Cartoon Photo Maker</h1>
<p>Upload your photo below and see cartoon effect!</p>

<input type="file" id="upload" accept="image/*">
<br>
<img id="preview" style="display:none">
<br>
<button id="downloadBtn" style="display:none">Download Cartoon</button>

<script>
const upload = document.getElementById("upload");
const preview = document.getElementById("preview");
const downloadBtn = document.getElementById("downloadBtn");

upload.addEventListener("change", function(){
    const file = upload.files[0];
    if(!file) return;
    preview.src = URL.createObjectURL(file);
    preview.style.display = "block";
    downloadBtn.style.display = "inline-block";
});

// Download button
downloadBtn.addEventListener("click", function(){
    const a = document.createElement("a");
    a.href = preview.src;
    a.download = "cartoon.png";
    a.click();
});
</script>

</body>
</html>
