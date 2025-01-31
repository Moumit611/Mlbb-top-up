# Mlbb-top-up
Mlbb low price topup
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MLBB Top-Up</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h2>MLBB Top-Up</h2>
        <form id="topupForm">
            <label for="mobile">Mobile Number:</label>
            <input type="text" id="mobile" required>

            <label for="mlbbID">MLBB ID:</label>
            <input type="text" id="mlbbID" required>

            <label for="zoneID">Zone ID:</label>
            <input type="text" id="zoneID" required>

            <label for="topupOption">Select Top-Up:</label>
            <select id="topupOption" required>
                <option value="120">Weekly Pass - ₹120</option>
                <option value="10">5 Diamonds - ₹10</option>
                <option value="35">40 Diamonds - ₹35</option>
                <option value="10">11 Diamonds - ₹10</option>
            </select>

            <button type="submit">Generate Receipt</button>
        </form>

        <div id="receipt" class="hidden">
            <h3>Receipt</h3>
            <p id="receiptDetails"></p>
            <img id="qrCode" src="" alt="QR Code">
        </div>
    </div>

    <script src="script.js"></script>
</body>
</html>
