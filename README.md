<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NetWorthChecker</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: #f7fafc;
            margin: 0;
            padding: 0;
            text-align: center;
        }
        .container {
            background: white;
            max-width: 400px;
            margin: 50px auto;
            padding: 30px 24px 24px 24px;
            border-radius: 12px;
            box-shadow: 0 8px 24px rgba(0,0,0,0.10);
        }
        h2 {
            color: #2c5282;
            margin-bottom: 16px;
        }
        label, input {
            display: block;
            width: 100%;
            text-align: left;
        }
        input[type="number"] {
            margin: 8px 0 16px 0;
            padding: 10px;
            border: 1px solid #cbd5e1;
            border-radius: 6px;
            font-size: 17px;
        }
        button {
            background: #2b6cb0;
            color: white;
            border: none;
            padding: 12px 0;
            border-radius: 6px;
            width: 100%;
            font-size: 18px;
            cursor: pointer;
            margin-top: 10px;
        }
        button:hover {
            background: #2c5282;
        }
        #result {
            margin-top: 20px;
            font-size: 22px;
            font-weight: bold;
            color: #2c5282;
        }
        .footer {
            margin-top: 60px;
            color: #a0aec0;
            font-size: 14px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>NetWorthChecker</h2>
        <label for="assets">Total Assets ($):</label>
        <input type="number" id="assets" placeholder="e.g., 100000" min="0">

        <label for="liabilities">Total Liabilities ($):</label>
        <input type="number" id="liabilities" placeholder="e.g., 35000" min="0">

        <button onclick="calculateNetWorth()">Calculate Net Worth</button>

        <div id="result"></div>
    </div>
    <div class="footer">
        &copy; 2025 NetWorthChecker &mdash; Built for public use
    </div>
    <script>
        function calculateNetWorth() {
            const assets = parseFloat(document.getElementById("assets").value) || 0;
            const liabilities = parseFloat(document.getElementById("liabilities").value) || 0;
            const netWorth = assets - liabilities;
            document.getElementById("result").innerText =
                "Your Net Worth: $" + netWorth.toLocaleString(undefined, {maximumFractionDigits: 2});
        }
    </script>
</body>
</html>
