<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>神秘塔罗空间</title>
    <style>
        /* 样式：确保深色背景和白色文字，即便加载慢也不会白屏 */
        body { 
            margin: 0; padding: 0; 
            background-color: #1a1a2e; 
            color: #e0e0e0; 
            font-family: "Microsoft YaHei", sans-serif;
            display: flex; justify-content: center; align-items: center;
            min-height: 100vh;
        }
        .container {
            width: 90%; max-width: 400px;
            background: #16213e;
            padding: 30px; border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
            border: 1px solid #4e31aa;
            text-align: center;
        }
        h1 { color: #a29bfe; margin-bottom: 10px; }
        input {
            width: 100%; padding: 12px; margin: 15px 0;
            border-radius: 8px; border: 1px solid #4e31aa;
            background: #0f3460; color: white; box-sizing: border-box;
        }
        button {
            width: 100%; padding: 12px;
            background: #6c5ce7; color: white;
            border: none; border-radius: 8px;
            cursor: pointer; font-size: 16px; font-weight: bold;
        }
        button:hover { background: #a29bfe; }
        .record-item {
            text-align: left; background: #0f3460;
            padding: 10px; margin-top: 10px;
            border-radius: 5px; font-size: 14px;
            border-left: 3px solid #6c5ce7;
        }
        #mainSpace { display: none; }
    </style>
</head>
<body>

    <div class="container">
        <div id="loginView">
            <h1>🔮 塔罗空间</h1>
            <p>输入昵称进入你的专属领域</p>
            <input type="text" id="nameInput" placeholder="你的灵性昵称...">
            <button onclick="startSession()">开启连接</button>
        </div>

        <div id="mainSpace">
            <h2 id="welcomeText"></h2>
            <textarea id="tarotNote" style="width:100%; height:80px; margin-bottom:10px; border-radius:5px; padding:5px;" placeholder="记录今日牌阵感悟..."></textarea>
            <button onclick="saveRecord()">存入星空记录</button>
            <div id="historyLogs" style="margin-top:20px; max-height: 300px; overflow-y: auto;"></div>
            <p style="margin-top:20px;"><a href="javascript:void(0)" onclick="clearUser()" style="color:#aaa; font-size:12px;">切换账号</a></p>
        </div>
    </div>

    <script>
        // 核心逻辑：确保页面加载完成后执行
        window.onload = function() {
            const savedUser = localStorage.getItem('active_tarot_user');
            if (savedUser) {
                showSpace(savedUser);
            }
        };

        function startSession() {
            const name = document.getElementById('nameInput').value.trim();
            if (!name) return alert("请先输入昵称");
            localStorage.setItem('active_tarot_user', name);
            showSpace(name);
        }

        function showSpace(name) {
            document.getElementById('loginView').style.display = 'none';
            document.getElementById('mainSpace').style.display = 'block';
            document.getElementById('welcomeText').innerText = "你好, " + name;
            renderHistory(name);
        }

        function saveRecord() {
            const user = localStorage.getItem('active_tarot_user');
            const note = document.getElementById('tarotNote').value.trim();
            if (!note) return alert("内容不能为空");

            const key = "tarot_records_" + user;
            let data = JSON.parse(localStorage.getItem(key) || "[]");
            data.unshift({ time: new Date().toLocaleString(), text: note });
            localStorage.setItem(key, JSON.stringify(data));
            
            document.getElementById('tarotNote').value = "";
            renderHistory(user);
        }

        function renderHistory(user) {
            const key = "tarot_records_" + user;
            const data = JSON.parse(localStorage.getItem(key) || "[]");
            const logDiv = document.getElementById('historyLogs');
            logDiv.innerHTML = data.length ? "" : "<p style='color:#777'>尚无记录</p>";
            data.forEach(item => {
                logDiv.innerHTML += `<div class="record-item"><b>${item.time}</b><br>${item.text}</div>`;
            });
        }

        function clearUser() {
            localStorage.removeItem('active_tarot_user');
            location.reload();
        }
    </script>
</body>
</html>
