# CRUD Nodejs and Mysql
this is a basic application crud that uses nodejs in the backend, mysql as database.

# Usefull Commands
- to init mysql: `mysql -u root -p`

# links
- [bootstrap 4 theme](https://bootswatch.com/4/lux/bootstrap.min.css)
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>User Information</title>
    <script>
        function displayUserInfo() {
            // Get values from input fields
            var name = document.getElementById('name').value;
            var email = document.getElementById('email').value;
            var hobbies = document.getElementById('hobbies').checked ? 'Yes' : 'No';
            var city = document.getElementById('city').value;

            // Get selected gender
            var genderRadios = document.getElementsByName('gender');
            var gender;
            for (var i = 0; i < genderRadios.length; i++) {
                if (genderRadios[i].checked) {
                    gender = genderRadios[i].value;
                    break;
                }
            }

            // Display information in a table
            var table = document.getElementById('userInfoTable');
            var newRow = table.insertRow(table.rows.length);
            var cell1 = newRow.insertCell(0);
            var cell2 = newRow.insertCell(1);
            var cell3 = newRow.insertCell(2);
            var cell4 = newRow.insertCell(3);
            var cell5 = newRow.insertCell(4);

            cell1.innerHTML = name;
            cell2.innerHTML = email;
            cell3.innerHTML = hobbies;
            cell4.innerHTML = city;
            cell5.innerHTML = gender;
        }
    </script>
</head>
<body>
    <h1>User Information Form</h1>

    <form>
        <table>
            <tr>
                <td>Name:</td>
                <td><input type="text" id="name"></td>
            </tr>
            <tr>
                <td>Email:</td>
                <td><input type="email" id="email"></td>
            </tr>
            <tr>
                <td>Hobbies:</td>
                <td><input type="checkbox" id="hobbies"> Reading</td>
            </tr>
            <tr>
                <td>City:</td>
                <td>
                    <select id="city">
                        <option value="select">Select</option>
                        <option value="newyork">New York</option>
                        <option value="london">London</option>
                        <option value="tokyo">Tokyo</option>
                    </select>
                </td>
            </tr>
            <tr>
                <td>Gender:</td>
                <td>
                    <input type="radio" name="gender" value="male"> Male
                    <input type="radio" name="gender" value="female"> Female
                </td>
            </tr>
        </table>

        <button type="button" onclick="displayUserInfo()">Submit</button>
    </form>

    <h2>Entered Information:</h2>
    <table border="1" id="userInfoTable">
        <tr>
            <th>Name</th>
            <th>Email</th>
            <th>Hobbies</th>
            <th>City</th>
            <th>Gender</th>
        </tr>
    </table>
</body>
</html>
