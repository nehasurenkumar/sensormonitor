<!DOCTYPE html>
<html>
<head>
  <title>Sensor Data from Pipedream</title>
</head>
<body>
  <h1>Sensor Data</h1>
  <pre id="dataDisplay">Loading data...</pre>

  <script>
    // Replace this URL with your actual Pipedream workflow HTTP trigger URL
    const pipedreamUrl = 'https://eoy5j7h0505i6av.m.pipedream.net'; 

    fetch(pipedreamUrl)
      .then(response => response.json())
      .then(data => {
        const formatted = `
Battery: ${data.battery}
Distance: ${data.distance}
Tilt: ${data.tilt}
        `.trim();

        document.getElementById('dataDisplay').textContent = formatted;
      })
      .catch(err => {
        document.getElementById('dataDisplay').textContent = 'Error loading data: ' + err;
      });
  </script>
</body>
</html>
