<!DOCTYPE html>
<html lang="ru">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Школьный дневник и презентация</title>
    <link rel="stylesheet" href="my.css" />
  </head>
  <body>
    <div class="container">
      <header>
        <h1>Полезный подручный инструментарий</h1>
        <p class="creator-info">
          Дневник создан Даниилом Пироженко<br />Электронная почта:
          daniilpirozhenko320@gmail.com
        </p>
      </header>

      <!-- Вкладки -->
      <div class="tabs">
        <button class="tablinks" onclick="openTab(event, 'subjects')">
          Предметы и ДЗ
        </button>
        <button class="tablinks" onclick="openTab(event, 'diary')">
          Дневник
        </button>
        <button class="tablinks" onclick="openTab(event, 'presentation')">
          Презентация
        </button>
        <button class="tablinks" onclick="openTab(event, 'drawing')">Рисование</button>
        <button class="tablinks" onclick="openTab(event, 'createTable')">Создать таблицу</button>
        <button class="tablinks" onclick="openTab(event, 'calculator')">Калькулятор</button>
        <button class="tablinks" onclick="openTab(event, 'learningLanguages')">Изучение языков</button>

        <div id="learningLanguages" class="tabcontent">
          <!-- Вкладка "Изучение языков" -->
          <h2>Выберите язык</h2>
          <div id="languageSelection">
            <img src="poland_flag.png" alt="Польша" class="flag-icon" onclick="selectLanguage('polish')">
            <img src="usa_flag.png" alt="США" class="flag-icon" onclick="selectLanguage('english')">
            <img src="spain_flag.png" alt="Испания" class="flag-icon" onclick="selectLanguage('spanish')">
            <select id="languageSelect" onchange="loadLanguageCards()">
                <option value="">Выбрать язык</option>
              <option value="polish">Польский</option>
              <option value="english">Английский</option>
              <option value="spanish">Испанский</option>
            </select>
          </div>
          <div id="flashcardsContainer"></div>
        </div>
        
        
        <div id="drawing" class="tabcontent">
          <!-- Вкладка "Рисование" -->
          <h2>Рисование</h2>
          <canvas id="drawCanvas" width="800" height="500"></canvas>
          <div class="drawing-controls">
            <label for="colorPicker">Выберите цвет: </label>
            <input type="color" id="colorPicker" value="#000000">
            <label for="brushSize">Толщина линии: </label>
            <input type="number" id="brushSize" value="5" min="1" max="20">
            <select id="tools">
              <option value="brush">Кисть</option>
              <option value="eraser">Ластик</option>
            </select>
            <button onclick="clearCanvas()">Очистить</button>
            <button onclick="saveDrawing()">Сохранить</button>
          </div>
          <div id="galleryContainer"></div>
        </div>
        
        <div id="createTable" class="tabcontent">
          <!-- Вкладка "Создать таблицу" -->
          <h2>Создать таблицу</h2>
          <div id="tableControls">
            <button onclick="createTable()">Создать таблицу</button>
            <button onclick="addRow()">Добавить строку</button>
            <button onclick="addColumn()">Добавить столбец</button>
            <button onclick="deleteTable()">Удалить таблицу</button>
          </div>
          <div id="tableContainer"></div>
        </div>
        
<div id="createTable" class="tabcontent">
  <!-- Вкладка "Создать таблицу" -->
  <h2>Создать таблицу</h2>
  <button onclick="createTable()">Создать новую таблицу</button>
  <div id="tableContainer"></div>
</div>
<div id="calculator" class="tabcontent">
    <!-- Вкладка "Калькулятор" -->
    <h2>Калькулятор</h2>
    <input type="text" id="calculatorInput">
    <div id="calculatorButtons">
      <button onclick="addToInput('1')">1</button>
      <button onclick="addToInput('2')">2</button>
      <button onclick="addToInput('3')">3</button>
      <button onclick="addToInput('+')">+</button>
      <br>
      <button onclick="addToInput('4')">4</button>
      <button onclick="addToInput('5')">5</button>
      <button onclick="addToInput('6')">6</button>
      <button onclick="addToInput('-')">-</button>
      <br>
      <button onclick="addToInput('7')">7</button>
      <button onclick="addToInput('8')">8</button>
      <button onclick="addToInput('9')">9</button>
      <button onclick="addToInput('*')">*</button>
      <br>
      <button onclick="addToInput('0')">0</button>
      <button onclick="addToInput('.')">.</button>
      <button onclick="clearInput()">C</button>
      <button onclick="calculate()">=</button>
      <button onclick="addToInput('/')">/</button>
    </div>
    
  </div>
  
    <div id="calculatorOutput">
      <!-- Здесь будет отображаться результат -->
    </div>
  </div>


        </div>
      </div>

      <!-- Содержимое вкладок -->
      <div id="subjects" class="tabcontent">
        <div class="subjects-grid" id="subjectsGrid">
          <!-- Сюда будут добавляться предметы и дз -->
        </div>
      </div>

      <div id="diary" class="tabcontent">
        <div class="editor">
          <input type="text" id="diaryTitle" placeholder="Заголовок" />
          <input type="date" id="diaryDate" />
          <textarea id="diaryContent" placeholder="Текст записи"></textarea>
          <button onclick="saveDiaryEntry()">Сохранить</button>
        </div>
        <div id="diaryEntries">
          <!-- Сюда будут добавляться записи из дневника -->
        </div>
      </div>

      <div id="presentation" class="tabcontent">
        <div class="presentation-controls">
          <button onclick="prevSlide()">Назад</button>
          <button onclick="nextSlide()">Вперед</button>
          <button onclick="newSlide()">Добавить новый слайд</button>
        </div>
        <div id="slidesContainer">
          <!-- Сюда будут добавляться слайды презентации -->
        </div>
      </div>
    </div>

    <script src="my.js"></script>
  </body>
</html>
