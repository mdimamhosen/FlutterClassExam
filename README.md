<div align="center">

  <img src="assets/images/welcome_hero.png" alt="Quizzical" width="280"/>

  # Quizzical

  <p>
    <strong>Trivia quiz app built with Flutter, Provider & OpenTDB.</strong><br/>
    Pick a category · Configure the quiz · Race the timer · See your score
  </p>

  <p>
    <img src="https://img.shields.io/badge/Flutter-02569B?style=for-the-badge&logo=flutter&logoColor=white" alt="Flutter"/>
    <img src="https://img.shields.io/badge/Provider-State%20Management-2ECC71?style=for-the-badge" alt="Provider"/>
    <img src="https://img.shields.io/badge/OpenTDB-API-00695C?style=for-the-badge" alt="OpenTDB"/>
  </p>

  <p>
    <a href="https://github.com/mdimamhosen/FlutterClassExam">github.com/mdimamhosen/FlutterClassExam</a>
  </p>

</div>

---

## App Showcase

| Welcome | Categories | Configuration | Quiz |
|:---:|:---:|:---:|:---:|
| <img src="assets/screenshots/quiz/welcome.png" width="180" alt="Welcome"/> | <img src="assets/screenshots/quiz/category_selection.png" width="180" alt="Categories"/> | <img src="assets/screenshots/quiz/quiz_config.png" width="180" alt="Configuration"/> | <img src="assets/screenshots/quiz/quiz.png" width="180" alt="Quiz"/> |

### Demo video

[Watch the screen recording](assets/videos/quizzical_demo.mov)

---

## Features

- **Welcome** — App title, student name, Start Quiz CTA
- **Category Selection** — Categories from OpenTDB, pastel cards, session cache, retry on error
- **Quiz Configuration** — Amount (1–50), difficulty, type (multiple / true-false); last config saved with SharedPreferences
- **Quiz** — One question at a time, shuffled answers, 30s timer, correct/incorrect feedback, progress + live score
- **Results** — Score, accuracy %, total time, Play Again (resets session, keeps last config)

---

## Screens

1. `WelcomeScreen` → Category Selection  
2. `CategorySelectionScreen` → Quiz Configuration (passes `categoryId`)  
3. `QuizConfigScreen` → fetches questions → `QuizScreen`  
4. `ResultsScreen` → Play Again → Category Selection  

---

## Tech Stack

| Layer | Choice |
|--------|--------|
| UI | Flutter (Material 3) |
| State | Provider |
| API | [OpenTDB](https://opentdb.com/) (`api_category.php`, `api.php`) |
| Persistence | SharedPreferences (amount, difficulty, type, last category) |
| Fonts | Google Fonts (Poppins / Lora) |

---

## Project structure (quiz)

```
lib/
  main.dart / app.dart
  core/          # theme, constants, assets
  models/        # TriviaCategory, TriviaQuestion
  services/      # OpenTdbService
  providers/     # CategoryProvider, QuizProvider
  ui/screens/    # welcome, categories, config, quiz, results
assets/
  images/        # illustrations + captures
  screenshots/quiz/
  videos/quizzical_demo.mov
```

---

## Getting Started

```bash
flutter pub get
flutter run
```

Requires network access for OpenTDB.

---

## API

**Categories**

```
GET https://opentdb.com/api_category.php
```

**Questions**

```
GET https://opentdb.com/api.php?amount=<n>&category=<id>&difficulty=<easy|medium|hard>&type=<multiple|boolean>
```

---

## Author

**Imam Hosen** — CSE class exam project (Quizzical)
