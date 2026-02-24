[![Syncthing][14]][15]

---

[![MPLv2 License](https://img.shields.io/badge/license-MPLv2-blue.svg?style=flat-square)](https://www.mozilla.org/MPL/2.0/)
[![CII Best Practices](https://bestpractices.coreinfrastructure.org/projects/88/badge)](https://bestpractices.coreinfrastructure.org/projects/88)
[![Go Report Card](https://goreportcard.com/badge/github.com/syncthing/syncthing)](https://goreportcard.com/report/github.com/syncthing/syncthing)

## Goals

Syncthing is a **continuous file synchronization program**. It synchronizes
files between two or more computers. We strive to fulfill the goals below.
The goals are listed in order of importance, the most important ones first.
This is the summary version of the goal list - for more
commentary, see the full [Goals document][13].

Syncthing should be:

1. **Safe From Data Loss**

   Protecting the user's data is paramount. We take every reasonable
   precaution to avoid corrupting the user's files.

2. **Secure Against Attackers**

   Again, protecting the user's data is paramount. Regardless of our other
   goals, we must never allow the user's data to be susceptible to
   eavesdropping or modification by unauthorized parties.

3. **Easy to Use**

   Syncthing should be approachable, understandable, and inclusive.

4. **Automatic**

   User interaction should be required only when absolutely necessary.

5. **Universally Available**

   Syncthing should run on every common computer. We are mindful that the
   latest technology is not always available to every individual.

6. **For Individuals**

   Syncthing is primarily about empowering the individual user with safe,
   secure, and easy to use file synchronization.

7. **Everything Else**

   There are many things we care about that don't make it on to the list. It
   is fine to optimize for these values, as long as they are not in conflict
   with the stated goals above.

## Getting Started

Take a look at the [getting started guide][2].

There are a few examples for keeping Syncthing running in the background
on your system in [the etc directory][3]. There are also several [GUI
implementations][11] for Windows, Mac, and Linux.

## Docker

To run Syncthing in Docker, see [the Docker README][16].

## Getting in Touch

The first and best point of contact is the [Forum][8].
If you've found something that is clearly a
bug, feel free to report it in the [GitHub issue tracker][10].

If you believe that you’ve found a Syncthing-related security vulnerability,
please report it by emailing security@syncthing.net. Do not report it in the
Forum or issue tracker.

## Building

Building Syncthing from source is easy. After extracting the source bundle from
a release or checking out git, you just need to run `go run build.go` and the
binaries are created in `./bin`. There's [a guide][5] with more details on the
build process.

## Signed Releases

Release binaries are GPG signed with the key available from
https://syncthing.net/security/. There is also a built-in automatic
upgrade mechanism (disabled in some distribution channels) which uses a
compiled in ECDSA signature. macOS and Windows binaries are also
code-signed.

## Documentation

Please see the Syncthing [documentation site][6] [[source]][17].

All code is licensed under the [MPLv2 License][7].

[1]: https://docs.syncthing.net/specs/bep-v1.html
[2]: https://docs.syncthing.net/intro/getting-started.html
[3]: https://github.com/syncthing/syncthing/blob/main/etc
[5]: https://docs.syncthing.net/dev/building.html
[6]: https://docs.syncthing.net/
[7]: https://github.com/syncthing/syncthing/blob/main/LICENSE
[8]: https://forum.syncthing.net/
[10]: https://github.com/syncthing/syncthing/issues
[11]: https://docs.syncthing.net/users/contrib.html#gui-wrappers
[13]: https://github.com/syncthing/syncthing/blob/main/GOALS.md
[14]: assets/logo-text-128.png
[15]: https://syncthing.net/
[16]: https://github.com/syncthing/syncthing/blob/main/README-Docker.md
[17]: https://github.com/syncthing/docs

24.02.26 sync fork
Ось результати аналізу та стратегія трансформації для проекту **Syncthing**, підготовлені у форматі для копіювання в Notion.

---

# 📑 Звіт AI-консультанта: Проект "Syncthing"

**Syncthing** — це програма для безперервної синхронізації файлів із відкритим вихідним кодом, що забезпечує безпечний обмін даними між двома або більше комп'ютерами без залучення центрального сервера.

---

## 🧬 Частина 1: "ДНК" Проекту

Логіку коду Syncthing можна розбити на такі **атомарні функції**, що базуються на його архітектурних цілях:

*   **Безперервний моніторинг та індексація:** Відстеження змін у файловій системі в реальному часі для негайної синхронізації оновлень.
*   **Захищене мережеве з’єднання:** Шифрування потоків даних для запобігання прослуховуванню або модифікації сторонніми особами.
*   **Механізм запобігання втраті даних:** Алгоритми перевірки цілісності та захисту файлів від пошкодження під час передачі.
*   **Автоматичне виявлення вузлів (Discovery):** Логіка пошуку інших пристроїв у мережі для встановлення з'єднання без ручного налаштування IP.
*   **Верифікація та підпис оновлень:** Використання підписів ECDSA та GPG для безпечного автоматичного оновлення компонентів системи.
*   **Керування через Web GUI:** Надання користувачеві інтерактивного інтерфейсу (HTML/JS) для налаштування папок та пристроїв.

### 💎 Головна технічна цінність
Головна цінність Syncthing полягає у **децентралізованій безпеці та приватності**. Проект повертає контроль над даними індивідуальному користувачеві, забезпечуючи синхронізацію "вузол-до-вузла" (P2P) без потреби у хмарних провайдерах, що робить його стійким до зовнішніх атак та цензури.

---

## 🚀 Частина 2: "Трансформація" (Інтеграція з Gemini LLM)

Додавання мультимодальної моделі **Gemini** (через інструменти **GitHub Models**) перетворює Syncthing з простого інструменту копіювання файлів на **інтелектуальну систему управління знаннями**.

### Як зміниться функціонал?
1.  **Семантична синхронізація:** Замість синхронізації всього підряд, Gemini може аналізувати вміст файлів і синхронізувати лише те, що релевантне для поточного контексту користувача (наприклад, "робочі документи" на офісний ПК, "фото" — на домашній архів).
2.  **Розумне вирішення конфліктів:** Якщо файл змінено на двох пристроях, Gemini може не просто створити копію конфлікту, а проаналізувати зміни в тексті чи коді та запропонувати інтелектуальне злиття (merge).
3.  **Автоматична каталогізація:** LLM може автоматично тегувати та сортувати вхідні файли за їхнім змістом, створюючи структуровану базу даних прямо в процесі синхронізації.

### Сценарій сервісу "Smart Archive" (Syncthing + Gemini + ваші ID_{$})

Сценарій створення сервісу інтелектуального архівування на вашому сайті:
1.  **Джерело даних (ID_{$1}):** Ваш Python-скрипт **ID_{$1}** збирає неструктуровані дані (наприклад, логи, скріншоти або звіти) з різних серверів.
2.  **Інтелектуальна обробка (Gemini):** Gemini аналізує ці дані, створює стислі резюме та визначає категорію важливості.
3.  **Розподіл (Syncthing API):** На основі вердикту ШІ, скрипт **ID_{$2}** керує API Syncthing, щоб миттєво відправити критичні файли на пристрій адміністратора, а другорядні — у довгострокове сховище.
4.  **Візуалізація:** Використовуючи **GitHub Spark**, ви розгортаєте веб-інтерфейс на вашому сайті, де користувач бачить не просто дерево файлів, а "карту знань", створену Gemini на основі синхронізованих даних.

---

## 📋 План дій для Notion
| Крок | Дія | Результат |
| :--- | :--- | :--- |
| **1** | Компіляція проекту: `go run build.go` | Робочий бінарний файл Syncthing |
| **2** | Налаштування MCP Registry для зв'язку з ШІ | Інтеграція зовнішніх інструментів |
| **3** | Підключення Gemini через **GitHub Models** | Додавання інтелектуального шару аналізу |
| **4** | Створення інтерфейсу через **GitHub Spark** | Готовий інтелектуальний сервіс на сайті |

---

### 💡 Резюме

**Суть:** **Безпечна децентралізована синхронізація файлів P2P**.

**AI-Роль:** **Створення інтелектуальних застосунків через Spark**.
