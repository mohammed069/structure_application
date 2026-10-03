# Flutter Starter

A reusable Flutter starter template for building scalable applications with a clean, feature-first architecture.

## ✨ Features

- Clean Architecture-oriented structure
- Feature-first organization
- BLoC / Cubit state management
- Dependency Injection with GetIt
- Dio networking
- API abstraction with `ApiConsumer`
- Centralized Dio exception handling
- Network connectivity abstraction
- SharedPreferences cache
- GoRouter navigation
- Easy Localization
- Light / Dark theme support
- Flutter ScreenUtil
- Reusable UI widgets
- Flutter Lints
- Ready for automated checks with GitHub Actions

## 📁 Project Structure

```text
lib/
├── core/
│   ├── api/
│   ├── cache/
│   ├── config/
│   ├── di/
│   ├── errors/
│   ├── localization/
│   ├── network/
│   ├── routes/
│   ├── theme/
│   ├── usecases/
│   ├── utils/
│   └── widgets/
│
├── features/
│   └── ...
│
└── main.dart
```

## 🚀 Getting Started

### 1. Create a repository from this template

On GitHub, use **Use this template** to create a new project repository.

### 2. Update project identity

Change the following according to your project:

- `name` in `pubspec.yaml`
- Application title
- Package/application ID
- App icons and splash screen
- Assets
- API base URL / environment configuration

### 3. Install dependencies

```bash
flutter pub get
```

### 4. Format the project

```bash
dart format .
```

### 5. Analyze the project

```bash
flutter analyze
```

### 6. Run tests

```bash
flutter test
```

## 🧱 Architecture

The intended dependency flow is:

```text
Presentation
    ↓
Use Case
    ↓
Repository
    ↓
Data Source
    ↓
ApiConsumer
    ↓
Dio
    ↓
Backend
```

Errors are translated at the infrastructure boundary:

```text
DioException
    ↓
DioExceptionHandler
    ↓
AppException
    ↓
Repository
    ↓
Failure
    ↓
Cubit / UI
```

## 📦 Adding a New Feature

For a complex feature, use:

```text
features/
└── feature_name/
    ├── data/
    │   ├── datasources/
    │   ├── models/
    │   └── repositories/
    │
    ├── domain/
    │   ├── entities/
    │   ├── repositories/
    │   └── usecases/
    │
    └── presentation/
        ├── cubit/
        ├── pages/
        └── widgets/
```

Do not put feature-specific business logic inside `core/`.

Use `core/` for functionality genuinely shared across multiple features.

## 🔐 Secrets

Do not commit API keys, passwords, tokens, or other secrets.

Use environment configuration or a suitable secret-management solution when required.

## 🧪 Quality Checks

Before pushing changes:

```bash
dart format .
flutter analyze
flutter test
```

## 📋 Changelog

See [CHANGELOG.md](CHANGELOG.md).

## 📄 License

This project is licensed under the MIT License. See [LICENSE](LICENSE).
