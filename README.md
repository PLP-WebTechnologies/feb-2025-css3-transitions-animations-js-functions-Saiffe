# CSS3 Transitions, Animations, and Advanced JavaScript Functions

## Objectives

Create smooth CSS transitions and animations.
Use JavaScript functions for dynamic behavior.
Implement local storage for data persistence.

## Instructions
Add CSS animations to elements like buttons or images.

>[!NOTE]
> - Write a JavaScript function that:
> - Stores and retrieves user preferences using localStorage.
> - Implements an animation triggered by user actions.

## Tasks

Create a CSS animation.
Store data in localStorage.
Apply JavaScript to trigger animations.
HTML
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CSS Animations for Buttons and Images</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>

  <div class="container">
    <!-- Box Element -->
    <div id="animatedBox" class="box"></div>

    <!-- Button Element -->
    <button id="triggerAnimationBtn" class="btn">Trigger Box Animation</button>

    <!-- Image Element -->
    <img id="image" src="https://via.placeholder.com/150" alt="Placeholder" class="image" />

    <!-- Button to animate the image -->
    <button id="triggerImageBtn" class="btn">Animate Image</button>
  </div>

  <script src="script.js"></script>
</body>
</html>
CSS/STYLES
/* Basic styling */
body {
  font-family: Arial, sans-serif;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  margin: 0;
  background-color: #f4f4f4;
}

.container {
  text-align: center;
}

.box {
  width: 100px;
  height: 100px;
  background-color: coral;
  transition: transform 1s ease-in-out;
  margin-bottom: 20px;
}

/* Button Styling */
.btn {
  padding: 10px 20px;
  margin: 10px;
  border: none;
  background-color: #008cba;
  color: white;
  font-size: 16px;
  cursor: pointer;
  transition: transform 0.3s ease;
}

/* Button hover effect */
.btn:hover {
  transform: scale(1.1);
}

/* Image Styling */
.image {
  width: 150px;
  height: 150px;
  margin-bottom: 20px;
  transition: transform 0.5s ease;
}

/* Animation keyframes */
@keyframes moveBox {
  0% {
    transform: translateX(0);
  }
  50% {
    transform: translateX(200px);
  }
  100% {
    transform: translateX(0);
  }
}

@keyframes scaleImage {
  0% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.5);
  }
  100% {
    transform: scale(1);
  }
}

/* Animation classes */
.animateBox {
  animation: moveBox 2s ease-in-out forwards;
}

.animateImage {
  animation: scaleImage 1s ease-in-out forwards;
}
JAVA SCRIPT
// Check if animation has been triggered previously for the box and image
if (localStorage.getItem("boxAnimationTriggered") === "true") {
  document.getElementById("animatedBox").classList.add("animateBox");
}

if (localStorage.getItem("imageAnimationTriggered") === "true") {
  document.getElementById("image").classList.add("animateImage");
}

// Add event listener to trigger box animation
document.getElementById("triggerAnimationBtn").addEventListener("click", () => {
  const box = document.getElementById("animatedBox");

  // Trigger box animation
  box.classList.add("animateBox");

  // Store that the animation has been triggered for the box
  localStorage.setItem("boxAnimationTriggered", "true");

  // Optionally, reset the animation after it finishes
  box.addEventListener("animationend", () => {
    box.classList.remove("animateBox");
  });
});

// Add event listener to trigger image animation
document.getElementById("triggerImageBtn").addEventListener("click", () => {
  const image = document.getElementById("image");

  // Trigger image animation
  image.classList.add("animateImage");

  // Store that the animation has been triggered for the image
  localStorage.setItem("imageAnimationTriggered", "true");

  // Optionally, reset the animation after it finishes
  image.addEventListener("animationend", () => {
    image.classList.remove("animateImage");
  });
});


Happy Coding! 💻✨
