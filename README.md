<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>爱好 — Мои увлечения | HSK 1</title>
<style>
:root {
  --blue:#4778d8;
  --light:#eaf1ff;
  --bg:#f4f7fc;
  --ink:#26334a;
  --muted:#68758b;
  --line:#dfe6f1;
  --green:#eaf8ef;
  --pink:#fff0f3;
  --shadow:0 8px 24px rgba(42,65,105,.08);
}
*{box-sizing:border-box}
body{
  margin:0;background:var(--bg);color:var(--ink);
  font:16px/1.55 system-ui,-apple-system,"Segoe UI",sans-serif;
}
header{
  background:linear-gradient(120deg,#e8efff,#fcecf2);
  padding:32px 18px;text-align:center;
}
header h1{font-size:clamp(28px,5vw,42px);margin:8px 0}
header p{margin:0;color:var(--muted)}
.tag{
  display:inline-block;background:var(--light);color:#315da9;
  padding:4px 11px;border-radius:20px;font-size:12px;font-weight:700;
}
nav{
  position:sticky;top:0;z-index:10;background:#ffffffed;
  display:flex;gap:7px;overflow-x:auto;padding:10px 14px;
  border-bottom:1px solid var(--line);
}
nav a{
  white-space:nowrap;text-decoration:none;color:var(--ink);
  font-size:13px;font-weight:650;padding:7px 11px;
  border-radius:20px;background:#f0f3f9;
}
nav a:hover{background:var(--light);color:var(--blue)}
.wrap{max-width:1050px;margin:auto;padding:18px}
section{
  background:white;border:1px solid var(--line);
  border-radius:18px;padding:22px;margin:18px 0;
  box-shadow:var(--shadow);scroll-margin-top:75px;
}
h2{font-size:22px;margin:0 0 5px}
h3{font-size:17px;margin:15px 0 8px}
.sub{color:var(--muted);margin:0 0 16px}
.grid{
  display:grid;grid-template-columns:repeat(auto-fit,minmax(145px,1fr));
  gap:10px;
}
.word{
  border:1px solid var(--line);border-radius:13px;
  padding:12px;text-align:center;background:#fff;
}
.emoji{font-size:32px;display:block}
.cn{font-size:21px;font-weight:750}
.py{font-size:13px;color:var(--muted)}
button{
  border:0;border-radius:10px;background:var(--blue);color:#fff;
  padding:9px 13px;font-weight:650;cursor:pointer;margin:4px 3px 4px 0;
}
button:hover{filter:brightness(.94)}
button.secondary{background:#edf1f8;color:var(--ink)}
button.good{background:#248451}
input,select,textarea{
  font:inherit;border:1px solid #cfd8e6;border-radius:9px;
  padding:9px;background:white;color:var(--ink);max-width:100%;
}
textarea{width:100%;min-height:75px}
label{display:inline-flex;align-items:center;gap:6px;margin:5px 10px 5px 0}
.feedback{font-weight:650;margin-top:10px;min-height:24px}
.ok{color:#20804b}.no{color:#b24c43}
.hint{background:#f5f7fb;border-radius:10px;padding:12px;color:#526078}
.pill{
  display:inline-block;border-radius:20px;padding:5px 10px;
  background:#f0f3f9;margin:3px;
}
.task{padding:13px 0;border-top:1px solid var(--line)}
.task:first-child{border-top:0}
.two{
  display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));
  gap:14px;
}
.choice{
  border:1px solid var(--line);border-radius:12px;
  padding:10px;margin:5px;display:inline-block;
}
footer{text-align:center;color:var(--muted);padding:20px;font-size:13px}
@media(max-width:600px){
  .wrap{padding:10px}section{padding:16px}
}
</style>
</head>
<body>

<header>
  <span class="tag">HSK 1 · Индивидуальный урок · 45 минут</span>
  <h1>爱好 — Мои увлечения</h1>
  <p>Учимся говорить о том, что нам нравится делать</p>
</header>

<nav>
  <a href="#warmup">1. Разминка</a>
  <a href="#choose">2. Что люблю</a>
  <a href="#errors">3. Ошибки</a>
  <a href="#guess">4. Угадай</a>
  <a href="#categories">5. Категории</a>
  <a href="#day">6. Мой день</a>
  <a href="#center">7. Спортцентр</a>
  <a href="#interview">8. Интервью</a>
  <a href="#final">9. Рассказ</a>
</nav>

<main class="wrap">

<!-- 1 -->
<section id="warmup">
<h2>1. Разминка — Угадай по эмодзи</h2>
<p class="sub">Назови занятие по-китайски. Нажми на 🔊, чтобы услышать произношение.</p>
<div class="grid" id="flashGrid"></div>

<div class="task">
<h3>Дополнительное задание: с русского на китайский</h3>
<p>Вспомни китайское слово.</p>
<div class="row">
  <span id="ruPrompt" class="pill"></span>
  <button onclick="newRussian()">Новое слово</button>
</div>
<input id="ruAnswer" placeholder="Напиши по-китайски">
<button onclick="checkRussian()">Проверить</button>
<div id="ruFeedback" class="feedback"></div>
</div>
</section>

<!-- 2 -->
<section id="choose">
<h2>2. Что я люблю?</h2>
<p class="sub">
Выбери ровно 3 любимых занятия, 2 нелюбимых и 1 занятие,
которое хочешь попробовать.
</p>
<div id="likeGrid" class="grid"></div>

<div>
  <span class="pill" id="likeCount">Люблю: 0/3</span>
  <span class="pill" id="dislikeCount">Не люблю: 0/2</span>
  <span class="pill" id="tryCount">Хочу попробовать: 0/1</span>
</div>
<button onclick="makeLikeSentences()">Составить предложения</button>
<div id="likeOutput" class="hint">Здесь появятся твои предложения.</div>
<p class="hint">
Модель: 我喜欢游泳。<br>
我不喜欢滑雪。<br>
我想玩滑板。<br>
Последняя конструкция — дополнительная, если ученик уже знает 想.
</p>
</section>

<!-- 3 -->
<section id="errors">
<h2>3. Исправь мои ошибки</h2>
<p class="sub">Преподаватель произносит фразы с ошибками. Выбери правильный вариант.</p>
<div id="errorTasks"></div>
<button onclick="checkErrors()">Проверить ответы</button>
<div id="errorFeedback" class="feedback"></div>

<div class="task">
<h3>Теперь твоя очередь!</h3>
<p>Придумай две неправильные фразы для преподавателя.</p>
<textarea id="studentErrors" placeholder="Например: 我喜欢打足球。"></textarea>
</div>
</section>

<!-- 4 -->
<section id="guess">
<h2>4. Угадай моё хобби</h2>
<p class="sub">
Преподаватель загадывает занятие и открывает подсказки по одной.
Ученик должен угадать.
</p>
<div class="hint">
  <b>Подсказка:</b>
  <p id="clueText"></p>
  <button onclick="nextClue()">Следующая подсказка</button>
  <button class="secondary" onclick="showGuess()">Показать ответ</button>
  <button class="secondary" onclick="speakCurrentClue()">🔊 Озвучить</button>
  <div id="guessFeedback" class="feedback"></div>
</div>

<div class="task">
<h3>Поменяйтесь ролями</h3>
<p>Теперь ученик загадывает хобби, а преподаватель отгадывает.</p>
<textarea placeholder="Подсказка 1…&#10;Подсказка 2…&#10;Подсказка 3…"></textarea>
</div>
</section>

<!-- 5 -->
<section id="categories">
<h2>5. Разложи увлечения по категориям</h2>
<p class="sub">Выбери подходящую категорию для каждого слова.</p>
<div id="categoryTasks"></div>
<button onclick="checkCategories()">Проверить</button>
<div id="categoryFeedback" class="feedback"></div>

<div class="task">
<h3>Ответь на вопросы преподавателя</h3>
<p>你喜欢运动吗？</p>
<p>你喜欢什么运动？</p>
<p>你喜欢唱歌还是跳舞？</p>
<button class="secondary" onclick="speak('你喜欢运动吗？你喜欢什么运动？你喜欢唱歌还是跳舞？')">
🔊 Озвучить вопросы
</button>
</div>
</section>

<!-- 6 -->
<section id="day">
<h2>6. Мой идеальный день</h2>
<p class="sub">
Выбери занятия для своего идеального выходного дня.
</p>

<div class="two">
  <label>上午 — утром
    <select id="morning"></select>
  </label>
  <label>下午 — днём
    <select id="afternoon"></select>
  </label>
  <label>晚上 — вечером
    <select id="evening"></select>
  </label>
  <label>Ещё одно занятие вечером
    <select id="evening2"></select>
  </label>
</div>

<button onclick="buildDay()">Составить расписание</button>
<div id="dayOutput" class="hint"></div>
</section>

<!-- 7 -->
<section id="center">
<h2>7. Где можно заниматься? — 体育中心</h2>
<p class="sub">
Выбери занятия, которыми можно заниматься в спортивном центре.
Затем составь предложения.
</p>
<div id="centerGrid"></div>
<button onclick="buildCenter()">Составить предложения</button>
<div id="centerOutput" class="hint"></div>

<div class="task">
<h3>Ответь на вопросы преподавателя</h3>
<p>你喜欢去体育中心吗？</p>
<p>你喜欢在体育中心做什么？</p>
<button class="secondary" onclick="speak('你喜欢去体育中心吗？你喜欢在体育中心做什么？')">
🔊 Озвучить вопросы
</button>
</div>
</section>

<!-- 8 -->
<section id="interview">
<h2>8. Мини-интервью с преподавателем</h2>
<p class="sub">
Ученик задаёт вопросы преподавателю и записывает ответы.
Затем рассказывает о преподавателе в 2–3 предложениях.
</p>
<div id="interviewFields"></div>
<button onclick="buildInterview()">Подготовить рассказ</button>
<div id="interviewOutput" class="hint"></div>
</section>

<!-- 9 -->
<section id="final">
<h2>9. Финальное задание — 我的爱好</h2>
<p class="sub">
Подготовь рассказ о себе из 4–6 предложений.
Заполни поля, затем прочитай получившийся текст вслух.
</p>

<div class="two">
  <label>Моё хобби
    <input id="hobby" placeholder="运动 / 画画 / 唱歌">
  </label>
  <label>Любимый спорт
    <input id="sport" placeholder="游泳 / 打篮球">
  </label>
  <label>Другие любимые занятия
    <input id="other" placeholder="听音乐 / 看视频">
  </label>
  <label>Что не нравится
    <input id="notLike" placeholder="滑雪 / 玩游戏">
  </label>
</div>

<button onclick="buildFinal()">Составить мой рассказ</button>
<div id="finalOutput" class="hint"></div>
<button class="good" onclick="speakFinal()">🔊 Прослушать рассказ</button>
</section>

</main>
<footer>爱好 · HSK 1 · Индивидуальный урок с преподавателем</footer>

<script>
const words = [
['⚽','踢足球','tī zúqiú','играть в футбол'],
['🏀','打篮球','dǎ lánqiú','играть в баскетбол'],
['🎾','打网球','dǎ wǎngqiú','играть в теннис'],
['🏸','打羽毛球','dǎ yǔmáoqiú','играть в бадминтон'],
['🏐','打排球','dǎ páiqiú','играть в волейбол'],
['🎿','滑雪','huáxuě','кататься на лыжах'],
['⛸️','滑冰','huábīng','кататься на коньках'],
['🏊','游泳','yóuyǒng','плавать'],
['🛹','玩滑板','wán huábǎn','кататься на скейтборде'],
['💃','跳舞','tiàowǔ','танцевать'],
['🎮','玩游戏','wán yóuxì','играть в игры'],
['🎤','唱歌','chànggē','петь'],
['🎧','听音乐','tīng yīnyuè','слушать музыку'],
['📹','看视频','kàn shìpín','смотреть видео'],
['📷','拍照','pāizhào','фотографировать'],
['🎨','画画','huàhuà','рисовать']
];

// Озвучивание
function speak(text) {
  if (!('speechSynthesis' in window)) {
    alert('Озвучивание не поддерживается этим браузером.');
    return;
  }
  speechSynthesis.cancel();
  const utterance = new SpeechSynthesisUtterance(text);
  utterance.lang = 'zh-CN';
  utterance.rate = 0.85;
  speechSynthesis.speak(utterance);
}

function speakCurrentClue() {
  speak(clues[clueSet][clueStep]);
}

function speakFinal() {
  speak(document.getElementById('finalOutput').innerText);
}

// 1. Карточки
document.getElementById('flashGrid').innerHTML =
  words.map(w => `
    <div class="word">
      <span class="emoji">${w[0]}</span>
      <div class="cn">${w[1]}</div>
      <div class="py">${w[2]}</div>
      <div class="py">${w[3]}</div>
      <button class="secondary" onclick="speak('${w[1]}')">🔊</button>
    </div>
  `).join('');

// Перевод с русского на китайский
let ruIndex = 7;

function newRussian() {
  ruIndex = Math.floor(Math.random() * words.length);
  document.getElementById('ruPrompt').textContent = words[ruIndex][3];
  document.getElementById('ruAnswer').value = '';
  document.getElementById('ruFeedback').textContent = '';
}

function checkRussian() {
  const answer = document.getElementById('ruAnswer').value.trim();
  const correct = answer === words[ruIndex][1];
  const feedback = document.getElementById('ruFeedback');

  feedback.textContent = correct
    ? 'Верно! ' + words[ruIndex][1] + ' — ' + words[ruIndex][2]
    : 'Попробуй ещё раз. Правильный ответ: ' + words[ruIndex][1];

  feedback.className = 'feedback ' + (correct ? 'ok' : 'no');
}

// 2. Выбор увлечений
const preferences = {};

document.getElementById('likeGrid').innerHTML = words.map((w,i) => `
  <div class="word">
    <span class="emoji">${w[0]}</span>
    <b>${w[1]}</b>
    <div class="py">${w[3]}</div>
    <select onchange="setPreference(${i},this.value)">
      <option value="">Выбери…</option>
      <option value="like">❤️ Люблю</option>
      <option value="dislike">🙅 Не люблю</option>
      <option value="try">⭐ Хочу попробовать</option>
    </select>
  </div>
`).join('');

function setPreference(i,value) {
  if (value) preferences[i] = value;
  else delete preferences[i];
  updateCounts();
}

function updateCounts() {
  const count = key => Object.values(preferences).filter(x => x === key).length;
  document.getElementById('likeCount').textContent = `Люблю: ${count('like')}/3`;
  document.getElementById('dislikeCount').textContent = `Не люблю: ${count('dislike')}/2`;
  document.getElementById('tryCount').textContent = `Хочу попробовать: ${count('try')}/1`;
}

function makeLikeSentences() {
  const count = key => Object.values(preferences).filter(x => x === key).length;
  const output = document.getElementById('likeOutput');

  if (count('like') !== 3 || count('dislike') !== 2 || count('try') !== 1) {
    output.textContent = 'Выбери ровно 3 любимых занятия, 2 нелюбимых и 1 новое занятие.';
    return;
  }

  const sentences = words.map((w,i) => {
    if (preferences[i] === 'like') return '我喜欢' + w[1] + '。';
    if (preferences[i] === 'dislike') return '我不喜欢' + w[1] + '。';
    if (preferences[i] === 'try') return '我想' + w[1] + '。';
    return null;
  }).filter(Boolean);

  output.innerHTML = sentences.join('<br>');
}

// 3. Исправление ошибок
const corrections = [
  ['我喜欢打足球。',['我喜欢踢足球。','我喜欢打足球。','我喜欢听足球。'],0],
  ['我喜欢踢篮球。',['我喜欢踢篮球。','我喜欢打篮球。','我喜欢看篮球。'],1],
  ['我喜欢听视频。',['我喜欢听视频。','我喜欢看视频。','我喜欢打视频。'],1],
  ['我喜欢看音乐。',['我喜欢听音乐。','我喜欢看音乐。','我喜欢踢音乐。'],0],
  ['我喜欢打游泳。',['我喜欢游泳。','我喜欢打游泳。','我喜欢听游泳。'],0],
  ['我喜欢拍歌。',['我喜欢唱歌。','我喜欢拍歌。','我喜欢看歌。'],0]
];

document.getElementById('errorTasks').innerHTML = corrections.map((q,i) => `
  <div class="task">
    <b>${i+1}. ${q[0]}</b><br>
    ${q[1].map((answer,j) => `
      <label>
        <input type="radio" name="err${i}" value="${j}">
        ${answer}
      </label>
    `).join('')}
  </div>
`).join('');

function checkErrors() {
  let score = 0;

  corrections.forEach((q,i) => {
    const selected = document.querySelector(`input[name="err${i}"]:checked`);
    if (selected && Number(selected.value) === q[2]) score++;
  });

  const feedback = document.getElementById('errorFeedback');
  feedback.textContent = `Правильно: ${score} из ${corrections.length}.`;
  feedback.className = 'feedback ' + (score === 6 ? 'ok' : 'no');
}

// 4. Загадки
const clues = [
  ['我喜欢运动。','我用球。','我用脚。','踢足球'],
  ['我喜欢运动。','我用球。','我用手。','打篮球'],
  ['我喜欢运动。','我在水里。','我会游。','游泳'],
  ['我喜欢音乐。','我用耳朵听。','我喜欢歌曲。','听音乐'],
  ['我喜欢艺术。','我用笔。','我在纸上画。','画画']
];

let clueSet = 0;
let clueStep = 0;

function renderClue() {
  document.getElementById('clueText').textContent = clues[clueSet][clueStep];
  document.getElementById('guessFeedback').textContent = '';
}

function nextClue() {
  if (clueStep < 2) {
    clueStep++;
  } else {
    clueStep = 0;
    clueSet = (clueSet + 1) % clues.length;
  }
  renderClue();
}

function showGuess() {
  const feedback = document.getElementById('guessFeedback');
  feedback.textContent = 'Ответ: ' + clues[clueSet][3];
  feedback.className = 'feedback ok';
}

// 5. Категории
const categories = {
  '运动':['踢足球','打篮球','打网球','打羽毛球','打排球','滑雪','滑冰','游泳','玩滑板'],
  '娱乐':['玩游戏','看视频','听音乐'],
  '其他爱好':['跳舞','唱歌','拍照','画画']
};

const categoryItems = Object.entries(categories)
  .flatMap(([category,list]) => list.map(word => [word,category]));

document.getElementById('categoryTasks').innerHTML =
  categoryItems.map(([word],i) => `
    <label style="display:flex;justify-content:space-between;border-bottom:1px solid #dfe6f1;padding:6px">
      <b>${word}</b>
      <select id="cat${i}">
        <option value="">Выбери категорию</option>
        <option value="运动">运动 — спорт</option>
        <option value="娱乐">娱乐 — развлечения</option>
        <option value="其他爱好">其他爱好 — другие увлечения</option>
      </select>
    </label>
  `).join('');

function checkCategories() {
  let score = 0;

  categoryItems.forEach(([word,category],i) => {
    if (document.getElementById('cat'+i).value === category) score++;
  });

  const feedback = document.getElementById('categoryFeedback');
  feedback.textContent = `Правильно распределено: ${score} из ${categoryItems.length}.`;
  feedback.className = 'feedback ' + (score === categoryItems.length ? 'ok' : 'no');
}

// 6. Идеальный день
function fillSelect(id) {
  document.getElementById(id).innerHTML = words.map(w =>
    `<option value="${w[1]}">${w[0]} ${w[1]}</option>`
  ).join('');
}

['morning','afternoon','evening','evening2'].forEach(fillSelect);

function buildDay() {
  const m = document.getElementById('morning').value;
  const a = document.getElementById('afternoon').value;
  const e = document.getElementById('evening').value;
  const e2 = document.getElementById('evening2').value;

  document.getElementById('dayOutput').innerHTML =
    `上午我喜欢${m}。<br>
     下午我喜欢${a}。<br>
     晚上我喜欢${e}，也喜欢${e2}。`;
}

// 7. Спортивный центр
const sportsCenter = [
  ['⚽','踢足球'],['🏀','打篮球'],['🎾','打网球'],
  ['🏸','打羽毛球'],['🏐','打排球'],['🏊','游泳'],
  ['⛸️','滑冰'],['🎿','滑雪'],['🛹','玩滑板']
];

document.getElementById('centerGrid').innerHTML = sportsCenter.map(w => `
  <label class="choice">
    <input type="checkbox" value="${w[1]}"> ${w[0]} ${w[1]}
  </label>
`).join('');

function buildCenter() {
  const selected = [...document.querySelectorAll('#centerGrid input:checked')]
    .map(x => x.value);

  document.getElementById('centerOutput').innerHTML = selected.length
    ? selected.map(x => `我在体育中心${x}。`).join('<br>')
    : 'Выбери хотя бы одно занятие.';
}

// 8. Интервью
const interviewQuestions = [
  '你的爱好是什么？',
  '你喜欢运动吗？',
  '你喜欢唱歌吗？',
  '你喜欢玩游戏吗？',
  '你喜欢什么运动？'
];

document.getElementById('interviewFields').innerHTML =
  interviewQuestions.map((q,i) => `
    <div class="task">
      <b>${q}</b><br>
      <button class="secondary" onclick="speak('${q}')">🔊</button>
      <input id="int${i}" placeholder="Запиши ответ преподавателя" style="width:min(100%,430px)">
    </div>
  `).join('');

function buildInterview() {
  const answers = interviewQuestions.map((q,i) =>
    document.getElementById('int'+i).value.trim()
  ).filter(Boolean);

  document.getElementById('interviewOutput').innerHTML = answers.length
    ? 'Используй ответы, чтобы рассказать о преподавателе:<br>' +
      answers.map((a,i) => `${i+1}. ${a}`).join('<br>')
    : 'Сначала запиши ответы преподавателя.';
}

// 9. Итоговый рассказ
function buildFinal() {
  const hobby = document.getElementById('hobby').value.trim();
  const sport = document.getElementById('sport').value.trim();
  const other = document.getElementById('other').value.trim();
  const notLike = document.getElementById('notLike').value.trim();

  const sentences = [];

  if (hobby) sentences.push('我的爱好是' + hobby + '。');
  if (sport) sentences.push('我喜欢' + sport + '。');
  if (other) sentences.push('我也喜欢' + other + '。');
  if (notLike) sentences.push('我不喜欢' + notLike + '。');

  document.getElementById('finalOutput').innerHTML =
    sentences.length ? sentences.join('<br>') : 'Заполни хотя бы одно поле.';
}

// Начальная настройка
newRussian();
renderClue();
</script>
</body>
</html>
