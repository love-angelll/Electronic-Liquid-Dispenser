# Flowmatic

<!-- фото проекта -->
![bg](https://github.com/love-angelll/Flowmatic/blob/main/img/bg.png )
###### от «flow» (поток) и «automatic» (автоматический).  

## Flowmatic — электронный дозатор жидкости

Flowmatic — это автоматический дозатор жидкости, основанный на известном проекте Алекса Гайвера — наливаторе. 

### 🔧 Основные возможности

- Автоматическое дозирование жидкости с высокой точностью.
- Режимы: ручной и автоматический.
- Регулируемый объём жидкости.
- Визуальный интерфейс на дисплее (отображение режима работы, объёма).

### 🧰 Электронные компоненты 
 
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


### 🎓 Источники проекта «Наливатор» — Алекса Гайвера

##### Flowmatic основан на проекте Алекса Гайвера, подробности которого можно узнать в его видео и иных его источниках:


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


