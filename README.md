# 09_notifications_vejledning

I denne øvelse skal du bygge en app til dine bøger, appen kan:

- Tag billeder af dine bøger (kamera)
- Se dem i din “læseliste” (AsyncStorage + FileSystem)
- Få en daglig påmindelse om at læse (Expo Notifications)
- Del dine bøger med andre (expo-sharing / Share)
- Oplev animationer (Reanimated)

## Start med the basic

Lav din app
````
npx create-expo-app bookbuddy --template blank


Download de nødvendige dependencies 

````
  "dependencies": {
    "@react-native-async-storage/async-storage": "^2.2.0",
    "@react-navigation/native": "^7.1.17",
    "@react-navigation/native-stack": "^7.3.26",
    "babel-preset-expo": "~54.0.0",
    "expo": "~54.0.12",
    "expo-camera": "~17.0.8",
    "expo-device": "~8.0.9",
    "expo-file-system": "~19.0.16",
    "expo-notifications": "~0.32.12",
    "expo-sharing": "~14.0.7",
    "expo-status-bar": "~3.0.8",
    "react": "19.1.0",
    "react-native": "0.81.4",
    "react-native-gesture-handler": "~2.28.0",
    "react-native-reanimated": "~4.1.1",
    "react-native-safe-area-context": "~5.6.0",
    "react-native-screens": "~4.16.0",
    "react-native-worklets": "0.5.1"
  },
````

Opret dine mapper med de nødvendige filer 
- components
  - Library.js
  - Notifications.js
  - Sharing
- screens
  - CameraScreen.js
  - HomeScreen.js
- style

## App.js

Lav din navigation i app.js

````
import React from 'react';
import { NavigationContainer } from '@react-navigation/native';
import { createNativeStackNavigator } from '@react-navigation/native-stack';

import HomeScreen from './screens/HomeScreen';

const Stack = createNativeStackNavigator();

export default function App() {
  return (
    <NavigationContainer>
      <Stack.Navigator>
        <Stack.Screen name="Home" component={HomeScreen} options={{ title: "BookBuddy 📚" }} />
      </Stack.Navigator>
    </NavigationContainer>
  );
}
 
## Lav noget sej styling

Indsæt dette i App.json
````
plugins: ['react-native-reanimated/plugin'],
````

