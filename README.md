# Dinh-c-L-<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dinh Độc Lập - Di Tích Lịch Sử</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" />
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Merriweather:wght@400;700&display=swap" rel="stylesheet">
    <style>.map-box { height: 300px; width: 100%; }</style>
</head>
<body class="bg-[#FFFBF0] text-[#1A202C] font-sans min-h-screen flex flex-col">
    <header class="bg-[#9B2C2C] text-white shadow-md py-4 px-6">
        <div class="max-w-4xl mx-auto flex items-center space-x-3">
            <i class="fa-solid fa-landmark text-2xl text-[#D69E2E]"></i>
            <h1 class="font-serif text-xl font-bold">Dinh Độc Lập (Hội Trường Thống Nhất)</h1>
        </div>
    </header>
    <main class="max-w-4xl mx-auto px-4 py-8 flex-1 space-y-6 w-full">
        <div class="relative h-72 md:h-96 rounded-2xl overflow-hidden shadow-lg">
            <img src="https://images.unsplash.com/photo-1583417319070-4a69db38a482?auto=format&fit=crop&w=1200&q=80" class="w-full h-full object-cover">
            <div class="absolute inset-0 bg-gradient-to-t from-black/80 via-transparent flex items-end p-6">
                <div>
                    <span class="px-3 py-1 bg-[#9B2C2C] text-white text-xs font-semibold rounded-full uppercase">Di tích Quốc gia Đặc biệt</span>
                    <h1 class="font-serif text-2xl md:text-4xl font-bold text-white mt-2">Dinh Độc Lập</h1>
                    <p class="text-gray-200 text-sm mt-1"><i class="fa-solid fa-location-dot text-[#D69E2E] mr-2"></i>135 Nam Kỳ Khởi Nghĩa, Quận 1</p>
                </div>
            </div>
        </div>
        <div class="bg-[#9B2C2C] text-white p-5 rounded-xl shadow flex flex-wrap items-center justify-between gap-4">
            <div class="flex items-center space-x-3">
                <i class="fa-solid fa-headphones text-2xl text-[#D69E2E]"></i>
                <div><h4 class="font-bold">Thuyết Minh Audio</h4><p class="text-xs text-red-200">Nghe hướng dẫn viên ảo giới thiệu</p></div>
            </div>
            <div class="flex space-x-2">
                <button onclick="speakText('Dinh Độc Lập là di tích lịch sử quốc gia đặc biệt, chứng nhân lịch sử ngày 30 tháng 4 năm 1975.')" class="px-4 py-2 bg-[#D69E2E] text-[#1A202C] font-bold rounded-lg text-sm hover:bg-yellow-400 transition"><i class="fa-solid fa-play mr-1"></i> Phát</button>
                <button onclick="stopSpeech()" class="px-4 py-2 bg-white/20 rounded-lg text-sm hover:bg-white/30 transition"><i class="fa-solid fa-stop mr-1"></i> Dừng</button>
            </div>
        </div>
        <div class="bg-white p-6 rounded-xl shadow-sm space-y-4">
            <h3 class="font-serif font-bold text-xl text-[#9B2C2C] border-b pb-2">Giới Thiệu Chi Tiết</h3>
            <p class="text-gray-700 leading-relaxed">Dinh Độc Lập là công trình kiến trúc nổi tiếng do kiến trúc sư Ngô Viết Thụ thiết kế. Đây là nơi ở và làm việc của Tổng thống Việt Nam Cộng hòa trước đây, đồng thời là biểu tượng của hòa bình và thống nhất đất nước ngày 30/4/1975.</p>
            <h4 class="font-bold text-gray-800 pt-2">Vị Trí Bản Đồ:</h4>
            <div id="map" class="map-box rounded-lg border"></div>
            <a href="https://www.google.com/maps/search/?api=1&query=10.7769,106.6953" target="_blank" class="block text-center py-2.5 bg-red-800 text-white font-bold rounded-lg hover:bg-red-900 transition text-sm">Mở Chỉ Đường Trên Google Maps</a>
        </div>
    </main>
    <footer class="bg-[#1A202C] text-gray-400 py-6 text-center text-xs"><p>© 2026 Trang Thông Tin Di Tích Lịch Sử TP.HCM</p></footer>
    <script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>
    <script>
        const map = L.map('map').setView([10.7769, 106.6953], 16);
        L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png').addTo(map);
        L.marker([10.7769, 106.6953]).addTo(map).bindPopup('<b>Dinh Độc Lập</b>').openPopup();
        let utterance = null;
        function speakText(text) { window.speechSynthesis.cancel(); utterance = new SpeechSynthesisUtterance(text); utterance.lang = 'vi-VN'; window.speechSynthesis.speak(utterance); }
        function stopSpeech() { if(window.speechSynthesis.speaking) window.speechSynthesis.cancel(); }
    </script>
</body>
</html>