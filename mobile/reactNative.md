###### tags: `Mobile`, `React Native`
# React Native
![](https://i.imgur.com/uUlUfKA.png)

# Project
## Creating a new application
React Native has a built-in command line interface, which you can use to generate a new project. You can access it without installing anything globally using npx, which ships with Node.js. Let's create a new React Native project called "Tasks":
```
npx react-native init Tasks
```

## Running your React Native application
### Step 1: Start Metro
First, you will need to start Metro, the JavaScript bundler that ships with React Native. Metro "takes in an entry file and various options, and returns a single JavaScript file that includes all your code and its dependencies."—Metro Docs

To start Metro, run npx react-native start inside your React Native project folder:
```
npx react-native start
```

### Step 2: Start your application
Let Metro Bundler run in its own terminal. Open a new terminal inside your React Native project folder. Run the following:
```
npx react-native run-android
```