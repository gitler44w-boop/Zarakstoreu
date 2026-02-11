<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>ZARAKI SHOP</title>

<style>
:root{
  --bg:#05030a;
  --bg2:#0b0616;
  --card:rgba(20,12,35,.78);
  --stroke:rgba(159,91,255,.35);
  --stroke2:rgba(255,255,255,.08);
  --violet:#9f5bff;
  --violet2:#6d28ff;
  --text:#f3edff;
  --muted:#c9b8ff;
  --radius:22px;
  --shadow: 0 22px 70px rgba(0,0,0,.62);
}

*{box-sizing:border-box}
body{
  margin:0;
  font-family:system-ui,-apple-system,"Segoe UI",Roboto,Arial,sans-serif;
  color:var(--text);
  background:
    radial-gradient(900px 550px at 20% -10%, rgba(159,91,255,.27), transparent 60%),
    radial-gradient(900px 550px at 90% 10%, rgba(109,40,255,.25), transparent 60%),
    linear-gradient(180deg,var(--bg),var(--bg2));
}
a{color:inherit;text-decoration:none}
.wrap{max-width:1000px;margin:auto;padding:22px 14px 60px}

/* ===== Top ===== */
.top{
  display:flex;
  align-items:center;
  justify-content:space-between;
  gap:12px;
  margin-bottom:14px;
}
.brand{
  display:flex;
  flex-direction:column;
  gap:4px;
}
.brand .name{
  font-size:34px;
  font-weight:1000;
  letter-spacing:3px;
  background:linear-gradient(90deg,var(--violet),#fff,var(--violet2));
  -webkit-background-clip:text;
  -webkit-text-fill-color:transparent;
}
.brand .sub{
  font-size:12px;
  color:rgba(201,184,255,.9);
  letter-spacing:1px;
}
.pill{
  padding:10px 12px;
  border-radius:999px;
  border:1px solid var(--stroke2);
  background:rgba(255,255,255,.03);
  color:var(--muted);
  font-size:13px;
  white-space:nowrap;
}

/* ===== Main Card ===== */
.shell{
  position:relative;
  border-radius:var(--radius);
  padding:18px;
  border:1px solid var(--stroke);
  background:linear-gradient(180deg, rgba(25,15,45,.82), rgba(10,6,18,.88));
  box-shadow:var(--shadow);
  overflow:hidden;
}
.shell::before{
  content:"";
  position:absolute;
  inset:-2px;
  background:
    radial-gradient(420px 240px at 20% 10%, rgba(159,91,255,.35), transparent 60%),
    radial-gradient(420px 240px at 90% 20%, rgba(109,40,255,.28), transparent 60%);
  filter: blur(10px);
  pointer-events:none;
}
.shell > *{position:relative}

.headline{
  display:flex;
  flex-wrap:wrap;
  align-items:center;
  gap:10px;
}
.title{
  font-size:18px;
  font-weight:900;
}
.kicker{
  font-size:13px;
  color:var(--muted);
}
.hr{
  height:1px;
  margin:14px 0;
  background:linear-gradient(90deg, transparent, rgba(159,91,255,.55), transparent);
}

/* ===== Menu Buttons ===== */
.menu{
  display:grid;
  grid-template-columns:repeat(4, 1fr);
  gap:12px;
  margin-top:10px;
}
@media(max-width:860px){ .menu{grid-template-columns:repeat(2,1fr)} }
@media(max-width:460px){ .menu{grid-template-columns:1fr} }

.tab{
  border:none;
  cursor:pointer;
  padding:14px 12px;
  border-radius:18px;
  font-weight:900;
  color:var(--text);
  background:rgba(255,255,255,.04);
  border:1px solid rgba(159,91,255,.35);
  transition:.18s;
  text-align:center;
}
.tab:hover{ transform:translateY(-2px); box-shadow:0 0 26px rgba(159,91,255,.45); }
.tab.active{
  background:linear-gradient(135deg, rgba(159,91,255,.38), rgba(109,40,255,.24));
  border-color: rgba(159,91,255,.65);
}

/* ===== Panels ===== */
.panels{ margin-top:14px; }
.panel{
  display:none;
  padding:16px;
  border-radius:var(--radius);
  border:1px solid var(--stroke2);
  background:rgba(0,0,0,.22);
}
.panel.show{ display:block; }

.h2{
  margin:0 0 10px;
  font-size:16px;
  font-weight:950;
  display:flex;
  align-items:center;
  gap:10px;
}
.tag{
  font-size:12px;
  color:var(--muted);
  border:1px solid rgba(159,91,255,.22);
  background:rgba(159,91,255,.08);
  padding:7px 10px;
  border-radius:999px;
}

.list{ display:grid; gap:10px; margin-top:10px; }
.item{
  display:flex;
  justify-content:space-between;
  gap:12px;
  padding:12px 14px;
  border-radius:16px;
  border:1px solid rgba(255,255,255,.06);
  background:rgba(10,7,16,.45);
}
.left{ display:flex; flex-direction:column; gap:3px; min-width:0; }
.it-title{ font-weight:950; font-size:14px; line-height:1.2; }
.it-desc{ color:var(--muted); font-size:12px; line-height:1.35; }
.price{ font-weight:1000; white-space:nowrap; text-align:right; }
.price small{ display:block; color:var(--muted); font-weight:800; margin-top:2px; }

.ctaRow{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:12px;
  margin-top:12px;
}
@media(max-width:560px){ .ctaRow{grid-template-columns:1fr} }

.btn{
  display:flex;
  justify-content:center;
  align-items:center;
  gap:10px;
  padding:14px 12px;
  border-radius:18px;
  font-weight:950;
  border:1px solid rgba(159,91,255,.35);
  background:rgba(255,255,255,.04);
  cursor:pointer;
  transition:.18s;
}
.btn:hover{ transform:translateY(-2px); box-shadow:0 0 26px rgba(159,91,255,.45); }
.btn.primary{ background:linear-gradient(135deg, rgba(159,91,255,.38), rgba(109,40,255,.24)); }

.note{
  margin-top:12px;
  padding:12px 14px;
  border-radius:16px;
  border:1px solid rgba(159,91,255,.18);
  background:rgba(159,91,255,.06);
  color:rgba(243,237,255,.92);
  font-size:13px;
  line-height:1.45;
}

.footer{
  margin-top:16px;
  text-align:center;
  font-size:12px;
  color:rgba(201,184,255,.85);
}
</style>
</head>

<body>
<div class="wrap">

  <div class="top">
    <div class="brand">
      <div class="name">ZARAKI SHOP</div>
      <div class="sub">🩸 DARK CODING SERVICE • BOT • WEB • PRIVATE</div>
    </div>
    <div class="pill">⚡️ Быстро | Чётко | Без воды</div>
  </div>

  <section class="shell">
    <div class="headline">
      <div class="title">adapter zaraki shop</div>
      <div class="kicker">Нажмите кнопку — блок откроется</div>
    </div>

    <div class="hr"></div>

    <!-- MENU -->
    <div class="menu">
      <button class="tab active" data-tab="bots">🤖 TELEGRAM-БОТЫ</button>
      <button class="tab" data-tab="web">🌐 WEB / САЙТЫ</button>
      <button class="tab" data-tab="nums">📱 ФИЗ. НОМЕРА</button>
      <button class="tab" data-tab="contact">💬 КОНТАКТЫ</button>
    </div>

    <!-- PANELS -->
    <div class="panels">

      <!-- BOTS -->
      <div class="panel show" id="bots">
        <div class="h2">🤖 TELEGRAM-БОТЫ <span class="tag">Логи / Продажи / Custom</span></div>
        <div class="list">
          <div class="item">
            <div class="left">
              <div class="it-title">🃏 ОТС-бот с логами</div>
              <div class="it-desc">Админка / логи / сценарии под вашу схему</div>
            </div>
            <div class="price">500⭐️ <small>| 5$</small></div>
          </div>
          <div class="item">
            <div class="left">
              <div class="it-title">🛒 Бот для продаж</div>
              <div class="it-desc">Каталог / заказы / выдача / авто-ответы</div>
            </div>
            <div class="price">100⭐️ <small>| 1.5$</small></div>
          </div>
          <div class="item">
            <div class="left">
              <div class="it-title">💬 Автоответы / FAQ</div>
              <div class="it-desc">Меню / быстрые ответы / сценарии</div>
            </div>
            <div class="price">80⭐️ <small>| 1$</small></div>
          </div>
          <div class="item">
            <div class="left">
              <div class="it-title">🧬 Кастом-бот по ТЗ</div>
              <div class="it-desc">PRIVATE PRICE — цена договорная</div>
            </div>
            <div class="price">PRIVATE <small>| PRICE</small></div>
          </div>
        </div>

<div class="ctaRow">
          <a class="btn primary" href="https://t.me/User_Zaraki" target="_blank" rel="noopener">🛒 За покупкой @User_Zaraki</a>
          <a class="btn" href="https://t.me/XDpih" target="_blank" rel="noopener">⭐️ Отзывы</a>
        </div>
        <div class="note">Пишите сразу: что нужно + сроки + пример/референс. Оплата: ⭐️ Stars / $.</div>
      </div>

      <!-- WEB -->
      <div class="panel" id="web">
        <div class="h2">🌐 WEB / САЙТЫ <span class="tag">Лендинг / Формы / Custom</span></div>
        <div class="list">
          <div class="item">
            <div class="left">
              <div class="it-title">🕷 Лендинг</div>
              <div class="it-desc">Стиль / кнопки / блоки / адаптив</div>
            </div>
            <div class="price">150⭐️ <small>| 2$</small></div>
          </div>
          <div class="item">
            <div class="left">
              <div class="it-title">🧱 Многостраничный сайт</div>
              <div class="it-desc">Структура / страницы / навигация</div>
            </div>
            <div class="price">300⭐️ <small>| 4$</small></div>
          </div>
          <div class="item">
            <div class="left">
              <div class="it-title">📥 Сайт + форма заявок</div>
              <div class="it-desc">Форма / заявки / отправка в Telegram</div>
            </div>
            <div class="price">350⭐️ <small>| 5$</small></div>
          </div>
          <div class="item">
            <div class="left">
              <div class="it-title">⚙️ Кастом-WEB по ТЗ</div>
              <div class="it-desc">PRIVATE PRICE — цена договорная</div>
            </div>
            <div class="price">PRIVATE <small>| PRICE</small></div>
          </div>
        </div>

        <div class="ctaRow">
          <a class="btn primary" href="https://t.me/User_Zaraki" target="_blank" rel="noopener">💬 Обсудить сайт</a>
          <a class="btn" href="#top" onclick="return false;">⬆️ Наверх</a>
        </div>
      </div>

      <!-- NUMBERS -->
      <div class="panel" id="nums">
        <div class="h2">📱 ФИЗИЧЕСКИЕ НОМЕРА <span class="tag">Наличие уточняйте</span></div>
        <div class="list">
          <div class="item"><div class="left"><div class="it-title">🇺🇸 +1</div><div class="it-desc">Физ. номер</div></div><div class="price">65⭐️ <small>| 0.7$</small></div></div>
          <div class="item"><div class="left"><div class="it-title">🇷🇺 +7</div><div class="it-desc">Физ. номер</div></div><div class="price">300⭐️ <small>| 3.5$</small></div></div>
          <div class="item"><div class="left"><div class="it-title">🇰🇿 +7</div><div class="it-desc">Физ. номер</div></div><div class="price">100⭐️ <small>| 1$</small></div></div>
          <div class="item"><div class="left"><div class="it-title">🇧🇾 +375</div><div class="it-desc">Физ. номер</div></div><div class="price">150⭐️ <small>| 2$</small></div></div>
          <div class="item"><div class="left"><div class="it-title">🇺🇦 +380</div><div class="it-desc">Физ. номер</div></div><div class="price">150⭐️ <small>| 2$</small></div></div>
          <div class="item"><div class="left"><div class="it-title">🇹🇷 +90</div><div class="it-desc">Физ. номер</div></div><div class="price">65⭐️ <small>| 0.7$</small></div></div>
          <div class="item"><div class="left"><div class="it-title">🇦🇷 +54</div><div class="it-desc">Физ. номер</div></div><div class="price">75⭐️ <small>| 0.8$</small></div></div>
          <div class="item"><div class="left"><div class="it-title">🇺🇿 +998</div><div class="it-desc">Физ. номер</div></div><div class="price">150⭐️ <small>| 1.5$</small></div></div>
          <div class="item"><div class="left"><div class="it-title">🇧🇷 +55</div><div class="it-desc">Физ. номер</div></div><div class="price">100⭐️ <small>| 1$</small></div></div>
          <div class="item"><div class="left"><div class="it-title">🇧🇩 +880</div><div class="it-desc">Физ. номер</div></div><div class="price">65⭐️ <small>| 0.7$</small></div></div>
        </div>

<div class="ctaRow">
          <a class="btn primary" href="https://t.me/User_Zaraki" target="_blank" rel="noopener">🛒 Купить номер</a>
          <a class="btn" href="https://t.me/XDpih" target="_blank" rel="noopener">⭐️ Отзывы</a>
        </div>
        <div class="note">Возможны лимиты по странам и времени. Перед оплатой уточните наличие.</div>
      </div>

      <!-- CONTACT -->
      <div class="panel" id="contact">
        <div class="h2">💬 КОНТАКТЫ <span class="tag">Связь</span></div>

        <div class="list">
          <div class="item">
            <div class="left">
              <div class="it-title">🛒 За покупкой</div>
              <div class="it-desc">@User_Zaraki</div>
            </div>
            <div class="price">
              <a class="btn primary" style="padding:10px 12px;border-radius:14px;display:inline-flex" href="https://t.me/User_Zaraki" target="_blank" rel="noopener">Открыть</a>
            </div>
          </div>

          <div class="item">
            <div class="left">
              <div class="it-title">⭐️ Отзывы</div>
              <div class="it-desc">t.me/XDpih</div>
            </div>
            <div class="price">
              <a class="btn" style="padding:10px 12px;border-radius:14px;display:inline-flex" href="https://t.me/XDpih" target="_blank" rel="noopener">Открыть</a>
            </div>
          </div>
        </div>

        <div class="ctaRow">
          <button class="btn" id="copyUser">📋 Скопировать @User_Zaraki</button>
          <button class="btn" id="copyReviews">📋 Скопировать t.me/XDpih</button>
        </div>

        <div class="note">Если хотите — добавлю “Форма заказа” (имя + что нужно) и отправку заявки прямо в Telegram.</div>
      </div>

    </div>

    <div class="footer">© ZARAKI SHOP • DARK CODING SERVICE</div>
  </section>

</div>

<script>
  // Tabs
  const tabs = document.querySelectorAll('.tab');
  const panels = document.querySelectorAll('.panel');

  function showTab(id){
    panels.forEach(p => p.classList.remove('show'));
    tabs.forEach(t => t.classList.remove('active'));
    document.getElementById(id).classList.add('show');
    document.querySelector(.tab[data-tab="${id}"]).classList.add('active');
  }

  tabs.forEach(t => {
    t.addEventListener('click', () => showTab(t.dataset.tab));
  });

  // Copy buttons
  async function copyText(text, el){
    try{
      await navigator.clipboard.writeText(text);
      const old = el.textContent;
      el.textContent = "✅ Скопировано";
      setTimeout(()=> el.textContent = old, 1400);
    }catch(e){
      alert("Скопируйте вручную: " + text);
    }
  }

  document.getElementById('copyUser').addEventListener('click', (e)=>copyText('@User_Zaraki', e.currentTarget));
  document.getElementById('copyReviews').addEventListener('click', (e)=>copyText('https://t.me/XDpih', e.currentTarget));
</script>
</body>
</html>
l>
