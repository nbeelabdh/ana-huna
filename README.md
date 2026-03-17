<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>أنا هنا - Ana Huna</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Cairo:wght@400;700&display=swap');
        body { font-family: 'Cairo', sans-serif; background-color: #f0f2f5; }
        .chat-bg { background-image: url('https://user-images.githubusercontent.com/15075759/28719144-86dc0f70-73b1-11e7-911d-60d70fcded21.png'); }
        .tab-active { border-bottom: 3px solid #128c7e; color: #128c7e; }
        .glass { background: rgba(255, 255, 255, 0.9); backdrop-filter: blur(10px); }
    </style>
</head>
<body class="h-screen flex flex-col overflow-hidden">

    <!-- Header -->
    <header class="bg-[#075E54] text-white p-4 shadow-lg flex justify-between items-center z-50">
        <h1 class="text-xl font-bold">أنا هنا</h1>
        <div class="flex space-x-4 space-x-reverse">
            <button onclick="showSection('profile')"><i class="fas fa-user-circle text-2xl"></i></button>
            <button><i class="fas fa-search text-xl"></i></button>
            <button class="relative">
                <i class="fas fa-ellipsis-v text-xl"></i>
            </button>
        </div>
    </header>

    <!-- Navigation Tabs -->
    <nav class="bg-white shadow flex justify-around text-gray-500 font-bold z-40">
        <button onclick="showSection('nearby')" id="tab-nearby" class="py-3 px-2 flex-1 tab-active"><i class="fas fa-map-marker-alt ml-2"></i>القريبين</button>
        <button onclick="showSection('chats')" id="tab-chats" class="py-3 px-2 flex-1"><i class="fas fa-comment ml-2"></i>دردشة</button>
        <button onclick="showSection('status')" id="tab-status" class="py-3 px-2 flex-1"><i class="fas fa-circle-notch ml-2"></i>حالات</button>
        <button onclick="showSection('calls')" id="tab-calls" class="py-3 px-2 flex-1"><i class="fas fa-phone ml-2"></i>مكالمات</button>
    </nav>

    <!-- Main Content Area -->
    <main class="flex-1 overflow-y-auto pb-20">
        
        <!-- Nearby Section -->
        <section id="section-nearby" class="p-4 space-y-4">
            <div class="bg-blue-100 p-4 rounded-xl flex items-center justify-between">
                <div>
                    <h3 class="font-bold text-blue-800">رادار القريبين نشط</h3>
                    <p class="text-sm text-blue-600">يتم عرض الأشخاص والمنشآت في نطاق 5 كم</p>
                </div>
                <button onclick="alert('جاري تحديث الموقع...')" class="bg-blue-500 text-white p-2 rounded-full"><i class="fas fa-sync"></i></button>
            </div>

            <div class="flex space-x-2 space-x-reverse overflow-x-auto pb-2">
                <button class="bg-white border rounded-full px-4 py-1 whitespace-nowrap active:bg-green-100">الكل</button>
                <button class="bg-white border rounded-full px-4 py-1 whitespace-nowrap">أشخاص</button>
                <button class="bg-white border rounded-full px-4 py-1 whitespace-nowrap">منشآت</button>
                <button class="bg-white border rounded-full px-4 py-1 whitespace-nowrap">مجموعات</button>
            </div>

            <div class="space-y-3">
                <!-- Nearby Item -->
                <div class="bg-white p-3 rounded-xl shadow-sm flex items-center justify-between">
                    <div class="flex items-center">
                        <div class="w-12 h-12 bg-gray-300 rounded-full flex items-center justify-center text-xl font-bold text-white">ن</div>
                        <div class="mr-3">
                            <h4 class="font-bold">نبيل (أنت)</h4>
                            <p class="text-xs text-green-500 font-bold">نشط الآن</p>
                        </div>
                    </div>
                    <span class="text-xs text-gray-400">0 كم</span>
                </div>

                <div class="bg-white p-3 rounded-xl shadow-sm flex items-center justify-between border-r-4 border-orange-500">
                    <div class="flex items-center">
                        <div class="w-12 h-12 bg-orange-100 rounded-lg flex items-center justify-center text-orange-600 text-xl"><i class="fas fa-store"></i></div>
                        <div class="mr-3">
                            <h4 class="font-bold">سوبر ماركت الأمانة</h4>
                            <p class="text-xs text-gray-500">منشأة تجارية • مفتوح</p>
                        </div>
                    </div>
                    <span class="text-xs text-gray-400">400 م</span>
                </div>
            </div>
        </section>

        <!-- Chats Section -->
        <section id="section-chats" class="hidden">
            <div class="divide-y">
                <div onclick="openChat('أحمد')" class="flex items-center p-4 bg-white hover:bg-gray-50 cursor-pointer">
                    <img src="https://ui-avatars.com/api/?name=Ahmed&background=random" class="w-14 h-14 rounded-full">
                    <div class="mr-4 flex-1">
                        <div class="flex justify-between">
                            <h4 class="font-bold">أحمد</h4>
                            <span class="text-xs text-gray-400">10:30 ص</span>
                        </div>
                        <p class="text-sm text-gray-500 truncate">هل أرسلت لي موقع المنشأة؟</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Profile Section -->
        <section id="section-profile" class="hidden p-6 text-center">
            <div class="relative inline-block">
                <img src="https://ui-avatars.com/api/?name=Nabeel&size=128" class="w-32 h-32 rounded-full border-4 border-white shadow">
                <button class="absolute bottom-0 left-0 bg-green-500 text-white p-2 rounded-full"><i class="fas fa-camera"></i></button>
            </div>
            <h2 class="text-2xl font-bold mt-4">نبيل</h2>
            <p class="text-gray-500">مرحباً! أنا أستخدم "أنا هنا"</p>
            <div class="mt-8 space-y-4 text-right">
                <button onclick="changeBg()" class="w-full bg-white p-4 rounded-xl shadow-sm flex items-center">
                    <i class="fas fa-image text-blue-500 ml-4"></i>
                    تغيير خلفية المحادثة
                </button>
                <button class="w-full bg-white p-4 rounded-xl shadow-sm flex items-center">
                    <i class="fas fa-lock text-red-500 ml-4"></i>
                    إعدادات الخصوصية (تشفير)
                </button>
            </div>
        </section>

    </main>

    <!-- Floating Buttons -->
    <div class="fixed bottom-24 left-6 flex flex-col space-y-3">
        <button onclick="showCreateGroup()" class="bg-[#128c7e] text-white w-14 h-14 rounded-full shadow-xl flex items-center justify-center">
            <i class="fas fa-users"></i>
        </button>
        <button onclick="showAddEntity()" class="bg-orange-500 text-white w-14 h-14 rounded-full shadow-xl flex items-center justify-center">
            <i class="fas fa-plus-square"></i>
        </button>
    </div>

    <!-- Chat Window (Overlay) -->
    <div id="chat-window" class="fixed inset-0 bg-white z-[100] hidden flex flex-col">
        <header class="bg-[#075E54] text-white p-4 flex items-center">
            <button onclick="closeChat()" class="ml-4 text-xl"><i class="fas fa-arrow-right"></i></button>
            <img id="chat-avatar" src="" class="w-10 h-10 rounded-full ml-3">
            <div class="flex-1">
                <h4 id="chat-name" class="font-bold">اسم الشخص</h4>
                <p class="text-xs opacity-75">نشط الآن</p>
            </div>
            <div class="flex space-x-4 space-x-reverse">
                <button onclick="startCall('video')"><i class="fas fa-video"></i></button>
                <button onclick="startCall('voice')"><i class="fas fa-phone"></i></button>
            </div>
        </header>
        <div id="chat-content" class="flex-1 p-4 overflow-y-auto chat-bg space-y-4">
            <!-- Messages go here -->
            <div class="flex justify-end">
                <div class="bg-[#dcf8c6] p-3 rounded-lg shadow-sm max-w-[80%] text-sm">
                    مرحباً نبيل، كيف حالك؟ 
                    <span class="block text-[10px] text-gray-400 text-left">10:30 ص</span>
                </div>
            </div>
        </div>
        <footer class="p-2 bg-gray-100 flex items-center space-x-2 space-x-reverse">
            <button class="text-gray-500 text-xl px-2"><i class="far fa-smile"></i></button>
            <input type="text" placeholder="اكتب رسالة..." class="flex-1 p-2 rounded-full border focus:outline-none">
            <button onclick="alert('جاري تسجيل الصوت...')" class="text-gray-500 text-xl px-2"><i class="fas fa-microphone text-green-600"></i></button>
            <button onclick="alert('إرسال الموقع...')" class="text-gray-500 text-xl px-2"><i class="fas fa-map-marker-alt text-red-500"></i></button>
        </footer>
    </div>

    <!-- Modals -->
    <div id="modal" class="fixed inset-0 bg-black bg-opacity-50 z-[200] hidden flex items-center justify-center p-6">
        <div class="bg-white rounded-2xl w-full max-w-sm p-6 space-y-4">
            <h3 id="modal-title" class="text-xl font-bold">عنوان</h3>
            <div id="modal-body"></div>
            <div class="flex justify-end space-x-2 space-x-reverse">
                <button onclick="closeModal()" class="px-4 py-2 text-gray-500">إلغاء</button>
                <button onclick="confirmModal()" id="modal-confirm" class="px-4 py-2 bg-green-500 text-white rounded-lg">تأكيد</button>
            </div>
        </div>
    </div>

    <!-- Call Screen -->
    <div id="call-screen" class="fixed inset-0 bg-[#075E54] z-[300] hidden flex flex-col items-center justify-center text-white">
        <div class="text-center animate-pulse">
            <img id="call-avatar" src="" class="w-32 h-32 rounded-full border-4 border-white/20 mb-6">
            <h2 id="call-name" class="text-3xl font-bold">اسم المتصل</h2>
            <p class="text-lg opacity-70 mt-2">جاري الاتصال...</p>
        </div>
        <div class="absolute bottom-20 flex space-x-8 space-x-reverse">
            <button class="bg-white/20 p-5 rounded-full"><i class="fas fa-microphone-slash text-2xl"></i></button>
            <button onclick="endCall()" class="bg-red-500 p-6 rounded-full shadow-2xl"><i class="fas fa-phone-slash text-3xl"></i></button>
            <button class="bg-white/20 p-5 rounded-full"><i class="fas fa-video-slash text-2xl"></i></button>
        </div>
    </div>

    <script>
        function showSection(id) {
            document.querySelectorAll('main section').forEach(s => s.classList.add('hidden'));
            document.getElementById('section-' + id).classList.remove('hidden');
            
            document.querySelectorAll('nav button').forEach(b => b.classList.remove('tab-active'));
            document.getElementById('tab-' + id)?.classList.add('tab-active');
        }

        function openChat(name) {
            document.getElementById('chat-name').innerText = name;
            document.getElementById('chat-avatar').src = "https://ui-avatars.com/api/?name=" + name + "&background=random";
            document.getElementById('chat-window').classList.remove('hidden');
        }

        function closeChat() {
            document.getElementById('chat-window').classList.add('hidden');
        }

        function showAddEntity() {
            document.getElementById('modal-title').innerText = "إضافة منشأة جديدة";
            document.getElementById('modal-body').innerHTML = `
                <input type="text" placeholder="اسم المنشأة" class="w-full border p-3 rounded-lg mb-3">
                <select class="w-full border p-3 rounded-lg mb-3">
                    <option>مطعم</option>
                    <option>محل تجاري</option>
                    <option>مكتب خدمات</option>
                </select>
                <p class="text-xs text-gray-400">سيتم استخدام موقعك الحالي كعنوان للمنشأة</p>
            `;
            document.getElementById('modal').classList.remove('hidden');
        }

        function showCreateGroup() {
            document.getElementById('modal-title').innerText = "إنشاء مجموعة جديدة";
            document.getElementById('modal-body').innerHTML = `
                <input type="text" placeholder="اسم المجموعة" class="w-full border p-3 rounded-lg mb-3">
                <div class="flex items-center text-sm text-gray-500">
                    <input type="checkbox" class="ml-2"> مجموعة عامة (تظهر في القريبين)
                </div>
            `;
            document.getElementById('modal').classList.remove('hidden');
        }

        function closeModal() {
            document.getElementById('modal').classList.add('hidden');
        }

        function confirmModal() {
            alert('تم تنفيذ العملية بنجاح وسيتم المزامنة مع قاعدة البيانات');
            closeModal();
        }

        function startCall(type) {
            const name = document.getElementById('chat-name').innerText;
            document.getElementById('call-name').innerText = name;
            document.getElementById('call-avatar').src = document.getElementById('chat-avatar').src;
            document.getElementById('call-screen').classList.remove('hidden');
        }

        function endCall() {
            document.getElementById('call-screen').classList.add('hidden');
        }

        function changeBg() {
            const color = prompt("أدخل كود اللون المفضل (مثلاً: #ffe4e1)");
            if(color) {
                document.getElementById('chat-content').style.backgroundImage = 'none';
                document.getElementById('chat-content').style.backgroundColor = color;
                alert('تم تغيير خلفية المحادثة بنجاح');
            }
        }
    </script>
</body>
</html>
