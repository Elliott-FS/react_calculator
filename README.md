# React calculator App
# Review, refactor, add features, change styles
# Review useReducer
# Add light/dark mode
# Change styling color scheme
# Animated Background?



# Getting Started with Create React App



This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

The page will reload when you make changes.\
You may also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can't go back!**

If you aren't satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you're on your own.

You don't have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn't feel obligated to use this feature. However we understand that this tool wouldn't be useful if you couldn't customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: [https://facebook.github.io/create-react-app/docs/code-splitting](https://facebook.github.io/create-react-app/docs/code-splitting)

### Analyzing the Bundle Size

This section has moved here: [https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size](https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size)

### Making a Progressive Web App

This section has moved here: [https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app](https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app)

### Advanced Configuration

This section has moved here: [https://facebook.github.io/create-react-app/docs/advanced-configuration](https://facebook.github.io/create-react-app/docs/advanced-configuration)

### Deployment

This section has moved here: [https://facebook.github.io/create-react-app/docs/deployment](https://facebook.github.io/create-react-app/docs/deployment)

### `npm run build` fails to minify

This section has moved here: [https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify](https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify)



*, * ::before, *::after {
    box-sizing: border-box;

}

body {
    margin: 0;
    background: linear-gradient(to right, #00AAFF, #00FF6C)
    
}

.calculator-grid{
    display: grid;
    margin-top: 2rem;
    justify-content: center;
    grid-template-columns: repeat(4, 6rem);
    grid-template-rows: minmax(7rem, auto) repeat(5, 6rem);
    
}

.calculator-grid > button {
    cursor: pointer;
    font-size: 2rem;
    border: 1px solid white;
    outline: none;
    background-color: rgb(255, 255, 255, .75);
}

.calculator-grid > button:hover,
.calculator-grid > button:focus{
    background-color: rgba(78, 89, 210, 0.9);
}


.span-two{
    grid-column: span 2;
}

.output{
    grid-column: 1/ -1;
    background-color:rgba(0, 0, 0, .75);
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    justify-content: space-around;
    padding: .75rem;
    word-wrap: break-word;
    word-break: break-all;
}

.output .previous-operand{
    color: rgb(255, 255, 255, .75);
    font-size: 1.5rem;
}

.output .current-operand{
    color: white;
    font-size: 2.5rem;
}

.container{
    width: 385px;
    height: 500px;
    background-color:rgba(0, 0, 0, .75);
    clip-path: polygon(75% 0%, 100% 50%, 75% 100%, 0% 100%, 25% 50%, 0% 0%);
    transition: all 2s ease;
    perspective: 200px;
}


.container:hover{
    /* altered shape path to create animations see % changes */
    clip-path: polygon(75% 0%, 100% 50%, 75% 50%, 0% 50%, 25% 100%, 0% 0%);
    transform: rotateY(180deg);
    transition: all 3s ease;
}
/* alternate shape path */
/* 25% 0%, 100% 0%, 75% 100%, 0% 100% */