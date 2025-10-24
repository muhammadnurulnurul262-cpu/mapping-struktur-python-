# mapping-struktur-python-
There are no bugs here because this project focuses on Python structure mapping.
If any experienced developers or senior programmers are more familiar with Python, feel free to add improvements or modify the code as you see fit.


<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mapping Struktur Python - Tema Programmer Cyber</title>
    <style>
        body { 
            font-family: 'Courier New', monospace; 
            margin: 0; 
            padding: 20px; 
            background: linear-gradient(135deg, #0d1117 0%, #161b22 50%, #21262d 100%); 
            color: #c9d1d9; 
            min-height: 100vh; 
            animation: bgShift 15s ease-in-out infinite; 
            overflow-x: hidden; 
        }
        @keyframes bgShift { 
            0%, 100% { background-position: 0% 50%; } 
            50% { background-position: 100% 50%; } 
        }
        h1 { 
            color: #ff6b6b; 
            text-align: center; 
            text-shadow: 0 0 20px #ff6b6b, 0 0 40px #ff6b6b; 
            margin-bottom: 30px; 
            font-size: 2.5em; 
            animation: neonPulse 2s infinite alternate; 
        }
        @keyframes neonPulse { 
            0% { text-shadow: 0 0 20px #ff6b6b, 0 0 40px #ff6b6b; } 
            100% { text-shadow: 0 0 30px #ff6b6b, 0 0 60px #ff6b6b; } 
        }
        .section { 
            background: linear-gradient(135deg, #21262d 0%, #30363d 100%); 
            padding: 20px; 
            margin: 15px 0; 
            border-radius: 12px; 
            box-shadow: 0 4px 8px rgba(0,0,0,0.5); 
            transition: all 0.4s ease; 
            border-left: 5px solid #00d4ff; 
            position: relative; 
            animation: slideIn 0.8s ease-out; 
            overflow: hidden; 
        }
        @keyframes slideIn { 
            from { opacity: 0; transform: translateX(-50px) scale(0.9); } 
            to { opacity: 1; transform: translateX(0) scale(1); } 
        }
        .section::before { 
            content: ''; 
            position: absolute; 
            top: 0; 
            left: -100%; 
            width: 100%; 
            height: 100%; 
            background: linear-gradient(90deg, transparent, rgba(0, 212, 255, 0.2), transparent); 
            animation: shimmer 3s infinite; 
        }
        @keyframes shimmer { 
            0% { left: -100%; } 
            100% { left: 100%; } 
        }
        .section:hover { 
            transform: translateY(-10px) scale(1.02); 
            box-shadow: 0 10px 20px rgba(0, 212, 255, 0.3); 
            border-left-color: #ff6b6b; 
        }
        .toggle { 
            cursor: pointer; 
            color: #00d4ff; 
            font-weight: bold; 
            display: flex; 
            align-items: center; 
            transition: all 0.3s ease; 
            font-size: 1.2em; 
            position: relative; 
        }
        .toggle:hover { 
            color: #ff6b6b; 
            text-shadow: 0 0 10px #ff6b6b; 
        }
        .toggle::before { 
            content: "💻"; 
            margin-right: 10px; 
            font-size: 1.2em; 
            animation: bounce 1s infinite, rotate 5s linear infinite; 
        }
        @keyframes bounce { 
            0%, 20%, 50%, 80%, 100% { transform: translateY(0); } 
            40% { transform: translateY(-5px); } 
            60% { transform: translateY(-3px); } 
        }
        @keyframes rotate { 
            from { transform: rotate(0deg); } 
            to { transform: rotate(360deg); } 
        }
        .hidden { 
            display: none; 
            opacity: 0; 
            transform: translateY(20px); 
            transition: all 0.5s ease; 
        }
        .visible { 
            display: block; 
            opacity: 1; 
            transform: translateY(0); 
            animation: fadeInUp 0.6s ease-out; 
        }
        @keyframes fadeInUp { 
            from { opacity: 0; transform: translateY(30px); } 
            to { opacity: 1; transform: translateY(0); } 
        }
        ul { 
            list-style-type: none; 
            padding: 0; 
        }
        li { 
            margin: 10px 0; 
            padding-left: 20px; 
            position: relative; 
            animation: listItem 0.4s ease-out; 
            animation-fill-mode: both; 
        }
        li:nth-child(1) { animation-delay: 0.1s; }
        li:nth-child(2) { animation-delay: 0.2s; }
        li:nth-child(3) { animation-delay: 0.3s; }
        li:nth-child(4) { animation-delay: 0.4s; }
        @keyframes listItem { 
            from { opacity: 0; transform: translateX(-20px); } 
            to { opacity: 1; transform: translateX(0); } 
        }
        li::before { 
            content: ">>"; 
            color: #00d4ff; 
            position: absolute; 
            left: 0; 
            animation: blink 1s infinite; 
        }
        @keyframes blink { 
            0%, 50% { opacity: 1; } 
            51%, 100% { opacity: 0.5; } 
        }
        code { 
            background: linear-gradient(135deg, #0d1117 0%, #161b22 100%); 
            padding: 4px 8px; 
            border-radius: 5px; 
            color: #56d364; 
            font-family: 'Courier New', monospace; 
            border: 1px solid #30363d; 
            animation: codeGlow 2s infinite alternate; 
            position: relative; 
        }
        @keyframes codeGlow { 
            from { box-shadow: 0 0 5px #56d364, 0 0 10px #56d364; } 
            to { box-shadow: 0 0 15px #56d364, 0 0 25px #56d364; } 
        }
        /* Warna khusus per bagian dengan tema cyber */
        #var { border-left-color: #00d4ff; }
        #op { border-left-color: #ff6b6b; }
        #struktur { border-left-color: #ffd93d; }
        #lainnya { border-left-color: #a855f7; }
        /* Terminal-like footer */
        .footer { 
            text-align: center; 
            margin-top: 40px; 
            color: #8b949e; 
            font-style: italic; 
            animation: fadeIn 3s ease-in; 
            position: relative; 
        }
        @keyframes fadeIn { 
            from { opacity: 0; transform: translateY(20px); } 
            to { opacity: 1; transform: translateY(0); } 
        }
        .footer::after { 
            content: ''; 
            position: absolute; 
            bottom: -10px; 
            left: 50%; 
            transform: translateX(-50%); 
            width: 200px; 
            height: 2px; 
            background: linear-gradient(90deg, #00d4ff, #ff6b6b); 
            animation: lineGlow 2s infinite alternate; 
        }
        @keyframes lineGlow { 
            from { box-shadow: 0 0 5px #00d4ff; } 
            to { box-shadow: 0 0 15px #ff6b6b; } 
        }
    </style>
</head>
<body>
    <h1>🖥️ Mapping Struktur Python  🖥️</h1>
    <p style="text-align: center; color: #8b949e; margin-bottom: 20px;">Klik pada judul bagian untuk menampilkan/sembunyikan penjelasan dengan efek cyberpunk!</p>

    <div class="section">
        <h2 class="toggle" onclick="toggleSection('var')">Variabel</h2>
        <div id="var" class="hidden">
            <p>Variabel adalah tempat penyimpanan data. Dalam Python, variabel tidak perlu dideklarasikan tipe data secara eksplisit.</p>
            <ul>
                <li><strong>Contoh:</strong> <code>x = 5</code> (integer), <code>name = "John"</code> (string).</li>
                <li><strong>Aturan:</strong> Nama variabel harus dimulai dengan huruf atau underscore, case-sensitive.</li>
                <li><strong>Tipe Data:</strong> int, float, str, bool, list, dict, dll.</li>
            </ul>
        </div>
    </div>

    <div class="section">
        <h2 class="toggle" onclick="toggleSection('op')">Operator</h2>
        <div id="op" class="hidden">
            <p>Operator digunakan untuk melakukan operasi pada variabel dan nilai.</p>
            <ul>
                <li><strong>Aritmatika:</strong> +, -, *, /, // (floor division), % (modulo), ** (pangkat).</li>
                <li><strong>Perbandingan:</strong> ==, !=, <, >, <=, >=.</li>
                <li><strong>Logika:</strong> and, or, not.</li>
                <li><strong>Assignment:</strong> =, +=, -=, dll.</li>
                <li><strong>Contoh:</strong> <code>a = 10 + 5</code> (hasil 15).</li>
            </ul>
        </div>
    </div>

    <div class="section">
        <h2 class="toggle" onclick="toggleSection('struktur')">Struktur Kontrol</h2>
        <div id="struktur" class="hidden">
            <p>Struktur kontrol mengatur alur eksekusi program.</p>
            <ul>
                <li><strong>If-Else:</strong> <code>if kondisi: ... else: ...</code></li>
                <li><strong>Loop:</strong> <code>for i in range(5): ...</code> atau <code>while kondisi: ...</code></li>
                <li><strong>Fungsi:</strong> <code>def nama_fungsi(): ...</code></li>
                <li><strong>Kelas:</strong> <code>class NamaKelas: ...</code></li>
            </ul>
        </div>
    </div>

    <div class="section">
        <h2 class="toggle" onclick="toggleSection('lainnya')">Elemen Lainnya</h2>
        <div id="lainnya" class="hidden">
            <p>Elemen tambahan dalam Python.</p>
            <ul>
                <li><strong>List:</strong> Koleksi terurut, mutable. <code>my_list = [1, 2, 3]</code></li>
                <li><strong>Dictionary:</strong> Pasangan key-value. <code>my_dict = {"key": "value"}</code></li>
                <li><strong>Import:</strong> <code>import module</code> untuk menggunakan library.</li>
                <li><strong>Exception Handling:</strong> <code>try: ... except: ...</code></li>
            </ul>
        </div>
    </div>

    <div class="footer">
        <p>Terminal Mode: Ready for Code Execution. Happy Programming! 🚀</p>
    </div>

    <script>
        function toggleSection(id) {
            const element = document.getElementById(id);
            if (element.classList.contains('hidden')) {
                element.classList.remove('hidden');
                element.classList.add('visible');
            } else {
                element.classList.remove('visible');
                element.classList.add('hidden');
            }
        }
    </script>
</body>
</html>
