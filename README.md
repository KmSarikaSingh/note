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
    <title>Tip Calculator</title>
    <link rel="stylesheet" href="style.css" />
  </head>
  <body>
    <div class="container">
       
      <div class="area">
        <h2>Welcome to the Ronak's Tip calculator!</h2>
        <h3>How Much Was Your Bill</h3>
        <div>Rs. <input type="text" id="billAmount" /></div>
        <h3 class="h3">How was your service?</h3>
        <div>
        <select id="ddlViewBy">
            <option value="0" disabled="" selected="" >Choose an Option</option>
            <option value=".3">30% Outstanding</option>
            <option value=".2">20% Good</option>
            <option value=".15">15% It was Okay</option>
            <option value=".10">10% Bad</option>
            <option value=".05">5% Terrible</option>
          </select>
          </div>
        <h3 class="h3">How many people are sharing the bill?</h3>
        <div> <input type="text" id="totalPeople" /></div>
        <button id="calculate">Calculate</button>
      </div>
   
    </div>
    <script src="index.js"></script>
  </body>
</html>
```
# JAVASCRIPT Code
```
let container = document.querySelector(".area");
let calculate = document.querySelector("#calculate");
let div = document.createElement("p");
calculate.addEventListener("click",()=>{
    div.innerText =""
    let amount=document.querySelector('#billAmount').value;
    let totalPeople = document.getElementById("totalPeople").value;
  
    var service = document.getElementById("ddlViewBy").value;
    div.innerText = ` Tip Amount is ${amount*service/totalPeople}`
    // console.log(div);
    container.appendChild(div);

   
})
```
