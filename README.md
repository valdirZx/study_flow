# StudyFlow

StudyFlow is a Flutter study app for students preparing for Brazil's National High School Exam (ENEM). It combines locally provided study topics with practice questions loaded from the ENEM API.

## Features

- Browse study areas: Mathematics, Languages, Human Sciences, and Natural Sciences.
- Explore study topics organized by basic, intermediate, and advanced levels.
- Load ENEM questions from the [ENEM API](https://api.enem.dev/).
- View question statements, images, and answer alternatives.
- Select an alternative and see whether it matches the answer key when one is available.
- Retry loading questions if the request fails.

Study topics are currently defined locally in the app. ENEM questions are fetched online; the current service requests the first 10 questions from the 2022 exam, so an internet connection is required for that section.

## Built With

- [Flutter](https://flutter.dev/) and Dart
- [`http`](https://pub.dev/packages/http) for API requests
- [api.enem.dev](https://api.enem.dev/) for ENEM exam questions

## Getting Started

### Requirements

- Flutter SDK compatible with the Dart constraint in `pubspec.yaml`
- A configured Flutter target, such as Android, iOS, web, Windows, macOS, or Linux
- Internet access to load ENEM questions

### Run the App

```bash
flutter pub get
flutter run
```

To run the automated tests:

```bash
flutter test
```

## Project Structure

```text
lib/
  data/       Local study areas and topics
  models/     Study content and ENEM question models
  screens/    App, study area, and question screens
  services/   ENEM API integration
  widgets/    Reusable study UI components
```

## API

The app requests questions from `https://api.enem.dev/v1/exams/{year}/questions` with a limit of 10 and an offset of 0. The current default year is 2022. API availability and the presence of answer keys depend on the external service.
