[index.html](https://github.com/user-attachments/files/25816019/index.html)
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
<html>
<head>
  <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
  <meta http-equiv="Content-Style-Type" content="text/css">
  <title></title>
  <meta name="Generator" content="Cocoa HTML Writer">
  <meta name="CocoaVersion" content="2575.7">
  <style type="text/css">
    body {background-color: #f2efe7}
    p.p1 {margin: 0.0px 0.0px 0.0px 0.0px; font: 12.0px 'Helvetica Neue'; color: #141310; -webkit-text-stroke: #141310}
    p.p2 {margin: 0.0px 0.0px 0.0px 0.0px; font: 12.0px 'Helvetica Neue'; color: #141310; -webkit-text-stroke: #141310; min-height: 15.0px}
    span.s1 {font-kerning: none}
  </style>
</head>
<body>
<p class="p1"><span class="s1">&lt;!DOCTYPE html&gt;</span></p>
<p class="p1"><span class="s1">&lt;html lang="zh-CN"&gt;</span></p>
<p class="p1"><span class="s1">&lt;head&gt;</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">    </span>&lt;meta charset="UTF-8"&gt;</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">    </span>&lt;title&gt;私人塔罗占卜空间&lt;/title&gt;</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">    </span>&lt;style&gt;</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">        </span>body { font-family: sans-serif; background: #1a1a2e; color: #fff; text-align: center; padding: 20px; }</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">        </span>.login-box { position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: #1a1a2e; z-index: 100; display: flex; flex-direction: column; align-items: center; justify-content: center; }</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">        </span>input { padding: 10px; border-radius: 5px; border: none; margin: 10px; width: 200px; }</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">        </span>button { padding: 10px 20px; background: #4e31aa; color: white; border: none; border-radius: 5px; cursor: pointer; }</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">        </span>.user-info { position: absolute; top: 10px; right: 10px; font-size: 14px; }</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">        </span>.card-area { margin-top: 50px; border: 2px dashed #4e31aa; padding: 40px; border-radius: 15px; }</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">    </span>&lt;/style&gt;</span></p>
<p class="p1"><span class="s1">&lt;/head&gt;</span></p>
<p class="p1"><span class="s1">&lt;body&gt;</span></p>
<p class="p2"><span class="s1"></span><br></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">    </span>&lt;div id="loginLayer" class="login-box"&gt;</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">        </span>&lt;h1&gt;✨ 塔罗占卜空间&lt;/h1&gt;</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">        </span>&lt;p&gt;输入昵称，开启你的专属记录空间&lt;/p&gt;</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">        </span>&lt;input type="text" id="nickName" placeholder="你的名字"&gt;</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">        </span>&lt;button onclick="joinSpace()"&gt;开启空间&lt;/button&gt;</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">    </span>&lt;/div&gt;</span></p>
<p class="p2"><span class="s1"></span><br></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">    </span>&lt;div id="mainLayer" style="display:none;"&gt;</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">        </span>&lt;div class="user-info"&gt;</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">            </span>当前空间：&lt;span id="showName"&gt;&lt;/span&gt; | &lt;a href="#" onclick="logout()" style="color:#aaa;"&gt;切换用户&lt;/a&gt;</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">        </span>&lt;/div&gt;</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">        </span>&lt;h1&gt;🔮 牌阵记录&lt;/h1&gt;</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">        </span>&lt;div class="card-area"&gt;</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">            </span>&lt;p&gt;点击下方按钮记录今日启示&lt;/p&gt;</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">            </span>&lt;textarea id="note" placeholder="写下你的感悟..." style="width:80%; height:100px; padding:10px;"&gt;&lt;/textarea&gt;&lt;br&gt;</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">            </span>&lt;button onclick="saveData()"&gt;存入我的空间&lt;/button&gt;</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">        </span>&lt;/div&gt;</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">        </span>&lt;div id="history"&gt;</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">            </span>&lt;h3&gt;--- 历史记录 ---&lt;/h3&gt;</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">            </span>&lt;ul id="historyList"&gt;&lt;/ul&gt;</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">        </span>&lt;/div&gt;</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">    </span>&lt;/div&gt;</span></p>
<p class="p2"><span class="s1"></span><br></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">    </span>&lt;script&gt;</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">        </span>let user = localStorage.getItem('tarot_user');</span></p>
<p class="p2"><span class="s1"></span><br></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">        </span>function checkUser() {</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">            </span>if(user) {</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">                </span>document.getElementById('loginLayer').style.display = 'none';</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">                </span>document.getElementById('mainLayer').style.display = 'block';</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">                </span>document.getElementById('showName').innerText = user;</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">                </span>loadHistory();</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">            </span>}</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">        </span>}</span></p>
<p class="p2"><span class="s1"></span><br></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">        </span>function joinSpace() {</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">            </span>let name = document.getElementById('nickName').value.trim();</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">            </span>if(!name) return alert("写个名字吧");</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">            </span>localStorage.setItem('tarot_user', name);</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">            </span>user = name;</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">            </span>checkUser();</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">        </span>}</span></p>
<p class="p2"><span class="s1"></span><br></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">        </span>function saveData() {</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">            </span>let note = document.getElementById('note').value;</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">            </span>if(!note) return alert("写点内容再保存");</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">            </span>let key = 'tarot_data_' + user;</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">            </span>let data = JSON.parse(localStorage.getItem(key) || '[]');</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">            </span>data.unshift({time: new Date().toLocaleString(), content: note});</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">            </span>localStorage.setItem(key, JSON.stringify(data));</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">            </span>document.getElementById('note').value = '';</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">            </span>loadHistory();</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">        </span>}</span></p>
<p class="p2"><span class="s1"></span><br></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">        </span>function loadHistory() {</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">            </span>let key = 'tarot_data_' + user;</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">            </span>let data = JSON.parse(localStorage.getItem(key) || '[]');</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">            </span>let html = data.map(i =&gt; `&lt;li&gt;[${i.time}] ${i.content}&lt;/li&gt;`).join('');</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">            </span>document.getElementById('historyList').innerHTML = html;</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">        </span>}</span></p>
<p class="p2"><span class="s1"></span><br></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">        </span>function logout() {</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">            </span>localStorage.removeItem('tarot_user');</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">            </span>location.reload();</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">        </span>}</span></p>
<p class="p2"><span class="s1"></span><br></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">        </span>checkUser();</span></p>
<p class="p1"><span class="s1"><span class="Apple-converted-space">    </span>&lt;/script&gt;</span></p>
<p class="p1"><span class="s1">&lt;/body&gt;</span></p>
<p class="p1"><span class="s1">&lt;/html&gt;</span></p>
</body>
</html>
