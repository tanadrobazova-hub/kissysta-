
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Запись к Татьяне</title>

  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: #f8f5f2;
      color: #292522;
    }

    .app {
      width: min(760px, calc(100% - 32px));
      margin: 40px auto;
    }

    .header {
      margin-bottom: 28px;
    }

    .header h1 {
      margin: 0 0 8px;
      font-size: 32px;
    }

    .header p {
      margin: 0;
      color: #817a75;
      line-height: 1.5;
    }

    .section {
      margin-bottom: 24px;
    }

    .section-title {
      margin-bottom: 12px;
      font-size: 16px;
      font-weight: 700;
    }

    /* Мастер */

    .master-card {
      display: flex;
      align-items: center;
      gap: 16px;
      padding: 20px;
      background: #fff;
      border: 2px solid #a76d52;
      border-radius: 18px;
    }

    .avatar {
      width: 58px;
      height: 58px;
      display: grid;
      place-items: center;
      flex-shrink: 0;
      border-radius: 50%;
      background: #ead8ce;
      font-size: 22px;
      font-weight: 700;
    }

    .master-name {
      margin-bottom: 5px;
      font-size: 19px;
      font-weight: 700;
    }

    .stars {
      color: #c58a25;
      letter-spacing: 2px;
    }

    .master-description {
      margin-top: 4px;
      color: #817a75;
      font-size: 13px;
    }

    /* Услуги */

    .services {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 12px;
    }

    .service {
      width: 100%;
      padding: 18px;
      text-align: left;
      border: 1px solid #ded8d3;
      border-radius: 16px;
      background: #fff;
      color: #292522;
      cursor: pointer;
      transition: .2s;
    }

    .service:hover {
      border-color: #b89a8b;
      transform: translateY(-1px);
    }

    .service.selected {
      border: 2px solid #a76d52;
      background: #f4e9e3;
    }

    .service-name {
      margin-bottom: 8px;
      font-weight: 700;
    }

    .service-description {
      color: #817a75;
      font-size: 13px;
      line-height: 1.5;
    }

    .service-price {
      margin-top: 12px;
      font-size: 18px;
      font-weight: 800;
    }

    /* Поля */

    .date-input,
    .telegram-input {
      width: 100%;
      max-width: 420px;
      padding: 14px;
      border: 1px solid #ded8d3;
      border-radius: 12px;
      background: #fff;
      color: #292522;
      font: inherit;
      outline: none;
    }

    .date-input:focus,
    .telegram-input:focus {
      border-color: #a76d52;
      box-shadow: 0 0 0 3px rgba(167, 109, 82, .12);
    }

    .telegram-hint {
      margin-top: 7px;
      color: #817a75;
      font-size: 13px;
    }

    .telegram-error {
      display: none;
      margin-top: 7px;
      color: #b33a3a;
      font-size: 13px;
    }

    /* Расписание */

    .schedule-info {
      margin-bottom: 14px;
      padding: 14px 16px;
      border-radius: 14px;
      background: #fff;
      color: #817a75;
      font-size: 14px;
      line-height: 1.5;
    }

    .schedule-info strong {
      color: #292522;
    }

    .times {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 10px;
    }

    .time {
      min-height: 50px;
      border: 1px solid #ded8d3;
      border-radius: 13px;
      background: #fff;
      color: #292522;
      font: inherit;
      font-weight: 600;
      cursor: pointer;
      transition: .2s;
    }

    .time:hover {
      border-color: #b89a8b;
    }

    .time.selected {
      border-color: #a76d52;
      background: #f4e9e3;
    }

    /* Итог */

    .summary {
      padding: 20px;
      border: 1px solid #ded8d3;
      border-radius: 18px;
      background: #fff;
    }

    .summary-row {
      display: flex;
      justify-content: space-between;
      gap: 20px;
      margin-bottom: 18px;
    }

    .summary-label {
      margin-bottom: 5px;
      color: #817a75;
      font-size: 13px;
    }

    .summary-value {
      font-weight: 700;
      line-height: 1.5;
    }

    .price {
      white-space: nowrap;
      font-size: 21px;
      font-weight: 800;
    }

    .book-button {
      width: 100%;
      min-height: 52px;
      border: 0;
      border-radius: 13px;
      background: #a76d52;
      color: white;
      font: inherit;
      font-weight: 700;
      cursor: pointer;
    }

    .book-button:hover:not(:disabled) {
      background: #8f5840;
    }

    .book-button:disabled {
      opacity: .4;
      cursor: not-allowed;
    }

    .result {
      margin-top: 14px;
      color: #39734a;
      font-weight: 600;
      line-height: 1.5;
    }

    /* Заявки */

    .applications {
      margin-top: 40px;
      padding-top: 25px;
      border-top: 1px solid #ded8d3;
    }

    .applications-title {
      margin-bottom: 14px;
      font-size: 20px;
      font-weight: 700;
    }

    .application {
      margin-bottom: 12px;
      padding: 16px;
      border: 1px solid #ded8d3;
      border-radius: 15px;
      background: #fff;
    }

    .application strong {
      display: block;
      margin-bottom: 7px;
    }

    .application-info {
      color: #5f5955;
      font-size: 14px;
      line-height: 1.7;
    }

    .telegram-link {
      color: #2677b8;
      text-decoration: none;
      font-weight: 700;
    }

    .delete-button {
      margin-top: 10px;
      padding: 8px 12px;
      border: 1px solid #ddd;
      border-radius: 9px;
      background: #fff;
      cursor: pointer;
    }

    .empty-applications {
      color: #817a75;
      font-size: 14px;
    }

    @media (max-width: 650px) {
      .app {
        margin: 24px auto;
      }

      .header h1 {
        font-size: 27px;
      }

      .services {
        grid-template-columns: 1fr;
      }

      .summary-row {
        flex-direction: column;
      }
    }

    @media (max-width: 380px) {
      .times {
        grid-template-columns: repeat(2, 1fr);
      }
    }
  </style>
</head>

<body>

<main class="app">

  <header class="header">
    <h1>Запись на маникюр</h1>
    <p>
      Выберите услугу, дату и удобное время.
      Все процедуры выполняет мастер Татьяна.
    </p>
  </header>


  <!-- МАСТЕР -->

  <section class="section">

    <div class="section-title">
      Мастер
    </div>

    <div class="master-card">

      <div class="avatar">Т</div>

      <div>
        <div class="master-name">Татьяна</div>

        <div class="stars">
          ★★★★★
        </div>

        <div class="master-description">
          Мастер маникюра
        </div>
      </div>

    </div>

  </section>


  <!-- УСЛУГИ -->

  <section class="section">

    <div class="section-title">
      1. Выберите услугу
    </div>

    <div class="services">

      <button
        type="button"
        class="service"
        data-service="Гигиенический маникюр"
        data-price="600"
      >
        <div class="service-name">
          Гигиенический маникюр
        </div>

        <div class="service-description">
          Без покрытия
        </div>

        <div class="service-price">
          600 ₽
        </div>
      </button>


      <button
        type="button"
        class="service"
        data-service="Покрытие гель-лаком"
        data-price="1300"
      >
        <div class="service-name">
          Покрытие гель-лаком
        </div>

        <div class="service-description">
          Снятие, комбинированный маникюр,
          укрепление гелем, покрытие гель-лаком,
          любой дизайн
        </div>

        <div class="service-price">
          1 300 ₽
        </div>
      </button>


      <button
        type="button"
        class="service"
        data-service="Наращивание MINI"
        data-price="1600"
      >
        <div class="service-name">
          Наращивание MINI
        </div>

        <div class="service-description">
          Снятие, комбинированный маникюр,
          наращивание небольшой длины,
          покрытие гель-лаком, любой дизайн
        </div>

        <div class="service-price">
          1 600 ₽
        </div>
      </button>


      <button
        type="button"
        class="service"
        data-service="Наращивание MAX"
        data-price="1800"
      >
        <div class="service-name">
          Наращивание MAX
        </div>

        <div class="service-description">
          Снятие, комбинированный маникюр,
          наращивание большой длины,
          покрытие гель-лаком, любой дизайн
        </div>

        <div class="service-price">
          1 800 ₽
        </div>
      </button>

    </div>

  </section>


  <!-- ДАТА -->

  <section class="section">

    <div class="section-title">
      2. Выберите дату
    </div>

    <input
      id="date"
      class="date-input"
      type="date"
    >

  </section>


  <!-- ВРЕМЯ -->

  <section class="section">

    <div class="section-title">
      3. Выберите время
    </div>

    <div
      id="scheduleInfo"
      class="schedule-info"
    ></div>

    <div
      id="times"
      class="times"
    ></div>

  </section>


  <!-- TELEGRAM -->

  <section class="section">

    <div class="section-title">
      4. Ваш Telegram
    </div>

    <input
      id="telegram"
      class="telegram-input"
      type="text"
      placeholder="@username"
      autocomplete="off"
      maxlength="33"
    >

    <div class="telegram-hint">
      Оставьте свой Telegram, чтобы Татьяна могла связаться с вами по поводу записи.
    </div>

    <div
      id="telegramError"
      class="telegram-error"
    >
      Укажите Telegram-тег в формате @username.
    </div>

  </section>


  <!-- ИТОГ -->

  <section class="summary">

    <div class="summary-row">

      <div>

        <div class="summary-label">
          Ваша запись
        </div>

        <div
          id="summary"
          class="summary-value"
        >
          Выберите услугу, дату и время
        </div>

      </div>

      <div
        id="price"
        class="price"
      ></div>

    </div>


    <button
      id="bookButton"
      class="book-button"
      type="button"
      disabled
    >
      Подтвердить запись
    </button>


    <div
      id="result"
      class="result"
      aria-live="polite"
    ></div>

  </section>


  <!-- СОХРАНЁННЫЕ ЗАЯВКИ -->

  <section class="applications">

    <div class="applications-title">
      Заявки
    </div>

    <div id="applicationsList"></div>

  </section>

</main>


<script>

  /*
  ==================================================
  СОСТОЯНИЕ
  ==================================================
  */

  const state = {
    service: null,
    price: null,
    date: null,
    time: null
  };


  /*
  ==================================================
  РАСПИСАНИЕ ТАТЬЯНЫ
  ==================================================
  */

  const schedule = {

    0: ["10:00", "12:00", "14:00"], // воскресенье
    1: ["15:00"],                    // понедельник
    2: ["15:00"],                    // вторник
    3: [],                           // среда
    4: ["15:00"],                    // четверг
    5: [],                           // пятница
    6: ["10:00", "12:00", "14:00"]  // суббота

  };


  const dayNames = [
    "воскресенье",
    "понедельник",
    "вторник",
    "среда",
    "четверг",
    "пятница",
    "суббота"
  ];


  /*
  ==================================================
  DOM
  ==================================================
  */

  const services =
    document.querySelectorAll(".service");

  const dateInput =
    document.getElementById("date");

  const timesContainer =
    document.getElementById("times");

  const scheduleInfo =
    document.getElementById("scheduleInfo");

  const telegramInput =
    document.getElementById("telegram");

  const telegramError =
    document.getElementById("telegramError");

  const summary =
    document.getElementById("summary");

  const price =
    document.getElementById("price");

  const bookButton =
    document.getElementById("bookButton");

  const result =
    document.getElementById("result");

  const applicationsList =
    document.getElementById("applicationsList");


  /*
  ==================================================
  ДАТА
  ==================================================
  */

  const today = new Date();


  function formatDateForInput(date) {

    const year =
      date.getFullYear();

    const month =
      String(date.getMonth() + 1)
        .padStart(2, "0");

    const day =
      String(date.getDate())
        .padStart(2, "0");

    return `${year}-${month}-${day}`;
  }


  dateInput.min =
    formatDateForInput(today);


  /*
  ==================================================
  НАЙТИ БЛИЖАЙШИЙ РАБОЧИЙ ДЕНЬ
  ==================================================
  */

  function getNextAvailableDate() {

    const date = new Date();

    for (let i = 0; i < 14; i++) {

      const day =
        date.getDay();

      if (schedule[day].length > 0) {
        return new Date(date);
      }

      date.setDate(
        date.getDate() + 1
      );
    }

    return new Date();
  }


  const defaultDate =
    getNextAvailableDate();


  dateInput.value =
    formatDateForInput(defaultDate);

  state.date =
    dateInput.value;


  /*
  ==================================================
  УСЛУГА
  ==================================================
  */

  services.forEach(service => {

    service.addEventListener(
      "click",
      () => {

        services.forEach(item => {
          item.classList.remove("selected");
        });

        service.classList.add("selected");

        state.service =
          service.dataset.service;

        state.price =
          Number(service.dataset.price);

        result.textContent = "";

        updateSummary();

      }
    );

  });


  /*
  ==================================================
  ДАТА
  ==================================================
  */

  dateInput.addEventListener(
    "change",
    () => {

      state.date =
        dateInput.value;

      state.time = null;

      result.textContent = "";

      renderTimes();
      updateSummary();

    }
  );


  /*
  ==================================================
  TELEGRAM
  ==================================================
  */

  telegramInput.addEventListener(
    "input",
    () => {

      /*
        Если пользователь написал username
        без @, автоматически добавляем @.
      */

      let value =
        telegramInput.value.trim();

      if (
        value &&
        !value.startsWith("@")
      ) {
        value = "@" + value;
        telegramInput.value = value;
      }

      telegramError.style.display =
        "none";

      result.textContent = "";

      updateSummary();

    }
  );


  /*
  ==================================================
  ПРОВЕРКА TELEGRAM
  ==================================================
  */

  function isValidTelegram(username) {

    /*
      Разрешаем:
      @anna
      @anna_123
      @anna123

      Telegram username:
      5–32 символа после @
    */

    const pattern =
      /^@[a-zA-Z0-9_]{4,31}$/;

    return pattern.test(username);

  }


  /*
  ==================================================
  ДЕНЬ НЕДЕЛИ
  ==================================================
  */

  function getSelectedDay() {

    if (!state.date) {
      return null;
    }

    return new Date(
      state.date + "T00:00:00"
    ).getDay();

  }


  /*
  ==================================================
  ВРЕМЯ
  ==================================================
  */

  function renderTimes() {

    timesContainer.innerHTML = "";

    if (!state.date) {

      scheduleInfo.textContent =
        "Выберите дату.";

      return;
    }


    const day =
      getSelectedDay();

    const dayName =
      dayNames[day];

    const availableTimes =
      schedule[day];


    /*
      Выходной
    */

    if (availableTimes.length === 0) {

      scheduleInfo.innerHTML =
        `В <strong>${dayName}</strong> ` +
        `Татьяна не принимает. ` +
        `Пожалуйста, выберите другой день.`;

      return;
    }


    scheduleInfo.innerHTML =
      `Татьяна принимает в <strong>${dayName}</strong>. ` +
      `Доступное время:`;


    availableTimes.forEach(time => {

      const button =
        document.createElement("button");

      button.type = "button";
      button.className = "time";
      button.textContent = time;


      button.addEventListener(
        "click",
        () => {

          document
            .querySelectorAll(".time")
            .forEach(item => {
              item.classList.remove("selected");
            });

          button.classList.add("selected");

          state.time = time;

          result.textContent = "";

          updateSummary();

        }
      );


      timesContainer.appendChild(button);

    });

  }


  /*
  ==================================================
  ИТОГ
  ==================================================
  */

  function updateSummary() {

    const parts = [];


    if (state.service) {
      parts.push(state.service);
    }


    if (state.date) {

      const selectedDate =
        new Date(
          state.date + "T00:00:00"
        );

      parts.push(
        selectedDate.toLocaleDateString(
          "ru-RU",
          {
            day: "numeric",
            month: "long"
          }
        )
      );

    }


    if (state.time) {
      parts.push(state.time);
    }


    if (parts.length === 0) {

      summary.textContent =
        "Выберите услугу, дату и время";

    } else {

      summary.textContent =
        "Татьяна · " +
        parts.join(" · ");

    }


    if (state.price) {

      price.textContent =
        state.price.toLocaleString("ru-RU") +
        " ₽";

    } else {

      price.textContent = "";

    }


    const telegram =
      telegramInput.value.trim();


    /*
      Теперь кнопка активна только если
      выбраны все параметры и указан Telegram.
    */

    const canBook =
      state.service &&
      state.price &&
      state.date &&
      state.time &&
      isValidTelegram(telegram);


    bookButton.disabled =
      !canBook;

  }


  /*
  ==================================================
  СОХРАНЕНИЕ ЗАЯВКИ
  ==================================================
  */

  function getApplications() {

    try {

      return JSON.parse(
        localStorage.getItem(
          "tatiana_nail_applications"
        )
      ) || [];

    } catch (error) {

      return [];

    }

  }


  function saveApplication(application) {

    const applications =
      getApplications();

    applications.push(application);

    localStorage.setItem(
      "tatiana_nail_applications",
      JSON.stringify(applications)
    );

  }


  /*
  ==================================================
  ОТОБРАЖЕНИЕ ЗАЯВОК
  ==================================================
  */

  function renderApplications() {

    const applications =
      getApplications();

    applicationsList.innerHTML = "";


    if (applications.length === 0) {

      applicationsList.innerHTML =
        `<div class="empty-applications">
          Пока заявок нет.
        </div>`;

      return;
    }


    /*
      Новые заявки сверху
    */

    applications
      .slice()
      .reverse()
      .forEach((application, reversedIndex) => {

        const originalIndex =
          applications.length - 1 - reversedIndex;


        const element =
          document.createElement("div");

        element.className =
          "application";


        const formattedDate =
          new Date(
            application.date + "T00:00:00"
          ).toLocaleDateString(
            "ru-RU",
            {
              weekday: "long",
              day: "numeric",
              month: "long",
              year: "numeric"
            }
          );


        element.innerHTML = `
          <strong>
            ${escapeHtml(application.service)}
          </strong>

          <div class="application-info">

            Клиент: ${escapeHtml(application.telegram)}
            <br>

            Дата: ${escapeHtml(formattedDate)}
            <br>

            Время: ${escapeHtml(application.time)}
            <br>

            Стоимость:
            ${application.price.toLocaleString("ru-RU")} ₽

            <br>

            <a
              class="telegram-link"
              href="https://t.me/${encodeURIComponent(
                application.telegram.replace("@", "")
              )}"
              target="_blank"
              rel="noopener noreferrer"
            >
              Написать в Telegram
            </a>

          </div>

          <button
            type="button"
            class="delete-button"
            data-index="${originalIndex}"
          >
            Удалить заявку
          </button>
        `;


        applicationsList.appendChild(element);

      });


    /*
      Удаление заявки
    */

    document
      .querySelectorAll(".delete-button")
      .forEach(button => {

        button.addEventListener(
          "click",
          () => {

            const index =
              Number(button.dataset.index);

            const applications =
              getApplications();

            applications.splice(index, 1);

            localStorage.setItem(
              "tatiana_nail_applications",
              JSON.stringify(applications)
            );

            renderApplications();

          }
        );

      });

  }


  /*
  ==================================================
  БЕЗОПАСНЫЙ ВЫВОД ТЕКСТА
  ==================================================
  */

  function escapeHtml(value) {

    return String(value)
      .replaceAll("&", "&amp;")
      .replaceAll("<", "&lt;")
      .replaceAll(">", "&gt;")
      .replaceAll('"', "&quot;")
      .replaceAll("'", "&#039;");

  }


  /*
  ==================================================
  ПОДТВЕРЖДЕНИЕ ЗАПИСИ
  ==================================================
  */

  bookButton.addEventListener(
    "click",
    () => {

      const telegram =
        telegramInput.value.trim();


      /*
        Дополнительная проверка
      */

      if (!isValidTelegram(telegram)) {

        telegramError.style.display =
          "block";

        telegramInput.focus();

        return;

      }


      if (bookButton.disabled) {
        return;
      }


      /*
        Создаём заявку
      */

      const application = {

        id:
          Date.now(),

        master:
          "Татьяна",

        service:
          state.service,

        price:
          state.price,

        date:
          state.date,

        time:
          state.time,

        telegram:
          telegram,

        createdAt:
          new Date().toISOString()

      };


      /*
        Сохраняем заявку
      */

      saveApplication(
        application
      );


      /*
        Показываем подтверждение
      */

      const formattedDate =
        new Date(
          state.date + "T00:00:00"
        ).toLocaleDateString(
          "ru-RU",
          {
            day: "numeric",
            month: "long"
          }
        );


      result.textContent =
        `✓ Заявка сохранена! ` +
        `Татьяна будет ждать вас ` +
        `${formattedDate} в ${state.time}. ` +
        `Связаться с вами можно в Telegram: ${telegram}.`;


      /*
        Обновляем список заявок
      */

      renderApplications();


      /*
        Блокируем повторную отправку
      */

      bookButton.disabled = true;

    }
  );


  /*
  ==================================================
  ЗАПУСК
  ==================================================
  */

  renderTimes();

  updateSummary();

  renderApplications();

</script>

</body>
</html>
