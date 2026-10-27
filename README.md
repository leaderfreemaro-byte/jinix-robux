# jinix-robux
from pathlib import Path

html = r'''<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>JINIX ROBUX</title>
<style>
:root{--bg:#0a0b16;--panel:#15162a;--panel2:#20213b;--line:#343653;--purple:#9165ff;--cyan:#43d8ff;--green:#38e0a2;--muted:#aaaecb;--white:#f7f7ff}
*{box-sizing:border-box}body{margin:0;background:radial-gradient(ellipse at top,#25124a 0,#0a0b16 48%);color:var(--white);font-family:system-ui,Arial,sans-serif;min-height:100vh}
header{text-align:center;padding:24px 15px 12px}.brand{display:flex;align-items:center;justify-content:center;gap:11px;font-weight:950;font-size:clamp(26px,7vw,38px);letter-spacing:.5px}.mark{width:48px;height:48px;border-radius:15px;display:grid;place-items:center;background:linear-gradient(135deg,var(--purple),var(--cyan));color:#fff;box-shadow:0 0 28px #9165ff55}.brandname{background:linear-gradient(90deg,#fff,var(--cyan));-webkit-background-clip:text;background-clip:text;color:transparent}.tag{color:var(--muted);font-size:13px;margin:8px 0 0}
main{max-width:780px;margin:auto;padding:12px 14px 35px}.notice{background:#251b3e;border:1px solid #60468e;padding:12px 14px;border-radius:14px;font-size:13px;line-height:1.8;margin:10px 0 16px;color:#eee4ff}
.stats{display:grid;grid-template-columns:repeat(2,1fr);gap:10px}.stat,.box{background:linear-gradient(145deg,#191a31,#111222);border:1px solid var(--line);border-radius:17px;padding:16px;box-shadow:0 12px 25px #0002}.muted{color:var(--muted);font-size:13px;line-height:1.7}.num{font-size:26px;font-weight:900;margin-top:4px}.num small{font-size:12px;color:var(--cyan)}
.box{margin-top:14px}.heading{display:flex;align-items:center;gap:9px;font-size:19px;font-weight:850;margin:0 0 7px}.desc{margin:0 0 13px}.field{margin-top:12px}label{display:block;font-size:13px;margin-bottom:6px;color:#e5e5ff}input{width:100%;padding:13px;border-radius:11px;border:1px solid #3b3e60;background:#0c0d1a;color:#fff;font:inherit;outline:none}input:focus{border-color:var(--purple)}
button{font:inherit;font-weight:800;border:0;border-radius:11px;padding:12px 14px;cursor:pointer}button:active{transform:scale(.99)}.primary{width:100%;margin-top:12px;background:linear-gradient(90deg,var(--purple),#5d72ff);color:white}.secondary{background:#292745;color:#eee8ff;border:1px solid #444465}.green{background:linear-gradient(90deg,#0da77c,var(--green));color:#05271e;width:100%;margin-top:12px}
.grid{display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:10px}.challenge{padding:13px;border-radius:13px;background:#101122;border:1px solid #2e304d}.challenge .emoji{font-size:23px}.challenge b{display:block;margin:5px 0}.challenge p{font-size:12px;color:var(--muted);line-height:1.6;min-height:38px;margin:0 0 10px}.challenge button{width:100%;font-size:12px;padding:10px}.challenge button:disabled{opacity:.45;cursor:not-allowed}
.task{display:flex;align-items:center;gap:10px;background:#101122;border:1px solid #2e304d;border-radius:13px;padding:12px;margin-top:10px}.task .icon{font-size:24px}.task .copy{flex:1}.copy b{display:block;font-size:14px}.copy span{font-size:12px;color:var(--muted)}.task button{font-size:12px;padding:9px;white-space:nowrap}
.bar{height:8px;background:#2c2e48;border-radius:10px;overflow:hidden;margin-top:13px}.bar>div{height:100%;width:0;background:linear-gradient(90deg,var(--purple),var(--cyan));transition:width .2s}.status{display:none;margin-top:11px;background:#101122;border-radius:10px;padding:10px;font-size:13px;line-height:1.7;color:#dedcff}.listitem{border-bottom:1px solid #2c2e48;padding:11px 0;font-size:13px;line-height:1.7}.listitem:last-child{border:0}.badge{display:inline-block;background:#393052;color:#e6d9ff;border-radius:20px;padding:3px 8px;font-size:11px;margin-right:5px}
footer{text-align:center;padding:0 15px 24px;color:#8588a6;font-size:12px;line-height:1.8}a{color:#81dcff}
@media(max-width:390px){.grid{gap:8px}.challenge{padding:10px}.stat{padding:13px}.num{font-size:23px}.task{gap:7px}}
</style>
</head>
<body>
<header>
 <div class="brand"><span class="mark">J</span><span class="brandname">JINIX ROBUX</span></div>
 <p class="tag">التحديات • النقاط • الإعلانات • طلبات المكافآت</p>
</header>
<main>
 <div class="notice"><b>نسخة تجريبية:</b> هاد الموقع ما كيوفرش Robux حقيقية دابا. النقاط والطلبات غير للتجربة ومحفوظة فهاد الجهاز فقط. ما تدخلش كلمة السر ديال Roblox ولا معلومات الأداء. خاص التأكد من شروط Roblox ومنصة الإعلانات قبل أي مكافآت حقيقية.</div>
 <div class="stats">
  <div class="stat"><div class="muted">النقاط ديالك</div><div class="num" id="points">0 <small>نقطة</small></div></div>
  <div class="stat"><div class="muted">الحد الأدنى لطلب المكافأة</div><div class="num">100 <small>Robux (تجريبي)</small></div></div>
 </div>

 <section class="box">
  <h2 class="heading">👤 الملف الشخصي</h2><p class="muted desc">كتب اسم حساب Roblox فقط. ما كنطلبوش كلمة السر.</p>
  <label for="username">اسم المستخدم</label><input id="username" maxlength="20" autocomplete="off" placeholder="مثال: Player123">
  <button class="primary" id="save">حفظ الاسم فهاد الجهاز</button><div class="status" id="profileStatus"></div>
 </section>

 <section class="box">
  <h2 class="heading">🎮 التحديات والمسابقات</h2><p class="muted desc">كمّل تحديات تجريبية وجمع نقاط. النقاط ما عندهاش قيمة نقدية.</p>
  <div class="grid">
   <div class="challenge"><div class="emoji">🧠</div><b>تحدي المعرفة</b><p>جاوب على سؤال تجريبي باش تجمع 5 نقاط.</p><button class="secondary" data-challenge="quiz">ابدأ التحدي</button></div>
   <div class="challenge"><div class="emoji">⭐</div><b>تسجيل الدخول اليومي</b><p>مكافأة تجريبية يومية قدرها 5 نقاط.</p><button class="secondary" data-challenge="daily">جمع النقاط</button></div>
   <div class="challenge"><div class="emoji">🎯</div><b>تحدي اليوم</b><p>كمّل تحدي بسيط وخذ 10 نقاط تجريبية.</p><button class="secondary" data-challenge="dailychallenge">ابدأ التحدي</button></div>
   <div class="challenge"><div class="emoji">🏆</div><b>مسابقة الأسبوع</b><p>نظام ترتيب تجريبي، بلا جوائز حقيقية.</p><button class="secondary" data-challenge="contest">شوف المسابقة</button></div>
  </div>
  <div class="bar"><div id="bar"></div></div><p class="muted" id="barText">0 من 100 نقطة تجريبية.</p><div class="status" id="challengeStatus"></div>
 </section>

 <section class="box">
  <h2 class="heading">📺 الإعلانات</h2><p class="muted desc">ما كاين حتى إعلان حقيقي مربوط بهاد النسخة. ما تضغطش على إعلانات بهدف رفع الأرباح بطريقة مصطنعة. خاصنا من بعد منصة كتسمح صراحةً بالمكافآت.</p>
  <div class="task"><div class="icon">📺</div><div class="copy"><b>إعلان تجريبي</b><span>محاكاة فقط — 10 نقاط</span></div><button class="secondary" id="adDemo">جرّب</button></div>
  <div class="status" id="adStatus"></div>
 </section>

 <section class="box">
  <h2 class="heading">🎁 طلب المكافأة</h2><p class="muted desc">الحد الأدنى 100 Robux فالتصميم، ولكن هاد الطلب تجريبي وغير مرسل لأي جهة.</p>
  <label for="amount">عدد Robux المطلوب</label><input id="amount" type="number" min="100" step="1" value="100" inputmode="numeric">
  <button class="green" id="request">إنشاء طلب تجريبي</button><div class="status" id="requestStatus"></div>
 </section>

 <section class="box">
  <h2 class="heading">📋 طلباتي</h2><div id="history" class="muted">ما كاين حتى طلب تجريبي.</div>
  <button class="secondary" id="reset" style="width:100%;margin-top:12px">مسح بيانات التجربة</button>
 </section>
</main>
<footer>JINIX ROBUX — نموذج تجريبي غير رسمي وماشي تابع لـ Roblox.<br>ما كايناش إعلانات فعلية ولا مكافآت حقيقية فهاد الملف.</footer>
<script>
const $=id=>document.getElementById(id), KEY='jinixRobuxFullDemoV2';
let s={username:'',points:0,history:[],done:{},dailyDate:''};
try{const v=JSON.parse(localStorage.getItem(KEY)||'null');if(v&&typeof v==='object')s={...s,...v}}catch(e){}
function save(){try{localStorage.setItem(KEY,JSON.stringify(s))}catch(e){}}
function validName(n){return /^[A-Za-z0-9_]{3,20}$/.test(n)}
function msg(id,t){$(id).textContent=t;$(id).style.display='block'}
function add(n){s.points+=n;save();render()}
function render(){
 $('points').innerHTML=`${s.points} <small>نقطة</small>`;$('username').value=s.username||'';
 $('bar').style.width=Math.min(100,s.points)+'%';$('barText').textContent=`${s.points} من 100 نقطة تجريبية. هاد النقاط ما كتتحولش تلقائياً لRobux.`;
 document.querySelectorAll('[data-challenge]').forEach(b=>{const k=b.dataset.challenge;b.disabled=!!s.done[k];if(s.done[k])b.textContent='تمت التجربة'});
 const h=$('history');h.innerHTML='';
 if(!s.history.length)h.textContent='ما كاين حتى طلب تجريبي.';
 [...s.history].reverse().forEach(x=>{const d=document.createElement('div');d.className='listitem';d.textContent=`${x.date} — ${x.amount} Robux — `;const badge=document.createElement('span');badge.className='badge';badge.textContent='تجريبي / غير مرسل';d.appendChild(badge);h.appendChild(d)});
}
$('save').onclick=()=>{const n=$('username').value.trim();if(!validName(n)){msg('profileStatus','دخل اسم مستخدم صالح من 3 حتى 20 حرف أو رقم أو _.');return} s.username=n;save();render();msg('profileStatus','تحفظ الاسم فهاد الجهاز فقط؛ ما تصيفط حتى شي معلومة للسيرفر.')};
document.querySelectorAll('[data-challenge]').forEach(b=>b.onclick=()=>{
 const k=b.dataset.challenge;
 if(k==='quiz'){const answer=prompt('تحدي تجريبي: شحال هي 2 + 2؟');if(answer===null)return;if(answer.trim()!=='4'){msg('challengeStatus','الجواب ماشي صحيح. جرّب مرة أخرى.');return}if(!s.done[k]){s.done[k]=true;add(5);msg('challengeStatus','مزيان! تزادت 5 نقاط تجريبية.')}return}
 if(k==='daily'){const today=new Date().toISOString().slice(0,10);if(s.dailyDate===today){msg('challengeStatus','خديتي نقاط اليوم من قبل فهاد الجهاز.');return}s.dailyDate=today}
 if(k==='contest'){msg('challengeStatus','المسابقة والترتيب غير تجريبيين دابا؛ ما كايناش جوائز حقيقية.');return}
 if(!s.done[k]){s.done[k]=true;const n=k==='daily'?5:10;add(n);msg('challengeStatus',`تزادت ${n} نقاط تجريبية.`)}
});
$('adDemo').onclick=()=>{add(10);msg('adStatus','تزادت 10 نقاط تجريبية فقط. ما تشاف حتى إعلان حقيقي وما تربح حتى Robux.')};
$('request').onclick=()=>{
 const n=$('username').value.trim(),a=Number($('amount').value);
 if(!validName(n)){msg('requestStatus','حفظ اسم Roblox صالح أولاً.');return}
 if(!Number.isInteger(a)||a<100){msg('requestStatus','الحد الأدنى التجريبي هو 100 Robux.');return}
 if(s.points<100){msg('requestStatus','خاصك 100 نقطة تجريبية على الأقل باش تنشئ نموذج الطلب.');return}
 s.username=n;s.history.push({amount:a,date:new Date().toLocaleString('ar-MA')});save();render();
 msg('requestStatus','تسجل نموذج الطلب فهاد الجهاز فقط. ما وصل حتى شي طلب للموقع وما غاديش توصلك Robux حقيقية.');
};
$('reset').onclick=()=>{if(confirm('واش متأكد بغيتي تمسح بيانات التجربة؟')){s={username:'',points:0,history:[],done:{},dailyDate:''};try{localStorage.removeItem(KEY)}catch(e){}document.querySelectorAll('.status').forEach(x=>x.style.display='none');render()}};
render();
</script>
</body></html>'''
path = Path("/mnt/data/jinix_robux_full_demo.html")
path.write_text(html, encoding="utf-8")
print(f"Created {path} ({path.stat().st_size} bytes)")
