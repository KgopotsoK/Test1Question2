# Welcome to your Expo app 👋

This is an [Expo](https://expo.dev) project created with [`create-expo-app`](https://www.npmjs.com/package/create-expo-app).

## Get started

1. Install dependencies

   ```bash
   npm install
   ```

2. Start the app

   ```bash
   npx expo start
   ```

In the output, you'll find options to open the app in a

- [development build](https://docs.expo.dev/develop/development-builds/introduction/)
- [Android emulator](https://docs.expo.dev/workflow/android-studio-emulator/)
- [iOS simulator](https://docs.expo.dev/workflow/ios-simulator/)
- [Expo Go](https://expo.dev/go), a limited sandbox for trying out app development with Expo

You can start developing by editing the files inside the **app** directory. This project uses [file-based routing](https://docs.expo.dev/router/introduction).

## Get a fresh project

When you're ready, run:

```bash
npm run reset-project
```

This command will move the starter code to the **app-example** directory and create a blank **app** directory where you can start developing.

## Learn more

To learn more about developing your project with Expo, look at the following resources:

- [Expo documentation](https://docs.expo.dev/): Learn fundamentals, or go into advanced topics with our [guides](https://docs.expo.dev/guides).
- [Learn Expo tutorial](https://docs.expo.dev/tutorial/introduction/): Follow a step-by-step tutorial where you'll create a project that runs on Android, iOS, and the web.

## Join the community

Join our community of developers creating universal apps.

- [Expo on GitHub](https://github.com/expo/expo): View our open source platform and contribute.
- [Discord community](https://chat.expo.dev): Chat with Expo users and ask questions.

React Native Shopping App

Project Overview
This React Native mobile application connects to the FakeStore API to display products in a shopping app interface. The app allows users to browse products and view detailed information about each item.



Navigation Structure 
**Technical Implementation:**
- Used `@react-navigation/native` and `@react-navigation/native-stack` for navigation
- Implemented a stack navigator with two main screens:
  - `HomeScreen` (product list) - located at `app/(tabs)/explore.jsx`
  - `DetailScreen` (product details) - located at `app/details.jsx`
- Registered screens in the navigator with appropriate options and titles

Product List Screen
**Implementation Details:**
- Created `ExploreScreen` component (`app/(tabs)/explore.jsx`) that:
  - Fetches products from `https://fakestoreapi.com/products` using `fetch` API
  - Uses `useEffect` for data fetching and `useState` for state management
  - Implements loading and error states with appropriate UI feedback
  - Displays products in a `FlatList` with card-like items
  - Each item shows product image, title, and price
  - Applied React Native StyleSheet for clean, responsive layout
  - Includes proper padding, borders, and styling for mobile UI

Product Detail Screen
**Implementation Details:**
- Created `DetailsScreen` component (`app/details.jsx`) that:
  - Receives product ID via route parameters using Expo Router's navigation
  - Fetches individual product details from `https://fakestoreapi.com/products/{id}`
  - Displays complete product information: image, title, price, description, and category
  - Handles loading states, error states, and "not found" scenarios
  - Uses appropriate styling for mobile UI (larger image, readable text formatting)
  - Demonstrates proper navigation between list and detail pages

Technical Stack
- **Framework**: React Native with Expo
- **Navigation**: Expo Router (file-based routing)
- **API**: FakeStore API (https://fakestoreapi.com)
- **State Management**: React hooks (useState, useEffect)
- **Styling**: React Native StyleSheet

File Structure
app/
├── (tabs)/              # Tab navigation group
│   ├── index.jsx        # Default home tab
│   ├── explore.jsx      # Products listing screen (main functionality)
│   └── _layout.jsx      # Tab navigator layout
├── details.jsx          # Product detail screen
└── _layout.jsx          # Root layout


Key Features
- **Product Browsing**: Clean grid layout of products with images and prices
- **Product Details**: Comprehensive product information display
- **Navigation**: Smooth transitions between screens using Expo Router
- **Error Handling**: Proper loading states and error messages
- **Responsive Design**: Mobile-optimized UI with appropriate touch targets

Screens
1. **Explore Screen** (`app/(tabs)/explore.jsx`): Displays all products in a scrollable list
2. **Detail Screen** (`app/details.jsx`): Shows detailed information about a single product

Data Flow
1. API call to FakeStore products endpoint
2. Data stored in component state using useState
3. Products passed to FlatList for rendering
4. On item press, navigation to detail screen with product ID
5. Detail screen fetches specific product data using the ID parameter

Styling Approach
- Used React Native's StyleSheet for consistent styling
- Implemented card-based design with shadows and borders
- Responsive image handling with contain resizeMode
- Typography hierarchy for better readability
- Mobile-first design principles

Setup Instructions
1. Install dependencies: `npm install`
2. Start the development server: `npx expo start`
3. Run on Android: `npx expo run:android`
4. Run on iOS: `npx expo run:ios`


