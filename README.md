<!DOCTYPE html>
<html>
<head>
<title>Tính toán Công thức A và B</title>
<style>
body {
  font-family: sans-serif;
}
.container {
  width: 500px;
  margin: 0 auto;
  padding: 20px;
  border: 1px solid #ccc;
}
label {
  display: block;
  margin-bottom: 5px;
}
input[type="number"] {
  width: 100%;
  padding: 10px;
  margin-bottom: 10px;
  border: 1px solid #ccc;
  box-sizing: border-box;
}
button {
  background-color: #4CAF50;
  color: white;
  padding: 12px 20px;
  border: none;
  cursor: pointer;
}
#result {
  margin-top: 20px;
  font-weight: bold;
}
</style>
</head>
<body>
<div class="container">
  <h2>Tính toán Công thức A và B</h2>

  <h3>Công thức A</h3>
  <label for="hb">Hb:</label>
  <input type="number" id="hb" name="hb">

  <label for="age">Tuổi:</label>
  <input type="number" id="age" name="age">

  <label for="ferritin">Ferritin:</label>
  <input type="number" id="ferritin" name="ferritin">

  <h3>Công thức B</h3>
  <label for="hb2">Hb:</label>
  <input type="number" id="hb2" name="hb2">

  <label for="age2">Tuổi:</label>
  <input type="number" id="age2" name="age2">

  <label for="transfusions">Số lần truyền máu:</label>
  <input type="number" id="transfusions" name="transfusions">

  <button onclick="calculate()">Tính toán</button>

  <div id="result"></div>
</div>

<script>
function calculate() {
  // Get values from input fields 
  const hb = parseFloat(document.getElementById("hb").value) || 0; // Default to 0 if empty
  const age = parseFloat(document.getElementById("age").value) || 0;
  const ferritin = parseFloat(document.getElementById("ferritin").value) || 0;
  const hb2 = parseFloat(document.getElementById("hb2").value) || 0;
  const age2 = parseFloat(document.getElementById("age2").value) || 0;
  const transfusions = parseFloat(document.getElementById("transfusions").value) || 0;

  // Calculate formulas A and B
  const resultA = 23.136 - 0.240 * hb - 0.140 * age + 0.00061 * ferritin;
  const resultB = 22.217 - 0.236 * hb2 - 0.138 * age2 + 0.673 * transfusions;

  // Display results
  document.getElementById("result").innerHTML = `
    Kết quả Công thức A: ${resultA.toFixed(2)}<br>
    Kết quả Công thức B: ${resultB.toFixed(2)}
  `;
}
</script>

</body>
</html>
