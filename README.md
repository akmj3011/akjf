<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Responsive Navigation Menu</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
    }
    .navbar {
      background-color: #333;
      overflow: hidden;
    }
    .navbar a {
      float: left;
      display: block;
      color: white;
      text-align: center;
      padding: 14px 20px;
      text-decoration: none;
    }
    .navbar a:hover {
      background-color: #ddd;
      color: black;
    }
    .navbar a.active {
      background-color: #555;
      color: white;
    }
    .navbar .icon {
      display: none;
    }
    .sidebar {
      display: none;
      position: fixed;
      width: 200px;
      background-color: #111;
      height: 100%;
      top: 0;
      left: -200px;
      transition: 0.3s;
      padding-top: 60px;
    }
    .sidebar a {
      padding: 10px 15px;
      text-decoration: none;
      font-size: 25px;
      color: #818181;
      display: block;
      transition: 0.3s;
    }
    .sidebar a:hover {
      color: #f1f1f1;
    }
    @media screen and (max-width: 600px) {
      .navbar a:not(:first-child) {display: none;}
      .navbar a.icon {
        float: right;
        display: block;
      }
      .navbar.responsive a:not(.icon) {display: block;}
      .navbar.responsive .icon {
        position: absolute;
        right: 0;
        top: 0;
      }
      .sidebar {
        display: block;
      }
    }
  </style>
</head>
<body>

<div class="navbar" id="myNavbar">
  <a href="#" class="active">Home</a>
  <a href="#">About</a>
  <a href="#">Contact</a>
  <a href="#">FAQ</a>
  <a href="javascript:void(0);" class="icon" onclick="myFunction()">
    &#9776;
  </a>
</div>

<div class="sidebar" id="sidebar">
  <a href="#">Home</a>
  <a href="#">About</a>
  <a href="#">Contact</a>
  <a href="#">FAQ</a>
</div>

<script>
function myFunction() {
  var x = document.getElementById("myNavbar");
  var y = document.getElementById("sidebar");
  if (x.className === "navbar") {
    x.className += " responsive";
    y.style.left = "0";
  } else {
    x.className = "navbar";
    y.style.left = "-200px";
  }
}
</script>

</body>
</html>




