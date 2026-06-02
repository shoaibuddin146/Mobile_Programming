COMP5450 - Exercise 3: Messages Directory App

Student: Shoaib Uddin Mohammed
Student ID: 1308823
Course: COMP5450 - Mobile Programming
Instructor: Dr. Sabah Mohammed
Date: June 2, 2026


WHAT THIS APP DOES

This is a React Native app that shows a directory of message categories. When you open the app, you see 6 colored circles: You, Home, Love, Family, Friends, and School. Each circle has a picture icon inside it on a white background. When you tap a circle, it opens a new screen that shows the messages saved in that category.

I built this for Exercise 3 of COMP5450. The app uses TypeScript and React Navigation to move between screens. It is responsive and works on phones, tablets, and web browsers.


HOW TO RUN THIS IN INTELLIJ IDEA

Step 1: Install What You Need

Before you start, make sure you have these installed on your computer:

1. Node.js 18 - Download from https://nodejs.org/dist/v18.20.4/node-v18.20.4-x64.msi (Use version 18, not 20)
2. IntelliJ IDEA - Download from https://www.jetbrains.com/idea/
3. Expo CLI - Open a terminal and run: npm install -g expo-cli
4. Android Studio - Download from https://developer.android.com/studio (for the Android emulator)

Step 2: Open the Project in IntelliJ

1. Open IntelliJ IDEA
2. Click File -> Open
3. Find the folder called MessagesDirectory and select it
4. Click OK
5. Wait for IntelliJ to load the project

Step 3: Install the Dependencies

1. In IntelliJ, open the Terminal tab at the bottom
2. Type this command and press Enter:
   **npm install
   npx expo install react-native-web@~0.19.6 react-dom@18.2.0 @expo/webpack-config@^19.0.0**
3. Wait for it to finish. This downloads all the packages the app needs.

Step 4: Start the App

You can run the app in 3 different ways:

Option A: Run in Chrome (Easiest)

1. In the terminal, type:
   npx expo start --web
2. Wait for it to start
3. It will open a new tab in Chrome automatically
4. You can see the app running in your browser

Option B: Run on Android Emulator

1. First, open Android Studio and start an emulator:
   - Open Android Studio
   - Click More Actions -> Virtual Device Manager
   - Click the Play button next to a device to start it
2. In IntelliJ terminal, type:
   npx expo start
3. Press a on your keyboard when it asks
4. The app will open on the Android emulator

Option C: Run on Your Real Phone

1. Install the Expo Go app from the App Store or Google Play
2. In IntelliJ terminal, type:
   npx expo start
3. A QR code will show up in the terminal
4. Open the Expo Go app on your phone
5. Scan the QR code
6. The app will load on your phone


PROJECT STRUCTURE

Here is what each folder and file does:

MessagesDirectory/
  App.tsx                    - Main file, sets up navigation
  package.json               - List of packages the app needs
  tsconfig.json              - TypeScript settings
  src/
    screens/
      HomeScreen.tsx         - Shows the 6 category circles
      MessagesScreen.tsx     - Shows messages for one category
    components/
      CategoryCard.tsx       - Circular category button
      MessageItem.tsx        - Message card component
    data/
      messagesData.ts        - Sample messages with my names
    types/
      index.ts               - TypeScript types
    constants/
      colors.ts              - Colors used in the app
  assets/
    images/                  - Category icons (PNG files)
    screenshots/             - Screenshots for README


HOW THE APP WORKS

Home Screen
- Shows a title "Messages Directory" at the top
- Shows 6 colored circles in a 2-column grid
- Each circle has:
  - A white square box in the middle with a picture icon
  - The category name below it
- Colors match the assignment picture:
  - You = Orange-Red (#FF4500)
  - Home = Light Blue (#87CEEB)
  - Love = Steel Blue (#4682B4)
  - Family = Purple (#6A5ACD)
  - Friends = Pink (#FF69B4)
  - School = Blue (#00BFFF)
- The icons are centered inside white boxes that match the circle color theme
- Responsive: Circles resize based on screen width

Messages Screen
- Opens when you tap a category
- Shows a header with the category color
- Has a back arrow to go back
- Shows all messages in that category
- Each message shows:
  - Who sent it
  - When it was sent
  - The message text
  - A colored line on the left
- Responsive: Text size and padding adjust based on screen size


PERSONALIZED NAMES I USED

I used names from my life in the messages:

You: Mine, Self
Home: Mom, Dad, Jameel Brother, Zameer Brother, Sister
Love: My_Love, Friends, Fareed, Sajjad, Naser
Family: Dadi, Aunt Sana, Daddy, Homies, Mom
Friends: Kaleem, Zaid, Zara, Mohammed, Sarah
School: Professor Sabah Mohammed, Classmate, Registrar, Advisor, TA


RESPONSIVE DESIGN

The app uses Dimensions from React Native to check screen size:

- Small phones (width < 360px): Smaller circles, smaller text, less padding
- Normal phones (360px - 768px): Standard size
- Tablets (width > 768px): Bigger circles, larger text, more padding

This means the app looks good on:
- iPhone SE (small screen)
- iPhone 14 / Samsung Galaxy (normal screen)
- iPad / Android tablet (large screen)
- Chrome web browser (any size window)


SCREENSHOTS

Home Screen
[assets/screenshots/home_screen.png]
The main screen with all 6 category circles and centered icons

Messages Screen
[assets/screenshots/messages_screen.png]
Messages inside the School category

Running in Chrome
[assets/screenshots/web_view.png]
The app running in Chrome browser


PROBLEMS I HAD AND HOW I FIXED THEM

1. Navigation was not working - I forgot to wrap the app in NavigationContainer. Fixed by adding it in App.tsx.

2. Icons were not centered - The icon images were off-center in the circles. I added a white square box inside each circle and centered the image inside it using justifyContent and alignItems.

3. Screen was too small on web - I used Dimensions to make the circles resize based on screen width. I check if the screen is small, normal, or tablet size and change sizes.

4. TypeScript errors - I had to add proper types for navigation props using StackNavigationProp and RouteProp.

5. Expo error on Windows with Node 20 - I got an error about node:sea. I fixed it by using Expo 49 and Node.js 18 instead of Expo 50 and Node.js 20.

6. Grid not centered on big screens - I added columnWrapperStyle and justifyContent center to center the 2-column grid.

7. Different theme colors - I made sure each circle uses the exact color from the assignment screenshot. The icon box is white so it matches the background theme of each circle.


WHAT I LEARNED

- How to use React Navigation to move between screens
- How to pass data between screens using route parameters
- How to make a grid layout with FlatList and numColumns
- How to use TypeScript with React Native
- How to style components with StyleSheet
- How to make an app responsive using Dimensions API
- How to center images inside circular buttons
- How to run a React Native app in Chrome, emulator, and real phone


NOTES

- I tested this on Chrome web browser, Android emulator, and my phone. It works on all three.
- All messages are fake sample data for the assignment, but I used real names from my life.
- The app was built with Expo 49 because it works better with Node.js 18 on Windows.
- The app is responsive and looks good on small phones, normal phones, tablets, and web browsers.
- The icons are centered inside white boxes that match the circle color theme.
