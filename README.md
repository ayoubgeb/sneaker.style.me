# sneaker.style.me
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Sneaker Style Matcher</title>
  <style>
    body { font-family: Arial, sans-serif; margin: 20px; max-width: 600px; }
    label { display: block; margin-top: 10px; font-weight: bold; }
    select, input[type="text"] { width: 100%; padding: 8px; margin-top: 5px; }
    button { margin-top: 15px; padding: 10px 20px; background-color: #000; color: #fff; border: none; cursor: pointer; }
    #result { margin-top: 20px; padding: 15px; background: #f0f0f0; border-radius: 5px; }
  </style>
</head>
<body>
  <h2>Sneaker Style Suggestion Tool</h2>

  <label for="sneakerColor">Sneaker Color:</label>
  <select id="sneakerColor">
    <option value="white">White</option>
    <option value="black">Black</option>
    <option value="pink">Pink</option>
    <option value="red">Red</option>
    <option value="beige">Beige</option>
  </select>

  <label for="topType">Top Type:</label>
  <select id="topType">
    <option value="tshirt">T-Shirt</option>
    <option value="shirt">Shirt</option>
    <option value="longsleeve">Long Sleeve</option>
    <option value="shortsleeve">Short Sleeve</option>
  </select>

  <label for="topColor">Top Color:</label>
  <input type="text" id="topColor" placeholder="e.g., blue, grey">

  <label for="bottomType">Bottom Type:</label>
  <select id="bottomType">
    <option value="pants">Pants</option>
    <option value="skirt">Skirt</option>
    <option value="shorts">Shorts</option>
  </select>

  <label for="bottomColor">Bottom Color:</label>
  <input type="text" id="bottomColor" placeholder="e.g., black, beige">

  <label for="season">Season:</label>
  <select id="season">
    <option value="summer">Summer</option>
    <option value="winter">Winter</option>
  </select>

  <label for="occasion">Occasion:</label>
  <select id="occasion">
    <option value="casual">Casual</option>
    <option value="smart">Smart</option>
    <option value="nightwear">Nightwear</option>
  </select>

  <label for="skinTone">Skin Tone:</label>
  <select id="skinTone">
    <option value="cool">Cool</option>
    <option value="warm">Warm</option>
    <option value="neutral">Neutral</option>
  </select>

  <button onclick="generateStyle()">Get Styling Suggestion</button>

  <div id="result"></div>

  <script>
    function generateStyle() {
      const sneakerColor = document.getElementById('sneakerColor').value;
      const topType = document.getElementById('topType').value;
      const topColor = document.getElementById('topColor').value;
      const bottomType = document.getElementById('bottomType').value;
      const bottomColor = document.getElementById('bottomColor').value;
      const season = document.getElementById('season').value;
      const occasion = document.getElementById('occasion').value;
      const skinTone = document.getElementById('skinTone').value;

      let suggestion = `👟 With your <b>${sneakerColor}</b> sneakers, try a <b>${topColor} ${topType}</b> and <b>${bottomColor} ${bottomType}</b>.<br>`;

      // Add basic logic for styling
      if (season === "summer") suggestion += "☀️ Light fabrics and pastel shades work well in summer.<br>";
      if (season === "winter") suggestion += "❄️ Add layers like jackets or scarves in darker tones.<br>";

      if (occasion === "smart") suggestion += "💼 Match with clean lines and neutral tones for a polished look.<br>";
      if (occasion === "casual") suggestion += "🎒 Go comfy with jeans or casual trousers.<br>";

      if (skinTone === "warm") suggestion += "🌻 Earthy colors like olive, mustard, or coral will pop on warm skin.<br>";
      if (skinTone === "cool") suggestion += "❄️ Cool tones like blue, silver, or lavender enhance cool skin tones.<br>";
      if (skinTone === "neutral") suggestion += "🎨 You’re lucky! Almost all colors suit you, try experimenting!<br>";

      document.getElementById('result').innerHTML = suggestion;
    }
  </script>
</body>
</html>
