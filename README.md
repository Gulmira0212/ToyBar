# ToyBar
<!DOCTYPE html>
<html lang="ky">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Chakyr.kg — Онлайн Чакыруу Конструктору</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,600;0,700;1,600&family=Plus+Jakarta+Sans:wght@400;500;600;700&display=swap" rel="stylesheet">
  <style>
    body { font-family: 'Plus Jakarta Sans', sans-serif; }
    .font-serif-display { font-family: 'Cormorant Garamond', serif; }
    .ornament-bg {
      background-image: radial-gradient(#d4af37 0.75px, transparent 0.75px), radial-gradient(#d4af37 0.75px, #fdfbf7 0.75px);
      background-size: 30px 30px;
      background-position: 0 0, 15px 15px;
    }
    /* Шаблондордун стилдери */
    .theme-wedding {
      background: linear-gradient(180deg, #fffdf9 0%, #f7efe2 100%);
      border-color: #d4af37;
      color: #3d2c1e;
    }
    .theme-uzatuu {
      background: linear-gradient(180deg, #fff8fa 0%, #fce7ef 100%);
      border-color: #d9779b;
      color: #4a1d2f;
    }
    .theme-jubilee {
      background: linear-gradient(180deg, #f4f7fb 0%, #e2ebf5 100%);
      border-color: #2b547e;
      color: #162b40;
    }
  </style>
</head>
<body class="bg-[#faf8f5] text-stone-800 antialiased">

  <!-- Навигация -->
  <header class="sticky top-0 z-40 bg-white/90 backdrop-blur-md border-b border-amber-200/60">
    <div class="max-w-6xl mx-auto px-4 py-3.5 flex items-center justify-between">
      <a href="#" class="flex items-center gap-2">
        <span class="w-8 h-8 rounded-full bg-amber-600 text-white flex items-center justify-center font-serif-display font-bold text-xl">Ч</span>
        <span class="font-serif-display text-2xl font-bold tracking-wide text-stone-900">Chakyr<span class="text-amber-600">.kg</span></span>
      </a>
      <a href="#builder" class="bg-amber-600 hover:bg-amber-700 text-white text-sm font-semibold px-4 py-2 rounded-full transition shadow-sm">
        Чакыруу жасоо
      </a>
    </div>
  </header>

  <!-- 1. Hero Бөлүмү -->
  <section class="ornament-bg border-b border-amber-200/60 py-14 md:py-20 px-4">
    <div class="max-w-3xl mx-auto text-center">
      <div class="inline-block px-3.5 py-1 rounded-full bg-amber-100 text-amber-800 text-xs font-semibold tracking-wider uppercase mb-4">
        Заманбап онлайн чакыруулар
      </div>
      <h1 class="font-serif-display text-4xl sm:text-5xl md:text-6xl font-bold text-stone-900 leading-tight mb-5">
        Тоюңузга кооз онлайн чакырууну <span class="text-amber-600 italic">2 мүнөттө</span> жасаңыз
      </h1>
      <p class="text-stone-600 text-base sm:text-lg max-w-xl mx-auto mb-8">
        Кагаз чакырууларга ашыкча чыгым болбоңуз. Конокторго WhatsApp аркылуу жөнөтүп, 2GIS картасын жана ким келерин оңой билиңиз.
      </p>
      <div class="flex flex-col sm:flex-row items-center justify-center gap-3">
        <a href="#builder" class="w-full sm:w-auto bg-amber-600 hover:bg-amber-700 text-white font-semibold px-8 py-4 rounded-xl shadow-lg shadow-amber-600/20 transition text-base">
          Чакыруу жасоо
        </a>
        <a href="#preview-card" class="w-full sm:w-auto bg-white hover:bg-stone-50 text-stone-800 border border-stone-200 font-semibold px-6 py-4 rounded-xl transition text-base">
          Үлгүсүн көрүү
        </a>
      </div>
    </div>
  </section>

  <!-- 2 & 3 & 4. Конструктор жана Жандуу Үлгү -->
  <section id="builder" class="max-w-6xl mx-auto px-4 py-12">
    <div class="text-center mb-10">
      <h2 class="font-serif-display text-3xl sm:text-4xl font-bold text-stone-900">Чакырууңузду түзүңүз</h2>
      <p class="text-stone-500 text-sm sm:text-base mt-1">Төмөнкү маалыматтарды толтурсаңыз, оң жактагы чакыруу дароо өзгөрөт</p>
    </div>

    <div class="grid grid-cols-1 lg:grid-cols-12 gap-8 items-start">
      
      <!-- Сол жак: Форма (Builder) -->
      <div class="lg:col-span-7 bg-white p-5 sm:p-7 rounded-2xl shadow-sm border border-stone-200/80 space-y-5">
        
        <!-- Шаблон тандоо -->
        <div>
          <label class="block text-sm font-semibold text-stone-700 mb-2">1. Шаблондун түрүн тандаңыз</label>
          <div class="grid grid-cols-3 gap-2.5">
            <button type="button" onclick="setTemplate('wedding')" id="btn-wedding" class="tpl-btn border-2 border-amber-600 bg-amber-50 text-amber-900 py-2.5 px-3 rounded-xl text-xs sm:text-sm font-semibold transition">
              💍 Үйлөнүү той
            </button>
            <button type="button" onclick="setTemplate('uzatuu')" id="btn-uzatuu" class="tpl-btn border border-stone-200 bg-white text-stone-700 py-2.5 px-3 rounded-xl text-xs sm:text-sm font-semibold transition">
              🌸 Кыз узатуу
            </button>
            <button type="button" onclick="setTemplate('jubilee')" id="btn-jubilee" class="tpl-btn border border-stone-200 bg-white text-stone-700 py-2.5 px-3 rounded-xl text-xs sm:text-sm font-semibold transition">
              👑 Юбилей / Маараке
            </button>
          </div>
        </div>

        <!-- Той ээлери -->
        <div>
          <label class="block text-sm font-semibold text-stone-700 mb-1.5">2. Той ээлери (Жубайлардын же маараке ээсинин аты)</label>
          <input type="text" id="input-names" value="Азамат & Айгерим" oninput="updatePreview()" placeholder="Мисалы: Азамат & Айгерим"
            class="w-full px-4 py-3 rounded-xl border border-stone-300 focus:ring-2 focus:ring-amber-500 focus:border-amber-500 outline-none text-sm" />
        </div>

        <!-- Күнү жана убактысы -->
        <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
          <div>
            <label class="block text-sm font-semibold text-stone-700 mb-1.5">3. Күнү жана убактысы</label>
            <input type="datetime-local" id="input-datetime" onchange="updatePreview()"
              class="w-full px-4 py-3 rounded-xl border border-stone-300 focus:ring-2 focus:ring-amber-500 outline-none text-sm" />
          </div>
          <div>
            <label class="block text-sm font-semibold text-stone-700 mb-1.5">4. Сүрөт жүктөө</label>
            <input type="file" id="input-photo" accept="image/*" onchange="handleImageUpload(event)"
              class="w-full text-xs text-stone-500 file:mr-3 file:py-2.5 file:px-4 file:rounded-xl file:border-0 file:text-xs file:font-semibold file:bg-amber-50 file:text-amber-700 hover:file:bg-amber-100 border border-stone-300 rounded-xl p-1" />
          </div>
        </div>

        <!-- Өтүүчү жай жана 2GIS -->
        <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
          <div>
            <label class="block text-sm font-semibold text-stone-700 mb-1.5">5. Өтүүчү жай (Ресторан жана дареги)</label>
            <input type="text" id="input-venue" value="«Ала-Тоо» рестораны, Чүй пр. 123" oninput="updatePreview()" placeholder="Ресторандын аты жана дареги"
              class="w-full px-4 py-3 rounded-xl border border-stone-300 focus:ring-2 focus:ring-amber-500 outline-none text-sm" />
          </div>
          <div>
            <label class="block text-sm font-semibold text-stone-700 mb-1.5">6. 2GIS / Google Карта шилтемеси</label>
            <input type="url" id="input-map" value="https://2gis.kg/bishkek" oninput="updatePreview()" placeholder="https://2gis.kg/..."
              class="w-full px-4 py-3 rounded-xl border border-stone-300 focus:ring-2 focus:ring-amber-500 outline-none text-sm" />
          </div>
        </div>

        <!-- Чакыруу тексти -->
        <div>
          <label class="block text-sm font-semibold text-stone-700 mb-1.5">7. Чакыруу тексти</label>
          <textarea id="input-message" rows="3" oninput="updatePreview()"
            class="w-full px-4 py-3 rounded-xl border border-stone-300 focus:ring-2 focus:ring-amber-500 outline-none text-sm">Урматтуу коноктор! Сиздерди биздин өмүрүбүздөгү эң бактылуу күндөрдүн бири — үйлөнүү тоюбузга арналган ак дасторконубузга чакырабыз!</textarea>
        </div>

        <!-- Төлөмгө өтүү баскычы -->
        <div class="pt-2">
          <button type="button" onclick="openPaymentModal()"
            class="w-full bg-stone-900 hover:bg-stone-800 text-white font-semibold py-4 px-6 rounded-xl shadow-md transition flex items-center justify-center gap-2 text-base">
            <span>Даяр шилтемени алуу (Төлөм: 390 сом)</span>
            <span>→</span>
          </button>
          <p class="text-center text-xs text-stone-400 mt-2">Төлөмдөн кийин конокторго жөнөтүү үчүн уникалдуу шилтеме ачылат</p>
        </div>
      </div>

      <!-- Оң жак: Жандуу Чакыруу Картасы (Live Preview) -->
      <div id="preview-card" class="lg:col-span-5 flex flex-col items-center">
        <div class="text-xs font-semibold uppercase tracking-wider text-stone-400 mb-2">Телефондо көрүнүшү (Live Preview)</div>
        
        <!-- Мобилдик рамка -->
        <div id="card-container" class="w-full max-w-[390px] theme-wedding border-2 rounded-[2rem] shadow-xl overflow-hidden transition-all duration-300">
          
          <!-- Сүрөт бөлүгү -->
          <div class="relative h-64 w-full bg-stone-200 overflow-hidden">
            <img id="preview-img" src="https://images.unsplash.com/photo-1519741497674-611481863552?auto=format&fit=crop&w=800&q=80" alt="Той сүрөтү" class="w-full h-full object-cover" />
            <div class="absolute inset-0 bg-gradient-to-t from-black/70 via-black/20 to-transparent flex flex-col justify-end p-6 text-white text-center">
              <span id="preview-badge" class="text-xs uppercase tracking-[0.2em] text-amber-200 mb-1">Үйлөнүү тойго чакыруу</span>
              <h3 id="preview-names" class="font-serif-display text-3xl font-bold leading-tight">Азамат & Айгерим</h3>
            </div>
          </div>

          <!-- Мазмун бөлүгү -->
          <div class="p-6 text-center space-y-5">
            
            <!-- Чакыруу тексти -->
            <p id="preview-message" class="text-sm leading-relaxed opacity-90">
              Урматтуу коноктор! Сиздерди биздин өмүрүбүздөгү эң бактылуу күндөрдүн бири — үйлөнүү тоюбузга арналган ак дасторконубузга чакырабыз!
            </p>

            <div class="border-y border-current/15 py-4 space-y-2">
              <div class="text-xs uppercase tracking-widest opacity-60">Тойдун күнү жана убактысы</div>
              <div id="preview-date" class="font-serif-display text-2xl font-bold">15-Август, 2026 • 17:00</div>
              <div id="preview-venue" class="text-xs font-medium opacity-85 pt-1">📍 «Ала-Тоо» рестораны, Чүй пр. 123</div>
            </div>

            <!-- Таймер -->
            <div>
              <div class="text-[11px] uppercase tracking-wider opacity-60 mb-2">Тойго чейин калды:</div>
              <div class="grid grid-cols-4 gap-2 text-center">
                <div class="bg-white/70 rounded-xl p-2 shadow-sm">
                  <div id="cd-days" class="font-bold text-lg">00</div>
                  <div class="text-[10px] opacity-70">Күн</div>
                </div>
                <div class="bg-white/70 rounded-xl p-2 shadow-sm">
                  <div id="cd-hours" class="font-bold text-lg">00</div>
                  <div class="text-[10px] opacity-70">Саат</div>
                </div>
                <div class="bg-white/70 rounded-xl p-2 shadow-sm">
                  <div id="cd-mins" class="font-bold text-lg">00</div>
                  <div class="text-[10px] opacity-70">Мүнөт</div>
                </div>
                <div class="bg-white/70 rounded-xl p-2 shadow-sm">
                  <div id="cd-secs" class="font-bold text-lg">00</div>
                  <div class="text-[10px] opacity-70">Секунд</div>
                </div>
              </div>
            </div>

            <!-- 2GIS Карта баскычы -->
            <a id="preview-map-btn" href="https://2gis.kg/bishkek" target="_blank"
              class="block w-full py-3 px-4 rounded-xl bg-emerald-600 hover:bg-emerald-700 text-white text-xs font-semibold shadow-sm transition">
              🗺️ 2GIS Картадан көрүү
            </a>

            <!-- RSVP Формасы (Коноктор үчүн) -->
            <div class="bg-white/80 rounded-2xl p-4 text-left space-y-3 border border-current/10">
              <div class="text-center font-serif-display text-xl font-bold">Келериңизди тастыктаңыз</div>
              <input type="text" id="rsvp-name" placeholder="Сиздин аты-жөнүңүз"
                class="w-full px-3 py-2 rounded-lg border border-stone-300 bg-white text-stone-800 text-xs outline-none" />
              <div class="grid grid-cols-2 gap-2">
                <label class="cursor-pointer">
                  <input type="radio" name="rsvp-choice" value="Барам" checked class="peer hidden" />
                  <div class="text-center py-2 rounded-lg border border-stone-300 text-xs font-semibold peer-checked:bg-amber-600 peer-checked:text-white peer-checked:border-amber-600 transition">
                    ✅ Барам
                  </div>
                </label>
                <label class="cursor-pointer">
                  <input type="radio" name="rsvp-choice" value="Барбайм" class="peer hidden" />
                  <div class="text-center py-2 rounded-lg border border-stone-300 text-xs font-semibold peer-checked:bg-stone-700 peer-checked:text-white peer-checked:border-stone-700 transition">
                    ❌ Барбайм
                  </div>
                </label>
              </div>
              <textarea id="rsvp-wish" rows="2" placeholder="Каалоо-тилегиңизди жазыңыз..."
                class="w-full px-3 py-2 rounded-lg border border-stone-300 bg-white text-stone-800 text-xs outline-none"></textarea>
              <button type="button" onclick="submitRsvp()"
                class="w-full py-2.5 rounded-lg bg-stone-900 text-white text-xs font-semibold hover:bg-stone-800 transition">
                Жоопту жөнөтүү
              </button>
              <div id="rsvp-feedback" class="hidden text-center text-xs font-semibold text-emerald-700 pt-1">
                Рахмат! Сиздин жообуңуз жана тилегиңиз кабыл алынды.
              </div>
            </div>

          </div>
        </div>
      </div>

    </div>
  </section>

  <!-- 5. Төлөм Модалдык Терезеси (Payment Modal) -->
  <div id="payment-modal" class="fixed inset-0 z-50 hidden bg-black/60 backdrop-blur-sm flex items-center justify-center p-4">
    <div class="bg-white rounded-3xl max-w-md w-full p-6 sm:p-7 shadow-2xl relative animate-fadeIn">
      <button onclick="closePaymentModal()" class="absolute top-4 right-4 w-8 h-8 rounded-full bg-stone-100 hover:bg-stone-200 flex items-center justify-center text-stone-600 font-bold">✕</button>
      
      <div class="text-center">
        <span class="inline-block px-3 py-1 rounded-full bg-emerald-100 text-emerald-800 text-xs font-semibold mb-2">Чакыруу дээрлик даяр!</span>
        <h3 class="font-serif-display text-2xl sm:text-3xl font-bold text-stone-900">Төлөм жүргүзүү</h3>
        <p class="text-stone-500 text-xs sm:text-sm mt-1">Уникалдуу шилтемени активдештирүү үчүн төлөм жасап, чекти WhatsApp аркылуу жөнөтүңүз.</p>
      </div>

      <!-- QR / Реквизиттер кутусу -->
      <div class="my-5 bg-stone-50 border border-stone-200 rounded-2xl p-4 text-center space-y-3">
        <div class="text-xs text-stone-500">Төлөм суммасы:</div>
        <div class="text-3xl font-bold text-stone-900">390 сом</div>
        
        <!-- Шарттуу QR-код (өзүңүздүн QR сүрөтүн койсоңуз болот) -->
        <div class="w-36 h-36 mx-auto bg-white p-2 rounded-xl border border-stone-200 flex items-center justify-center">
          <img src="https://api.qrserver.com/v1/create-qr-code/?size=150x150&data=MBank:996700000000" alt="QR Code" class="w-full h-full object-contain" />
        </div>

        <div class="text-xs text-stone-700 space-y-1 pt-1">
          <div><strong>MBank / О!Деньги:</strong> +996 700 000 000</div>
          <div class="text-stone-500">Алуучу: Аман Б.</div>
        </div>
      </div>

      <!-- WhatsApp чек жөнөтүү баскычы -->
      <button type="button" onclick="sendWhatsAppReceipt()"
        class="w-full bg-[#25D366] hover:bg-[#20bd5a] text-white font-semibold py-3.5 px-5 rounded-xl shadow-md transition flex items-center justify-center gap-2 text-sm">
        <span>💬 Чекти WhatsApp'ка жөнөтүү</span>
      </button>
    </div>
  </div>

  <!-- Футер -->
  <footer class="border-t border-stone-200 py-8 text-center text-xs text-stone-500">
    © 2026 Chakyr.kg — Бардык укуктар корголгон.
  </footer>

  <script>
    // Баштапкы датаны 30 күн алдыга коюу
    const defaultDate = new Date(Date.now() + 30 * 24 * 60 * 60 * 1000);
    defaultDate.setHours(17, 0, 0, 0);
    const tzOffset = defaultDate.getTimezoneOffset() * 60000;
    document.getElementById('input-datetime').value = new Date(defaultDate - tzOffset).toISOString().slice(0, 16);

    let currentTemplate = 'wedding';

    const templateConfig = {
      wedding: {
        badge: 'Үйлөнүү тойго чакыруу',
        themeClass: 'theme-wedding',
        defaultImg: 'https://images.unsplash.com/photo-1519741497674-611481863552?auto=format&fit=crop&w=800&q=80'
      },
      uzatuu: {
        badge: 'Кыз узатуу тоюна чакыруу',
        themeClass: 'theme-uzatuu',
        defaultImg: 'https://images.unsplash.com/photo-1522673607200-164d1b6ce486?auto=format&fit=crop&w=800&q=80'
      },
      jubilee: {
        badge: 'Маараке / Юбилейге чакыруу',
        themeClass: 'theme-jubilee',
        defaultImg: 'https://images.unsplash.com/photo-1530103862676-de8c9debad1d?auto=format&fit=crop&w=800&q=80'
      }
    };

    let customImageUploaded = false;

    function setTemplate(type) {
      currentTemplate = type;
      const card = document.getElementById('card-container');
      card.classList.remove('theme-wedding', 'theme-uzatuu', 'theme-jubilee');
      card.classList.add(templateConfig[type].themeClass);
      document.getElementById('preview-badge').innerText = templateConfig[type].badge;

      if (!customImageUploaded) {
        document.getElementById('preview-img').src = templateConfig[type].defaultImg;
      }

      // Баскычтардын стилин жаңылоо
      document.querySelectorAll('.tpl-btn').forEach(btn => {
        btn.className = 'tpl-btn border border-stone-200 bg-white text-stone-700 py-2.5 px-3 rounded-xl text-xs sm:text-sm font-semibold transition';
      });
      document.getElementById('btn-' + type).className = 'tpl-btn border-2 border-amber-600 bg-amber-50 text-amber-900 py-2.5 px-3 rounded-xl text-xs sm:text-sm font-semibold transition';
    }

    function handleImageUpload(event) {
      const file = event.target.files[0];
      if (file) {
        const reader = new FileReader();
        reader.onload = function(e) {
          document.getElementById('preview-img').src = e.target.result;
          customImageUploaded = true;
        };
        reader.readAsDataURL(file);
      }
    }

    function updatePreview() {
      const names = document.getElementById('input-names').value || 'Той ээлери';
      const venue = document.getElementById('input-venue').value || 'Ресторандын дареги';
      const mapUrl = document.getElementById('input-map').value || '#';
      const message = document.getElementById('input-message').value || '';
      const dtVal = document.getElementById('input-datetime').value;

      document.getElementById('preview-names').innerText = names;
      document.getElementById('preview-venue').innerText = '📍 ' + venue;
      document.getElementById('preview-map-btn').href = mapUrl;
      document.getElementById('preview-message').innerText = message;

      if (dtVal) {
        const d = new Date(dtVal);
        const months = ['Январь', 'Февраль', 'Март', 'Апрель', 'Май', 'Июнь', 'Июль', 'Август', 'Сентябрь', 'Октябрь', 'Ноябрь', 'Декабрь'];
        const hours = String(d.getHours()).padStart(2, '0');
        const mins = String(d.getMinutes()).padStart(2, '0');
        document.getElementById('preview-date').innerText = `${d.getDate()}-${months[d.getMonth()]}, ${d.getFullYear()} • ${hours}:${mins}`;
      }
    }

    // Таймерди эсептөө
    function updateCountdown() {
      const dtVal = document.getElementById('input-datetime').value;
      if (!dtVal) return;
      const target = new Date(dtVal).getTime();
      const now = new Date().getTime();
      const diff = target - now;

      if (diff <= 0) {
        ['cd-days', 'cd-hours', 'cd-mins', 'cd-secs'].forEach(id => document.getElementById(id).innerText = '00');
        return;
      }

      const days = Math.floor(diff / (1000 * 60 * 60 * 24));
      const hours = Math.floor((diff / (1000 * 60 * 60)) % 24);
      const mins = Math.floor((diff / 1000 / 60) % 60);
      const secs = Math.floor((diff / 1000) % 60);

      document.getElementById('cd-days').innerText = String(days).padStart(2, '0');
      document.getElementById('cd-hours').innerText = String(hours).padStart(2, '0');
      document.getElementById('cd-mins').innerText = String(mins).padStart(2, '0');
      document.getElementById('cd-secs').innerText = String(secs).padStart(2, '0');
    }
    setInterval(updateCountdown, 1000);
    updatePreview();
    updateCountdown();

    // Коноктун RSVP жообу
    function submitRsvp() {
      const guestName = document.getElementById('rsvp-name').value.trim();
      if (!guestName) {
        alert('Сураныч, аты-жөнүңүздү жазыңыз!');
        return;
      }
      document.getElementById('rsvp-feedback').classList.remove('hidden');
      document.getElementById('rsvp-name').value = '';
      document.getElementById('rsvp-wish').value = '';
    }

    // Төлөм терезеси
    function openPaymentModal() {
      document.getElementById('payment-modal').classList.remove('hidden');
    }
    function closePaymentModal() {
      document.getElementById('payment-modal').classList.add('hidden');
    }

    // WhatsApp аркылуу чек жөнөтүү
    function sendWhatsAppReceipt() {
      const adminPhone = '996700000000'; // Өзүңүздүн WhatsApp номериңизди жазыңыз
      const names = document.getElementById('input-names').value;
      const dateText = document.getElementById('preview-date').innerText;
      const venue = document.getElementById('input-venue').value;
      
      const text = `Саламатсызбы! Chakyr.kg сайтынан онлайн чакыруу жасадым.\n\n` +
                   `📌 Той ээлери: ${names}\n` +
                   `📅 Күнү: ${dateText}\n` +
                   `📍 Жайы: ${venue}\n\n` +
                   `Төлөм чегин тиркеп жөнөтүп жатам, шилтемемди ачып бериңизчи.`;
      
      const url = `https://wa.me/${adminPhone}?text=${encodeURIComponent(text)}`;
      window.open(url, '_blank');
    }
  </script>
</body>
</html>
