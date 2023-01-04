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

# We have looked at three kinds of asynchronous programming mechanisms,namely callbacks, promises and streams. Mention one advantage and one disadvantage of each type.

# With the aid of a diagram and example code, describe the Cascading Style Sheets (CSS) Box Model and show how it can be used to space DOM elements

# Detail how the browser loads and bootstraps a rich web application from an initial URL