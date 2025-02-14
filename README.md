# First React Native App using Expo Router

## Project Setup
1. Navigate to the project directory:
   ```sh
   cd prodev-mobile-setup

## Initialize the Expo project:
npx create-expo-app@latest .

## start development server:
npx expo start

# PROJECT GUIDE

<img width="377" alt="4fbff16de8c8372cbd733d057e9ddc321e9b2105" src="https://github.com/user-attachments/assets/1e03abd1-e190-49e6-bd34-5b5bae3df7a2" />


Instructions:
Step 1: Set Up Your Project

Create a new expo app in the directory prodev-mobile-app-0x03 using the following command:

npx create-expo-app@latest prodev-mobile-app-0x03

Navigate into the project directory:

cd prodev-mobile-app-0x03

## Reset the project using:
```
npm run reset-project
```

Download the required assets from here and place them in the assets/images directory inside your project.

## Step 2: Implement Styles

Create the following file styles/index.tsx under the project root directory. Open styles/index.tsx and define the following styles** 
```
import { StyleSheet } from "react-native";

const styles = StyleSheet.create({
  container: {
    flex: 1,
    padding: 20,
    backgroundColor: '#fff',
    position: 'relative'
  },
  navGroup: {
    flexDirection: 'row',
    justifyContent: 'space-between',
    marginBottom: 20,
    marginTop: 11
  },
  largeText: {
    fontSize: 40,
    fontWeight: 700,
  },
  smallText: {
    fontSize: 12,
    color: '#7E7B7B'
  },
  placeholderText: {
    fontSize: 18,
    color: '#7E7B7B',
    marginBottom: 7
  },
  inputField: {
    borderWidth: 1,
    borderRadius: 10,
    height: 50,
    borderColor: '#7E7B7B',
    paddingHorizontal: 10
  },
  passwordGroup: {
    flexDirection: 'row',
    borderWidth: 1,
    alignItems: 'center',
    height: 50,
    borderRadius: 10,
    paddingHorizontal: 10,
    borderColor: '#7e7b7b'
  },
  formGroup: {
    marginTop: 44
  },
  forgotPasswordText: {
    fontSize: 17,
    marginTop: 9,
    textAlign: 'right',
    color: '#34967C'
  },
  button: {
    backgroundColor: '#2B876E',
    height: 53,
    borderRadius: 10,
    marginTop: 25,
    justifyContent: 'center',
    alignItems: 'center'
  },
  buttonText: {
    fontSize: 17,
    color: 'white'
  },
  socialMediaButton: {
    borderWidth: 1,
    height: 50,
    justifyContent: 'center',
    alignItems: 'center',
    borderRadius: 10
  },
  socialMediaButtonText: {
    fontSize: 18,
    color: '#0D0D0D',
    fontWeight: 400
  },
  socialMediaButtonGroup: {
    gap: 15,
    marginTop: 25
  },
  dividerGroup: {
    flexDirection: 'row',
    alignItems: 'center',
    gap: 10,
    marginTop: 29
  },
  divider: {
    borderWidth: 0.5,
    borderColor: "#c2c2c2",
    flex: 1
  },
  dividerText: {
    fontSize: 17,
    color: "#C2C2C2",
  },
  subTextGroup: {
    flexDirection: 'row',
    position: 'absolute',
    bottom: 33,
    left: 77,
    right: 76
  },
  subText: {
    fontSize: 18,
    color: '#b5b5b5'
  },
  subTextJoin: {
    fontSize: 18,
    color: '#FFA800',
    fontWeight: 600
  }
});


export {
  styles
}
```
## Step 3: Modify App Files

Modify your app/_layout.tsx file to look like this   
```
import { Stack } from "expo-router";

export default function RootLayout() {
  return <Stack screenOptions={{
    headerShown: false
  }} />;
}
```
## Modify app/index.tsx to structure the login screen:
```
import { Text, TextInput, View, TouchableOpacity, Image } from "react-native";
import { styles } from "@/styles";
import { SafeAreaView, SafeAreaProvider } from "react-native-safe-area-context";
import { FontAwesome, Ionicons } from "@expo/vector-icons";

export default function Index() {
  return (
    <SafeAreaProvider>
      <SafeAreaView style={styles.container}>
        <View style={styles.navGroup}>
          <Ionicons name="arrow-back" size={25} />
          <Image source={require('@/assets/images/logo.png')} />
        </View>
        <Text style={styles.largeText}>Sign in to your</Text>
        <Text style={styles.largeText}>Account</Text>
        <Text style={styles.smallText}>
          Enter your email and password to sign in.
        </Text>

        <View style={styles.formGroup}>
          <View>
            <Text style={styles.placeholderText}>Email</Text>
            <TextInput keyboardType="email-address" style={styles.inputField} />
          </View>
          <View style={{ marginTop: 20 }}>
            <Text style={styles.placeholderText}>Password</Text>
            <View style={styles.passwordGroup}>
              <TextInput style={{ flex: 1 }} />
              <FontAwesome name="eye-slash" size={24} color="#7E7B7B" />
            </View>
          </View>
          <Text style={styles.forgotPasswordText}>Forgot password?</Text>
        </View>

        <TouchableOpacity style={styles.button}>
          <Text style={styles.buttonText}>Sign in</Text>
        </TouchableOpacity>

        <View style={styles.dividerGroup}>
          <View
            style={styles.divider}
          ></View>
          <Text
            style={styles.dividerText}
          >
            OR
          </Text>
          <View
            style={styles.divider}
          ></View>
        </View>

        <View style={styles.socialMediaButtonGroup}>
          <TouchableOpacity style={styles.socialMediaButton}>
            <View
              style={{
                flexDirection: "row",
                alignItems: "center",
                gap: 5,
              }}
            >
              <Image source={require("@/assets/images/google.png")} />
              <Text style={styles.socialMediaButtonText}>
                Continue with Google
              </Text>
            </View>
          </TouchableOpacity>

          <TouchableOpacity style={styles.socialMediaButton}>
            <View
              style={{
                flexDirection: "row",
                alignItems: "center",
                gap: 5,
              }}
            >
              <Image source={require("@/assets/images/facebook.png")} />
              <Text style={styles.socialMediaButtonText}>
                Continue with Facebook
              </Text>
            </View>
          </TouchableOpacity>
        </View>

        <View style={styles.subTextGroup}>
          <Text style={styles.subText}>Don't have an account?</Text>
          <Text style={styles.subTextJoin}>Join now</Text>
        </View>
      </SafeAreaView>
    </SafeAreaProvider>
  );
}
```

## Final Steps 1. Run the application on Expo Go:

npx expo start

Test the app on a physical device using Expo Go App and confirm all render correctly.
