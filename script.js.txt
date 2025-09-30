// -------- Notes Feature --------
function addNote() {
  let text = document.getElementById("note").value;
  if (text.trim() !== "") {
    let li = document.createElement("li");
    li.textContent = text;
    document.getElementById("notes").appendChild(li);
    document.getElementById("note").value = "";
  }
}

// -------- Photo Upload Feature --------
document.getElementById("photoUpload").addEventListener("change", function(e) {
  let file = e.target.files[0];
  if (file) {
    let reader = new FileReader();
    reader.onload = function(event) {
      let img = document.createElement("img");
      img.src = event.target.result;
      document.getElementById("gallery").appendChild(img);
    };
    reader.readAsDataURL(file);
  }
});
