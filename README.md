
<html lang="ar" dir="rtl">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>اختبار تفاعلي - قواعد الأزمنة</title>
<style>
  :root{
    --bg:#f5f7fa;
    --card:#ffffff;
    --border:#dfe7ee;
    --text:#222;
    --accent:#0a7a44;
    --wrong:#e66;
  }
  body{
    font-family: "Segoe UI", Tahoma, Arial, sans-serif;
    background: var(--bg);
    margin: 0;
    padding: 18px;
    color: var(--text);
    -webkit-font-smoothing:antialiased;
  }
  .wrapper{
    max-width: 900px;
    margin: 0 auto;
  }
  header{
    background: linear-gradient(90deg,#fff 0,#fbfffb 100%);
    border:1px solid var(--border);
    padding: 18px;
    border-radius: 8px;
    text-align: center;
    box-shadow: 0 2px 8px rgba(10,10,10,0.03);
  }
  header h1{ margin:6px 0; font-size:20px; }
  header .meta{ margin-top:6px; color:#444; font-size:14px; }
  .section-title{
    margin-top:20px;
    margin-bottom:8px;
    font-size:18px;
    color:var(--accent);
    text-align:center;
  }

  .question {
    background: var(--card);
    border:1px solid var(--border);
    padding:12px;
    border-radius:8px;
    margin:12px 0;
  }
  .q-text { font-weight:600; margin-bottom:10px; }
  .options { display:flex; flex-direction:column; gap:8px; }
  .opt {
    border:1px solid #c9d6df;
    padding:10px 12px;
    border-radius:6px;
    cursor:pointer;
    background:#fff;
    transition: all 0.18s ease;
    text-align: right;
  }
  .opt:hover { transform: translateY(-2px); box-shadow:0 4px 12px rgba(10,10,10,0.04); }
  .opt.correct { background: #dff7df; border-color: #37a65a; color: #034b20; }
  .opt.wrong { background: #ffe6e6; border-color: #e04a4a; color: #6b0d0d; }
  .opt.disabled { opacity:0.8; pointer-events:none; }
  .meta-small { font-size:13px; color:#666; text-align:center; margin-top:10px; }

  /* print friendly */
  @media print{
    body{ background: #fff; }
    header, .question { box-shadow: none; border: 1px solid #ccc; }
  }
</style>
<script>
  // يتأكد أن السؤال لم يُجب من قبل ثم يفعل التلوين وحظر باقي الخيارات
  function selectOption(optEl){
    // parent .options element
    const optionsEl = optEl.closest('.options');
    // already answered?
    if(optionsEl.dataset.answered === "true") return;
    // mark answered
    optionsEl.dataset.answered = "true";
    // find correct option within this options group
    const opts = optionsEl.querySelectorAll('.opt');
    const correctOpt = optionsEl.querySelector('.opt[data-correct="true"]');

    // if clicked correct
    const clickedIsCorrect = optEl.dataset.correct === "true";

    if(clickedIsCorrect){
      optEl.classList.add('correct');
    } else {
      // mark clicked wrong
      optEl.classList.add('wrong');
      // highlight the correct one
      if(correctOpt) correctOpt.classList.add('correct');
    }

    // disable all options for this question (prevent further clicks)
    opts.forEach(o => {
      o.classList.add('disabled');
      // remove inline pointer events if any
      o.style.pointerEvents = 'none';
    });
  }

  // Optional: keyboard accessibility (Enter/Space to select when focused)
  document.addEventListener('keydown', function(e){
    if(e.key === 'Enter' || e.key === ' '){
      const active = document.activeElement;
      if(active && active.classList && active.classList.contains('opt')){
        active.click();
        e.preventDefault();
      }
    }
  });
</script>
</head>
<body>
  <div class="wrapper">
    <header>
      <h1>مدرسة سعيد بن العاص المتوسطة</h1>
      <div class="meta">الصف: ثالث متوسط &nbsp; | &nbsp; المعلم: أ. فهد الخالدي</div>
    </header>

    <main>

      <!-- Simple Past -->
      <div class="section-title">الجزء 1 — Simple Past (الماضي البسيط)</div>

      <div class="question">
        <div class="q-text">1. I _____ to the park yesterday.</div>
        <div class="options" data-answered="false">
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">A. go</div>
          <div class="opt" tabindex="0" data-correct="true"  onclick="selectOption(this)">B. went</div>
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">C. goes</div>
        </div>
      </div>

      <div class="question">
        <div class="q-text">2. She _____ a movie last night.</div>
        <div class="options" data-answered="false">
          <div class="opt" tabindex="0" data-correct="true" onclick="selectOption(this)">A. watched</div>
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">B. watches</div>
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">C. watching</div>
        </div>
      </div>

      <div class="question">
        <div class="q-text">3. They _____ football on Friday.</div>
        <div class="options" data-answered="false">
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">A. plays</div>
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">B. play</div>
          <div class="opt" tabindex="0" data-correct="true"  onclick="selectOption(this)">C. played</div>
        </div>
      </div>

      <div class="question">
        <div class="q-text">4. He _____ his homework yesterday.</div>
        <div class="options" data-answered="false">
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">A. do</div>
          <div class="opt" tabindex="0" data-correct="true"  onclick="selectOption(this)">B. did</div>
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">C. does</div>
        </div>
      </div>

      <div class="question">
        <div class="q-text">5. We _____ dinner at 7 PM last night.</div>
        <div class="options" data-answered="false">
          <div class="opt" tabindex="0" data-correct="true" onclick="selectOption(this)">A. ate</div>
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">B. eat</div>
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">C. eating</div>
        </div>
      </div>

      <!-- Present Simple -->
      <div class="section-title">الجزء 2 — Present Simple (المضارع البسيط)</div>

      <div class="question">
        <div class="q-text">1. He _____ to school every day.</div>
        <div class="options" data-answered="false">
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">A. go</div>
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">B. going</div>
          <div class="opt" tabindex="0" data-correct="true"  onclick="selectOption(this)">C. goes</div>
        </div>
      </div>

      <div class="question">
        <div class="q-text">2. They _____ football every Friday.</div>
        <div class="options" data-answered="false">
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">A. plays</div>
          <div class="opt" tabindex="0" data-correct="true"  onclick="selectOption(this)">B. play</div>
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">C. played</div>
        </div>
      </div>

      <div class="question">
        <div class="q-text">3. The sun _____ in the east.</div>
        <div class="options" data-answered="false">
          <div class="opt" tabindex="0" data-correct="true" onclick="selectOption(this)">A. rises</div>
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">B. rise</div>
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">C. rising</div>
        </div>
      </div>

      <div class="question">
        <div class="q-text">4. She _____ milk every morning.</div>
        <div class="options" data-answered="false">
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">A. drink</div>
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">B. drinking</div>
          <div class="opt" tabindex="0" data-correct="true"  onclick="selectOption(this)">C. drinks</div>
        </div>
      </div>

      <div class="question">
        <div class="q-text">5. I _____ English.</div>
        <div class="options" data-answered="false">
          <div class="opt" tabindex="0" data-correct="true" onclick="selectOption(this)">A. like</div>
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">B. liking</div>
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">C. likes</div>
        </div>
      </div>

      <!-- Present Progressive -->
      <div class="section-title">الجزء 3 — Present Progressive (المضارع المستمر)</div>

      <div class="question">
        <div class="q-text">1. She _____ TV now.</div>
        <div class="options" data-answered="false">
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">A. watch</div>
          <div class="opt" tabindex="0" data-correct="true"  onclick="selectOption(this)">B. is watching</div>
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">C. watched</div>
        </div>
      </div>

      <div class="question">
        <div class="q-text">2. They _____ football right now.</div>
        <div class="options" data-answered="false">
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">A. play</div>
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">B. playing</div>
          <div class="opt" tabindex="0" data-correct="true"  onclick="selectOption(this)">C. are playing</div>
        </div>
      </div>

      <div class="question">
        <div class="q-text">3. I _____ a book (now).</div>
        <div class="options" data-answered="false">
          <div class="opt" tabindex="0" data-correct="true" onclick="selectOption(this)">A. am reading</div>
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">B. read</div>
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">C. reading</div>
        </div>
      </div>

      <div class="question">
        <div class="q-text">4. He _____ his homework now.</div>
        <div class="options" data-answered="false">
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">A. do</div>
          <div class="opt" tabindex="0" data-correct="true"  onclick="selectOption(this)">B. is doing</div>
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">C. did</div>
        </div>
      </div>

      <div class="question">
        <div class="q-text">5. We _____ dinner at the moment.</div>
        <div class="options" data-answered="false">
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">A. eat</div>
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">B. eating</div>
          <div class="opt" tabindex="0" data-correct="true"  onclick="selectOption(this)">C. are eating</div>
        </div>
      </div>

      <!-- Present Perfect -->
      <div class="section-title">الجزء 4 — Present Perfect (المضارع التام)</div>

      <div class="question">
        <div class="q-text">1. I _____ my homework (الآن النتيجة: الواجب جاهز).</div>
        <div class="options" data-answered="false">
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">A. do</div>
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">B. did</div>
          <div class="opt" tabindex="0" data-correct="true"  onclick="selectOption(this)">C. have done</div>
        </div>
      </div>

      <div class="question">
        <div class="q-text">2. She _____ the movie already.</div>
        <div class="options" data-answered="false">
          <div class="opt" tabindex="0" data-correct="true" onclick="selectOption(this)">A. has watched</div>
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">B. watched</div>
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">C. watches</div>
        </div>
      </div>

      <div class="question">
        <div class="q-text">3. They _____ the task (والنتيجة الآن: اكتمل).</div>
        <div class="options" data-answered="false">
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">A. finish</div>
          <div class="opt" tabindex="0" data-correct="true"  onclick="selectOption(this)">B. have finished</div>
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">C. finished</div>
        </div>
      </div>

      <div class="question">
        <div class="q-text">4. He _____ the car (الآن النتيجة: السيارة نظيفة).</div>
        <div class="options" data-answered="false">
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">A. clean</div>
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">B. cleaned</div>
          <div class="opt" tabindex="0" data-correct="true"  onclick="selectOption(this)">C. has cleaned</div>
        </div>
      </div>

      <div class="question">
        <div class="q-text">5. We _____ lunch (الآن النتيجة: لقد أكلنا).</div>
        <div class="options" data-answered="false">
          <div class="opt" tabindex="0" data-correct="true" onclick="selectOption(this)">A. have eaten</div>
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">B. ate</div>
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">C. eat</div>
        </div>
      </div>

      <!-- Present Perfect vs Simple Past -->
      <div class="section-title">الجزء 5 — Present Perfect vs Simple Past</div>

      <div class="question">
        <div class="q-text">1. I _____ my keys yesterday. (وقت محدد ↑)</div>
        <div class="options" data-answered="false">
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">A. have lost</div>
          <div class="opt" tabindex="0" data-correct="true"  onclick="selectOption(this)">B. lost</div>
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">C. have lose</div>
        </div>
      </div>

      <div class="question">
        <div class="q-text">2. She _____ the book already. (التجربة/النتيجة — بدون وقت محدد)</div>
        <div class="options" data-answered="false">
          <div class="opt" tabindex="0" data-correct="true" onclick="selectOption(this)">A. has read</div>
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">B. read</div>
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">C. reads</div>
        </div>
      </div>

      <div class="question">
        <div class="q-text">3. They _____ the movie last week. (وقت محدد)</div>
        <div class="options" data-answered="false">
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">A. have watched</div>
          <div class="opt" tabindex="0" data-correct="true"  onclick="selectOption(this)">B. watched</div>
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">C. watches</div>
        </div>
      </div>

      <div class="question">
        <div class="q-text">4. He _____ lunch (النتيجة الآن: لقد أكل).</div>
        <div class="options" data-answered="false">
          <div class="opt" tabindex="0" data-correct="true" onclick="selectOption(this)">A. has eaten</div>
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">B. ate</div>
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">C. eat</div>
        </div>
      </div>

      <div class="question">
        <div class="q-text">5. We _____ here since 2010. (استخدم: since)</div>
        <div class="options" data-answered="false">
          <div class="opt" tabindex="0" data-correct="true" onclick="selectOption(this)">A. have lived</div>
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">B. live</div>
          <div class="opt" tabindex="0" data-correct="false" onclick="selectOption(this)">C. lived</div>
        </div>
      </div>

      <div class="meta-small">اضغط على خيار واحد لكل سؤال. الإجابة الصحيحة ستظهر باللون الأخضر، والخاطئة باللون الأحمر.</div>

    </main>
  </div>
</body>
</html>
