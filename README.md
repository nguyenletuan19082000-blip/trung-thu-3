DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lời Chúc Trung Thu Đặc Biệt Gửi Phương</title>
    <!-- Tải Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        /* Sử dụng font Inter hoặc một font sans-serif đẹp */
        body {
            font-family: 'Inter', sans-serif;
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            /* Tạo nền trời sao lấp lánh */
            background: #0d1222; 
            background-image: 
                radial-gradient(circle at 100px 50px, rgba(255, 255, 255, 0.5) 1px, transparent 0),
                radial-gradient(circle at 400px 300px, rgba(255, 255, 255, 0.6) 1px, transparent 0),
                radial-gradient(circle at 50% 80%, rgba(255, 255, 255, 0.4) 1px, transparent 0),
                radial-gradient(circle at 20% 40%, rgba(255, 255, 255, 0.8) 1.5px, transparent 0),
                radial-gradient(circle at 80% 60%, rgba(255, 255, 255, 0.7) 1.5px, transparent 0);
            background-size: 500px 500px, 300px 300px, 400px 400px, 600px 600px, 700px 700px;
            background-repeat: repeat;
        }

        /* Hiệu ứng nhấp nháy cho con trỏ */
        .cursor {
            display: inline-block;
            animation: blink 0.7s infinite;
        }
        @keyframes blink {
            0%, 100% { opacity: 1; }
            50% { opacity: 0; }
        }

        /* Tạo hiệu ứng mờ ảo và nhịp đập cho mặt trăng */
        .moon-shadow {
            text-shadow: 0 0 15px #fcd34d, 0 0 30px #f59e0b, 0 0 45px #fcd34d;
            animation: moon-pulse 3s infinite alternate;
        }
        @keyframes moon-pulse {
            0% { transform: scale(1); opacity: 0.9; }
            100% { transform: scale(1.05); opacity: 1; }
        }

        /* Hiệu ứng trôi nhẹ cho lồng đèn */
        .lantern-float {
            animation: float 4s infinite alternate ease-in-out;
        }
        #lantern-left {
            animation-delay: 0.5s;
        }
        #lantern-right {
            animation-delay: 1.5s;
        }
        @keyframes float {
            0% { transform: translateY(0); }
            100% { transform: translateY(-10px); }
        }
        
        /* Thẻ chính (Card) đẹp hơn: bán trong suốt và có box shadow lấp lánh */
        .elegant-card {
            background-color: rgba(22, 28, 43, 0.95); /* Deep blue semi-transparent */
            box-shadow: 0 10px 40px rgba(255, 215, 0, 0.2), 0 0 20px rgba(255, 165, 0, 0.1);
            transition: all 0.5s ease;
        }
    </style>
</head>
<body class="p-4 md:p-8">

    <div id="app" class="w-full max-w-2xl elegant-card p-6 md:p-10 rounded-3xl border border-yellow-500/30">
        
        <!-- Khu vực tiêu đề -->
        <h1 class="text-3xl md:text-5xl font-extrabold text-center mb-6 text-yellow-300 tracking-wider">
            💌 THƯ GỬI PHƯƠNG NHÂN DỊP TRUNG THU 💌
        </h1>

        <!-- Khu vực hình ảnh/Icon -->
        <div class="text-center mb-8">
            <span id="moon-icon" class="text-8xl md:text-9xl text-yellow-400 moon-shadow opacity-0 transition-opacity duration-1000">
                🌕
            </span>
            <div class="flex justify-center space-x-8 mt-4">
                <span id="lantern-left" class="text-5xl md:text-6xl text-red-400 lantern-float opacity-0 transition-opacity duration-1000 delay-500">
                    🏮
                </span>
                <span id="rabbit-icon" class="text-4xl md:text-5xl text-gray-300 opacity-0 transition-opacity duration-1000 delay-700">
                    🐇
                </span>
                <span id="lantern-right" class="text-5xl md:text-6xl text-red-400 lantern-float opacity-0 transition-opacity duration-1000 delay-500">
                    🏮
                </span>
            </div>
        </div>

        <!-- Khu vực lời chúc với hiệu ứng gõ chữ -->
        <div id="message-container" class="space-y-4 text-lg md:text-xl font-medium min-h-[150px] text-gray-200">
            <p id="line1" class="text-pink-300"></p>
            <p id="line2" class="text-sky-300"></p>
            <p id="line3" class="text-emerald-300"></p>
            <p id="line4" class="text-amber-200"></p>
            <p id="line5" class="text-red-400 font-bold mt-6 text-2xl"></p>
        </div>
        
    </div>

    <script>
        // --- Cấu hình và Logic JavaScript ---
        
        // Dữ liệu các dòng chữ cần in ra và màu sắc tương ứng (GIỮ NGUYÊN LỜI CHÚC CỦA TUẤN)
        const messages = [
            { id: 'line1', text: '✨ Sắp tới Trung Thu rồi! Tuấn chúc Phương có một mùa Trung Thu thật vui vẻ và ấm áp.', delay: 70 },
            { id: 'line2', text: 'Chúc Phương có tất cả, trừ buồn bã. Phải luôn nhớ giữ gìn sức khỏe nha.', delay: 70 },
            { id: 'line3', text: 'Phương hong được suy nghĩ tiêu cực và suy nghĩ tùm lum đâu nha. Luôn cười tươi nhé! 😊', delay: 70 },
            { id: 'line4', text: 'Tuấn cũng xin lỗi vì không có món quà vật chất nào cho Phương.', delay: 70 },
            { id: 'line5', text: '🎁 Tuấn làm cái này thay cho món quà đặc biệt gửi tặng Phương! ⭐ Chúc Phương Đoàn Viên trọn vẹn! ⭐', delay: 40, skipCursor: true }
        ];

        /**
         * Tạo hiệu ứng gõ chữ chậm rãi (typing effect) cho một phần tử.
         */
        function slowPrint(elementId, text, delay, skipCursor = false) {
            return new Promise(resolve => {
                const element = document.getElementById(elementId);
                let i = 0;
                let cursor;

                // Thêm con trỏ nhấp nháy
                if (!skipCursor) {
                    cursor = document.createElement('span');
                    cursor.className = 'cursor';
                    cursor.innerHTML = '|';
                    element.appendChild(cursor);
                }

                function type() {
                    if (i < text.length) {
                        // Thêm ký tự vào trước con trỏ
                        element.innerHTML = text.substring(0, i + 1) + (cursor ? cursor.outerHTML : '');
                        i++;
                        setTimeout(type, delay);
                    } else {
                        // Xóa con trỏ khi hoàn thành
                        if (cursor) {
                            cursor.remove();
                        }
                        resolve(); // Hoàn thành Promise
                    }
                }
                
                type();
            });
        }

        /**
         * Chạy tuần tự các lời chúc và hiệu ứng icon.
         */
        async function runMidAutumnWishes() {
            // Hiển thị các icon trước
            document.getElementById('moon-icon').classList.remove('opacity-0');
            document.getElementById('lantern-left').classList.remove('opacity-0');
            document.getElementById('lantern-right').classList.remove('opacity-0');
            document.getElementById('rabbit-icon').classList.remove('opacity-0');
            
            // Chờ một chút để icon hiển thị
            await new Promise(r => setTimeout(r, 1500)); 

            // Chạy từng dòng chữ
            for (const msg of messages) {
                // Đảm bảo dòng cuối cùng có font lớn và đậm hơn
                const isLastLine = msg.id === 'line5';
                if (isLastLine) {
                    document.getElementById(msg.id).classList.remove('text-lg', 'md:text-xl', 'font-medium');
                    document.getElementById(msg.id).classList.add('text-xl', 'md:text-2xl', 'font-extrabold', 'text-yellow-400');
                }
                
                await slowPrint(msg.id, msg.text, msg.delay, msg.skipCursor);
                await new Promise(r => setTimeout(r, 800)); // Chờ giữa các dòng
            }
        }

        // Bắt đầu khi trang tải xong
        window.onload = runMidAutumnWishes;

    </script>
</body>
</html>
