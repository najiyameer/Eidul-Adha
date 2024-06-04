# Eidul-Adha

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Eid-ul-Adha Form</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
        }

        .container {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f3f3f3;
        }

        .content {
            width: 80%;
            max-width: 600px;
            padding: 20px;
            background-color: #fff;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }

        .logo {
            text-align: center;
            margin-bottom: 20px;
        }

        .logo img {
            max-width: 100%;
            height: auto;
        }

        form {
            text-align: left;
        }

        .parts-container {
            display: flex;
            flex-direction: column;
        }

        .part {
            display: flex;
            align-items: center;
            margin-bottom: 8px;
        }

        input[type="checkbox"] {
            margin-right: 5px;
        }

        input[type="text"],
        input[type="number"],
        select,
        input[type="date"] {
            width: calc(100% - 16px);
            padding: 8px;
            margin-bottom: 12px;
            border: 1px solid #ccc;
            border-radius: 4px;
            box-sizing: border-box;
        }

        button {
            background-color: #4CAF50;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }

        button:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="content">
            <header class="logo">
                <img src="C:\Users\DELL\Logo1.png.jpg](https://raw.githubusercontent.com/najiyameer/logo/1d6cff8d9d6f101efcb1134d19592a0cf3bcca94/Logo1.png.jpg" alt="Logo">
            </header>

            <form name="Invoice">
                <label for="name">Name:</label>
                <input type="text" id="name" name="name" placeholder="Your name" required>

                <label for="a_name">Animal Number:</label>
                <input type="number" id="a_number" name="a_number" placeholder="Animal Number" required>

                <div class="parts-container">
                    <div class="part">
                        <input type="checkbox" id="part1" name="part1">
                        <label for="part1">Part 1</label>
                    </div>
                    <div class="part">
                        <input type="checkbox" id="part2" name="part2">
                        <label for="part2">Part 2</label>
                    </div>
                    <div class="part">
                        <input type="checkbox" id="part3" name="part3">
                        <label for="part3">Part 3</label>
                    </div>

                    <div class="part">
                        <input type="checkbox" id="part4" name="part4">
                        <label for="part4">Part 4</label>
                    </div>

                    <div class="part">
                        <input type="checkbox" id="part5" name="part5">
                        <label for="part5">Part 5</label>
                    </div>

                    <div class="part">
                        <input type="checkbox" id="part6" name="part6">
                        <label for="part6">Part 6</label>
                    </div>

                    <div class="part">
                        <input type="checkbox" id="part7" name="part7">
                        <label for="part3">Part 7</label>
                    </div>
                    <!-- Add more parts as needed -->
                </div>

                <label for="date1">Select Date 1:</label>
                <input type="date" id="date1" name="date1" min="2024-06-01" max="2024-06-31" >

                <!-- Add similar date inputs for date2 and date3 -->

                <label for="date2">Select Date 2:</label>
                <input type="date" id="date2" name="date2" min="2024-06-01" max="2024-06-31" >

                <label for="date3">Select Date 3:</label>
                <input type="date" id="date3" name="date3" min="2024-06-01" max="2024-06-31" >

                <!-- Date selection -->
                <label for="date">Booking Date:</label>
                <input type="date" id="date" name="date" min="2024-05-25" max="2024-06-25">

                <!-- Set date to current date by default -->
                <script>
                    // Get current date in yyyy-mm-dd format
                    const today = new Date().toISOString().split('T')[0];

                    // Set the value of the date input field to today's date
                    document.getElementById('date').value = today;

                </script>

                <label for="phone">Contact Number:</label>
                <input type="text" id="phone" name="phone" required>

                <button type="submit">Submit</button>
            </form>
            <span id="Success"></span>
        </div>
    </div>

    <script>
        const scriptURL = 'https://script.google.com/macros/s/AKfycbwAHhOrMIbxCSDMIXmLxeggqP63RjxeMwIAjC0-V5As35KIVByDlKSeHDg_mdeH1z26/exec'
        const form = document.forms['Invoice'];
        const Success = document.getElementById('Success');
        form.addEventListener('submit', e => {
            e.preventDefault();
            const formData = new FormData(form);
            fetch(scriptURL, { method: 'POST', body: formData })
                .then(response => {
                    Success.textContent = "Data Successfully Submitted";
                    setTimeout(function() {
                        Success.textContent = "";
                    }, 2000);
                    form.reset();
                })
                .catch(error => console.error('Error!', error.message));
        });
    </script>
</body>
</html>
