<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AI 自然奇景图鉴</title>
    <style>
        /* 全局样式 */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        body {
            background-color: #f0f4f8;
            color: #2d3748;
            line-height: 1.6;
        }
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* 头部样式 */
        header {
            background: linear-gradient(135deg, #4299e1, #38b2ac);
            color: white;
            padding: 40px 0;
            text-align: center;
            box-shadow: 0 4px 12px rgba(0,0,0,0.1);
        }
        header h1 {
            font-size: 2.8rem;
            margin-bottom: 15px;
            text-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }
        header p {
            font-size: 1.2rem;
            opacity: 0.9;
            max-width: 800px;
            margin: 0 auto;
        }

        /* 导航栏样式 */
        nav {
            background-color: white;
            padding: 15px 0;
            box-shadow: 0 2px 8px rgba(0,0,0,0.05);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        nav ul {
            list-style: none;
            display: flex;
            justify-content: center;
            gap: 30px;
        }
        nav a {
            color: #4a5568;
            text-decoration: none;
            font-weight: 500;
            font-size: 1.1rem;
            padding: 8px 12px;
            border-radius: 6px;
            transition: all 0.3s ease;
        }
        nav a:hover {
            background-color: #e8f4f8;
            color: #4299e1;
        }

        /* 主体内容样式 */
        .main-content {
            padding: 60px 0;
        }
        .section-title {
            text-align: center;
            font-size: 2rem;
            color: #2d3748;
            margin-bottom: 40px;
            position: relative;
        }
        .section-title::after {
            content: '';
            display: block;
            width: 80px;
            height: 4px;
            background-color: #4299e1;
            margin: 15px auto;
            border-radius: 2px;
        }

        /* 奇景卡片样式 */
        .gallery {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
            margin-bottom: 80px;
        }
        .card {
            background-color: white;
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 6px 16px rgba(0,0,0,0.08);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        .card:hover {
            transform: translateY(-8px);
            box-shadow: 0 12px 24px rgba(0,0,0,0.12);
        }
        .card-img {
            width: 100%;
            height: 250px;
            object-fit: cover;
            border-bottom: 1px solid #f0f0f0;
        }
        .card-content {
            padding: 25px;
        }
        .card-title {
            font-size: 1.5rem;
            color: #2d3748;
            margin-bottom: 12px;
        }
        .card-desc {
            color: #4a5568;
            margin-bottom: 20px;
            line-height: 1.7;
        }
        .card-tag {
            display: inline-block;
            background-color: #e8f4f8;
            color: #4299e1;
            padding: 6px 12px;
            border-radius: 20px;
            font-size: 0.9rem;
            margin-right: 8px;
            margin-bottom: 8px;
        }

        /* 生成说明样式 */
        .generation-process {
            background-color: white;
            border-radius: 12px;
            padding: 40px;
            box-shadow: 0 6px 16px rgba(0,0,0,0.08);
            margin-bottom: 80px;
        }
        .process-step {
            margin-bottom: 30px;
            padding-bottom: 30px;
            border-bottom: 1px solid #f0f0f0;
        }
        .process-step:last-child {
            border-bottom: none;
            margin-bottom: 0;
            padding-bottom: 0;
        }
        .step-number {
            display: inline-block;
            width: 36px;
            height: 36px;
            background-color: #4299e1;
            color: white;
            border-radius: 50%;
            text-align: center;
            line-height: 36px;
            font-weight: bold;
            margin-right: 15px;
            vertical-align: middle;
        }
        .step-title {
            display: inline-block;
            font-size: 1.3rem;
            color: #2d3748;
            vertical-align: middle;
        }
        .step-content {
            margin-top: 15px;
            margin-left: 51px;
            color: #4a5568;
        }

        /* 页脚样式 */
        footer {
            background-color: #2d3748;
            color: white;
            padding: 40px 0;
            text-align: center;
        }
        .footer-links {
            margin: 20px 0;
        }
        .footer-links a {
            color: #a0aec0;
            text-decoration: none;
            margin: 0 15px;
            transition: color 0.3s ease;
        }
        .footer-links a:hover {
            color: #4299e1;
        }
        .copyright {
            opacity: 0.7;
            font-size: 0.9rem;
        }

        /* 响应式调整 */
        @media (max-width: 768px) {
            header h1 {
                font-size: 2.2rem;
            }
            header p {
                font-size: 1rem;
            }
            nav ul {
                gap: 15px;
            }
            nav a {
                font-size: 1rem;
            }
            .section-title {
                font-size: 1.8rem;
            }
            .gallery {
                grid-template-columns: 1fr;
            }
            .generation-process {
                padding: 30px;
            }
            .step-title {
                font-size: 1.2rem;
            }
        }
    </style>
</head>
<body>
    <!-- 头部 -->
    <header>
        <div class="container">
            <h1>AI 自然奇景图鉴</h1>
            <p>探索由人工智能创造的、现实中不存在的绝美自然景观，感受科技与想象力的碰撞</p>
        </div>
    </header>

    <!-- 导航栏 -->
    <nav>
        <div class="container">
            <ul>
                <li><a href="#gallery">奇景画廊</a></li>
                <li><a href="#process">生成流程</a></li>
                <li><a href="#about">关于项目</a></li>
            </ul>
        </div>
    </nav>

    <!-- 主体内容 -->
    <main class="main-content">
        <div class="container">
            <!-- 奇景画廊 -->
            <section id="gallery">
                <h2 class="section-title">奇景画廊</h2>
                <div class="gallery">
                    <!-- 卡片1：悬浮森林 -->
                    <div class="card">
                        <img src="https://picsum.photos/id/1036/800/500" alt="悬浮森林" class="card-img">
                        <div class="card-content">
                            <h3 class="card-title">悬浮森林</h3>
                            <p class="card-desc">这片森林生长在漂浮于云层之上的巨型岩石上，树木的根系裸露在外，缠绕成金色的网络，吸收空气中的水汽与阳光。每当微风拂过，树叶会发出风铃般的声响，地面覆盖着发光的苔藓，夜晚如同星河坠落。</p>
                            <span class="card-tag">AI 生成</span>
                            <span class="card-tag">空中景观</span>
                            <span class="card-tag">奇幻风格</span>
                        </div>
                    </div>

                    <!-- 卡片2：水晶湖泊 -->
                    <div class="card">
                        <img src="https://picsum.photos/id/1025/800/500" alt="水晶湖泊" class="card-img">
                        <div class="card-content">
                            <h3 class="card-title">水晶湖泊</h3>
                            <p class="card-desc">湖泊的湖水由液态水晶构成，清澈透明到能看清湖底千米处的矿物结晶。湖岸环绕着冰蓝色的悬崖，阳光照射时，湖面会折射出七彩光晕，湖边生长着能发出柔和蓝光的水生植物，吸引着虚构的荧光鱼类穿梭其间。</p>
                            <span class="card-tag">AI 生成</span>
                            <span class="card-tag">水域景观</span>
                            <span class="card-tag">梦幻风格</span>
                        </div>
                    </div>

                    <!-- 卡片3：彩虹峡谷 -->
                    <div class="card">
                        <img src="https://picsum.photos/id/1015/800/500" alt="彩虹峡谷" class="card-img">
                        <div class="card-content">
                            <h3 class="card-title">彩虹峡谷</h3>
                            <p class="card-desc">峡谷的岩壁由多层彩色矿物构成，从红、橙、黄到绿、蓝、紫渐变分布，如同大自然的调色盘。峡谷底部流淌着温热的溪流，水汽蒸发形成的薄雾在阳光照射下形成双重彩虹，岩壁上栖息着能模仿鸟鸣的发光昆虫。</p>
                            <span class="card-tag">AI 生成</span>
                            <span class="card-tag">山地景观</span>
                            <span class="card-tag">绚丽风格</span>
                        </div>
                    </div>

                    <!-- 卡片4：星尘沙漠 -->
                    <div class="card">
                        <img src="https://picsum.photos/id/1049/800/500" alt="星尘沙漠" class="card-img">
                        <div class="card-content">
                            <h3 class="card-title">星尘沙漠</h3>
                            <p class="card-desc">沙漠的沙粒并非普通黄沙，而是由微小的星尘结晶组成，白天呈现出柔和的淡紫色，夜晚则会发出微弱的银光，如同整片沙漠都在闪烁。沙漠中矗立着巨大的岩石柱，表面刻有天然形成的几何纹路，远处的沙丘轮廓如同海浪般起伏。</p>
                            <span class="card-tag">AI 生成</span>
                            <span class="card-tag">沙漠景观</span>
                            <span class="card-tag">神秘风格</span>
                        </div>
                    </div>

                    <!-- 卡片5：云海瀑布 -->
                    <div class="card">
                        <img src="https://picsum.photos/id/1039/800/500" alt="云海瀑布" class="card-img">
                        <div class="card-content">
                            <h3 class="card-title">云海瀑布</h3>
                            <p class="card-desc">瀑布并非水流，而是由浓密的云层构成，从万丈悬崖顶端倾泻而下，形成白色的云瀑。云瀑下方是无尽的云海，偶尔有山峰露出顶端，如同海中孤岛。阳光穿透云层时，会形成巨大的光柱，照亮整个天空。</p>
                            <span class="card-tag">AI 生成</span>
                            <span class="card-tag">气象景观</span>
                            <span class="card-tag">壮阔风格</span>
                        </div>
                    </div>

                    <!-- 卡片6：荧光洞穴 -->
                    <div class="card">
                        <img src="https://picsum.photos/id/1059/800/500" alt="荧光洞穴" class="card-img">
                        <div class="card-content">
                            <h3 class="card-title">荧光洞穴</h3>
                            <p class="card-desc">洞穴内部布满了能发出荧光的钟乳石和石笋，颜色从青色、绿色到紫色渐变，照亮了整个洞穴。洞穴底部有一片地下湖，湖水倒映着荧光，形成对称的绝美景观。洞穴中还生长着罕见的地下植物，花瓣能随着声音的频率变换颜色。</p>
                            <span class="card-tag">AI 生成</span>
                            <span class="card-tag">洞穴景观</span>
                            <span class="card-tag">静谧风格</span>
                        </div>
                    </div>
                </div>
            </section>

            <!-- 生成流程 -->
            <section id="process" class="generation-process">
                <h2 class="section-title">AI 生成流程</h2>
                <div class="process-step">
                    <span class="step-number">1</span>
                    <h3 class="step-title">主题构思与 Prompt 设计</h3>
                    <div class="step-content">
                        <p>通过 ChatGPT  brainstorm 虚构自然景观主题，确定“悬浮森林”“水晶湖泊”等6个核心方向，同时设计详细 Prompt，明确景观元素、色彩风格、氛围感受（如“悬浮森林：云层上的岩石森林，金色根系，发光苔藓，奇幻风格，高清细节”）。</p>
                    </div>
                </div>
                <div class="process-step">
                    <span class="step-number">2</span>
                    <h3 class="step-title">景观图片生成</h3>
                    <div class="step-content">
                        <p>将设计好的 Prompt 输入 MidJourney，生成初始图片，针对不满意的细节（如色彩饱和度、元素比例）反馈给 AI 进行调整（如“增加悬浮岩石的体积感，降低苔藓发光强度”），反复迭代3-5次得到最终景观图。</p>
                    </div>
                </div>
                <div class="process-step">
                    <span class="step-number">3</span>
                    <h3 class="step-title">网站结构与文案生成</h3>
                    <div class="step-content">
                        <p>让 ChatGPT 设计网站结构（首页、画廊、生成流程、关于项目），并根据每个景观的特点生成描述文案，要求兼具画面感和想象力。同时否定了 AI 最初提出的“纯图片展示”方案，增加了“生成流程”板块，提升网站信息密度。</p>
                    </div>
                </div>
                <div class="process-step">
                    <span class="step-number">4</span>
                    <h3 class="step-title">HTML + CSS 代码生成与优化</h3>
                    <div class="step-content">
                        <p>向 CodeLlama 输入网站结构需求，生成基础 HTML 框架和 CSS 样式，随后反馈优化意见（如“增加卡片hover动画”“优化响应式布局”“调整配色为蓝绿色系，贴合自然主题”），AI 多次修正后得到最终代码。</p>
                    </div>
                </div>
                <div class="process-step">
                    <span class="step-number">5</span>
                    <h3 class="step-title">部署与问题修复</h3>
                    <div class="step-content">
                        <p>将代码导入 GitHub Desktop，推送至 GitHub 仓库并开启 GitHub Pages 功能。初始部署后出现图片加载缓慢问题，让 AI 提供解决方案，采用 Picsum Photos 占位图（实际可替换为 MidJourney 生成图的在线链接），修复加载问题。</p>
                    </div>
                </div>
            </section>

            <!-- 关于项目 -->
            <section id="about">
                <h2 class="section-title">关于项目</h2>
                <div class="generation-process">
                    <p style="margin-bottom: 20px; color: #4a5568;">本项目是“AI-Built Website”期末作业的成果，核心是完全以 AI 为主体搭建网站，人类仅作为指挥者、编辑者和审稿人。</p>
                    <p style="margin-bottom: 20px; color: #4a5568;">网站不追求“实用性”，而是聚焦于“AI 创造力的展示”—— 通过虚构自然景观这一主题，探索 AI 在创意设计、内容生成、代码编写等方面的能力边界。</p>
                    <p style="color: #4a5568;">所有景观图片（示例中用 Picsum 占位）、文案描述、网站代码均由 AI 生成，人类仅进行方向引导、方案筛选和细节优化。</p>
                </div>
            </section>
        </div>
    </main>

    <!-- 页脚 -->
    <footer>
        <div class="container">
            <h3>AI 自然奇景图鉴</h3>
            <div class="footer-links">
                <a href="#gallery">奇景画廊</a>
                <a href="#process">生成流程</a>
                <a href="#about">关于项目</a>
            </div>
            <p class="copyright">© 2026 AI-Built Website 期末作业 | 由 AI 生成 + 人类指挥完成</p>
        </div>
    </footer>
</body>
</html>
