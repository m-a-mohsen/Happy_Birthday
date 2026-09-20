# Improve Compose Code to Modern Best Practices

This plan aims to refactor the current "Happy Birthday" app code to follow modern Jetpack Compose and Material 3 best practices. This includes centralizing styling in the theme, improving component naming, and enhancing the preview experience.

## Proposed Changes

### UI Theme

#### [MODIFY] [Type.kt](file:///C:/Users/Admin/StudioProjects/Happy_Birthday/app/src/main/java/com/example/happybirthday/ui/theme/Type.kt)
- Move hardcoded font sizes and line heights from `MainActivity.kt` to the centralized `Typography` definition.
- Define `displayLarge` for the main birthday message and `headlineMedium` for the "from" text.

### Main Activity

#### [MODIFY] [MainActivity.kt](file:///C:/Users/Admin/StudioProjects/Happy_Birthday/app/src/main/java/com/example/happybirthday/MainActivity.kt)
- **Component Renaming**: Rename `GreetingImage` to `BirthdayGreetingCard` to better describe its role as a full-screen card component.
- **Surface Usage**: Wrap the content in a `Surface` to ensure correct background and content color handling according to Material 3.
- **Typography Integration**: Replace hardcoded `fontSize` and `lineHeight` parameters in `Text` composables with `style = MaterialTheme.typography...`.
- **Layout Improvements**:
    - Use `Modifier.align(Alignment.Center)` for the text overlay.
    - Ensure `GreetingText` fills the available space correctly.
- **Enhanced Previews**:
    - Add `@PreviewLightDark` to verify the UI in both themes.
    - Add a device preview to see how the large text fits on a standard screen.

## Verification Plan

### Automated Tests
- Run `./gradlew assembleDebug` to ensure the project still builds correctly after refactoring.

### Manual Verification
- Use **Compose Preview** in Android Studio to verify the UI appearance in both Light and Dark modes.
- Verify that the text remains legible and properly aligned with the new typography styles.
