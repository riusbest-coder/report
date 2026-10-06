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
        
        /* Dynamic input sizing styles */
        .auto-size-input {
            min-width: 6ch;
            max-width: 100%;
            box-sizing: content-box;
        }

        .auto-size-textarea {
            overflow: hidden;
            resize: none;
        }

        /* Print styles: Allow all tabs to be visible in PDF / Print preview */
        @media print {
            .no-print {
                display: none !important;
            }
            body {
                background-color: #ffffff !important;
                color: #000000 !important;
            }
            .print-all-tabs .tab-content {
                display: block !important;
                margin-bottom: 2rem !important;
                page-break-inside: avoid;
            }
            .print-card {
                background: white !important;
                border: 1px solid #cbd5e1 !important;
                color: black !important;
                box-shadow: none !important;
                break-inside: avoid;
            }
            .print-table th {
                background-color: #f1f5f9 !important;
                color: #0f172a !important;
            }
            .print-table td, .print-table th {
                border-color: #cbd5e1 !important;
                color: #0f172a !important;
            }
            input, textarea, select {
                border: none !important;
                background: transparent !important;
                padding: 0 !important;
                resize: none !important;
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
                <div class="flex items-center space-x-3">
                    <div class="bg-brand-blue/10 p-2 rounded-xl border border-brand-blue/20 flex items-center justify-center shrink-0">
                        <i class="fa-solid fa-robot text-brand-blue text-2xl"></i>
                    </div>
                    <div>
                        <div class="flex items-center space-x-2">
                            <span class="text-xl font-bold tracking-wide text-slate-900">店小秘</span>
                        </div>
                        <p class="text-xs text-slate-500 hidden sm:block">海外实施月度例会系统</p>
                    </div>
                </div>

                <!-- Meta Details & Actions -->
                <div class="flex items-center space-x-3 sm:space-x-4">
                    <div class="hidden md:flex items-center space-x-4 text-xs lg
