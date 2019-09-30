# RNDemo1 - NativeBase

[Slides](https://docs.google.com/presentation/d/1BjiKXKonZIDzd2KSts2kLdwj7Zh6FW3UcFv5fK4QYDw/edit?usp=sharing)

1.  `yarn global add expo-cli` to add expo-cli globally on our machines.
2.  `expo-cli init my-first-app` to create our React Native application.
3.  The terminal will now prompt us for several actions. Select the following:
    - select `blank` as our template.
    - give the app the name `First App`
    - Choose `Y` to install all dependencies.
4.  Show them the project structure.
    - `App.json` is the root component.
    - `package.json` - just like in React, this holds the packages installed in this project.
    - `app.json` - further applicaiton configurations.
5.  Finally, while inside the project directory, run `yarn start`.
6.  Show them how to run the app using the `Expo` mobile application by scanning the barcode.
7.  Now, show them how to run the app on the Xcode iPhone simulator (clicking `i` in the terminal or the `Run iOS Simulator` in the Metro Bundler window).
8.  Change the text inide the `<Text> </Text>` of `App.js` to anything else. Save and show them that the simulator responds and updates instantly.
9.  Show them that `export default App()` and having `export default App` at the bottom are equivalent.
10. Show them the components being imported from `react-native` in `App.js`. These are great, but we can do more easily using [NativeBase](https://nativebase.io/). Show them a few components from the documentation.

11. Setting up NativeBase:

    - `yarn add native-base`
    - `yarn add @expo/vector-icons`

12. Now let us use this [card](https://docs.nativebase.io/Components.html#card-def-headref) in our application.

13. From the documentation, copy the card components and place them in `App.js`:

        ```javascript
        export default function App() {
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

        ```

14. An error should occur. That is because we have not imported the NativeBase components! In `App.js`:

    ```javascript
    import {
      Container,
      Header,
      Content,
      Card,
      CardItem,
      Body,
      Text
    } from "native-base";
    ```

15. Another error should occur. READ the error out loud and let the students try to figure it out. This time, it's because we are importing the `Text` component from both `native-base` and `react-native`. Stick to the one from `NativeBase`.

16. Finally, change the `//Your text here`.
    ```javascript
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
                    ullamco laboris nisi ut aliquip ex ea commodo consequat.
                    Duis aute irure dolor in reprehenderit in voluptate velit
                    esse cillum dolore eu fugiat nulla pariatur. Excepteur sint
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
