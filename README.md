<!DOCTYPE html>
<html>
<head>
    <title>Electricity Bill Calculator</title>
</head>
<body>

<h2>Electricity Bill Calculator</h2>

<form method="post">
    Enter Units Consumed:
    <input type="number" name="units" required>
    <input type="submit" name="submit" value="Calculate">
</form>

<?php
function calculateBill($units)
{
    $bill = 0;

    if ($units <= 100) {
        $bill = $units * 3;
    }
    elseif ($units <= 200) {
        $bill = (100 * 3) + (($units - 100) * 4);
    }
    else {
        $bill = (100 * 3) + (100 * 4) + (($units - 200) * 5);
    }

    return $bill;
}

if (isset($_POST['submit'])) {
    $units = $_POST['units'];
    $amount = calculateBill($units);

    echo "<h3>Total Electricity Bill = Rs. $amount</h3>";
}
?>

</body>
</html>
output:
Units Consumed = 250
Total Electricity Bill = Rs. 950
