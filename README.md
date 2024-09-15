# my-electronic-configuration
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Electronic Configuration</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1>Electronic Configuration of Elements</h1>
    </header>
    <main>
        <section id="periodic-table">
            <!-- Jadual berkala akan dimasukkan di sini -->
        </section>
        <section id="element-info">
            <h2>Element Information</h2>
            <p id="element-name">Select an element to see its configuration.</p>
            <p id="element-config">Configuration will be displayed here.</p>
        </section>
    </main>
    <script src="script.js"></script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f4f4f4;
}

header {
    background-color: #333;
    color: white;
    text-align: center;
    padding: 1em 0;
}

main {
    display: flex;
    justify-content: space-around;
    padding: 20px;
}

#periodic-table {
    width: 50%;
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
}

#element-info {
    width: 45%;
}

.element {
    display: inline-block;
    width: 50px;
    height: 50px;
    line-height: 50px;
    text-align: center;
    margin: 5px;
    background-color: #ddd;
    cursor: pointer;
    border-radius: 5px;
}

.element:hover {
    background-color: #ccc;
}
document.addEventListener('DOMContentLoaded', function() {
    const elements = {
        'H': '1s1',
        'He': '1s2',
        'Li': '1s2 2s1',
        'Be': '1s2 2s2',
        'B': '1s2 2s2 2p1',
        'C': '1s2 2s2 2p2',
        'N': '1s2 2s2 2p3',
        'O': '1s2 2s2 2p4',
        'F': '1s2 2s2 2p5',
        'Ne': '1s2 2s2 2p6',
        'Na': '1s2 2s2 2p6 3s1',
        'Mg': '1s2 2s2 2p6 3s2',
        'Al': '1s2 2s2 2p6 3s2 3p1',
        'Si': '1s2 2s2 2p6 3s2 3p2',
        'P': '1s2 2s2 2p6 3s2 3p3',
        'S': '1s2 2s2 2p6 3s2 3p4',
        'Cl': '1s2 2s2 2p6 3s2 3p5',
        'Ar': '1s2 2s2 2p6 3s2 3p6',
        'K': '1s2 2s2 2p6 3s2 3p6 4s1',
        'Ca': '1s2 2s2 2p6 3s2 3p6 4s2',
        // Tambah lebih banyak unsur di sini jika diperlukan
    };

    const periodicTable = document.getElementById('periodic-table');
    const elementName = document.getElementById('element-name');
    const elementConfig = document.getElementById('element-config');

    // Buat elemen untuk setiap unsur
    for (const [symbol, config] of Object.entries(elements)) {
        const elementDiv = document.createElement('div');
        elementDiv.className = 'element';
        elementDiv.textContent = symbol;
        elementDiv.addEventListener('click', function() {
            elementName.textContent = symbol;
            elementConfig.textContent = config;
        });
        periodicTable.appendChild(elementDiv);
    }
});
