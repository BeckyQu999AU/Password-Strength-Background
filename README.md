Password Blur Effect
📌 Overview
This is a simple front-end interaction effect:
When the user types into the password field, the background gradually becomes clearer as the input length increases.
It’s often used on login pages to create a more engaging and secure feel.

🎯 Features
Background starts with a strong blur (20px).

Each character typed reduces the blur proportionally.

When the input reaches a certain length, the background is fully clear.

Optional smooth transition animation with CSS.

🛠 Tech Stack
HTML – Creates the input field and background elements.

CSS – Sets the initial background style and transition animation.

JavaScript – Listens to input events and dynamically adjusts the blur.

📂 File Structure
plaintext
Copy
Edit
index.html     # Page structure
style.css      # Background styles & transitions
script.js      # Blur calculation & event handling
📜 Core Code
javascript
Copy
Edit
const password = document.getElementById('password');
const background = document.getElementById('background');

password.addEventListener('input', (e) => {
  const length = e.target.value.length;
  const blurValue = Math.max(20 - length * 2, 0); // More input = less blur
  background.style.filter = `blur(${blurValue}px)`; // Must include px unit
});
💡 Adjusting the Blur Speed
Slower blur reduction: Change * 2 to * 1 or smaller.

Faster blur reduction: Change * 2 to * 3 or larger.

Smooth transition: Add to CSS:

css
Copy
Edit
#background {
  transition: filter 300ms ease;
}
🚀 How to Use
Create an HTML page and link your CSS and JS files.

Add the following to your HTML:

html
Copy
Edit
<input type="password" id="password" placeholder="Enter password" />
<div id="background"></div>
Open the page in a browser, type into the password field, and watch the background gradually become clear.

