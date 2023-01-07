# Explain using code examples what is meant by props and state in React JS?

In React, props and state are both used to store and manage data within a component.

Props, short for properties, are a way to pass data from a parent component to a child component. They are essentially read-only values that are either passed directly to the component when it is created.

            function Note( {note, deleteNote, changeColor, editNote} ) {

                function handleDelete(){
                    deleteNote(note.id)
                }

In the example above, {note, deleteNote, changeColor, editNote} are all props. note is an object, and deleteNote, changeColor and editNote are all functions.

State, on the other hand, is used to store data within a component that can change and cause the component to re-render. It should be used for values that are specific to a particular component and are likely to change within the component.

            function Notepad() {
                const [notes, setNotes] = useState([])  
                const newText = useRef()

                // Add note to the current set of notes
                function addNote(){
                    const text = newText.current.value
                    setNotes(prevNotes => {
                        return [...prevNotes, {id: new_id, name: text, bg: null}]
                    })  
                }
}

In the above example, useState is used to  store an initially empty list of note components, which can be updated using the setNotes function. When the list of notes is changed the component is re-rendered.



# In functional programming, what does the term functor mean? Can you give an example in JavaScript?

A functor is a type of object that can be "mapped" over. This means that it has a built-in way to apply a function to each element in the object and create a new object with the transformed elements.

One common example of a functor in JavaScript is the Array type. You can use the Array.map() method to apply a function to each element in an array and create a new array with the transformed elements.

let nums = [1, 2, 3, 4];
nums = nums.map(number => number + 1);

In the above example, each number in the array is incremented by one.

# We have looked at three kinds of asynchronous programming mechanisms,namely callbacks, promises and streams. Mention one advantage and one disadvantage of each type.

Callbacks
	Advantages:
	- Callbacks are compatible with most JavaScript environments, including older browsers.
	Disadvantages:
	- Using callbacks exclusively can lead to multiple nested callbacks that are difficult to read and maintain.
Promises
	Advantages:
	- Promises can be chained together, allowing you to write asynchronous code in a linear, easy-to-read style.
	Disadvantages:
	- Promises do not provide a way to cancel an asynchronous operation once it has started.
Streams
	Advantages:
	- Streams are easy to chain together, allowing developers to create complex data processing pipelines
	Disadvantages:
	- Streams are not suitable for all types of data and use cases. They are best suited for handling large amounts of data that can be processed in a sequential or incremental manner.

# With the aid of a diagram and example code, describe the Cascading Style Sheets (CSS) Box Model and show how it can be used to space DOM elements

The CSS Box Model is a way of representing the layout of a webpage as a series of boxes that can be styled with CSS.

Please find a box model diagram in the same folder as this answers.md file. the box model diagram was taken from a div element created by the following code, displayed in the google chrome inspect window:

<!DOCTYPE html>
<html>
    <style>
        html, body{
            margin:0;
        }
        div{
            margin-top: 50px;
            margin-left: 50px;
            padding: 50px;
            border: 3px solid black;
            height: 100px;
            width: 100px;
        }
    </style>
<body>
    <div></div>
</body>
</html>

Content (Corresponds to the blue section in the diagram): This is the content of the HTML element, such as text or an image. This div happens to have a content of 100 pixels by 100 pixels.

Padding (Corresponds to the green section in the diagram): This is the space around the content, inside the border. You can specify the padding for each side of the element (top, right, bottom, left) using the padding property in CSS.

Border (Corresponds to the light-orange section in the diagram): This is the line around the padding and content. You can specify the border for each side of the element (top, right, bottom, left) using the border property in CSS. You can also specify the border thickness and color.

Margin (Corresponds to the brown section in the diagram): This is the space outside the border. You can specify the margin for each side of the element (top, right, bottom, left) using the margin property in CSS.

# Detail how the browser loads and bootstraps a rich web application from an initial URL

When you enter a URL into a web browser, the browser will first send a request to a web server to retrieve the HTML document corresponding to that URL. The browser will then start parsing the HTML, looking for other resources that need to be loaded, such as stylesheets and JavaScript files.

The browser will begin loading these resources as soon as it discovers them, and will block the rendering of the page until they have been downloaded. Once all of the resources have been downloaded, the browser will start rendering the page according to the instructions in the HTML, CSS, and JavaScript.

In the case of a rich web application, the initial HTML document is often very minimal, containing only the bare minimum HTML required to bootstrap the application. The bulk of the application's functionality is usually contained in one or more JavaScript files that are loaded asynchronously.

The JavaScript code will typically run as soon as it is downloaded, and will perform any necessary initialization tasks and set up event handlers. It may also make additional requests to the server to retrieve data or other resources needed by the application.

Once the application is fully initialized and the page has been rendered, the user can interact with the application through the user interface. Any user interactions will be handled by the JavaScript code, which may make additional requests to the server or manipulate the page in other ways as needed.