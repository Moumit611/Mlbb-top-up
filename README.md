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
https://api.qrserver.com/v1/create-qr-code/?size=200x200&data=upi://pay?pa=${upiID}&pn=MLBB+TopUp&mc=0000&tid=123456&tr=MLBBTopUp&tn=Top-Up&am=${amount}&cu=INR
document.getElementById("topupForm").addEventListener("submit", function(event) {
    event.preventDefault();

    let mobile = document.getElementById("mobile").value;
    let mlbbID = document.getElementById("mlbbID").value;
    let zoneID = document.getElementById("zoneID").value;
    let amount = document.getElementById("topupOption").value;

    let receiptText = `
        Mobile: ${mobile} <br>
        MLBB ID: ${mlbbID} <br>
        Zone ID: ${zoneID} <br>
        Amount: ₹${amount}
    `;

    document.getElementById("receiptDetails").innerHTML = receiptText;

    // Generate QR Code (Google Pay UPI Link)
    let upiID = "yourupi@upi"; // Replace with your actual UPI ID
    let qrCodeURL = `https://api.qrserver.com/v1/create-qr-code/?size=200x200&data=upi://pay?pa=${upiID}&pn=MLBB+TopUp&mc=0000&tid=123456&tr=MLBBTopUp&tn=Top-Up&am=${amount}&cu=INR`;

    document.getElementById("qrCode").src = qrCodeURL;
    document.getElementById("receipt").classList.remove("hidden");
});
