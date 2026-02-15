
<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Yesh Gifts | Custom Mug Orders</title>

<style>
body{
    margin:0;
    font-family:Arial, sans-serif;
    background:#f5f6fa;
    text-align:center;
}

header{
    background:linear-gradient(135deg,#00b894,#0984e3);
    color:white;
    padding:50px 20px;
}

.section{
    padding:40px 20px;
}

.form-box{
    background:white;
    max-width:600px;
    margin:auto;
    padding:25px;
    border-radius:15px;
    box-shadow:0 5px 15px rgba(0,0,0,0.1);
}

input, textarea, select{
    width:100%;
    padding:10px;
    margin:10px 0;
    border-radius:8px;
    border:1px solid #ccc;
}

button{
    background:#00b894;
    color:white;
    border:none;
    padding:12px;
    width:100%;
    border-radius:25px;
    font-size:16px;
    cursor:pointer;
    margin-top:10px;
}

button:hover{
    background:#0984e3;
}

.preview-wrapper{
    perspective:1000px;
    margin-top:20px;
}

.mug{
    width:220px;
    height:220px;
    margin:auto;
    border-radius:50%;
    background:white;
    overflow:hidden;
    transform-style:preserve-3d;
    animation:rotateMug 6s linear infinite;
    box-shadow:0 5px 20px rgba(0,0,0,0.2);
}

.mug img{
    width:100%;
    height:100%;
    object-fit:cover;
}

@keyframes rotateMug{
    0%{transform:rotateY(0deg);}
    100%{transform:rotateY(360deg);}
}

.payment-buttons button{
    background:#6c5ce7;
}

.payment-buttons button:hover{
    background:#341f97;
}

footer{
    background:#2d3436;
    color:white;
    padding:20px;
    margin-top:40px;
}
</style>

<script>
function previewImage(event){
    var reader = new FileReader();
    reader.onload = function(){
        document.getElementById("previewImg").src = reader.result;
    }
    reader.readAsDataURL(event.target.files[0]);
}

function sendOrder(){
    var name = document.getElementById("name").value;
    var phone = document.getElementById("phone").value;
    var address = document.getElementById("address").value;
    var design = document.getElementById("design").value;

    var url = "https://wa.me/917760932963?text="
    + "New Mug Order%0A"
    + "Name: " + name + "%0A"
    + "Phone: " + phone + "%0A"
    + "Design: " + design + "%0A"
    + "Address: " + address;

    window.open(url, "_blank");
}
</script>

</head>

<body>

<header>
<h1>🎁 Yesh Gifts</h1>
<p>Upload Photo & Order Your Customized Mug ☕</p>
</header>

<div class="section">

<div class="form-box">

<input type="text" id="name" placeholder="Your Name" required>
<input type="tel" id="phone" placeholder="Your Phone Number" required>

<select id="design">
<option>Good Morning Mug - ₹299</option>
<option>Couple Mug - ₹349</option>
<option>Birthday Mug - ₹399</option>
<option>Best Friend Mug - ₹299</option>
</select>

<textarea id="address" placeholder="Delivery Address" required></textarea>

<label>Upload Your Image</label>
<input type="file" accept="image/*" onchange="previewImage(event)">

<div class="preview-wrapper">
<h3>360° Mug Preview</h3>
<div class="mug">
<img id="previewImg" src="https://via.placeholder.com/300" alt="Preview">
</div>
</div>

<button onclick="sendOrder()">Send Order on WhatsApp</button>

<div class="payment-buttons">
<a href="upi://pay?pa=7760932963@ybl&pn=Yesh%20Gifts&cu=INR">
<button type="button">Pay with PhonePe</button>
</a>

<a href="upi://pay?pa=7760932963@ybl&pn=Yesh%20Gifts&am=299&cu=INR">
    <button type="button">Pay with PhonePe</button>
</a>

</div>

<p>After payment, send screenshot on WhatsApp.</p>

</div>

</div>

<footer>
<p>📍 Bengaluru</p>
<p>📞 7760932963</p>
<p>© 2026 Yesh Gifts</p>
</footer>

</body>
</html>
