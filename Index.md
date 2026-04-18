<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Green Coins System</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      background: #f4f4f4;
    }
    header {
      background: #2e7d32;
      color: white;
      padding: 15px;
      text-align: center;
    }
    .container {
      padding: 20px;
    }
    .card {
      background: white;
      padding: 15px;
      margin: 15px 0;
      border-radius: 8px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    }
    button {
      background: #4caf50;
      color: white;
      border: none;
      padding: 10px 15px;
      cursor: pointer;
      border-radius: 5px;
    }
    button:hover {
      background: #388e3c;
    }
    input, select {
      margin-top: 10px;
      padding: 5px;
    }
  </style>
</head>
<body>

<header>
  <h1>🌱 Green Coins System</h1>
  <p>Rewarding Social Work & Sustainable Actions</p>
</header>

<div class="container">

  <div class="card">
    <h2>👩‍🎓 About Our Project</h2>
    <p>
      We are Computer Science students working on a project related to <b>Social Work and Sustainability</b>. 
      We chose the <b>Green Coins System</b> to reward people for their contributions.
    </p>
  </div>

  <div class="card">
    <h2>🌟 Earn Green Coins</h2>
    <p>Select your activity, upload proof 📸, and earn coins.</p>

    <label>Select Activity:</label><br>
    <select id="activity">
      <option value="tree">Tree Plantation (10 coins)</option>
      <option value="book">Book Donation (5 coins each)</option>
      <option value="shawl">Shawl Donation (3 coins each)</option>
      <option value="food">Food Donation (2 coins each)</option>
    </select><br>

    <label>Enter Quantity:</label><br>
    <input type="number" id="quantity" min="1" value="1"><br>

    <input type="file" id="photoUpload" accept="image/*"><br><br>

    <button onclick="earnCoins()">Submit & Earn Coins</button>
  </div>

  <div class="card">
    <h2>Your Green Coins 💰</h2>
    <p id="coins">0 Coins</p>
  </div>

  <div class="card">
    <h2>📋 Reward System</h2>
    <ul>
      <li>🌳 Tree Plantation → 10 coins</li>
      <li>📚 Book Donation → 5 coins</li>
      <li>🧣 Shawl Donation → 3 coins</li>
      <li>🍱 Food Donation → 2 coins</li>
    </ul>
  </div>

</div>

<script>
  let coins = 0;

  function earnCoins() {
    let fileInput = document.getElementById("photoUpload");
    let activity = document.getElementById("activity").value;
    let qty = document.getElementById("quantity").value;

    if (fileInput.files.length === 0) {
      alert("⚠️ Please upload proof image!");
      return;
    }

    let reward = 0;

    if (activity === "tree") reward = 10 * qty;
    if (activity === "book") reward = 5 * qty;
    if (activity === "shawl") reward = 3 * qty;
    if (activity === "food") reward = 2 * qty;

    coins += reward;

    document.getElementById("coins").innerText = coins + " Coins";

    alert("🎉 You earned " + reward + " Green Coins!");
  }
</script>

</body>
</html>
