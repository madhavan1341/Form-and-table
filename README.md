# Form-and-table

<!DOCTYPE html>
<html>
<head>
  <title>Form and Table Example</title>
  <style>
    table {
      border-collapse: collapse;
      width: 100%;
    }
    th, td {
      border: 1px solid black;
      padding: 8px;
      text-align: left;
    }
  </style>
</head>
<body>
  <h1>Form and Table Example</h1>
  <form id="myForm">
    <label for="firstName">First Name:</label>
    <input type="text" id="firstName" required><br><br>
    <label for="lastName">Last Name:</label>
    <input type="text" id="lastName" required><br><br>
    <label for="address">Address:</label>
    <input type="text" id="address" required><br><br>
    <label for="pincode">Pincode:</label>
    <input type="text" id="pincode" required><br><br>
    <label for="gender">Gender:</label>
    <input type="radio" id="male" name="gender" value="Male" required>
    <label for="male">Male</label>
    <input type="radio" id="female" name="gender" value="Female" required>
    <label for="female">Female</label><br><br>
    <label for="food">Choice of Food (select at least 2):</label>
    <select id="food" multiple required>
      <option value="Pizza">Pizza</option>
      <option value="Burger">Burger</option>
      <option value="Pasta">Pasta</option>
      <option value="Sushi">Sushi</option>
      <option value="Salad">Salad</option>
    </select><br><br>
    <label for="state">State:</label>
    <input type="text" id="state" required><br><br>
    <label for="country">Country:</label>
    <input type="text" id="country" required><br><br>
    <input type="submit" value="Submit">
  </form>
  
  <h2>Records:</h2>
  <table id="records">
    <thead>
      <tr>
        <th>First Name</th>
        <th>Last Name</th>
        <th>Address</th>
        <th>Pincode</th>
        <th>Gender</th>
        <th>Food</th>
        <th>State</th>
        <th>Country</th>
      </tr>
    </thead>
    <tbody>
    </tbody>
  </table>
  
  <script>
    document.getElementById("myForm").addEventListener("submit", function(event) {
      event.preventDefault(); // prevent form submission
      var firstName = document.getElementById("firstName").value;
      var lastName = document.getElementById("lastName").value;
      var address = document.getElementById("address").value;
      var pincode = document.getElementById("pincode").value;
      var gender = document.querySelector('input[name="gender"]:checked').value;
      var food = Array.from(document.getElementById("food").selectedOptions).map(option => option.value);
      var state = document.getElementById("state").value;
      var country = document.getElementById("country").value;
      
      var table = document.getElementById("records").getElementsByTagName("tbody")[0];
      var row
