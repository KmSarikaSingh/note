# Note-Wall

NotesWall is a simple note that allows users to create and save notes.

# Hosted Link- https://kmsarikasingh.github.io/note/
# HTML Code
```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link
      rel="stylesheet"
      href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/css/bootstrap.min.css"
      integrity="sha384-9aIt2nRpC12Uk9gS9baDl411NQApFmC26EwAOH8WgZl5MYYxFfc+NcPb1dKGj7Sk"
      crossorigin="anonymous"
    />
    <link rel="stylesheet" href="style.css" />
    <title>NotesWall</title>
  </head>
  <body>
    <div class="header">
      <div class="content">
        <div class="note-input">
          <textarea
            class="input-text m-1 get-note"
            rows="3"
            placeholder="// Write a note here"
          ></textarea>
          <div class="action m-3">
            <input type="color" value="#ccffcc" class="theme m-1 get-color" />
            <button class="btn m-1" id="add-btn">Add note</button>
          </div>
        </div>
      </div>
    </div>

    <div class="notes-list mt-3">
      <div class="no-notes">
        <h4 class="msg">You haven't added notes.</h4>
      </div>
    </div>
    <script src="./index.js"></script>
  </body>
</html>
```
# JAVASCRIPT Code
```
const input = document.querySelector('.get-note');
const addNoteBtn = document.querySelector('#add-btn');
addNoteBtn.addEventListener("click", addNewNote);
const allNotes = [];

const color = document.querySelector('.get-color');
const notesList = document.querySelector('.notes-list');

document.addEventListener('keypress', (event) => {
    if (event.keyCode === 13) {
        addNewNote();
    }
})

function addNewNote() {
    if (input.value) {
        let newNote = {
            note: input.value,
            noteColor: color.value

        };
        allNotes.push(newNote);
    }
    else {
        alert("A note can't be empty.");

    }
   



    input.value = "";
    input.focus();
    
    displayNotes(allNotes);

    
   
}


function displayNotes(notes) {
    notesList.innerHTML = " ";
    notes.forEach(element => {
       let noteHTML= `
        <div class="note" style="background-color:${element.noteColor};">
            <div class="note-view">
                ${element.note}
            </div>
            <div>
                <a class="deleteBtn">Del</a>
            </div>
        </div>
        `;

        notesList.insertAdjacentHTML('afterbegin', noteHTML);
        
        const deleteBtn = document.querySelector('.deleteBtn');
        deleteBtn.addEventListener('click', e => { deleteNote(e,element);})


    });
}


function deleteNote(e,element) {
    let item = e.target.parentElement.parentElement.parentElement;
    item.parentNode.removeChild(item);
    allNotes.pop(element);
    
}
```
