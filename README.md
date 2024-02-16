<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fitness App</title>
</head>
<body>
    <h1>Fitness Level Calculator</h1>
    <form method="post">
        <label for="steps">Enter the number of steps walked:</label>
        <input type="number" id="steps" name="steps" required>
        <input type="submit" value="Calculate">
    </form>

    <?php
    if ($_SERVER["REQUEST_METHOD"] == "POST") {
        // Get the number of steps from user input
        $steps = $_POST["steps"];

        // Determine the fitness level based on the number of steps
        if ($steps < 5000) {
            $fitnessLevel = 'Beginner';
        } elseif ($steps >= 5000 && $steps <= 10000) {
            $fitnessLevel = 'Intermediate';
        } else {
            $fitnessLevel = 'Advanced';
        }

        // Display the result
        echo "<p>Your fitness level: <strong>$fitnessLevel</strong></p>";
    }
    ?>
</body>
</html>
