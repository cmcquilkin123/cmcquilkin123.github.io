---
layout: page
title: Mapping the Gran Chaco
description: Cartography and Colonialism.
background: '/img/gran-chaco-1732.jpg'
---
<iframe src="https://api.mapbox.com/styles/v1/cmcquilkin/cjtajxpw819ib1fma0wss7su6.html?fresh=true&title=true&access_token=pk.eyJ1IjoiY21jcXVpbGtpbiIsImEiOiJjanJoMWI0ZG0wMnZpM3l0MHM0bWVlbGFpIn0.RuixYRSV3hkcp2C3jMAbhA#2.1/-22.476997/-59.596439/0" width="100%" height ="300px" frameborder="0"></iframe>

<html>
<style>
.filterDiv {
  float: left;
  background-color: #2196F3;
  color: #ffffff;
  width: 100px;
  line-height: 100px;
  text-align: center;
  margin: 2px;
  display: none;
}

.show {
  display: block;
}

.container {
  margin-top: 20px;
  overflow: hidden;
}

<!--Style the buttons -->
.btn {
  border: none;
  outline: none;
  padding: 12px 16px;
  background-color: #f1f1f1;
  cursor: pointer;
}

.btn:hover {
  background-color: #ddd;
}

.btn.active {
  background-color: #666;
  color: white;
}
</style>
<body>

<h2>Filter DIV Elements</h2>

<div id="myBtnContainer">
  <button class="btn active" onclick="filterSelection('all')"> Show all</button>
  <button class="btn" onclick="filterSelection('sts')"> STS</button>
  <button class="btn" onclick="filterSelection('labor')"> Labor and EH</button>
  <button class="btn" onclick="filterSelection('water')"> Water Histories</button>
  <button class="btn" onclick="filterSelection('forests')"> Forests and Deforestation</button>
  <button class="btn" onclick="filterSelection('mining')"> Mining</button>
  <button class="btn" onclick="filterSelection('scimed')"> Science, Knowledge and Medicine</button>
  <button class="btn" onclick="filterSelection('conservation')"> Conservation and Environmentalism</button>
  <button class="btn" onclick="filterSelection('commodities')"> Commodities</button>
</div>

<div class="container">
  <div class="filterDiv scimed">Science in the Vanished Arcadia</div>
  <div class="filterDiv sts">Networking Peripheries</div>
  <div class="filterDiv cars">Volvo</div>
  <div class="filterDiv colors">Red</div>
  <div class="filterDiv cars animals">Mustang</div>
  <div class="filterDiv colors">Blue</div>
  <div class="filterDiv animals">Cat</div>
  <div class="filterDiv animals">Dog</div>
  <div class="filterDiv fruits">Melon</div>
  <div class="filterDiv fruits animals">Kiwi</div>
  <div class="filterDiv fruits">Banana</div>
  <div class="filterDiv fruits">Lemon</div>
  <div class="filterDiv animals">Cow</div>
</div>

<script>
filterSelection("all")
function filterSelection(c) {
  var x, i;
  x = document.getElementsByClassName("filterDiv");
  if (c == "all") c = "";
  for (i = 0; i < x.length; i++) {
    w3RemoveClass(x[i], "show");
    if (x[i].className.indexOf(c) > -1) w3AddClass(x[i], "show");
  }
}

function w3AddClass(element, name) {
  var i, arr1, arr2;
  arr1 = element.className.split(" ");
  arr2 = name.split(" ");
  for (i = 0; i < arr2.length; i++) {
    if (arr1.indexOf(arr2[i]) == -1) {element.className += " " + arr2[i];}
  }
}

function w3RemoveClass(element, name) {
  var i, arr1, arr2;
  arr1 = element.className.split(" ");
  arr2 = name.split(" ");
  for (i = 0; i < arr2.length; i++) {
    while (arr1.indexOf(arr2[i]) > -1) {
      arr1.splice(arr1.indexOf(arr2[i]), 1);     
    }
  }
  element.className = arr1.join(" ");
}

// Add active class to the current button (highlight it)
var btnContainer = document.getElementById("myBtnContainer");
var btns = btnContainer.getElementsByClassName("btn");
for (var i = 0; i < btns.length; i++) {
  btns[i].addEventListener("click", function(){
    var current = document.getElementsByClassName("active");
    current[0].className = current[0].className.replace(" active", "");
    this.className += " active";
  });
}
</script>

</body>
</html>
