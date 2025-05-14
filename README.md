# 🎯 JavaScript Event Handling & Interactive Elements Assignment

Welcome to the **ultimate JavaScript playground**! 🎉 This assignment is where we turn boring web pages into dynamic, responsive, *alive* experiences. Get ready to master **event handling**, build **interactive components**, and validate forms like a pro! 💪

## 📁 Assignment Structure

```
📂 js-event-assignment/
├── index.html         # Your playground – where it all comes together
├── style.css          # Keep it cute (optional but encouraged)
└── script.js          # The JavaScript wizardry happens here
```

---

## 🧪 What to Build

Here’s what your interactive bundle of joy should include:

### 1. Event Handling 🎈  
- Button click ✅  
- Hover effects ✅  
- Keypress detection ✅  
- Bonus: A secret action for a *double-click* or *long press* 🤫

### 2. Interactive Elements 🎮  
- A button that changes text or color  
- An image gallery or slideshow  
- Tabs or accordion-style content  
- Bonus: Add some animation using JS or CSS ✨

### 3. Form Validation 📋✅  
- Required field checks  
- Email format validation  
- Password rules (e.g., min 8 characters)  
- Bonus: Real-time feedback while typing

---

## 🧙‍♂️ Pro Tips

- Keep your code clean and commented – your future self will thank you!
- Think about **user experience** – what makes your site more *fun* to use?
- Don’t be afraid to **Google and experiment** – that’s how real developers roll!

---

## 🎉 Now Go Make It Fun!

Remember – this isn't just code. It's your **first step toward creating magical user experiences**. So play around, break stuff (then fix it), and most of all, have FUN! 😄

Happy Coding! 💻✨  

index.html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Interactive Event Assignment</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

  <h1>Interactive JavaScript Event Assignment</h1>

  <!-- Button Click Event -->
  <button id="changeTextButton">Click Me!</button>

  <!-- Hover Effect -->
  <div class="hoverBox">Hover over me!</div>

  <!-- Image Gallery -->
  <div class="gallery">
    <img src="https://via.placeholder.com/150" alt="Image 1" class="galleryImage">
    <img src="https://via.placeholder.com/150" alt="Image 2" class="galleryImage">
    <img src="https://via.placeholder.com/150" alt="Image 3" class="galleryImage">
  </div>

  <!-- Tabs -->
  <div class="tabs">
    <button class="tabButton" data-tab="tab1">Tab 1</button>
    <button class="tabButton" data-tab="tab2">Tab 2</button>
    <button class="tabButton" data-tab="tab3">Tab 3</button>
  </div>

  <div class="tabContent" id="tab1">
    <p>This is Tab 1 content!</p>
  </div>
  <div class="tabContent" id="tab2">
    <p>This is Tab 2 content!</p>
  </div>
  <div class="tabContent" id="tab3">
    <p>This is Tab 3 content!</p>
  </div>

  <!-- Form Validation -->
  <form id="form">
    <label for="email">Email:</label>
    <input type="email" id="email" required>
    <br>
    <label for="password">Password:</label>
    <input type="password" id="password" minlength="8" required>
    <br>
    <button type="submit">Submit</button>
  </form>

  <script src="script.js"></script>
</body>
</html>

style.css
body {
  font-family: Arial, sans-serif;
  padding: 20px;
}

h1 {
  text-align: center;
}

button {
  padding: 10px 20px;
  background-color: lightcoral;
  color: white;
  border: none;
  cursor: pointer;
  margin: 10px;
}

button:hover {
  background-color: coral;
}

.hoverBox {
  width: 200px;
  height: 100px;
  background-color: lightgreen;
  margin: 20px auto;
  text-align: center;
  line-height: 100px;
  transition: background-color 0.3s;
}

.gallery {
  display: flex;
  justify-content: space-around;
  margin-top: 20px;
}

.galleryImage {
  width: 100px;
  height: 100px;
  cursor: pointer;
}

.tabs {
  margin-top: 20px;
}

.tabButton {
  padding: 10px;
  margin-right: 5px;
  background-color: lightgray;
  cursor: pointer;
}

.tabButton:hover {
  background-color: gray;
}

.tabContent {
  display: none;
  margin-top: 20px;
}

form {
  margin-top: 30px;
}

script.js
// Event Handling
const changeTextButton = document.getElementById("changeTextButton");
changeTextButton.addEventListener("click", function() {
  changeTextButton.textContent = "You clicked me!";
  changeTextButton.style.backgroundColor = "green";
});

const hoverBox = document.querySelector(".hoverBox");
hoverBox.addEventListener("mouseenter", function() {
  hoverBox.style.backgroundColor = "yellow";
});
hoverBox.addEventListener("mouseleave", function() {
  hoverBox.style.backgroundColor = "lightgreen";
});

// Image Gallery: Click to enlarge
const galleryImages = document.querySelectorAll(".galleryImage");
galleryImages.forEach(image => {
  image.addEventListener("click", function() {
    alert("Image clicked: " + image.alt);
  });
});

// Tabs: Switch content
const tabs = document.querySelectorAll(".tabButton");
tabs.forEach(tab => {
  tab.addEventListener("click", function() {
    const tabId = tab.getAttribute("data-tab");
    const allTabContents = document.querySelectorAll(".tabContent");
    allTabContents.forEach(content => {
      content.style.display = "none";
    });
    document.getElementById(tabId).style.display = "block";
  });
});

// Form Validation: Check fields and provide feedback
const form = document.getElementById("form");
form.addEventListener("submit", function(event) {
  const email = document.getElementById("email").value;
  const password = document.getElementById("password").value;

  // Email validation
  const emailPattern = /^[^ ]+@[^ ]+\.[a-z]{2,3}$/;
  if (!email.match(emailPattern)) {
    alert("Please enter a valid email.");
    event.preventDefault();  // Prevent form submission
    return;
  }

  // Password validation
  if (password.length < 8) {
    alert("Password must be at least 8 characters long.");
    event.preventDefault();  // Prevent form submission
    return;
  }

  alert("Form submitted successfully!");
});

