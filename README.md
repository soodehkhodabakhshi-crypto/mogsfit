
<!DOCTYPE html>
<html lang="fa">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MOGS.FIT</title>
<style>
    body {
        font-family: Arial, sans-serif;
        background: url('mogsfit_bg.png') no-repeat center center fixed;
        background-size: cover;
        margin: 0;
        padding: 0;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        direction: rtl;
    }
    .form-container {
        background: rgba(255, 255, 255, 0.9);
        padding: 20px;
        border-radius: 12px;
        box-shadow: 0 0 15px rgba(0,0,0,0.2);
        max-width: 350px;
        width: 100%;
    }
    h2 {
        text-align: center;
        margin-bottom: 20px;
        color: #333;
    }
    label {
        font-weight: bold;
        margin-top: 10px;
        display: block;
    }
    input, select, button {
        width: 100%;
        padding: 10px;
        margin-top: 5px;
        border: 1px solid #ccc;
        border-radius: 8px;
        font-size: 14px;
    }
    button {
        background-color: #007BFF;
        color: white;
        border: none;
        cursor: pointer;
        font-size: 16px;
        margin-top: 15px;
    }
    button:hover {
        background-color: #0056b3;
    }
</style>
</head>
<body>

<div class="form-container">
    <h2>فرم ورزشی MOGS.FIT</h2>
    <form id="fitnessForm">
        <label>نام:</label>
        <input type="text" name="firstName" required>

        <label>نام خانوادگی:</label>
        <input type="text" name="lastName" required>

        <label>سن:</label>
        <input type="number" name="age" required>

        <label>وزن (کیلوگرم):</label>
        <input type="number" name="weight" required>

        <label>قد (سانتی‌متر):</label>
        <input type="number" name="height" required>

        <label>جنسیت:</label>
        <select name="gender" required>
            <option value="">انتخاب کنید</option>
            <option value="male">مرد</option>
            <option value="female">زن</option>
        </select>

        <label>میزان فعالیت روزانه:</label>
        <select name="activity" required>
            <option value="">انتخاب کنید</option>
            <option value="low">کم</option>
            <option value="medium">متوسط</option>
            <option value="high">زیاد</option>
        </select>

        <button type="submit">ارسال</button>
    </form>
</div>

<script>
document.getElementById('fitnessForm').addEventListener('submit', function(e) {
    e.preventDefault();

    const formData = new FormData(this);
    fetch("https://script.google.com/macros/s/AKfycbw061ivBdzqPk-Nphb7DrLniAMJlAFS8R5vH9ps9UgzPeLdvjrec2hZz9Dja5IYN8ScDg/exec", {
        method: "POST",
        body: formData
    })
    .then(response => {
        alert("اطلاعات شما با موفقیت ارسال شد ✅");
        this.reset();
    })
    .catch(error => {
        alert("خطا در ارسال اطلاعات ❌");
        console.error(error);
    });
});
</script>

</body>
</html>

