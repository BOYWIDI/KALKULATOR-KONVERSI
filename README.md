<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Kalkulator Konversi Unit</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background-color: #f4f4f4;
    }

    .converter {
      background: #b1cf04;
      padding: 20px;
      border-radius: 8px;
      box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
      width: 300px;
      text-align: center;
    }

    h1 {
      margin-bottom: 20px;
    }

    .form-group {
      margin-bottom: 15px;
    }

    label {
      display: block;
      margin-bottom: 5px;
      font-weight: bold;
    }

    input, select {
      width: 100%;
      padding: 10px;
      border: 1px solid #ddd;
      border-radius: 4px;
      font-size: 14px;
    }

    button {
      width: 100%;
      padding: 10px;
      background-color: #0fd54e;
      color: white;
      border: none;
      border-radius: 4px;
      font-size: 16px;
      cursor: pointer;
    }

    button:hover {
      background-color: #b14705;
    }

    .result {
      margin-top: 20px;
    }

    #result-value {
      font-size: 20px;
      font-weight: bold;
    }
  </style>
</head>
<body>
  <div class="converter">
    <h1>Kalkulator Konversi Unit</h1>
    <h2>WIDI YANTORO</h2>
    <h1>221011403044</h1>
    <div class="form-group">
      <label for="value">Masukkan Nilai:</label>
      <input type="number" id="value" placeholder="Masukkan nilai...">
    </div>

    <div class="form-group">
      <label for="unit-select">Pilih Konversi:</label>
      <select id="unit-select">
        <option value="km-to-miles">Kilometer ke Mil</option>
        <option value="miles-to-km">Mil ke Kilometer</option>
        <option value="c-to-f">Celsius ke Fahrenheit</option>
        <option value="f-to-c">Fahrenheit ke Celsius</option>
      </select>
    </div>

    <button id="convert-btn">Konversi</button>

    <div class="result">
      <h3>Hasil:</h3>
      <p id="result-value">0</p>
    </div>
  </div>

  <script>
    document.getElementById("convert-btn").addEventListener("click", function () {
      const value = parseFloat(document.getElementById("value").value);
      const conversionType = document.getElementById("unit-select").value;
      let result;

      if (isNaN(value)) {
        result = "Masukkan nilai yang valid!";
      } else {
        switch (conversionType) {
          case "km-to-miles":
            result = (value * 0.621371).toFixed(2) + " mil";
            break;
          case "miles-to-km":
            result = (value / 0.621371).toFixed(2) + " km";
            break;
          case "c-to-f":
            result = ((value * 9) / 5 + 32).toFixed(2) + " °F";
            break;
          case "f-to-c":
            result = (((value - 32) * 5) / 9).toFixed(2) + " °C";
            break;
          default:
            result = "Konversi tidak valid.";
        }
      }

      document.getElementById("result-value").textContent = result;
    });
  </script>
</body>
</html>
