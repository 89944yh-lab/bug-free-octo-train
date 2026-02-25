[index.html](https://github.com/user-attachments/files/25553061/index.html)
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>留学生办案合同审查避坑指南 | AI 智能增强版</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;700;900&display=swap');
        
        :root {
            --primary-blue: #2563EB;
            --warning-red: #EF4444;
            --safe-green: #10B981;
            --deep-navy: #1E293B;
        }

        body {
            font-family: 'Inter', 'Noto Sans SC', sans-serif;
            background-color: #F8FAFC;
        }

        .chart-container {
            position: relative;
            width: 100%;
            max-width: 650px;
            margin-left: auto;
            margin-right: auto;
            height: 350px;
            max-height: 400px;
        }

        .card {
            background: white;
            border-radius: 1rem;
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
        }

        .card:hover {
            transform: translateY(-5px);
        }

        .ai-glow {
            box-shadow: 0 0 20px rgba(37, 99, 235, 0.15);
            border: 1px solid rgba(37, 99, 235, 0.2);
        }

        .gradient-text {
            background: linear-gradient(90deg, #2563EB, #9333EA);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        #drop-zone.drag-over {
            background-color: rgba(37, 99, 235, 0.05);
            border-color: #2563EB;
        }
    </style>
</head>
<body class="text-slate-800">

    <header class="bg-[#1E293B] text-white py-16 px-6 text-center shadow-2xl relative overflow-hidden">
        <div class="max-w-4xl mx-auto relative z-10">
            <span class="bg-indigo-500 text-white text-xs font-bold px-3 py-1 rounded-full mb-4 inline-block">
                GEMINI 2.5 POWERED
            </span>
            <h1 class="text-4xl md:text-6xl font-black mb-6 leading-tight">
                留学生合同条款审查<br><span class="text-blue-400">AI 避坑智能助手</span>
            </h1>
            <p class="text-lg text-slate-300 mb-8">
                不仅是数据看板，更是你的私人法律顾问。支持拍照识别与智能话术生成。
            </p >
            <div class="flex flex-wrap justify-center gap-4">
                <button onclick="readIntro()" class="bg-slate-700 hover:bg-slate-600 text-white px-6 py-3 rounded-full font-bold transition-all flex items-center space-x-2">
                    <span>✨ 语音听取核心要点</span>
                </button>
                <a href=" " class="bg-blue-600 hover:bg-blue-500 text-white px-6 py-3 rounded-full font-bold transition-all flex items-center space-x-2">
                    <span>✨ 立即开始 AI 审计</span>
                </a >
            </div>
        </div>
    </header>

    <main class="max-w-7xl mx-auto px-4 py-12">
        
        <!-- AI Smart Auditor Section -->
        <section id="ai-section" class="card p-8 mb-12 ai-glow border-t-4 border-blue-600">
            <h2 class="text-2xl font-bold text-slate-900 mb-6 flex items-center">
                <span class="mr-2">✨</span> AI 智能风险审计与拍照识别
            </h2>
            
            <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 items-start">
                <div class="space-y-6">
                    <!-- Method 1: Text Input -->
                    <div>
                        <label class="block text-sm font-bold text-slate-700 mb-2">方式一：粘贴条款原文</label>
                        <textarea id="clauseInput" rows="4" class="w-full p-4 border rounded-xl bg-slate-50 focus:ring-2 focus:ring-blue-500 outline-none transition-all" placeholder="粘贴怀疑有问题的条款..."></textarea>
                    </div>

                    <!-- Method 2: Image Upload -->
                    <div>
                        <label class="block text-sm font-bold text-slate-700 mb-2">方式二：上传合同照片</label>
                        <div id="drop-zone" class="border-2 border-dashed border-slate-300 rounded-xl p-8 text-center hover:border-blue-400 transition-all cursor-pointer" onclick="document.getElementById('fileInput').click()">
                            <input type="file" id="fileInput" class="hidden" accept="image/*" onchange="handleImage(this.files[0])">
                            <p class="text-slate-500 text-sm">点击或拖拽照片到此处 (支持 JPG/PNG)</p >
                            <div id="imagePreview" class="mt-4 hidden">
                                < img src="" id="previewImg" class="max-h-40 mx-auto rounded shadow-md">
                            </div>
                        </div>
                    </div>

                    <button id="analyzeBtn" onclick="runAnalysis()" class="w-full bg-blue-600 hover:bg-blue-700 text-white font-bold py-4 px-8 rounded-xl transition-all shadow-lg hover:shadow-blue-200">
                        ✨ 启动 AI 深度审计
        
