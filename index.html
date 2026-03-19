<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GreenLog - 家庭菜園成育管理アプリ</title>
    <!-- Scripts -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/lucide/0.263.0/umd/lucide.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/3.9.1/chart.min.js"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@400;500;700&display=swap');
        body {
            font-family: 'Noto Sans JP', sans-serif;
            background-color: #f8faf8;
            user-select: none;
            -webkit-tap-highlight-color: transparent;
        }
        .safe-area-bottom {
            padding-bottom: calc(env(safe-area-inset-bottom) + 5rem);
        }
        .custom-shadow {
            box-shadow: 0 4px 20px -2px rgba(0, 0, 0, 0.05);
        }
        .modal-overlay {
            background: rgba(0, 0, 0, 0.4);
            backdrop-filter: blur(4px);
        }
        /* Loading animation for icons */
        .lucide {
            visibility: hidden;
        }
        .lucide--rendered {
            visibility: visible;
        }
    </style>
</head>
<body class="safe-area-bottom">

    <!-- Header -->
    <header class="bg-white/80 backdrop-blur-md border-b border-gray-100 p-4 sticky top-0 z-40">
        <div class="container mx-auto flex justify-between items-center max-w-2xl">
            <h1 class="text-xl font-bold text-green-700 flex items-center gap-2">
                <i data-lucide="sprout"></i> GreenLog
            </h1>
            <button onclick="toggleModal('add-modal', true)" class="bg-green-600 text-white p-2 rounded-xl hover:bg-green-700 transition-colors shadow-sm">
                <i data-lucide="plus"></i>
            </button>
        </div>
    </header>

    <!-- Main Content -->
    <main class="container mx-auto p-4 max-w-2xl">
        
        <!-- Tab Navigation Content -->
        <div id="content-area">
            <!-- Dashboard Section (Default) -->
            <section id="dashboard-section" class="space-y-6">
                <div class="flex justify-between items-center">
                    <h2 class="text-lg font-bold text-gray-800">栽培中の野菜</h2>
                    <span id="veg-count" class="text-xs bg-gray-200 text-gray-600 px-2 py-1 rounded-full">0件</span>
                </div>

                <!-- Empty State -->
                <div id="empty-state" class="hidden text-center py-20">
                    <div class="bg-gray-100 w-20 h-20 rounded-full flex items-center justify-center mx-auto mb-4 text-gray-400">
                        <i data-lucide="shrub" class="w-10 h-10"></i>
                    </div>
                    <p class="text-gray-500">育てている野菜がありません。<br>右上の「＋」から追加しましょう！</p>
                </div>

                <!-- Vegetable Cards Container -->
                <div class="grid gap-4" id="veg-list">
                    <!-- Cards will be injected here by JS -->
                </div>
            </section>

            <!-- Stats Section (Hidden) -->
            <section id="stats-section" class="hidden space-y-6">
                <h2 class="text-xl font-bold text-gray-800">成長の記録</h2>
                <div class="bg-white p-6 rounded-3xl custom-shadow">
                    <p class="text-gray-500 text-sm mb-1">今シーズンの活動量</p>
                    <p class="text-3xl font-bold text-green-600 italic">Excellent!</p>
                    <div class="mt-6 h-64">
                        <canvas id="statsChart"></canvas>
                    </div>
                </div>
                <div class="grid grid-cols-2 gap-4">
                    <div class="bg-white p-4 rounded-2xl custom-shadow text-center">
                        <p class="text-xs text-gray-400">総栽培数</p>
                        <p id="total-stats" class="text-2xl font-bold">0</p>
                    </div>
                    <div class="bg-white p-4 rounded-2xl custom-shadow text-center">
                        <p class="text-xs text-gray-400">収穫済み</p>
                        <p class="text-2xl font-bold">0</p>
                    </div>
                </div>
            </section>
        </div>
    </main>

    <!-- Vegetable Detail Modal (Hidden) -->
    <div id="detail-modal" class="fixed inset-0 z-50 hidden">
        <div class="modal-overlay absolute inset-0" onclick="toggleModal('detail-modal', false)"></div>
        <div class="absolute bottom-0 left-0 right-0 bg-white rounded-t-[2.5rem] p-6 max-h-[90vh] overflow-y-auto transform transition-transform duration-300">
            <div class="w-12 h-1 bg-gray-200 rounded-full mx-auto mb-6"></div>
            <div id="detail-content">
                <!-- Content dynamic -->
            </div>
            <button onclick="deleteVegetable()" class="w-full mt-8 text-red-500 text-sm font-medium py-2">このデータを削除する</button>
        </div>
    </div>

    <!-- Add Vegetable Modal (Hidden) -->
    <div id="add-modal" class="fixed inset-0 z-50 hidden">
        <div class="modal-overlay absolute inset-0" onclick="toggleModal('add-modal', false)"></div>
        <div class="absolute bottom-0 left-0 right-0 bg-white rounded-t-[2.5rem] p-8 transform transition-transform duration-300">
            <h2 class="text-xl font-bold mb-6 text-center">新しい野菜を追加</h2>
            <form id="add-veg-form" class="space-y-4">
                <div>
                    <label class="block text-sm font-medium text-gray-700 mb-1">野菜の名前</label>
                    <input type="text" id="veg-name" placeholder="例: ミニトマト" required class="w-full px-4 py-3 bg-gray-50 border border-gray-200 rounded-xl focus:outline-none focus:ring-2 focus:ring-green-500">
                </div>
                <div>
                    <label class="block text-sm font-medium text-gray-700 mb-1">アイコン（絵文字）</label>
                    <input type="text" id="veg-emoji" placeholder="例: 🍅" required class="w-full px-4 py-3 bg-gray-50 border border-gray-200 rounded-xl focus:outline-none focus:ring-2 focus:ring-green-500">
                </div>
                <div>
                    <label class="block text-sm font-medium text-gray-700 mb-1">開始日</label>
                    <input type="date" id="veg-date" required class="w-full px-4 py-3 bg-gray-50 border border-gray-200 rounded-xl focus:outline-none focus:ring-2 focus:ring-green-500">
                </div>
                <button type="submit" class="w-full bg-green-600 text-white py-4 rounded-2xl font-bold shadow-lg mt-4 active:scale-95 transition-transform">
                    栽培をスタート
                </button>
            </form>
        </div>
    </div>

    <!-- Bottom Navigation -->
    <nav class="fixed bottom-0 left-0 right-0 bg-white/90 backdrop-blur-lg border-t border-gray-100 py-3 px-10 z-40">
        <div class="container mx-auto flex justify-around items-center max-w-md">
            <button onclick="switchTab('dashboard')" id="nav-dashboard" class="flex flex-col items-center text-green-600">
                <i data-lucide="layout-grid"></i>
                <span class="text-[10px] mt-1 font-medium">栽培中</span>
            </button>
            <button onclick="switchTab('stats')" id="nav-stats" class="flex flex-col items-center text-gray-400">
                <i data-lucide="line-chart"></i>
                <span class="text-[10px] mt-1 font-medium">統計</span>
            </button>
        </div>
    </nav>

    <!-- Toast Notification -->
    <div id="toast" class="fixed top-20 left-1/2 transform -translate-x-1/2 bg-black/80 text-white px-6 py-3 rounded-full text-sm hidden z-[100] transition-opacity">
        保存しました
    </div>

    <script>
        // --- State Management ---
        let vegetables = JSON.parse(localStorage.getItem('greenlog_vegs')) || [];
        let selectedVegId = null;

        // --- Icon Helper ---
        function refreshIcons() {
            if (window.lucide) {
                window.lucide.createIcons();
                // Add class to reveal icons once rendered
                document.querySelectorAll('.lucide').forEach(icon => icon.classList.add('lucide--rendered'));
            }
        }

        // --- Initialization ---
        window.addEventListener('DOMContentLoaded', () => {
            refreshIcons();
            renderVegList();
            initChart();
            // Default date to today
            const dateInput = document.getElementById('veg-date');
            if (dateInput) dateInput.valueAsDate = new Date();
        });

        // Backup initialization in case DOMContentLoaded fired too early
        window.onload = () => {
            refreshIcons();
        };

        // --- UI Logic ---
        function switchTab(tab) {
            const dashboard = document.getElementById('dashboard-section');
            const stats = document.getElementById('stats-section');
            const navDash = document.getElementById('nav-dashboard');
            const navStats = document.getElementById('nav-stats');

            if (tab === 'dashboard') {
                dashboard.classList.remove('hidden');
                stats.classList.add('hidden');
                navDash.classList.add('text-green-600');
                navDash.classList.remove('text-gray-400');
                navStats.classList.add('text-gray-400');
                navStats.classList.remove('text-green-600');
            } else {
                dashboard.classList.add('hidden');
                stats.classList.remove('hidden');
                navStats.classList.add('text-green-600');
                navStats.classList.remove('text-gray-400');
                navDash.classList.add('text-gray-400');
                navDash.classList.remove('text-green-600');
                updateStats();
            }
            refreshIcons();
        }

        function toggleModal(id, show) {
            const modal = document.getElementById(id);
            if (!modal) return;
            if (show) {
                modal.classList.remove('hidden');
            } else {
                modal.classList.add('hidden');
            }
            refreshIcons();
        }

        // --- CRUD Logic ---
        const addForm = document.getElementById('add-veg-form');
        if (addForm) {
            addForm.addEventListener('submit', (e) => {
                e.preventDefault();
                const newVeg = {
                    id: Date.now(),
                    name: document.getElementById('veg-name').value,
                    emoji: document.getElementById('veg-emoji').value,
                    startDate: document.getElementById('veg-date').value,
                    logs: []
                };
                vegetables.push(newVeg);
                saveData();
                renderVegList();
                toggleModal('add-modal', false);
                addForm.reset();
                showToast('新しい野菜を追加しました！');
            });
        }

        function renderVegList() {
            const list = document.getElementById('veg-list');
            const empty = document.getElementById('empty-state');
            const countEl = document.getElementById('veg-count');
            
            if (!list) return;
            list.innerHTML = '';
            countEl.innerText = `${vegetables.length}件`;

            if (vegetables.length === 0) {
                empty.classList.remove('hidden');
                return;
            }
            empty.classList.add('hidden');

            vegetables.forEach(veg => {
                const days = Math.floor((new Date() - new Date(veg.startDate)) / (1000 * 60 * 60 * 24));
                const card = document.createElement('div');
                card.className = 'veg-card bg-white p-4 rounded-2xl custom-shadow cursor-pointer flex items-center gap-4 active:scale-[0.98] transition-all';
                card.onclick = () => openDetail(veg.id);
                card.innerHTML = `
                    <div class="w-16 h-16 bg-green-50 rounded-2xl flex items-center justify-center text-3xl shadow-inner">${veg.emoji}</div>
                    <div class="flex-1">
                        <h3 class="font-bold text-gray-800">${veg.name}</h3>
                        <p class="text-xs text-gray-400 mt-1">${veg.startDate} 開始 (${days}日目)</p>
                        <div class="w-full bg-gray-100 rounded-full h-1.5 mt-3">
                            <div class="bg-green-500 h-1.5 rounded-full" style="width: ${Math.min(days * 2, 100)}%"></div>
                        </div>
                    </div>
                    <i data-lucide="chevron-right" class="text-gray-300 w-5"></i>
                `;
                list.appendChild(card);
            });
            refreshIcons();
        }

        function openDetail(id) {
            selectedVegId = id;
            const veg = vegetables.find(v => v.id === id);
            if (!veg) return;
            const days = Math.floor((new Date() - new Date(veg.startDate)) / (1000 * 60 * 60 * 24));
            
            const detailContent = document.getElementById('detail-content');
            detailContent.innerHTML = `
                <div class="text-center mb-8">
                    <div class="text-7xl mb-4 drop-shadow-sm">${veg.emoji}</div>
                    <h2 class="text-2xl font-bold text-gray-800">${veg.name}</h2>
                    <p class="text-gray-400 text-sm mt-1">${veg.startDate} に栽培開始</p>
                    <div class="inline-block mt-4 px-6 py-2 bg-green-50 text-green-700 rounded-full text-sm font-bold">
                        栽培 ${days} 日目
                    </div>
                </div>
                
                <div class="grid grid-cols-2 gap-4 mb-8">
                    <div class="bg-blue-50/50 p-4 rounded-2xl border border-blue-100">
                        <div class="flex items-center gap-2 text-blue-600 mb-1">
                            <i data-lucide="droplets" class="w-4 h-4"></i>
                            <span class="text-xs font-bold uppercase">水やり</span>
                        </div>
                        <p class="text-lg font-bold text-blue-900 italic">Today OK</p>
                    </div>
                    <div class="bg-orange-50/50 p-4 rounded-2xl border border-orange-100">
                        <div class="flex items-center gap-2 text-orange-600 mb-1">
                            <i data-lucide="sun" class="w-4 h-4"></i>
                            <span class="text-xs font-bold uppercase">日光</span>
                        </div>
                        <p class="text-lg font-bold text-orange-900 italic">Good</p>
                    </div>
                </div>

                <div class="space-y-4">
                    <h3 class="font-bold text-gray-800 flex items-center gap-2">
                        <i data-lucide="file-text" class="w-4 h-4 text-green-600"></i> 成育ログ
                    </h3>
                    <div class="bg-gray-50 rounded-2xl p-4 text-sm text-gray-500 text-center py-8">
                        まだログがありません。日々の成長を記録しましょう。
                    </div>
                    <button onclick="showToast('ログ機能は開発中です！')" class="w-full bg-white border-2 border-green-600 text-green-600 py-3 rounded-xl font-bold flex items-center justify-center gap-2">
                        <i data-lucide="edit-3" class="w-4 h-4"></i> 記録を書く
                    </button>
                </div>
            `;
            
            toggleModal('detail-modal', true);
            refreshIcons();
        }

        function deleteVegetable() {
            if (!confirm('本当に削除しますか？')) return;
            vegetables = vegetables.filter(v => v.id !== selectedVegId);
            saveData();
            renderVegList();
            toggleModal('detail-modal', false);
            showToast('削除しました');
        }

        function saveData() {
            localStorage.setItem('greenlog_vegs', JSON.stringify(vegetables));
        }

        function showToast(msg) {
            const toast = document.getElementById('toast');
            if (!toast) return;
            toast.innerText = msg;
            toast.classList.remove('hidden');
            toast.style.opacity = '1';
            setTimeout(() => {
                toast.style.opacity = '0';
                setTimeout(() => toast.classList.add('hidden'), 300);
            }, 2000);
        }

        // --- Charts ---
        function initChart() {
            const canvas = document.getElementById('statsChart');
            if (!canvas) return;
            const ctx = canvas.getContext('2d');
            new Chart(ctx, {
                type: 'line',
                data: {
                    labels: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun'],
                    datasets: [{
                        label: '活動指数',
                        data: [2, 5, 3, 8, 12, 15],
                        borderColor: '#10b981',
                        backgroundColor: 'rgba(16, 185, 129, 0.1)',
                        tension: 0.4,
                        fill: true,
                        pointRadius: 0
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: { legend: { display: false } },
                    scales: {
                        x: { display: false },
                        y: { display: false }
                    }
                }
            });
        }

        function updateStats() {
            const statEl = document.getElementById('total-stats');
            if (statEl) statEl.innerText = vegetables.length;
        }

    </script>
</body>
</html>