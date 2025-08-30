# JEE Mock Test Series

JEE Mock Test Series is an Android application designed to help JEE aspirants practice mock tests, track their progress, and view solutions. The app is built using Kotlin, Android Jetpack components, Firebase, and Material Design.

## Features

- **User Authentication:** Sign in with Google using Firebase Authentication.
- **Mock Test Listing:** Browse available mock tests with subject and time details.
- **Test Taking:** Answer multiple-choice questions, navigate between questions, and submit answers.
- **Result Calculation:** View detailed results including subject-wise marks, wrong answers, attempts, and accuracy.
- **Solution Review:** Review solutions for each question after submitting a test.
- **Navigation Drawer:** Access Home, About, and Logout from the side menu.
- **Data Persistence:** User preferences and test data are stored using Firebase Firestore and SharedPreferences.

## Detailed Features

### Test Taking System
- **Timer Function:** Real-time countdown timer for each mock test
- **Question Navigation:** 
  - Quick jump to any question
  - Mark questions for review
  - Color-coded indicators (Attempted, Not Attempted, Marked for Review)
- **Auto-Submit:** Tests are automatically submitted when time expires

### Scoring System
- **Marking Scheme:**
  - +4 marks for correct answers
  - -1 mark for incorrect answers
  - 0 marks for unattempted questions
- **Section-wise Analysis:**
  - Physics
  - Chemistry
  - Mathematics
- **Detailed Analytics:**
  - Time spent per question
  - Subject-wise accuracy
  - Overall percentile
  - Comparison with other test-takers

### Technical Specifications

#### Firebase Integration
- **Authentication:** Google Sign-in API
- **Cloud Firestore:**
  - Real-time data synchronization
  - Offline data persistence
  - Secure data access rules
- **Cloud Storage:** For storing images and diagrams
- **Analytics:** User engagement tracking

#### Android Architecture Components
- **ViewModel:** For managing UI-related data
- **LiveData:** For observable data holders
- **Navigation Component:** For handling fragment transactions
- **Data Binding:** For declarative UI elements
- **Room Database:** For local caching

#### UI/UX Features
- **Material Design Components:**
  - Material Cards for questions
  - Bottom Navigation
  - Floating Action Buttons
  - Custom Toolbar
- **Custom Animations:**
  - Question transitions
  - Loading animations
  - Result presentation
- **Responsive Layout:**
  - Support for different screen sizes
  - Portrait and landscape modes
  - Tablet optimization

### Security Features
- **Data Encryption:** For stored user data
- **Session Management:** Auto logout on inactivity
- **Test Security:**
  - Screenshot prevention
  - Back button handling
  - Multiple session prevention

### Performance Optimization
- **Lazy Loading:** For images and heavy content
- **Cache Management:** For offline access
- **Memory Management:**
  - Image compression
  - Efficient data structures
  - Resource cleanup

### Error Handling
- **Network Issues:**
  - Offline mode support
  - Auto-retry mechanism
  - Data synchronization
- **Crash Reporting:** Using Firebase Crashlytics
- **User Feedback:** In-app error reporting

## System Requirements

### Minimum Requirements
- Android 6.0 (API level 23) or higher
- 2GB RAM
- 50MB free storage
- Active internet connection for synchronization

### Recommended Requirements
- Android 8.0 or higher
- 4GB RAM
- 200MB free storage
- Stable internet connection

## Future Enhancements
- Video solutions integration
- Peer comparison
- Personalized test recommendations
- Live tests with real-time rankings
- Performance prediction using AI
- Study material integration

## Main Components

### Activities

- **SpActivity:** Splash screen shown at app launch.
- **getstartedActivity:** Entry screen with a "Get Started" button leading to sign-in.
- **signinActivity:** Handles Google sign-in and Firebase authentication.
- **MainActivity:** Hosts the navigation drawer and main fragments.

### Fragments

- **HomeFragment:** Displays a list of available mock tests using [`Tests_Adapter`](app/src/main/java/com/farfromcampus/jeemocktestseries/Tests_Adapter.kt).
- **MockReviewFragment:** Shows mock test details and instructions before starting the test.
- **MockTestFragment:** Main test interface for answering questions, navigating, and submitting.
- **SubmissionFragment:** Displays test results and provides access to solutions.
- **SolutionFragment:** Lists all questions with their solutions for review.
- **AboutFragment:** Information about the app and its creators.
- **BlankFragment:** Placeholder fragment for logout.

### Data Models

- [`Mocktest`](app/src/main/java/com/farfromcampus/jeemocktestseries/models/Mocktest.kt): Represents a mock test with questions, type, and metadata.
- [`Test`](app/src/main/java/com/farfromcampus/jeemocktestseries/models/Questions.kt): Represents a user's test session, answers, and marks.
- [`Questions`](app/src/main/java/com/farfromcampus/jeemocktestseries/models/Questions.kt): Represents individual questions.
- [`Aspirant`](app/src/main/java/com/farfromcampus/jeemocktestseries/models/Aspirant.kt): Represents a user/aspirant.
- [`AsptAnswer`](app/src/main/java/com/farfromcampus/jeemocktestseries/models/AsptAnswer.kt): Stores answers submitted by aspirants.

### Data Access Objects (DAOs)

- [`Mocktestdao`](app/src/main/java/com/farfromcampus/jeemocktestseries/daos/Mocktestdao.kt): CRUD operations for mock tests.
- [`Questiondao`](app/src/main/java/com/farfromcampus/jeemocktestseries/daos/Questiondao.kt): CRUD operations for questions.
- [`Aspirantdao`](app/src/main/java/com/farfromcampus/jeemocktestseries/daos/Aspirantdao.kt): CRUD operations for aspirants.
- [`AsptAnswerdao`](app/src/main/java/com/farfromcampus/jeemocktestseries/daos/AsptAnswerdao.kt): CRUD operations for aspirant answers.

### UI

- Uses Material Design components and custom styles defined in [app/src/main/res/values](app/src/main/res/values).
- Data binding is enabled for efficient UI updates.

## How to Build and Run

1. Clone the repository.
2. Open in Android Studio or VS Code with Android extensions.
3. Ensure you have a valid `google-services.json` for Firebase.
4. Build the project using Gradle (`./gradlew build` or via IDE).
5. Run on an emulator or Android device.

## Contributing

Feel free to open issues or submit pull requests for improvements.

## License

This project is licensed under the MIT License.

---

**For more details, see the source files:**
- [app/src/main/java/com/farfromcampus/jeemocktestseries/](app/src/main/java/com/farfromcampus/jeemocktestseries/)
- [app/src/main/res/layout/](app/src/main/res/layout/)
- [app/build.gradle](app/build.gradle)