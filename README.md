# RecipeHub 🍽️

> An Android app that fetches and displays real meal data from a live REST API using Retrofit, Coroutines, and Jetpack Compose.

<img width="1440" height="900" alt="Screenshot 2026-05-15 at 12 08 01 AM" src="https://github.com/user-attachments/assets/0af7a9fb-57f9-41b0-9123-db65f71d60ab" />
<img width="1440" height="900" alt="Screenshot 2026-05-15 at 12 07 49 AM" src="https://github.com/user-attachments/assets/74b2d833-48f7-49e9-978a-3dc7c170f14d" />


---

## Overview

RecipeHub is an Android application that demonstrates real-world REST API consumption in a clean, modern Android stack. It fetches meal data from the [TheMealDB API](https://www.themealdb.com/) and displays it in a scrollable list with meal images and names — built entirely with Jetpack Compose and structured around MVVM architecture.

> **Note:** This is a read-only browse experience. Users can scroll and view meals — data modification is intentionally not included, keeping the focus on networking and UI patterns.

---

## Features

- Live meal data fetched from the **TheMealDB REST API**
- Meal images and names displayed in a smooth, scrollable list
- Asynchronous network calls handled with **Kotlin Coroutines**
- Reactive UI built entirely with **Jetpack Compose**
- Screen navigation via **Jetpack Navigation Component**
- MVVM architecture for clean separation of networking and UI logic

---

## Tech Stack

| Layer | Technology |
|---|---|
| Language | Kotlin |
| UI | Jetpack Compose |
| Architecture | MVVM (Model-View-ViewModel) |
| Networking | Retrofit |
| API | TheMealDB REST API |
| Asynchronous | Kotlin Coroutines |
| Navigation | Jetpack Navigation Component |
| Build System | Gradle (Kotlin DSL) |
| Version Control | Git + GitHub |

---

## Architecture

The app follows **MVVM** with Retrofit handling all network requests and Coroutines managing async execution off the main thread.

```
Data Flow:
TheMealDB API ──► Retrofit ──► Repository ──► ViewModel ──► Compose UI
                                                   │
                                            Kotlin Coroutines
                                          (Dispatchers.IO / Main)
```

---

## API Reference

This app consumes the free [TheMealDB API](https://www.themealdb.com/api.php).

| Endpoint | Description |
|---|---|
| `/api/json/v1/1/search.php?s=` | Fetch meals by name |
| `/api/json/v1/1/categories.php` | Fetch all meal categories |

No API key is required for the free tier.

---

## Project Structure

```
app/src/main/java/
│
├── ui/           # Jetpack Compose screens and UI components
├── viewmodel/    # ViewModel managing API state
├── data/
│   ├── model/    # Data classes for API response (Meal, Category)
│   └── api/      # Retrofit service interface and API client
└── MainActivity  # App entry point and navigation host
```

---

## Getting Started

### Prerequisites
- Android Studio (Arctic Fox or later)
- Android device or emulator running **API 21+**
- Active internet connection (app fetches live data)

### Setup
```bash
git clone https://github.com/RajatGaidhane1/RecipeHub.git
cd RecipeHub
```

1. Open the project in **Android Studio**
2. Let Gradle sync and download all dependencies
3. Run the app on an emulator or physical device
4. The app will automatically fetch and display meals on launch

---

## Screenshots

> _Add screenshots here — suggested: Meal list screen, Meal card detail, Loading state_

| Meal List | Meal Card | Loading State |
|---|---|---|
| `screenshot_list.png` | `screenshot_card.png` | `screenshot_loading.png` |

---

## Roadmap

Potential improvements for future versions:

- [ ] Search and filter meals by name or category
- [ ] Meal detail screen with full ingredients and instructions
- [ ] Save favourite meals locally with Room
- [ ] Offline support with local caching
- [ ] Pagination for large result sets
- [ ] Unit tests for ViewModel and Repository layers

---

## Author

**Rajat Gaidhane**
- GitHub: https://github.com/RajatGaidhane1?tab=repositories
- LinkedIn: https://www.linkedin.com/in/rajat-gaidhane-5383002b7/

---

## License

This project is open source and available under the [MIT License](LICENSE).
