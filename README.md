<!DOCTYPE html>
<html>
<head>
  <title>KSCA ID Checker</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      padding: 50px;
    }
    input {
      padding: 10px;
      width: 300px;
      font-size: 16px;
    }
    button {
      padding: 10px 20px;
      font-size: 16px;
      margin-left: 10px;
    }
    #result {
      margin-top: 30px;
    }
  </style>
</head>
<body>
  <h1>KSCA ID Checker</h1>
  <p>Enter KSCA ID to check details</p>
  <input type="text" id="kscaId" placeholder="e.g., 18933KSCA2024">
  <button onclick="checkKSCAID()">Check</button>

  <div id="result"></div>

  <script>
    function checkKSCAID() {
      const id = document.getElementById(\"kscaId\").value.trim();
      const resultDiv = document.getElementById(\"result\");
      
      if (!id) {
        resultDiv.innerHTML = \"<p style='color: red;'>Please enter a valid KSCA ID.</p>\";
        return;
      }

      const url = https://karnatakachess.com/player-details/?id=${encodeURIComponent(id)};
      resultDiv.innerHTML = `
        <p>Checking details for <strong>${id}</strong>...</p>
        <p><a href=\"${url}\" target=\"_blank\">Click here if not automatically redirected</a></p>
        <iframe src=\"${url}\" width=\"100%\" height=\"600px\" style=\"border:1px solid #ccc;\"></iframe>
      `;
    }
  </script>
</body>
</html>
