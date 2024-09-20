// KABALE UNIVERSITY.
PHP ASSIGNMENT
SCRIPTING LANGUAGES
Name. Twebaze James yakaobo. 2023/a/abit/1803/f



//Develop a php script that captures your name, date of birth, your home address, and returns a statement that welcomes you home and also reminds you of your age that day.
All codes should follow the php syntax


<?php
// Function to calculate age
function calculate Age($dateOfBirth) {
    $birthDate = new DateTime($dateOfBirth);
    $today = new DateTime('today');
    return $birthDate->diff($today)->y; // Returns age in years
}

// Check if the form is submitted
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    // Capture user inputs
    $name = htmlspecialchars($_POST['name']);
    $dateOfBirth = htmlspecialchars($_POST['dob']);
    $address = htmlspecialchars($_POST['address']);
    
    // Calculate age
    $age = calculate Age($dateOfBirth);
    
    // Create welcome message
    $welcome Message = "Welcome home, " . $name . "! You are " . $age . " years old today.";
    echo $welcome Message;
} else {
    // Display the form
    ?>
    <form method="post" action="">
        <label for="name">Name:</label>
        <input type="text" id="name" name="name" required><br><br>
        
        <label for="dob">Date of Birth:</label>
        <input type="date" id="dob" name="dob" required><br><br>
        
        <label for="address">Home Address:</label>
        <input type="text" id="address" name="address" required><br><br>
        
        <input type="submit" value="Submit">
    </form>
    <?php
}
?>
