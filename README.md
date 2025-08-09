# story-app
Writing app
<!DOCTYPE html><html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>برنامج كتابة القصص</title>
    <style>
        body {
            font-family: 'Tahoma', sans-serif;
            background-color: #f5f5f5;
            margin: 0;
            padding: 20px;
        }
        h1 {
            text-align: center;
            color: #333;
        }
        .chapter {
            background: #fff;
            padding: 15px;
            margin: 10px 0;
            border-radius: 10px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        button {
            background-color: #4CAF50;
            color: white;
            padding: 10px 15px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            margin-top: 10px;
        }
        button:hover {
            background-color: #45a049;
        }
        input, textarea {
            width: 100%;
            padding: 10px;
            margin-top: 5px;
            border-radius: 5px;
            border: 1px solid #ccc;
            box-sizing: border-box;
        }
        .copy-btn {
            background-color: #2196F3;
            margin-top: 5px;
        }
        .copy-btn:hover {
            background-color: #0b7dda;
        }
    </style>
</head>
<body>
    <h1>📖 برنامج كتابة القصص</h1>
    <button onclick="addChapter()">➕ إضافة فصل</button><div id="chapters"></div>

<script>
    function addChapter() {
        let title = prompt("أدخل عنوان الفصل:");
        if (!title) return;
        
        let chapterDiv = document.createElement("div");
        chapterDiv.className = "chapter";

        let chapterTitle = document.createElement("h2");
        chapterTitle.innerText = title;

        let chapterContent = document.createElement("textarea");
        chapterContent.placeholder = "اكتب هنا نص الفصل...";
        chapterContent.rows = 6;

        let copyButton = document.createElement("button");
        copyButton.innerText = "📋 نسخ الفصل";
        copyButton.className = "copy-btn";
        copyButton.onclick = function() {
            navigator.clipboard.writeText(chapterContent.value).then(() => {
                alert("تم نسخ النص بنجاح ✅");
            });
        };

        chapterDiv.appendChild(chapterTitle);
        chapterDiv.appendChild(chapterContent);
        chapterDiv.appendChild(copyButton);

        document.getElementById("chapters").appendChild(chapterDiv);
    }
</script>

</body>
</html>
