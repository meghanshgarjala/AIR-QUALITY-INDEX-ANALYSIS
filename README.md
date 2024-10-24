<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Analysis Dashboard</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f5;
            text-align: center;
            margin: 0;
            padding: 0;
        }

        .container {
            max-width: 1000px;
            margin: auto;
            padding: 20px;
        }

        h1 {
            color: #333;
        }

        .button-group {
            margin: 20px 0;
        }

        button {
            padding: 10px 20px;
            font-size: 16px;
            margin: 5px;
            cursor: pointer;
            background-color: #3498db;
            color: white;
            border: none;
            border-radius: 5px;
        }

        button:hover {
            background-color: #2980b9;
        }

        .content {
            display: none;
            margin-top: 20px;
        }

        .active {
            display: block;
        }

        img {
            max-width: 100%;
            height: auto;
        }

        .summary {
            text-align: left;
            margin: 20px;
        }

        .analysis {
            display: none;
            margin-top: 20px;
        }

        li {
            margin-bottom: 10px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Analysis Dashboard</h1>
        <div class="button-group">
            <button onclick="showContent('analysis1')">Analysis 1</button>
            <button onclick="showContent('analysis2')">Analysis 2</button>
            <button onclick="showContent('analysis3')">Analysis 3</button>
            <button onclick="showAnalysis()">Show Pollutant Analysis</button>
        </div>

        <div id="analysis1" class="content active">
            <h2>Analysis 1: Time Series Analysis</h2>
            <img src="time_series_anal.png" alt="Time Series Graph">
            <div class="summary">
                <ul>
                    <li style="color: white;">CO levels are substantially higher and more volatile than the other pollutants, indicating a major source of pollution from CO emissions during this period.</li>
                    <li style="color: white;">Spikes in PM10 and PM2.5 suggest particulate matter pollution during some specific events (e.g., fires, traffic, or weather conditions) on January 12 and January 19.</li>
                    <li style="color: white;">NO, NO2, O3, SO2, and NH3 seem to contribute less to the overall pollution compared to CO and particulate matter.</li>
                    <li style="color: white;">This time series analysis reveals that CO and particulate matter (PM10 and PM2.5) are the primary pollutants affecting Delhi’s air quality during this period, likely from vehicular emissions, industrial activity, or other sources of combustion.</li>
                  </ul>
                  
            </div>
        </div>

        <div id="analysis2" class="content">
            <h2>Analysis 2: Pollutant Concentration</h2>
            <img src="pollutant_conc_delhi.png" alt="Customer Demographics Graph">
            <div class="summary">
                <ul>
                    <li style="color: white;">Carbon Monoxide (CO) stands out as the largest single contributor, highlighting significant concerns about its sources (likely vehicles, industrial activities, or combustion).</li>
                    <li style="color: white;">Particulate matter (PM10 and PM2.5) also contributes significantly to air quality issues, representing around 15.83% of the total pollution.</li>
                    <li style="color: white;">The other pollutants—gases like NO, NO2, SO2, O3, NH3—are relatively minor contributors but still important from a regulatory and health perspective.</li>
                    <li style="color: white;">In summary, CO is overwhelmingly the largest pollutant, followed by PM10 and PM2.5. The presence of particulate matter also indicates serious health implications, particularly with long-term exposure in urban areas like Delhi.</li>
                </ul>
                
                
            </div>
        </div>

        <div id="analysis3" class="content">
            <h2>Analysis 3: Heatmap of Pollutants</h2>
            <img src="heatmap.png" alt="Product Performance Graph">
            <div class="summary">
                <ul>
                    <li style="color:white;">NO and NO2, and PM10 and PM2.5 show strong correlations, which means they often increase or decrease together, likely due to common sources (traffic, combustion, etc.).</li>
                    <li style="color:white;">O3 appears to behave independently of most pollutants, as it is more likely affected by atmospheric reactions rather than direct emissions.</li>
                    <li style="color :white;">The lack of correlation between CO and other pollutants could indicate that it comes from specific sources (like vehicles) that are distinct from other pollutants measured.</li>
                    <li style="color:white;">Overall, this heatmap helps understand the relationships between various pollutants, aiding in identifying common sources and contributing factors to air quality issues in Delhi.</li>
                  </ul>
                  
            </div>
        </div>

        <!-- Pollutant Analysis -->
        <div id="pollutantAnalysis" class="analysis">
            <h2>Pollutant Analysis</h2>
            <ul>
                <li style="color: blue;">CO levels are substantially higher and more volatile than the other pollutants, indicating a major source of pollution from CO emissions during this period.</li>
                <li style="color: green;">Spikes in PM10 and PM2.5 suggest particulate matter pollution during some specific events (e.g., fires, traffic, or weather conditions) on January 12 and January 19.</li>
                <li style="color: orange;">NO, NO2, O3, SO2, and NH3 seem to contribute less to the overall pollution compared to CO and particulate matter.</li>
                <li style="color: red;">This time series analysis reveals that CO and particulate matter (PM10 and PM2.5) are the primary pollutants affecting Delhi’s air quality during this period, likely from vehicular emissions, industrial activity, or other sources of combustion.</li>
            </ul>
        </div>
    </div>

    <script>
        function showContent(contentId) {
            const contents = document.querySelectorAll('.content');
            contents.forEach(content => {
                content.classList.remove('active');
            });
            document.getElementById(contentId).classList.add('active');
        }

        function showAnalysis() {
            document.getElementById('pollutantAnalysis').style.display = 'block';
        }
    </script>
</body>
</html>
