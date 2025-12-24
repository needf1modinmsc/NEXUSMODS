# NEXUSMODS
<!DOCTYPE html>
<html>
<head>
    <title>My JSONL Table</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/tabulator/5.5.2/js/tabulator.min.js"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/tabulator/5.5.2/css/tabulator.min.css" rel="stylesheet">
</head>
<body>
    <div id="table"></div>
    <script>
        fetch('job-16435344-result.jsonl')  // 파일명 맞춰주세요
            .then(response => response.text())
            .then(text => {
                const data = text.split('\n').filter(line => line.trim()).map(line => JSON.parse(line));
                new Tabulator("#table", {
                    data: data,
                    autoColumns: true,  // 자동으로 열 생성
                    layout: "fitColumns",
                    pagination: "local",
                    paginationSize: 20,
                });
            });
    </script>
</body>
</html>
