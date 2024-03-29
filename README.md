<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Paper Plane Animation</title>
<style>
    body, html {
        margin: 0;
        padding: 0;
        height: 100%;
    }
    .container {
        position: relative;
        width: 100%;
        height: 100vh;
        background-color: #f0f0f0;
        overflow: hidden;
    }
    .paper-plane {
        position: absolute;
        width: 50px;
        height: 50px;
        background-image: url('paper-plane.png'); /* Add the path to your paper plane image */
        background-size: contain;
        transition: transform 2s ease-in-out;
    }
</style>
</head>
<body>
<div class="container">
    <div class="paper-plane"></div>
</div>

<script>
    document.addEventListener('DOMContentLoaded', function() {
        const plane = document.querySelector('.paper-plane');
        let angle = 0;
        let direction = 1;

        function flyPlane() {
            angle += direction * 10;
            plane.style.transform = `translateX(${angle}px) rotate(${angle}deg)`;
            if (angle > window.innerWidth) {
                direction = -1;
            } else if (angle < 0) {
                direction = 1;
            }
            requestAnimationFrame(flyPlane);
        }

        flyPlane();
    });
</script>
</body>
</html>
