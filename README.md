<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>College Event Registration</title>
  <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body {
            font-family: Arial, sans-serif;
            background: linear-gradient(45deg, #3498db, #9b59b6);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }
        .form-container {
            background: white;
            padding: 40px;
            border-radius: 10px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
            width: 100%;
            max-width: 400px;
        }
        h1 {
            text-align: center;
            color: #333;
            margin-bottom: 30px;
          }
        .form-group {
            margin-bottom: 20px;
        }
        label {
            display: block;
            margin-bottom: 5px;
            color: #555;
            font-weight: bold;
        }
        input, select {
            width: 100%;
            padding: 12px;
            border: 2px solid #ddd;
            border-radius: 5px;
            font-size: 16px;
        }
        input:focus, select:focus {
            outline: none;
            border-color: #3498db;
        }
        .error {
            border-color: #e74c3c !important;
            background-color: #ffeaea;
        }
        
        .error-message {
            color: #e74c3c;
            font-size: 14px;
            margin-top: 5px;
        }
        .submit-btn {
            width: 100%;
            padding: 15px;
            background: linear-gradient(45deg, #3498db, #9b59b6);
            color: white;
            border: none;
            border-radius: 5px;
            font-size: 18px;
            cursor: pointer;
        }
        .submit-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.3);
        }
        .success {
            background: #2ecc71;
            color: white;
            padding: 15px;
            border-radius: 5px;
            text-align: center;
            margin-top: 20px;
            display: none;
        }
        }
    </style>
</head>
<body>
    <div class="form-container">
        <h1>Event Registration</h1>
        <form id="myForm">
            <!-- NAME FIELD -->
            <div class="form-group">
                <label for="name">Full Name *</label>
                <input type="text" id="name" placeholder="Enter your name">
                <div id="nameError" class="error-message"></div>
            </div>
            <!-- EMAIL FIELD -->
            <div class="form-group">
                <label for="email">Email *</label>
                <input type="email" id="email" placeholder="Enter your email">
                <div id="emailError" class="error-message"></div>
            </div>
            <!-- EVENT SELECTION -->
            <div class="form-group">
                <label for="event">Select Event *</label>
                <select id="event">
                    <option value="">Choose an event...</option>
                    <option value="tech-fest">Tech Festival</option>
                    <option value="cultural-fest">Cultural Event</option>
                    <option value="hackathon">Hackathon</option>
                    <option value="club orientation">Club Orientation</option>
                </select>
                <div id="eventError" class="error-message"></div>
            </div>
            <!-- SUBMIT BUTTON -->
            <button type="submit" class="submit-btn">Register Now</button>
        </form>
        <!-- SUCCESS MESSAGE -->
        <div id="success" class="success">
           Registration Successful! Check your email for details.
        </div>
    </div>
    <script>
        const form = document.getElementById('myForm');
        const nameInput = document.getElementById('name');
        const emailInput = document.getElementById('email');
        const eventSelect = document.getElementById('event');
        const successDiv = document.getElementById('success');
        form.addEventListener('submit', function(e) {
            e.preventDefault(); // Stop form from submitting normally
            clearErrors();
            
            let isValid = true;
            if (nameInput.value.trim() === '') {
                showError('name', 'nameError', 'Please enter your name');
                isValid = false;
            }
            const email = emailInput.value.trim();
            if (email === '') {
                showError('email', 'emailError', 'Please enter your email');
                isValid = false;
            } else if (!isValidEmail(email)) {
                showError('email', 'emailError', 'Please enter a valid email');
                isValid = false;
            }
            if (eventSelect.value === '') {
                showError('event', 'eventError', 'Please select an event');
                isValid = false;
            }
        })
        reset.form();
        }
    </script>
</body>
</html>
