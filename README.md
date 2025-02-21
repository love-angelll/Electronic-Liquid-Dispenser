<!-- Начало README.md файла (RU версия) -->
![bg](https://github.com/love-angelll/Flowmatic/blob/main/img/bg.png )

# Электронный дозатор жидкости 

Электронный дозатор жидкости — это автоматический дозатор жидкости, основанный на известном проекте [Алекса Гайвера](https://www.google.com/url?sa=t&source=web&rct=j&opi=89978449&url=https://alexgyver.ru/about_gyver/&ved=2ahUKEwi2q-HMqdOLAxXq9QIHHc0FFR0QFnoECCYQAQ&usg=AOvVaw1rDqv2uakHtufNj98641UN)' — наливаторе. Этот репозиторий был создан в рамках моей дипломной работы по специальности «[Техническое обслуживание и ремонт радиоэлектронной аппаратуры](https://www.google.com/url?sa=t&source=web&rct=j&opi=89978449&url=http://ttiip.ru/technik_2110202.html&ved=2ahUKEwibq_acqdOLAxUN-AIHHZ_fA44QFnoECB0QAQ&usg=AOvVaw1QHKlo13XkNP1YWU1fiTzu )'» в [Тираспольском Техникуме Информатики и Права](https://ttiip.ru/index.php)'.

Проект был выбран для дипломной работы, так как он идеально сочетает теоретические знания и практические навыки, полученные в процессе обучения. В данном репозитории я делюсь всеми материалами, использованными для разработки устройства, включая компоненты, 3D модель корпуса, схемы подключения и другие важные файлы.

### 📃 Описание проекта

Электронный дозатор жидкости представляет собой автоматический дозатор жидкости, который управляет процессом наливания жидкости в ёмкости. Устройство контролирует объем налитой жидкости и автоматически останавливает процесс, когда уровень достигает заданного значения. Это позволяет избежать переполнения ёмкости и оптимизировать расход жидкости.

Целью проекта было создание устройства, которое бы автоматизировало процесс наливания и обеспечивало точность дозирования, что крайне важно в ряде промышленных и бытовых применений. В основе проекта лежат микроконтроллеры Arduino и датчики уровня жидкости, что позволяет точно измерять уровень жидкости в реальном времени и управлять насосом.

#### Система рассчитана на 1-6 рюмок.

### 🌈 Подсветка рюмок

- **Красный** – пустая
- **Жёлтый** – в процессе заполнения
- **Зелёный** – готово к употреблению

### ⚡ Система энергосбережения

- Система “пинания” powerbank’a, не дающая ему уйти в сон.
- Продуманная система энергосбережения:
  - Дисплей снижает яркость при простое.
  - Серво отключается от питания.

### 🔧 Режимы работы

#### 1. **Калибровка (Режим сервиса)**

- Подать питание с зажатой большой кнопкой.
- Дождаться надписи **SERVICE**.
- Энкодер управляет положением крана, на дисплей выводится угол.
- Кнопка энкодера запускает помпу и таймер.
- Удержание большой кнопки – выход из сервиса в обычный режим работы.

#### 2. **Ручной режим**

- Буква **Р** в левом краю дисплея.
- Выставляем стаканчики и кликаем по кнопке.
- Во время цикла заполнения можно доставить стакан, он будет заполнен.

#### 3. **Автоматический режим**

- Смена режимов – удержание большой кнопки.
- Буква **А** в левом краю дисплея.
- Каждый поставленный стаканчик будет заполнен!

### ⚙️ Общие особенности

- Если поднять стакан до заполнения, помпа отключится, и система перейдёт к следующему стакану.
- Если наблюдаются глюки (неправильное положение крана при заливке, промахи) – проблема в питании! Попробуйте добавить конденсаторы как на схеме, попробуйте другой powerbank, а ещё лучше проверить работу системы на нормальном зарядном блоке питания от смартфона. Система многократно протестирована, работа отлажена, неадекватное поведение замечено при плохом питании.

### 🔋 Поддержание питания

Практически все powerbank’и отключают линию питания при отсутствии нагрузки. Для этого в системе предусмотрено периодическое подёргивание сервопривода с целью создания скачков нагрузки, которые вынуждают powerbank не уходить в сон и не отключать наливатор от питания.

- В этом режиме система будет каждые 15 секунд дёргать приводом и мигать дисплеем.
- Если вам это не нужно – отключите настройку `KEEP_POWER`, присвоив ей 0 вместо 1.

### 📦 Включенные материалы

- Компоненты
- 3D модель корпуса
- Схемы подключения
- И другие файлы, необходимые для реализации проекта

### 📅 Информация о проекте

Проект был создан в рамках дипломной работы и направлен на практическое применение знаний и навыков в области электроники и программирования.

### 🔧 Основные возможности

- Автоматическое дозирование жидкости с высокой точностью.
- Режимы: ручной и автоматический.
- Регулируемый объём жидкости.
- Визуальный интерфейс на дисплее (отображение режима работы, объёма).

### 🧰 Элементная база компонентов

| **Компонент**                 | **Описание**                                                                 | **Количество**  | **Примечания**                                                 |
|-------------------------------|-----------------------------------------------------------------------------|-----------------|--------------------------------------------------------------|
| **Arduino Nano ATMega328**     | Микроконтроллер для управления системой.                                      | 1               | Главное устройство управления.                                |
| **Адресная лента**             | Лента с адресными светодиодами, различных типов (IP30, IP65, IP67).           | В зависимости от проекта | Цвет подложки: Black PCB / White PCB.                         |
| **Энкодер**                    | Устройство для управления углом вращения.                                    | 1               | Для точного управления движением.                             |
| **Кнопка**                     | Кнопка для управления устройством.                                           | 1               | Для включения/выключения или других действий.                  |
| **Дисплей TM1637**             | Дисплей для отображения информации.                                          | 1               | Используется для вывода информации о состоянии устройства.     |
| **Концевик**                   | Механический датчик положения.                                               | В зависимости от проекта               | Для точного определения положения объекта.                     |
| **Драйвер MX1508**             | Моторный драйвер для управления моторами.                                    | 1               | Для управления мощными моторами или сервоприводами.            |
| **Сервопривод**                | Механизм для точного управления положением.                                 | 1               | Для точного регулирования механизма или подачи жидкости.       |
| **Модуль USB**                 | Модуль для подключения устройства к компьютеру или другому USB-устройству.   | 1               | Для подключения и обмена данными.                              |
| **Помпа**                      | Насос для подачи жидкости в ёмкость.                                         | 1               | Для автоматического наливания жидкости в ёмкость.              |


### 🗺️ Схема проекта

<div align="center">
  <img src="https://github.com/love-angelll/Flowmatic/blob/main/Project%20Files/sheme.jpg" alt="sheme">
  <h6>Electronic liquid dispenser Sheme</h6>
</div> 

<!--
### 📷 Фото моего готового проекта

![Карусель](https://github.com/love-angelll/Flowmatic/blob/main/Project%20Files/sheme.jpg) 
-->


<!-- Официальные источники и лицензия -->

---

### 🎓 Источники проекта «Наливатор» — Алекса Гайвера

##### Электронный дозатор жидкости основан на проекте Алекса Гайвера, подробности которого можно узнать в его видео и иных его источниках:


<div align="center">
  <a href="https://youtube.com/@alexgyvershow" target="_blank">
    <img src="https://img.shields.io/badge/YouTube-Канал-red?style=for-the-badge&logo=youtube" alt="YouTube Channel">
  </a>
  
  <a href="https://www.youtube.com/watch?v=VNx4pFdzfI4" target="_blank">
    <img src="https://img.shields.io/badge/YouTube-Наливатор-red?style=for-the-badge&logo=youtube" alt="YouTube Nalivator">
  </a>
  
  <a href="https://github.com/AlexGyver/GyverDrink/" target="_blank">
    <img src="https://img.shields.io/badge/GitHub-Проект-black?style=for-the-badge&logo=github" alt="GitHub Repo">
  </a>

  <a href="https://alexgyver.ru/gyverdrink/" target="_blank">
    <img src="https://img.shields.io/badge/Site-Наливатор-blue?style=for-the-badge&logo=google-chrome" alt="Nalivator Site">
  </a>
  
  <a href="https://community.alexgyver.ru/threads/der-nalivator-modificirovannaja-versija-gyverdrink.4021/" target="_blank">
    <img src="https://img.shields.io/badge/Forum-Обсуждение-blue?style=for-the-badge&logo=google-chrome" alt="Forum">
  </a>
</div>

### ⚖️ Лицензия

Данный проект свободно распространяется для любых нужд. При использовании укажите источник.

##### Моя лицензия: [LICENSE](LICENSE)
##### Лицензия Алекса Гайвера: [LICENSE](https://github.com/AlexGyver/GyverDrink/blob/master/LICENSE)

<!-- Конец README.md -->
<p align="center">
  © Иван Фрунза | 
  Алекс Гайвер | 
  Электронный дозатор жидкости
</p> 






<!-- Начало ENG версии -->

# Electronic Liquid Dispenser

The electronic liquid dispenser is an automatic liquid dispenser based on the well-known project by [Alex Gyver](https://www.google.com/url?sa=t&source=web&rct=j&opi=89978449&url=https://alexgyver.ru/about_gyver/&ved=2ahUKEwi2q-HMqdOLAxXq9QIHHc0FFR0QFnoECCYQAQ&usg=AOvVaw1rDqv2uakHtufNj98641UN) — the "Nalivator".  
This repository was created as part of my diploma work in the specialty **"[Maintenance and Repair of Radio-Electronic Equipment](https://www.google.com/url?sa=t&source=web&rct=j&opi=89978449&url=http://ttiip.ru/technik_2110202.html&ved=2ahUKEwibq_acqdOLAxUN-AIHHZ_fA44QFnoECB0QAQ&usg=AOvVaw1QHKlo13XkNP1YWU1fiTzu)"** at the **[Tiraspol College of Informatics and Law](https://ttiip.ru/index.php)**.

This project was chosen for the diploma work because it perfectly combines theoretical knowledge and practical skills acquired during the learning process.  
In this repository, I share all the materials used in the development of the device, including components, 3D model of the case, wiring diagrams, and other important files.

### 📃 Project Description

The electronic liquid dispenser is an automatic liquid dispenser that controls the process of pouring liquid into containers. The device monitors the volume of liquid dispensed and automatically stops the process when the level reaches the preset value. This prevents overfilling and optimizes liquid consumption.

The goal of this project was to create a device that automates the pouring process and ensures precise dosing, which is crucial in various industrial and household applications. The project is based on Arduino microcontrollers and liquid level sensors, enabling real-time liquid level measurement and pump control.

#### The system is designed for 1-6 shot glasses.

### 🌈 Shot Glass Lighting

- **Red** – empty
- **Yellow** – filling in progress
- **Green** – ready for consumption

### ⚡ Power Saving System

- A system to "ping" the power bank, preventing it from going into sleep mode.
- Thoughtful energy-saving measures:
  - The display dims when idle.
  - The servo motor disconnects from power.

### 🔧 Operating Modes

#### 1. **Calibration (Service Mode)**

- Power on while holding the large button.
- Wait for the **SERVICE** message.
- The encoder controls the tap position, with the angle displayed on the screen.
- The encoder button starts the pump and timer.
- Holding the large button exits the service mode and returns to normal operation.

#### 2. **Manual Mode**

- The letter **P** appears in the top left of the display.
- Place the shot glasses and press the button.
- You can add a glass during the filling cycle, and it will be filled.

#### 3. **Automatic Mode**

- Switch modes by holding the large button.
- The letter **A** appears in the top left of the display.
- Each placed glass will be automatically filled!

### ⚙️ General Features

- If a glass is lifted before being filled, the pump stops, and the system moves to the next glass.
- If malfunctions occur (incorrect tap position, misalignment), the issue is power-related! Try adding capacitors as shown in the schematic, using a different power bank, or, ideally, testing with a standard smartphone power adapter. The system has been extensively tested, and any abnormal behavior is linked to poor power supply.

### 🔋 Power Maintenance

Most power banks turn off the power line when no load is detected. To prevent this, the system periodically moves the servo motor to create load spikes, keeping the power bank active.

- In this mode, the system will move the servo and flash the display every 15 seconds.
- If you do not need this feature, disable the `KEEP_POWER` setting by setting it to 0 instead of 1.

### 📦 Included Materials

- Components
- 3D model of the case
- Connection schematics
- Other files necessary for project implementation

### 📅 Project Information

This project was created as part of a thesis and is aimed at practical application of knowledge and skills in electronics and programming.

### 🔧 Key Features

- Automatic liquid dispensing with high precision.
- Manual and automatic modes.
- Adjustable liquid volume.
- Visual interface on the display (mode and volume display).

### 🧰 Component List

| **Component**                 | **Description**                                                | **Quantity** | **Notes**                                            |
|-------------------------------|----------------------------------------------------------------|--------------|----------------------------------------------------|
| **Arduino Nano ATMega328**     | Microcontroller for system control.                           | 1            | Main control unit.                               |
| **Addressable LED strip**      | LED strip with individually controlled LEDs (IP30, IP65, IP67). | Depends on project | Color options: Black PCB / White PCB.             |
| **Encoder**                    | Device for rotation angle control.                           | 1            | Provides precise movement control.               |
| **Button**                     | Button for device operation.                                | 1            | Used for toggling modes or other actions.        |
| **TM1637 Display**             | Display for information output.                            | 1            | Displays system status and operation mode.      |
| **Limit switch**               | Mechanical position sensor.                                | Depends on project | Ensures precise object positioning.             |
| **MX1508 Motor Driver**        | Motor driver for motor control.                           | 1            | Controls powerful motors or servos.             |
| **Servo motor**                | Mechanism for precise position control.                    | 1            | Regulates movement or liquid dispensing.        |
| **USB Module**                 | Module for USB connection.                                | 1            | Used for connectivity and data exchange.        |
| **Pump**                       | Pump for liquid dispensing.                              | 1            | Enables automatic liquid pouring.               |

### 🗺️ Project Schematic

<div align="center">
  <img src="https://github.com/love-angelll/Flowmatic/blob/main/Project%20Files/sheme.jpg" alt="sheme">
  <h6>Electronic liquid dispenser Scheme</h6>
</div>

<!--
### 📷 Photos of My Completed Project

![Carousel](https://github.com/love-angelll/Flowmatic/blob/main/Project%20Files/sheme.jpg) 
-->

<!-- Official Sources and License -->

---

### 🎓 Sources – "Nalivator" by Alex Gyver

##### The electronic liquid dispenser is based on Alex Gyver's project, details of which can be found in his videos and other sources:

<div align="center">
  <a href="https://youtube.com/@alexgyvershow" target="_blank">
    <img src="https://img.shields.io/badge/YouTube-Channel-red?style=for-the-badge&logo=youtube" alt="YouTube Channel">
  </a>
  
  <a href="https://www.youtube.com/watch?v=VNx4pFdzfI4" target="_blank">
    <img src="https://img.shields.io/badge/YouTube-Nalivator-red?style=for-the-badge&logo=youtube" alt="YouTube Nalivator">
  </a>
  
  <a href="https://github.com/AlexGyver/GyverDrink/" target="_blank">
    <img src="https://img.shields.io/badge/GitHub-Project-black?style=for-the-badge&logo=github" alt="GitHub Repo">
  </a>

  <a href="https://alexgyver.ru/gyverdrink/" target="_blank">
    <img src="https://img.shields.io/badge/Site-Nalivator-blue?style=for-the-badge&logo=google-chrome" alt="Nalivator Site">
  </a>
  
  <a href="https://community.alexgyver.ru/threads/der-nalivator-modificirovannaja-versija-gyverdrink.4021/" target="_blank">
    <img src="https://img.shields.io/badge/Forum-Discussion-blue?style=for-the-badge&logo=google-chrome" alt="Forum">
  </a>
</div>

### ⚖️ License

This project is freely distributed for any purpose. If used, please credit the source.

##### My license: [LICENSE](LICENSE)
##### Alex Gyver's license: [LICENSE](https://github.com/AlexGyver/GyverDrink/blob/master/LICENSE)

<!-- Конец README.md -->
<p align="center">
  © Ivan Frunza | 
  Alex Gyver | 
  Electronic Liquid Dispenser
</p>

















<!--
1. **Микроконтроллер** – Arduino Nano  
2. **Адресная светодиодная лента** – WS2812B  
3. **Энкодер** – KY-040 (для выбора режимов)  
4. **Кнопка** – тактовая кнопка 12×12 мм (для подтверждения выбора)  
5. **Дисплей** – TM1637 или OLED 0.96" (для отображения информации)  
6. **Реле** – 4-канальное реле 5 В (управление насосами)  
7. **Блок питания** – 12 В, 5 А  
8. **DC-DC преобразователь** – 12 В → 5 В (для питания Arduino и других компонентов)  

### 🔩 Механические и гидравлические части  
9. **Перистальтический насос** – 12 В (4 шт.)  
10. **Силиконовые трубки** – внутренний диаметр 4-6 мм  
11. **Клапаны обратные** – предотвращают обратный поток жидкости  
12. **Корпус** – изготовленный из акрила, пластика или дерева  
13. **Держатели и крепления** – для фиксации компонентов  

### ⚙️ Дополнительно  
14. **Проводка и разъёмы** – соединительные провода, клеммы, клеммные колодки  
15. **Программное обеспечение** – код на Arduino (C++)  
16. **Корпус** – для установки всех компонентов
-->


