# RNDemo1 - NativeBase

[Slides](https://docs.google.com/presentation/d/1BjiKXKonZIDzd2KSts2kLdwj7Zh6FW3UcFv5fK4QYDw/edit?usp=sharing)

# Setup + Packages

1.  Install expo globally:
    ```bash
    yarn global add expo-cli
    ```
2.  Install the react native debugger [here](https://github.com/jhen0409/react-native-debugger/releases/tag/v0.10.7)

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
5.  Change the text inide the `<Text> </Text>` of `App.js` to anything else. The simulator responds and updates instantly.
6.  `export default App()` and having `export default App` at the bottom are equivalent.
7.  The components being imported from `react-native` in `App.js`. These are great, but we can do better using [NativeBase](https://nativebase.io/). Show them a few components from the documentation.

# Native Base

1. Set up NativeBase (until the vector icons issue is resolved):
   ```bash
   yarn add -E native-base@2.13.8
   ```
2. Use this [card](https://docs.nativebase.io/Components.html#card-def-headref) in the application
3. Copy the card components from the documentations and place them in `App.js`:
   ```jsx
   function App() {
     return (
       <Container>
         <Header />
         <Content>
           <Card>
             <CardItem>
               <Body>
                 <Text>//Your text here</Text>
               </Body>
             </CardItem>
           </Card>
         </Content>
       </Container>
     );
   }
   export default App;
   ```
4. An error should occur. That is because we have not imported the NativeBase components! In `App.js`:
   ```javascript
   import {
     Container,
     Header,
     Content,
     Card,
     CardItem,
     Body,
     Text,
   } from "native-base";
   ```
5. Another error should occur. READ the error out loud and try to figure it out. This time, it's because we are importing the `Text` component from both `native-base` and `react-native`. Stick to the one from `NativeBase`.
6. Change the `//Your text here`.

   ```jsx
   function App() {
     return (
       <Container>
         <Header />
         <Content>
           <Card>
             <CardItem>
               <Body>
                 <Text>
                   Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed
                   do eiusmod tempor incididunt ut labore et dolore magna
                   aliqua. Ut enim ad minim veniam, quis nostrud exercitation
                   ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis
                   aute irure dolor in reprehenderit in voluptate velit esse
                   cillum dolore eu fugiat nulla pariatur. Excepteur sint
                   occaecat cupidatat non proident, sunt in culpa qui officia
                   deserunt mollit anim id est laborum.
                 </Text>
               </Body>
             </CardItem>
           </Card>
         </Content>
       </Container>
     );
   }
   export default App;
   ```

7. Add an Icon component somwhere in the app. The available icons can be found [here](https://expo.github.io/vector-icons/)

   Somewhere in `App.js`, add:

   ```jsx
   <Icon type="FontAwesome5" name="home" />
   ```
