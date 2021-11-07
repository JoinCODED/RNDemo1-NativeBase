# RNDemo1 - NativeBase

[Slides](https://docs.google.com/presentation/d/1BjiKXKonZIDzd2KSts2kLdwj7Zh6FW3UcFv5fK4QYDw/edit?usp=sharing)

# Setup + Packages

1.  Install expo globally:
    ```bash
    yarn global add expo-cli
    ```
2.  Install the react native debugger [here](https://github.com/jhen0409/react-native-debugger/releases/tag/v0.10.7)
3.  Install `Expo` on your phones
4.  Install [XCode](https://docs.expo.io/versions/v37.0.0/workflow/ios-simulator/) if you're on Mac
5.  Install [android studio](https://docs.expo.io/versions/latest/workflow/android-studio-emulator/) if you're on PC

# Create an application

1.  Create a React Native application:
    ```bash
    expo-cli init my-first-app
    ```
2.  The terminal will now prompt us to select a template - select `blank` as our template.
3.  Explore the project structure.
    - `App.js` is the root component.
    - `package.json` - just like in React, this holds the packages installed in this project.
    - `app.json` - further applicaiton configurations.

# Run + Explore the application

1.  Start the application using `yarn start`
2.  Explore the Metro Bundler
3.  Run the app using the `Expo` mobile application by scanning the barcode.
4.  Run the app on the Xcode iPhone simulator (clicking `i` in the terminal or the `Run iOS Simulator` in the Metro Bundler window).
5.  Connect the app to the debugger
6.  Change the text inide the `<Text> </Text>` of `App.js` to anything else. The simulator responds and updates instantly.
7.  `export default App()` and having `export default App` at the bottom are equivalent.
8.  The components being imported from `react-native` in `App.js`. These are great, but we can do better using [NativeBase](https://nativebase.io/). Show them a few components from the documentation.

# Native Base

1.  Set up NativeBase (use version 2.13.8 until the vector icons issue is resolved):

    ```bash
    yarn add native-base styled-system
    ```

    ```bash
    expo install react-native-svg
    ```

    ```bash
    expo install react-native-safe-area-context
    ```

2.  Use this [card](https://docs.nativebase.io/building-card) in the application
3.  Copy the card components from the documentations and place them in `App.js`:
    ```jsx
    function App() {
      return (
        <Box rounded="lg" overflow="hidden" width="72" shadow={1}>
          <Box>
            <AspectRatio ratio={16 / 9}>
              <Image
                source={{
                  uri: 'https://www.techinafrica.com/wp-content/uploads/2019/07/carles-rabada-635097-unsplash-compressor.jpg',
                }}
                alt="image"
              />
            </AspectRatio>
            <Center
              bg="violet.500"
              _text={{ color: 'white', fontWeight: '700', fontSize: 'xs' }}
              position="absolute"
              bottom={0}
              px="3"
              py="1.5"
            >
              PHOTOS
            </Center>
          </Box>
          <Stack p="4" space={3}>
            <Stack space={2}>
              <Heading size="md" ml="-1">
                //Heading
              </Heading>
              <Text fontSize="xs" fontWeight="500" ml="-0.5" mt="-1">
                //Subheading
              </Text>
            </Stack>
            <Text fontWeight="400">//Description</Text>
          </Stack>
        </Box>
      );
    }
    export default App;
    ```
4.  An error should occur. That is because we have not imported the NativeBase components! In `App.js`:
    ```javascript
    import {
      Box,
      Heading,
      Icon,
      AspectRatio,
      Image,
      Text,
      Center,
      HStack,
      Stack,
      NativeBaseProvider,
    } from 'native-base';
    ```
5.  Another error should occur. READ the error out loud and try to figure it out. This time, it's because we are importing the `Text` component from both `native-base` and `react-native`. Stick to the one from `NativeBase`.
6.  Change the `//Heading //Subheading and //Description `.

    ```jsx
    function App() {
      return (
        <Box rounded="lg" overflow="hidden" width="72" shadow={1}>
          <Box>
            <AspectRatio ratio={16 / 9}>
              <Image
                source={{
                  uri: 'https://www.techinafrica.com/wp-content/uploads/2019/07/carles-rabada-635097-unsplash-compressor.jpg',
                }}
                alt="image"
              />
            </AspectRatio>
            <Center
              bg="violet.500"
              _text={{ color: 'white', fontWeight: '700', fontSize: 'xs' }}
              position="absolute"
              bottom={0}
              px="3"
              py="1.5"
            >
              PHOTOS
            </Center>
          </Box>
          <Stack p="4" space={3}>
            <Stack space={2}>
              <Heading size="md" ml="-1">
                The Silicon Valley
              </Heading>
              <Text fontSize="xs" fontWeight="500" ml="-0.5" mt="-1">
                The global center for high technology and innovation.
              </Text>
            </Stack>
            <Text fontWeight="400">
              Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
              eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut
              enim ad minim veniam, quis nostrud exercitation ullamco laboris
              nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in
              reprehenderit in voluptate velit esse cillum dolore eu fugiat
              nulla pariatur. Excepteur sint occaecat cupidatat non proident,
              sunt in culpa qui officia deserunt mollit anim id est laborum.
            </Text>
          </Stack>
        </Box>
      );
    }
    export default App;
    ```
"# RNDemo1-NativeBase-2021" 
