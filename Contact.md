<?php
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    $name = htmlspecialchars($_POST['name']);
    $email = htmlspecialchars($_POST['email']);
    $message = htmlspecialchars($_POST['message']);

    echo "<h3>Thank you, $name!</h3>";
    echo "<p>Your message has been received:</p>";
    echo "<blockquote>$message</blockquote>";
}
?>
<!DOCTYPE html>
<html>
<head>
    <title>Contact Form</title>
</head>
<body>
    <form method="post" action="">
        <label>Name: <input type="text" name="name" required></label><br>
        <label>Email: <input type="email" name="email" required></label><br>
        <label>Message: <textarea name="message" required></textarea></label><br>
        <button type="submit">Submit</button>
    </form>
</body>
</html>
