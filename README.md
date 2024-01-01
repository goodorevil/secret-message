# secret-message
save message with pasword
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cool Notepad</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 0;
            padding: 0;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            background-color: #1a1a1a;
            color: #ffffff;
        }

        #notepad {
            width: 80%;
            height: 60vh;
            margin-bottom: 20px;
            padding: 10px;
            background-color: #2b2b2b;
            color: #ffffff;
            border: 2px solid #3c3c3c;
            border-radius: 5px;
            outline: none;
            resize: none;
        }

        #fileName {
            width: 60%;
            padding: 8px;
            margin-bottom: 10px;
            background-color: #2b2b2b;
            color: #ffffff;
            border: 1px solid #3c3c3c;
            border-radius: 5px;
            outline: none;
        }

        button {
            padding: 10px;
            background-color: #3498db;
            color: #ffffff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        button:hover {
            background-color: #2b2b2b;
        }
    </style>
</head>
<body>
    <textarea id="notepad" placeholder="Write something..."></textarea>
    <input type="text" id="fileName" placeholder="Enter file name">
    <button onclick="saveContent()">Save</button>
    <button onclick="loadContent()">Open</button>

    <script>
        function saveContent() {
            const fileName = document.getElementById('fileName').value;
            const content = document.getElementById('notepad').value;

            if (fileName && content) {
                localStorage.setItem(fileName, content);
                alert('Content saved successfully!');
            } else {
                alert('Please enter both a file name and content.');
            }
        }

        function loadContent() {
            const fileName = document.getElementById('fileName').value;
            const content = localStorage.getItem(fileName);

            if (content) {
                document.getElementById('notepad').value = content;
            } else {
                alert('File not found. Please enter a valid file name.');
            }
        }
    </script>
</body>
</html>

