Assignment 2 Android App – NIT3213
I developed this Android app as Assignment 2 for the NIT3213 unit at Victoria University. It is a final assignment Android app that uses the latest Android development trends, including user authentication, showing an entity on a dashboard, and clean architecture with MVVM, Retrofit, and dependency injection.

1. Features
1.1 Login Screen
- Authenticated users using first name and student ID (e.g., s12345678).
- Endpoint-based login based on location: /footscray/auth, /sydney/auth, /ort/auth
1.2 Dashboard Screen
- Displays API return list of destinations with keypass.
- Utilizes RecyclerView for simple and scrollable data presentation.
1.3 Details Screen
- Presents detailed information about a destination, including long descriptions.
1.4 Logout
- Allows users to return to the login screen from the details screen.
2. Architecture
- MVVM (Model-View-ViewModel): Simple separation of UI and logic
- Hilt: Dependency Injection
- Retrofit: For HTTP request
- Gson: For JSON parsing
- LiveData + ViewModel: Decoupling of UI with data changes
- ViewBinding: Type-safe access to views in Kotlin
3. Project Structure

com.example.vuapp
├── data
│   ├── api
│   │   ├── AuthApiService.kt
│   │   └── DashboardApiService.kt
│   ├── model
│   │   ├── DashboardResponse.kt
│   │   └── Entity.kt
│   └── repository
│       ├── AuthRepository.kt
│       └── DashboardRepository.kt
├── di
│   └── AppModule.kt
├── ui
│   ├── login
│   │   ├── LoginActivity.kt
│   │   └── LoginViewModel.kt
│   ├── dashboard
│   │   ├── DashboardActivity.kt
│   │   ├── DashboardViewModel.kt
│   │   └── EntityAdapter.kt
│   └── details
│       └── DetailsActivity.kt
├── utils
│   └── Constants.kt
├── MainActivity.kt
└── MainApplication.kt

4. Dependencies

// Retrofit
implementation("com.squareup.retrofit2:retrofit:2.9.0")
implementation("com.squareup.retrofit2:converter-gson:2.9.0")

// Hilt for DI
implementation("com.google.dagger:hilt-android:2.50")
kapt("com.google.dagger:hilt-compiler:2.50")

// ViewModel & LiveData
implementation("androidx.lifecycle:lifecycle-viewmodel-ktx:2.6.2")
implementation("androidx.lifecycle:lifecycle-livedata-ktx:2.6.2")

// Material UI
implementation("com.google.android.material:material:1.11.0")

// ViewBinding
buildFeatures {
    viewBinding = true
}

5. API Endpoints
Base URL: https://nit3213api.onrender.com/
Endpoint	  Method	  Description
/footscray/auth	  POST	  Login (location-based)
/dashboard/{keypass}	  GET	  Fetch destination entity list
6. UI/UX
- Adheres to current Material Design principles
- Scrollable layouts for extended content
- Shows error messages for missing fields, invalid credentials, and API errors
- Supports back button and logout navigation
- Compatible with emulator and real device
7. Testing
- Tested on the emulator
- Verified successful and failed logins
- Tested API delay and navigation patterns
- viewModel unit tests included optionally
8. Using the App
1. Open the project on Android Studio
2. Plug in a hardware device or start an emulator
3. Run the app
4. Login with:
   - Username: Your first name
- Password: Student ID (e.g., s12345678)
5. Observe the dashboard and select a destination for details
6. Use logout to return to login screen
9. License
This work has been developed for educational purposes alone as part of the NIT3213 course in Victoria University.
Use is restricted to testing and demonstration in an educational setting.
10. Author
Student Name: Pratikshya Bhujel
Student ID: s8136432
