<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Coming Soon</title>
    <style>
        .body {
            margin: 0;
            font-family: Arial, sans-serif;
            background-color: #f5f5f5;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            text-align: center;
        }
        .container {
            background: #fff;
            border-radius: 8px;
            padding: 40px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        h1 {
            font-size: 3em;
            color: #333;
            margin-bottom: 10px;
        }
        p {
            font-size: 1.2em;
            color: #555;
            margin-bottom: 20px;
        }
        .countdown {
            font-size: 2em;
            margin-bottom: 20px;
            color: #e94e77;
        }
        .subscribe {
            display: flex;
            justify-content: center;
            margin-top: 20px;
        }
        .subscribe input {
            padding: 10px;
            font-size: 1em;
            border: 1px solid #ddd;
            border-radius: 4px;
            margin-right: 10px;
            width: 300px;
        }
        .subscribe button {
            padding: 10px 20px;
            font-size: 1em;
            border: none;
            border-radius: 4px;
            background-color: #e94e77;
            color: #fff;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        .subscribe button:hover {
            background-color: #d43f5a;
        }
        footer {
            margin-top: 20px;
            font-size: 0.8em;
            color: #999;
        }
        footer a {
            color: #e94e77;
            text-decoration: none;
        }
        footer a:hover {
            text-decoration: underline;
        }
    </style>
</head>
<body class="body">
    <div class="container">
        <h1>Coming Soon!</h1>
        <p>We're working hard to bring you something awesome. Stay tuned!</p>
        <div class="countdown" id="countdown">
            <!-- Countdown timer will go here -->
        </div>
    </div>
</body>
</html>
