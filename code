<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>海外实施月度例会 - 店小秘报告系统</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        brand: {
                            blue: '#0066FF',
                            navy: '#1E293B',
                            lightBg: '#F8FAFC',
                            cardBg: '#FFFFFF',
                            border: '#E2E8F0',
                            accent: '#0284C7'
                        }
                    },
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                    }
                }
            }
        }
    </script>
    <style>
        body {
            background-color: #F8FAFC;
            color: #1E293B;
            font-family: 'Inter', sans-serif;
        }
        ::-webkit-scrollbar {
            width: 6px;
            height: 6px;
        }
        ::-webkit-scrollbar-track {
            background: #F1F5F9;
        }
        ::-webkit-scrollbar-thumb {
            background: #CBD5E1;
            border-radius: 3px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #94A3B8;
        }
        
        @media print {
            .no-print {
                display: none !important;
            }
            body {
                background-color: #ffffff !important;
                color: #000000 !important;
            }
            .print-container {
                background: white !important;
                color: black !important;
                box-shadow: none !important;
                border: none !important;
                width: 100% !important;
            }
            .print-card {
                background: white !important;
                border: 1px solid #d1d5db !important;
                color: black !important;
                box-shadow: none !important;
            }
            .print-table th {
                background-color: #f3f4f6 !important;
                color: #111827 !important;
            }
            .print-table td, .print-table th {
                border-color: #d1d5db !important;
                color: #111827 !important;
            }
        }
    </style>
</head>
<body class="min-h-screen flex flex-col justify-between">

    <!-- Top Header -->
    <header class="bg-white border-b border-slate-200 sticky top-0 z-50 shadow-sm no-print">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-16">
                <!-- Brand & Logo -->
                <div class="flex items-center space-x-4">
                    <div class="bg-brand-blue/10 p-2 rounded-xl border border-brand-blue/20 flex items-center justify-center">
                        <i class="fa-solid fa-robot text-brand-blue text-2xl"></i>
                    </div>
                    <div>
                        <div class="flex items-center space-x-2">
                            <span class="text-xl font-bold tracking-wide text-slate-900">店小秘</span>
                            <span class="text-xs px-2 py-0.5 bg-brand-blue/10 text-brand-blue border border-brand-blue/30 rounded-full font-semibold">ERP Cross-Border</span>
                        </div>
                        <p class="text-xs text-slate-500">海外实施月度例会系统</p>
                    </div>
                </div>

                <!-- Meta Details & Actions -->
                <div class="flex items-center space-x-4">
                    <div class="hidden md:flex items-center space-x-6 text-sm border-r border-slate-200 pr-6">
                        <div class="flex items-center space-x-2">
                            <i class="fa-solid fa-earth-asia text-slate-400"></i>
                            <span class="text-slate-500">区域：</span>
                            <span class="font-semibold text-slate-800 bg-slate-100 px-2.5 py-1 rounded border border-slate-200">越南</span>
                        </div>
                        <div class="flex items-center space-x-2">
                            <i class="fa-solid fa-user-tie text-slate-400"></i>
                            <span class="text-slate-500">汇报人：</span>
                            <span class="font-semibold text-slate-800 bg-slate-100 px-2.5 py-1 rounded border border-slate-200">阮红云</span>
                        </div>
                    </div>

                    <!-- Action Buttons -->
                    <div class="flex items-center space-x-2">
                        <button onclick="saveToLocalStorage()" class="px-3 py-2 bg-slate-100 hover:bg-slate-200 text-slate-700 rounded-lg text-sm font-medium transition flex items-center space-x-1.5 border border-slate-300" title="暂存至浏览器">
                            <i class="fa-solid fa-floppy-disk text-emerald-600"></i>
                            <span class="hidden sm:inline">保存</span>
                        </button>
                        <button onclick="exportDataJSON()" class="px-3 py-2 bg-slate-100 hover:bg-slate-200 text-slate-700 rounded-lg text-sm font-medium transition flex items-center space-x-1.5 border border-slate-300" title="导出 JSON 数据文件">
                            <i class="fa-solid fa-download text-blue-600"></i>
                            <span class="hidden sm:inline">导出 JSON</span>
                        </button>
                        <label class="px-3 py-2 bg-slate-100 hover:bg-slate-200 text-slate-700 rounded-lg text-sm font-medium transition flex items-center space-x-1.5 border border-slate-300 cursor-pointer" title="从 JSON 文件导入数据">
                            <i class="fa-solid fa-upload text-amber-600"></i>
                            <span class="hidden sm:inline">导入 JSON</span>
                            <input type="file" id="importFileInput" class="hidden" accept=".json" onchange="importDataJSON(event)">
                        </label>
                        <button onclick="window.print()" class="px-3.5 py-2 bg-brand-blue hover:bg-blue-700 text-white font-medium rounded-lg text-sm transition flex items-center space-x-1.5 shadow-md shadow-brand-blue/20">
                            <i class="fa-solid fa-print"></i>
                            <span>打印 / 导出 PDF</span>
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </header>

    <!-- Main Content Area -->
    <main class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-6 flex-grow w-full">
        
        <!-- Tab Navigation Bar -->
        <div class="flex flex-wrap items-center justify-between border-b border-slate-200 mb-6 gap-2 no-print">
            <nav class="flex space-x-2 overflow-x-auto pb-2 scrollbar-none" id="tabNav">
                <button onclick="switchTab('tab1')" id="btn-tab1" class="tab-btn px-4 py-2.5 rounded-t-lg font-semibold text-sm transition flex items-center space-x-2 bg-brand-blue text-white border-b-2 border-brand-blue shadow-sm">
                    <i class="fa-solid fa-chart-line"></i>
                    <span>1. 绩效目标进展</span>
                </button>
                <button onclick="switchTab('tab2')" id="btn-tab2" class="tab-btn px-4 py-2.5 rounded-t-lg font-medium text-sm transition flex items-center space-x-2 text-slate-600 hover:text-slate-900 hover:bg-slate-100">
                    <i class="fa-solid fa-users"></i>
                    <span>2. 客户跟进情况</span>
                </button>
                <button onclick="switchTab('tab3')" id="btn-tab3" class="tab-btn px-4 py-2.5 rounded-t-lg font-medium text-sm transition flex items-center space-x-2 text-slate-600 hover:text-slate-900 hover:bg-slate-100">
                    <i class="fa-solid fa-list-check"></i>
                    <span>3. 下月重点工作</span>
                </button>
                <button onclick="switchTab('tab4')" id="btn-tab4" class="tab-btn px-4 py-2.5 rounded-t-lg font-medium text-sm transition flex items-center space-x-2 text-slate-600 hover:text-slate-900 hover:bg-slate-100">
                    <i class="fa-solid fa-triangle-exclamation"></i>
                    <span>4. 卡点/异常问题</span>
                </button>
            </nav>

            <button onclick="toggleReferenceModal()" class="text-xs px-3 py-1.5 bg-white hover:bg-slate-50 text-brand-blue border border-brand-blue/40 rounded-lg font-semibold mb-2 transition flex items-center space-x-1.5 shadow-sm">
                <i class="fa-solid fa-book-open"></i>
                <span>查看 KPI 标准参考</span>
            </button>
        </div>

        <!-- Print Title Section (Only Visible when Printing) -->
        <div class="hidden print:block mb-6 border-b-2 border-slate-900 pb-4">
            <div class="flex justify-between items-center">
                <div>
                    <h1 class="text-2xl font-bold text-slate-900">店小秘 - 海外实施月度例会报告</h1>
                    <p class="text-sm text-slate-600 mt-1">Dianxiaomi ERP Overseas Implementation Monthly Report</p>
                </div>
                <div class="text-right text-sm text-slate-800">
                    <p><strong>区域：</strong> 越南</p>
                    <p><strong>汇报人：</strong> 阮红云</p>
                    <p><strong>报告导出日期：</strong> <span id="printDate"></span></p>
                </div>
            </div>
        </div>

        <!-- ==================== TAB 1: 绩效目标进展 ==================== -->
        <div id="tab1" class="tab-content space-y-6">
            <!-- KPI Table Card -->
            <div class="bg-white rounded-xl p-6 border border-slate-200 shadow-sm print-card">
                <div class="flex flex-col sm:flex-row sm:items-center justify-between gap-4 mb-4">
                    <div>
                        <h2 class="text-lg font-bold text-slate-900 flex items-center space-x-2">
                            <span class="w-2.5 h-6 bg-brand-blue rounded-full inline-block"></span>
                            <span>1. 绩效目标达成情况</span>
                        </h2>
                        <p class="text-xs text-slate-500 mt-1">对照 KPI 指标，明确目标值、实际完成值并说明偏差原因。</p>
                    </div>
                    <button onclick="addKpiRow()" class="no-print px-3 py-1.5 bg-brand-blue/10 hover:bg-brand-blue/20 text-brand-blue border border-brand-blue/30 rounded-lg text-xs font-semibold transition flex items-center space-x-1.5 self-start sm:self-auto">
                        <i class="fa-solid fa-plus"></i>
                        <span>添加 KPI 指标</span>
                    </button>
                </div>

                <div class="overflow-x-auto border border-slate-200 rounded-lg">
                    <table class="w-full text-sm text-left text-slate-700 print-table">
                        <thead class="text-xs text-slate-700 uppercase bg-slate-50 border-b border-slate-200 font-bold">
                            <tr>
                                <th scope="col" class="px-3 py-3 min-w-[160px]">指标名称</th>
                                <th scope="col" class="px-3 py-3 w-28">目标值</th>
                                <th scope="col" class="px-3 py-3 w-28">实际完成值</th>
                                <th scope="col" class="px-3 py-3 w-28">达成率 (%)</th>
                                <th scope="col" class="px-3 py-3 min-w-[200px]">偏差说明 / 改进动作</th>
                                <th scope="col" class="px-2 py-3 w-12 text-center no-print">操作</th>
                            </tr>
                        </thead>
                        <tbody id="kpiTableBody" class="divide-y divide-slate-200 bg-white">
                            <!-- Rows injected via JS -->
                        </tbody>
                    </table>
                </div>

                <!-- KPI Summary Box -->
                <div class="mt-5 pt-4 border-t border-slate-200">
                    <label class="block text-xs font-semibold text-slate-800 mb-2 flex items-center space-x-1">
                        <i class="fa-solid fa-pen-to-square text-brand-blue"></i>
                        <span>达成情况小结（亮点 / 未达标原因）：</span>
                    </label>
                    <textarea id="kpiSummary" rows="3" class="w-full p-3 bg-slate-50 border border-slate-300 rounded-lg text-sm text-slate-800 focus:ring-1 focus:ring-brand-blue focus:border-brand-blue focus:outline-none focus:bg-white" placeholder="请填写：本月核心亮点、未达标原因及后续改进计划..."></textarea>
                </div>
            </div>
        </div>

        <!-- ==================== TAB 2: 客户跟进情况 ==================== -->
        <div id="tab2" class="tab-content space-y-6 hidden">
            <div class="bg-white rounded-xl p-6 border border-slate-200 shadow-sm print-card">
                <div class="flex flex-col sm:flex-row sm:items-center justify-between gap-4 mb-4">
                    <div>
                        <h2 class="text-lg font-bold text-slate-900 flex items-center space-x-2">
                            <span class="w-2.5 h-6 bg-brand-blue rounded-full inline-block"></span>
                            <span>2. 客户跟进情况</span>
                        </h2>
                        <p class="text-xs text-slate-500 mt-1">围绕客户画像、最新动态及付费转化机会展开。</p>
                    </div>
                    <button onclick="addCustomerRow()" class="no-print px-3 py-1.5 bg-brand-blue/10 hover:bg-brand-blue/20 text-brand-blue border border-brand-blue/30 rounded-lg text-xs font-semibold transition flex items-center space-x-1.5 self-start sm:self-auto">
                        <i class="fa-solid fa-plus"></i>
                        <span>添加客户</span>
                    </button>
                </div>

                <div class="overflow-x-auto border border-slate-200 rounded-lg">
                    <table class="w-full text-sm text-left text-slate-700 print-table">
                        <thead class="text-xs text-slate-700 uppercase bg-slate-50 border-b border-slate-200 font-bold">
                            <tr>
                                <th scope="col" class="px-3 py-3 min-w-[140px]">客户名称</th>
                                <th scope="col" class="px-3 py-3 min-w-[180px]">客户画像</th>
                                <th scope="col" class="px-3 py-3 min-w-[200px]">最新动态</th>
                                <th scope="col" class="px-3 py-3 min-w-[200px]">付费转化机会点</th>
                                <th scope="col" class="px-2 py-3 w-12 text-center no-print">操作</th>
                            </tr>
                        </thead>
                        <tbody id="customerTableBody" class="divide-y divide-slate-200 bg-white">
                            <!-- Rows injected via JS -->
                        </tbody>
                    </table>
                </div>

                <!-- Customer Summary Box -->
                <div class="mt-5 pt-4 border-t border-slate-200">
                    <label class="block text-xs font-semibold text-slate-800 mb-2 flex items-center space-x-1">
                        <i class="fa-solid fa-pen-to-square text-brand-blue"></i>
                        <span>关键动态与转化机会小结：</span>
                    </label>
                    <textarea id="customerSummary" rows="3" class="w-full p-3 bg-slate-50 border border-slate-300 rounded-lg text-sm text-slate-800 focus:ring-1 focus:ring-brand-blue focus:border-brand-blue focus:outline-none focus:bg-white" placeholder="小结：本月重点客户、存在风险的客户群、潜在变现挖掘点..."></textarea>
                </div>
            </div>
        </div>

        <!-- ==================== TAB 3: 下月重点工作 ==================== -->
        <div id="tab3" class="tab-content space-y-6 hidden">
            <div class="bg-white rounded-xl p-6 border border-slate-200 shadow-sm print-card">
                <div class="flex flex-col sm:flex-row sm:items-center justify-between gap-4 mb-4">
                    <div>
                        <h2 class="text-lg font-bold text-slate-900 flex items-center space-x-2">
                            <span class="w-2.5 h-6 bg-brand-blue rounded-full inline-block"></span>
                            <span>3. 下月重点工作计划</span>
                        </h2>
                        <p class="text-xs text-slate-500 mt-1">聚焦可交付、可衡量的重点工作，明确优先级与所需支持。</p>
                    </div>
                    <button onclick="addTaskRow()" class="no-print px-3 py-1.5 bg-brand-blue/10 hover:bg-brand-blue/20 text-brand-blue border border-brand-blue/30 rounded-lg text-xs font-semibold transition flex items-center space-x-1.5 self-start sm:self-auto">
                        <i class="fa-solid fa-plus"></i>
                        <span>添加工作项</span>
                    </button>
                </div>

                <div class="overflow-x-auto border border-slate-200 rounded-lg">
                    <table class="w-full text-sm text-left text-slate-700 print-table">
                        <thead class="text-xs text-slate-700 uppercase bg-slate-50 border-b border-slate-200 font-bold">
                            <tr>
                                <th scope="col" class="px-3 py-3 min-w-[220px]">重点工作说明</th>
                                <th scope="col" class="px-3 py-3 min-w-[200px]">目标 / 交付物</th>
                                <th scope="col" class="px-3 py-3 min-w-[200px]">需求支持/协同</th>
                                <th scope="col" class="px-2 py-3 w-12 text-center no-print">操作</th>
                            </tr>
                        </thead>
                        <tbody id="taskTableBody" class="divide-y divide-slate-200 bg-white">
                            <!-- Rows injected via JS -->
                        </tbody>
                    </table>
                </div>
            </div>
        </div>

        <!-- ==================== TAB 4: 卡点 / 异常问题 ==================== -->
        <div id="tab4" class="tab-content space-y-6 hidden">
            <div class="bg-white rounded-xl p-6 border border-slate-200 shadow-sm print-card">
                <div class="flex flex-col sm:flex-row sm:items-center justify-between gap-4 mb-4">
                    <div>
                        <h2 class="text-lg font-bold text-slate-900 flex items-center space-x-2">
                            <span class="w-2.5 h-6 bg-brand-blue rounded-full inline-block"></span>
                            <span>4. 卡点 / 异常问题讨论</span>
                        </h2>
                        <p class="text-xs text-slate-500 mt-1">记录业务、客户、系统及工作体验方面的异常问题。</p>
                    </div>
                    <button onclick="addIssueRow()" class="no-print px-3 py-1.5 bg-brand-blue/10 hover:bg-brand-blue/20 text-brand-blue border border-brand-blue/30 rounded-lg text-xs font-semibold transition flex items-center space-x-1.5 self-start sm:self-auto">
                        <i class="fa-solid fa-plus"></i>
                        <span>添加问题</span>
                    </button>
                </div>

                <div class="overflow-x-auto border border-slate-200 rounded-lg">
                    <table class="w-full text-sm text-left text-slate-700 print-table">
                        <thead class="text-xs text-slate-700 uppercase bg-slate-50 border-b border-slate-200 font-bold">
                            <tr>
                                <th scope="col" class="px-3 py-3 w-36">问题分类</th>
                                <th scope="col" class="px-3 py-3 min-w-[200px]">问题描述</th>
                                <th scope="col" class="px-3 py-3 min-w-[200px]">影响与已尝试措施</th>
                                <th scope="col" class="px-3 py-3 min-w-[200px]">需协调/支持事项</th>
                                <th scope="col" class="px-2 py-3 w-12 text-center no-print">操作</th>
                            </tr>
                        </thead>
                        <tbody id="issueTableBody" class="divide-y divide-slate-200 bg-white">
                            <!-- Rows injected via JS -->
                        </tbody>
                    </table>
                </div>
            </div>
        </div>

    </main>

    <!-- KPI Standard Reference Modal -->
    <div id="referenceModal" class="fixed inset-0 bg-slate-900/60 backdrop-blur-sm z-50 flex items-center justify-center p-4 hidden no-print">
        <div class="bg-white border border-slate-200 rounded-2xl max-w-4xl w-full max-h-[85vh] flex flex-col shadow-2xl">
            <!-- Modal Header -->
            <div class="p-4 border-b border-slate-200 flex items-center justify-between bg-slate-50 rounded-t-2xl">
                <div class="flex items-center space-x-2">
                    <i class="fa-solid fa-book-open text-brand-blue text-lg"></i>
                    <h3 class="text-base font-bold text-slate-900">KPI 数据参考标准</h3>
                </div>
                <button onclick="toggleReferenceModal()" class="text-slate-400 hover:text-slate-700 p-1 rounded-lg">
                    <i class="fa-solid fa-xmark text-xl"></i>
                </button>
            </div>
            
            <!-- Modal Body (Scrollable) -->
            <div class="p-6 overflow-y-auto space-y-6 text-xs text-slate-700">
                <!-- Implementation Role KPI -->
                <div>
                    <h4 class="text-sm font-bold text-brand-blue mb-3 flex items-center space-x-2">
                        <i class="fa-solid fa-user-gear"></i>
                        <span>实施岗 KPI</span>
                    </h4>
                    <div class="overflow-x-auto border border-slate-200 rounded-lg">
                        <table class="w-full text-left">
                            <thead class="bg-slate-100 text-slate-800 font-bold">
                                <tr>
                                    <th class="p-2 border-b border-slate-200">KPI指标</th>
                                    <th class="p-2 border-b border-slate-200">定义</th>
                                    <th class="p-2 border-b border-slate-200">衡量标准</th>
                                    <th class="p-2 border-b border-slate-200 w-16">权重</th>
                                </tr>
                            </thead>
                            <tbody class="divide-y divide-slate-200 bg-white">
                                <tr>
                                    <td class="p-2 font-semibold text-slate-900">演示目标</td>
                                    <td class="p-2">国内每日2个，海外每日1个</td>
                                    <td class="p-2">100%≤实际完成: 100分 | 85%-99%: 80分 | 70%-84%: 50分 | ≤69%: 0分<br><span class="text-red-600 font-medium">* 问卷回收低于60%或有差评：扣10分</span></td>
                                    <td class="p-2 text-brand-blue font-bold">15%</td>
                                </tr>
                                <tr>
                                    <td class="p-2 font-semibold text-slate-900">日活转化率目标</td>
                                    <td class="p-2">完成 DAU 转化率目标</td>
                                    <td class="p-2">东南亚、巴西: ≥30%: 100分 | 25-29%: 85分 | 20-24%: 70分 | ≤19%: 55分<br>其他区域: ≥20%: 100分 | 15-19%: 85分 | 10-14%: 55分 | ≤9%: 0分<br><span class="text-red-600 font-medium">* 若服务流程问题导致客户拒绝付费，最高扣10分</span></td>
                                    <td class="p-2 text-brand-blue font-bold">20%</td>
                                </tr>
                                <tr>
                                    <td class="p-2 font-semibold text-slate-900">售后跟进</td>
                                    <td class="p-2">SA客户：1份/月；其他：1份/季度（S: 至尊/尊享, A: 旗舰）</td>
                                    <td class="p-2">按时完成数量: 100分 | 缺3次: 80分 | 缺3-5次: 60分 | 缺≥6次: 0分<br><span class="text-red-600 font-medium">* 若出现客户流失（Churn），每流失1家扣30分</span></td>
                                    <td class="p-2 text-brand-blue font-bold">35%</td>
                                </tr>
                                <tr>
                                    <td class="p-2 font-semibold text-slate-900">学习提效</td>
                                    <td class="p-2">X + Y（X: 考试平均分，Y: 文档及培训完成度，Q: QA反馈）</td>
                                    <td class="p-2">X: 均分≥96 (50分) | 90-95 (40分) | 80-89 (30分) | ≤79 (20分)<br>Y: 按时完成 (50分)，延迟1次 (30分)，延迟≥2次 (20分)<br>Q: 按时达标 Q=10，延迟/错误2次 Q=8，多次延迟 Q=0-5</td>
                                    <td class="p-2 text-brand-blue font-bold">20%</td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                </div>

                <!-- Customer Support Role KPI -->
                <div>
                    <h4 class="text-sm font-bold text-brand-blue mb-3 flex items-center space-x-2">
                        <i class="fa-solid fa-headset"></i>
                        <span>售后岗 KPI</span>
                    </h4>
                    <div class="overflow-x-auto border border-slate-200 rounded-lg">
                        <table class="w-full text-left">
                            <thead class="bg-slate-100 text-slate-800 font-bold">
                                <tr>
                                    <th class="p-2 border-b border-slate-200">KPI指标</th>
                                    <th class="p-2 border-b border-slate-200">定义</th>
                                    <th class="p-2 border-b border-slate-200">衡量标准</th>
                                    <th class="p-2 border-b border-slate-200 w-16">权重</th>
                                </tr>
                            </thead>
                            <tbody class="divide-y divide-slate-200 bg-white">
                                <tr>
                                    <td class="p-2 font-semibold text-slate-900">响应效率1</td>
                                    <td class="p-2">首次响应（X*60% + Y*40%）<br>X: 平均时长，Y: 天数 >90s</td>
                                    <td class="p-2">X: ≤90s (10分) | 91-120s (8分) | ≥121s (4分)<br>Y: 0天 (10分) | 1-6天 (8分) | ≥7天 (4分)</td>
                                    <td class="p-2 text-brand-blue font-bold">10%</td>
                                </tr>
                                <tr>
                                    <td class="p-2 font-semibold text-slate-900">响应效率2</td>
                                    <td class="p-2">服务过程（X*70% + Y*30%）<br>X: 日均在线时长，Y: 远程协助次数</td>
                                    <td class="p-2">X: ≥8h (10分) | 7.3-7.9h (8分) | 6.9-7.2h (6分) | ≤6.8h (4分)<br>Y: ≥36次 (10分) | 20-35 (8分) | 10-19 (5分) | 4-9 (3分) | ≤3 (0分)<br><span class="text-red-600 font-medium">* 付费客户排队超过5分钟且人数>5人：总分扣20%</span></td>
                                    <td class="p-2 text-brand-blue font-bold">25%</td>
                                </tr>
                                <tr>
                                    <td class="p-2 font-semibold text-slate-900">回复质量</td>
                                    <td class="p-2">高效解决问题质量度</td>
                                    <td class="p-2">满分10分。每次违规扣1分：<br>1. 未能准确理解客户需求<br>2. 争议/争执超过1小时未给出解决方案<br>3. 未查阅历史记录强求客户重新解释<br>4. 当天未闭环反馈问题</td>
                                    <td class="p-2 text-brand-blue font-bold">25%</td>
                                </tr>
                                <tr>
                                    <td class="p-2 font-semibold text-slate-900">学习提效</td>
                                    <td class="p-2">X*50% + Q*40% + Y*10%<br>X: 考试，Y: 更新文档，Q: 每周 QA</td>
                                    <td class="p-2">X: ≥96 (10分) | 88-95 (8分) | 80-87 (7分) | ≤79 (5分)<br>Y: 无错误 (10分) | 1-2次错误 (6分) | ≥3次错误 (0分)<br>Q: 按时达标 Q=10，不达标/多次延迟 Q=0-8</td>
                                    <td class="p-2 text-brand-blue font-bold">30%</td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                </div>
            </div>

            <!-- Modal Footer -->
            <div class="p-4 border-t border-slate-200 bg-slate-50 flex justify-end rounded-b-2xl">
                <button onclick="toggleReferenceModal()" class="px-4 py-2 bg-slate-800 hover:bg-slate-900 text-white rounded-lg text-xs font-semibold">
                    关闭
                </button>
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer class="bg-white border-t border-slate-200 py-4 no-print mt-auto">
        <div class="max-w-7xl mx-auto px-4 text-center text-xs text-slate-500">
            <p>© 店小秘 海外实施月度例会系统 | 免费跨境电商 ERP</p>
        </div>
    </footer>

    <!-- Notification Toast -->
    <div id="toast" class="fixed bottom-5 right-5 bg-slate-900 text-white px-4 py-3 rounded-xl shadow-2xl flex items-center space-x-2 transition-opacity duration-300 opacity-0 pointer-events-none z-50">
        <i class="fa-solid fa-circle-check text-emerald-400"></i>
        <span id="toastMsg" class="text-sm font-medium">保存成功！</span>
    </div>

    <script>
        // Sample Initial Data (Pure Chinese)
        const initialData = {
            kpiList: [
                { name: '演示目标', target: '100%', actual: '95%', rate: 95, desc: '达到越南市场演示目标的 95%。' },
                { name: '日活转化率', target: '30%', actual: '28%', rate: 93.3, desc: '东南亚区域需在下阶段加速推进。' },
                { name: '售后跟进', target: '100%', actual: '100%', rate: 100, desc: '已按时完成 SA/A 级客户定期回访报告。' },
                { name: '学习提效', target: '95分', actual: '96分', rate: 101, desc: '已完成内部培训及指导文档编写。' }
            ],
            kpiSummary: '本月团队在 SA 重点客户服务指标上表现良好，日活转化率在深入演示环节仍需加强。',
            customerList: [
                { name: '客户 A (Shopee 大卖家)', profile: '大卖家 / 多渠道仓储对接需求', status: '已安装试用 ERP，反馈良好', chance: '预计 11 月转化尊享版 (12,000,000 VND)' },
                { name: '店铺 B (Lazada 品牌商)', profile: '服装主理人 / 订单管理需求', status: '需协助配置自动打印面单', chance: '预计下周升级旗舰版' }
            ],
            customerSummary: '重点客户 A 进展非常顺利，需集中力量解决店铺 B 遗留的服务工单。',
            taskList: [
                { title: '优化 VIP 客户 Onboarding 流程', target: '指导周期由 3 天缩短至 1 天', support: '需技术团队支持 API 仓库对接' },
                { title: '组织新功能线上研讨会 (Webinar)', target: '至少 50 家企业参会', support: '越南市场团队协助宣传推广' }
            ],
            issueList: [
                { category: '系统', desc: '高峰期（20点-22点）大批量同步订单网络卡顿', impact: '客户反馈稍慢，已提交技术排查', support: '需开发优化服务器带宽与并发' },
                { category: '业务', desc: '新税收政策导致客户需要增加发票字段', impact: '目前临时人工指导处理', support: '需系统更新标准发票模板' }
            ]
        };

        let appData = JSON.parse(localStorage.getItem('dianxiaomi_report_data')) || initialData;

        // Initialize App on DOM Load
        window.onload = function() {
            document.getElementById('printDate').innerText = new Date().toLocaleDateString('zh-CN');
            renderAll();
        };

        // Render All Sections
        function renderAll() {
            renderKPI();
            renderCustomers();
            renderTasks();
            renderIssues();
        }

        // Tab Switcher
        function switchTab(tabId) {
            document.querySelectorAll('.tab-content').forEach(el => el.classList.add('hidden'));
            document.getElementById(tabId).classList.remove('hidden');

            document.querySelectorAll('.tab-btn').forEach(btn => {
                btn.classList.remove('bg-brand-blue', 'text-white', 'border-b-2', 'border-brand-blue', 'shadow-sm');
                btn.classList.add('text-slate-600', 'hover:text-slate-900', 'hover:bg-slate-100');
            });

            const activeBtn = document.getElementById('btn-' + tabId);
            activeBtn.classList.remove('text-slate-600', 'hover:text-slate-900', 'hover:bg-slate-100');
            activeBtn.classList.add('bg-brand-blue', 'text-white', 'border-b-2', 'border-brand-blue', 'shadow-sm');
        }

        // Reference Modal Toggle
        function toggleReferenceModal() {
            const modal = document.getElementById('referenceModal');
            modal.classList.toggle('hidden');
        }

        // ==================== KPI FUNCTIONS ====================
        function renderKPI() {
            const tbody = document.getElementById('kpiTableBody');
            tbody.innerHTML = '';
            appData.kpiList.forEach((item, index) => {
                const tr = document.createElement('tr');
                tr.className = "hover:bg-slate-50 transition";
                tr.innerHTML = `
                    <td class="p-2"><input type="text" value="${escapeHtml(item.name)}" onchange="updateKPI(${index}, 'name', this.value)" class="w-full bg-slate-50 border border-slate-300 rounded px-2.5 py-1.5 text-xs text-slate-800 focus:bg-white focus:border-brand-blue focus:outline-none print:bg-transparent print:border-none"></td>
                    <td class="p-2"><input type="text" value="${escapeHtml(item.target)}" onchange="updateKPI(${index}, 'target', this.value)" class="w-full bg-slate-50 border border-slate-300 rounded px-2.5 py-1.5 text-xs text-slate-800 focus:bg-white focus:border-brand-blue focus:outline-none print:bg-transparent print:border-none"></td>
                    <td class="p-2"><input type="text" value="${escapeHtml(item.actual)}" onchange="updateKPI(${index}, 'actual', this.value)" class="w-full bg-slate-50 border border-slate-300 rounded px-2.5 py-1.5 text-xs text-slate-800 focus:bg-white focus:border-brand-blue focus:outline-none print:bg-transparent print:border-none"></td>
                    <td class="p-2"><input type="number" value="${item.rate}" onchange="updateKPI(${index}, 'rate', this.value)" class="w-full bg-slate-50 border border-slate-300 rounded px-2.5 py-1.5 text-xs text-brand-blue font-bold focus:bg-white focus:border-brand-blue focus:outline-none print:bg-transparent print:border-none"></td>
                    <td class="p-2"><input type="text" value="${escapeHtml(item.desc)}" onchange="updateKPI(${index}, 'desc', this.value)" class="w-full bg-slate-50 border border-slate-300 rounded px-2.5 py-1.5 text-xs text-slate-800 focus:bg-white focus:border-brand-blue focus:outline-none print:bg-transparent print:border-none"></td>
                    <td class="p-2 text-center no-print"><button onclick="removeKPI(${index})" class="text-red-500 hover:text-red-700 p-1" title="删除"><i class="fa-solid fa-trash-can"></i></button></td>
                `;
                tbody.appendChild(tr);
            });
            document.getElementById('kpiSummary').value = appData.kpiSummary || '';
            document.getElementById('kpiSummary').onchange = (e) => appData.kpiSummary = e.target.value;
        }

        function addKpiRow() {
            appData.kpiList.push({ name: '', target: '', actual: '', rate: 100, desc: '' });
            renderKPI();
        }

        function updateKPI(index, field, value) {
            appData.kpiList[index][field] = field === 'rate' ? parseFloat(value) || 0 : value;
        }

        function removeKPI(index) {
            appData.kpiList.splice(index, 1);
            renderKPI();
        }

        // ==================== CUSTOMER FUNCTIONS ====================
        function renderCustomers() {
            const tbody = document.getElementById('customerTableBody');
            tbody.innerHTML = '';
            appData.customerList.forEach((item, index) => {
                const tr = document.createElement('tr');
                tr.className = "hover:bg-slate-50 transition";
                tr.innerHTML = `
                    <td class="p-2"><input type="text" value="${escapeHtml(item.name)}" onchange="updateCustomer(${index}, 'name', this.value)" class="w-full bg-slate-50 border border-slate-300 rounded px-2.5 py-1.5 text-xs text-slate-800 focus:bg-white focus:border-brand-blue focus:outline-none print:bg-transparent print:border-none"></td>
                    <td class="p-2"><input type="text" value="${escapeHtml(item.profile)}" onchange="updateCustomer(${index}, 'profile', this.value)" class="w-full bg-slate-50 border border-slate-300 rounded px-2.5 py-1.5 text-xs text-slate-800 focus:bg-white focus:border-brand-blue focus:outline-none print:bg-transparent print:border-none"></td>
                    <td class="p-2"><input type="text" value="${escapeHtml(item.status)}" onchange="updateCustomer(${index}, 'status', this.value)" class="w-full bg-slate-50 border border-slate-300 rounded px-2.5 py-1.5 text-xs text-slate-800 focus:bg-white focus:border-brand-blue focus:outline-none print:bg-transparent print:border-none"></td>
                    <td class="p-2"><input type="text" value="${escapeHtml(item.chance)}" onchange="updateCustomer(${index}, 'chance', this.value)" class="w-full bg-slate-50 border border-slate-300 rounded px-2.5 py-1.5 text-xs text-slate-800 focus:bg-white focus:border-brand-blue focus:outline-none print:bg-transparent print:border-none"></td>
                    <td class="p-2 text-center no-print"><button onclick="removeCustomer(${index})" class="text-red-500 hover:text-red-700 p-1" title="删除"><i class="fa-solid fa-trash-can"></i></button></td>
                `;
                tbody.appendChild(tr);
            });
            document.getElementById('customerSummary').value = appData.customerSummary || '';
            document.getElementById('customerSummary').onchange = (e) => appData.customerSummary = e.target.value;
        }

        function addCustomerRow() {
            appData.customerList.push({ name: '', profile: '', status: '', chance: '' });
            renderCustomers();
        }

        function updateCustomer(index, field, value) {
            appData.customerList[index][field] = value;
        }

        function removeCustomer(index) {
            appData.customerList.splice(index, 1);
            renderCustomers();
        }

        // ==================== TASK FUNCTIONS ====================
        function renderTasks() {
            const tbody = document.getElementById('taskTableBody');
            tbody.innerHTML = '';
            appData.taskList.forEach((item, index) => {
                const tr = document.createElement('tr');
                tr.className = "hover:bg-slate-50 transition";
                tr.innerHTML = `
                    <td class="p-2"><input type="text" value="${escapeHtml(item.title)}" onchange="updateTask(${index}, 'title', this.value)" class="w-full bg-slate-50 border border-slate-300 rounded px-2.5 py-1.5 text-xs text-slate-800 focus:bg-white focus:border-brand-blue focus:outline-none print:bg-transparent print:border-none"></td>
                    <td class="p-2"><input type="text" value="${escapeHtml(item.target)}" onchange="updateTask(${index}, 'target', this.value)" class="w-full bg-slate-50 border border-slate-300 rounded px-2.5 py-1.5 text-xs text-slate-800 focus:bg-white focus:border-brand-blue focus:outline-none print:bg-transparent print:border-none"></td>
                    <td class="p-2"><input type="text" value="${escapeHtml(item.support)}" onchange="updateTask(${index}, 'support', this.value)" class="w-full bg-slate-50 border border-slate-300 rounded px-2.5 py-1.5 text-xs text-slate-800 focus:bg-white focus:border-brand-blue focus:outline-none print:bg-transparent print:border-none"></td>
                    <td class="p-2 text-center no-print"><button onclick="removeTask(${index})" class="text-red-500 hover:text-red-700 p-1" title="删除"><i class="fa-solid fa-trash-can"></i></button></td>
                `;
                tbody.appendChild(tr);
            });
        }

        function addTaskRow() {
            appData.taskList.push({ title: '', target: '', support: '' });
            renderTasks();
        }

        function updateTask(index, field, value) {
            appData.taskList[index][field] = value;
        }

        function removeTask(index) {
            appData.taskList.splice(index, 1);
            renderTasks();
        }

        // ==================== ISSUE FUNCTIONS ====================
        function renderIssues() {
            const tbody = document.getElementById('issueTableBody');
            tbody.innerHTML = '';
            appData.issueList.forEach((item, index) => {
                const tr = document.createElement('tr');
                tr.className = "hover:bg-slate-50 transition";
                tr.innerHTML = `
                    <td class="p-2">
                        <select onchange="updateIssue(${index}, 'category', this.value)" class="w-full bg-slate-50 border border-slate-300 rounded px-2 py-1.5 text-xs text-slate-800 focus:bg-white focus:border-brand-blue focus:outline-none print:bg-transparent print:border-none">
                            <option value="业务" ${item.category === '业务' ? 'selected' : ''}>业务</option>
                            <option value="客户" ${item.category === '客户' ? 'selected' : ''}>客户</option>
                            <option value="系统" ${item.category === '系统' ? 'selected' : ''}>系统</option>
                            <option value="体验" ${item.category === '体验' ? 'selected' : ''}>体验</option>
                        </select>
                    </td>
                    <td class="p-2"><input type="text" value="${escapeHtml(item.desc)}" onchange="updateIssue(${index}, 'desc', this.value)" class="w-full bg-slate-50 border border-slate-300 rounded px-2.5 py-1.5 text-xs text-slate-800 focus:bg-white focus:border-brand-blue focus:outline-none print:bg-transparent print:border-none"></td>
                    <td class="p-2"><input type="text" value="${escapeHtml(item.impact)}" onchange="updateIssue(${index}, 'impact', this.value)" class="w-full bg-slate-50 border border-slate-300 rounded px-2.5 py-1.5 text-xs text-slate-800 focus:bg-white focus:border-brand-blue focus:outline-none print:bg-transparent print:border-none"></td>
                    <td class="p-2"><input type="text" value="${escapeHtml(item.support)}" onchange="updateIssue(${index}, 'support', this.value)" class="w-full bg-slate-50 border border-slate-300 rounded px-2.5 py-1.5 text-xs text-slate-800 focus:bg-white focus:border-brand-blue focus:outline-none print:bg-transparent print:border-none"></td>
                    <td class="p-2 text-center no-print"><button onclick="removeIssue(${index})" class="text-red-500 hover:text-red-700 p-1" title="删除"><i class="fa-solid fa-trash-can"></i></button></td>
                `;
                tbody.appendChild(tr);
            });
        }

        function addIssueRow() {
            appData.issueList.push({ category: '系统', desc: '', impact: '', support: '' });
            renderIssues();
        }

        function updateIssue(index, field, value) {
            appData.issueList[index][field] = value;
        }

        function removeIssue(index) {
            appData.issueList.splice(index, 1);
            renderIssues();
        }

        // ==================== STORAGE & UTILS ====================
        function saveToLocalStorage() {
            localStorage.setItem('dianxiaomi_report_data', JSON.stringify(appData));
            showToast("已保存报告数据至浏览器！");
        }

        function exportDataJSON() {
            const dataStr = "data:text/json;charset=utf-8," + encodeURIComponent(JSON.stringify(appData, null, 2));
            const downloadAnchor = document.createElement('a');
            downloadAnchor.setAttribute("href", dataStr);
            downloadAnchor.setAttribute("download", `Dianxiaomi_Report_Vietnam_${new Date().toISOString().slice(0,10)}.json`);
            document.body.appendChild(downloadAnchor);
            downloadAnchor.click();
            downloadAnchor.remove();
            showToast("已导出 JSON 报告文件！");
        }

        function importDataJSON(event) {
            const fileReader = new FileReader();
            fileReader.onload = function(e) {
                try {
                    const parsedData = JSON.parse(e.target.result);
                    appData = parsedData;
                    renderAll();
                    saveToLocalStorage();
                    showToast("数据导入成功！");
                } catch (err) {
                    showToast("JSON 文件格式不正确！");
                }
            };
            if(event.target.files[0]){
                fileReader.readAsText(event.target.files[0]);
            }
        }

        function showToast(message) {
            const toast = document.getElementById('toast');
            document.getElementById('toastMsg').innerText = message;
            toast.classList.remove('opacity-0', 'pointer-events-none');
            setTimeout(() => {
                toast.classList.add('opacity-0', 'pointer-events-none');
            }, 3000);
        }

        function escapeHtml(str) {
            if (!str) return '';
            return str.replace(/&/g, "&amp;").replace(/</g, "&lt;").replace(/>/g, "&gt;").replace(/"/g, "&quot;").replace(/'/g, "&#039;");
        }
    </script>
</body>
</html>