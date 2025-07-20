<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>متجر الاشتراكات - FORJA VIP</title>
  <style>
    body {
      font-family: 'Arial', sans-serif;
      background-color: #f4f4f4;
      margin: 0;
      padding: 0;
      direction: rtl;
      text-align: right;
    }
    header {
      background-color: #222;
      color: white;
      padding: 15px;
      text-align: center;
    }
    .container {
      padding: 20px;
    }
    .package {
      background: white;
      border-radius: 10px;
      padding: 15px;
      margin-bottom: 20px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    }
    .package h3 {
      margin-top: 0;
    }
    button {
      padding: 10px 20px;
      background-color: #1e90ff;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    form {
      background: white;
      padding: 15px;
      border-radius: 10px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    }
    input, select {
      width: 100%;
      padding: 10px;
      margin-top: 10px;
      margin-bottom: 15px;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
  </style>
</head>
<body>

<header>
  <h1>متجر الاشتراكات الرقمية - FORJA VIP</h1>
</header>

<div class="container">

  <div id="home">
    <h2>اختر الباقة:</h2>

    <div class="package">
      <h3>نتفليكس</h3>
      <button onclick="showDetails('Netflix')">عرض التفاصيل</button>
    </div>

    <div class="package">
      <h3>شاهد</h3>
      <button onclick="showDetails('Shahid')">عرض التفاصيل</button>
    </div>

    <div class="package">
      <h3>برايم فيديو</h3>
      <button onclick="showDetails('Prime Video')">عرض التفاصيل</button>
    </div>

    <div class="package">
      <h3>Watch It</h3>
      <button onclick="showDetails('Watch It')">عرض التفاصيل</button>
    </div>
  </div>

  <div id="details" style="display:none;">
    <h2 id="packageTitle">تفاصيل الباقة:</h2>
    <button onclick="selectPlan('شهر')">شهر - 20 دينار</button><br><br>
    <button onclick="selectPlan('3 أشهر')">3 أشهر - 50 دينار</button><br><br>
    <button onclick="selectPlan('سنة')">سنة - 90 دينار</button><br><br>
    <button onclick="goBack()">⬅ رجوع</button>
  </div>

  <div id="formSection" style="display:none;">
    <h2>معلومات الدفع</h2>
    <form>
      <label>الاسم الكامل:</label>
      <input type="text" placeholder="اكتب اسمك الكامل">

      <label>البريد الإلكتروني:</label>
      <input type="email" placeholder="example@email.com">

      <label>رقم واتساب:</label>
      <input type="text" placeholder="09XXXXXXXX">

      <label>المنصة المختارة:</label>
      <input type="text" id="selectedPlatform" readonly>

      <label>المدة المختارة:</label>
      <input type="text" id="selectedPlan" readonly>

      <label>اختر وسيلة الدفع:</label>
      <select>
        <option>كارت ليبيانا</option>
        <option>رسيل ليبيانا</option>
      </select>

      <button type="submit">إرسال الطلب</button>
    </form>
    <br>
    <button onclick="goBack()">⬅ رجوع</button>
  </div>

</div>

<script>
  let platform = "";
  let plan = "";

  function showDetails(selected) {
    platform = selected;
    document.getElementById("home").style.display = "none";
    document.getElementById("details").style.display = "block";
    document.getElementById("packageTitle").innerText = "تفاصيل باقة " + selected;
  }

  function selectPlan(selectedPlan) {
    plan = selectedPlan;
    document.getElementById("details").style.display = "none";
    document.getElementById("formSection").style.display = "block";
    document.getElementById("selectedPlatform").value = platform;
    document.getElementById("selectedPlan").value = plan;
  }

  function goBack() {
    document.getElementById("formSection").style.display = "none";
    document.getElementById("details").style.display = "none";
    document.getElementById("home").style.display = "block";
  }
</script>

</body>
</html>
