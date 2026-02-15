<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>抖音同频聊 - 告别AI树洞，找真人说真心话</title>
    <!-- 抖音官方字体适配 -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+SC:wght@400;500;700;900&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            /* 抖音官方核心色值 */
            --douyin-black: #000000;
            --douyin-red: #FE2C55;
            --douyin-cyan: #25F4EE;
            --douyin-white: #FFFFFF;
            --douyin-gray: #8A8A8A;
            --douyin-dark-gray: #161616;
            /* 抖音经典渐变 */
            --douyin-gradient: linear-gradient(90deg, var(--douyin-red), var(--douyin-cyan));
            --shadow-gradient: 0 0 20px rgba(254, 44, 85, 0.6);
        }

        body {
            font-family: 'Noto Sans SC', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
            background-color: var(--douyin-black);
            color: var(--douyin-white);
            overflow-x: hidden;
            line-height: 1.5;
        }

        /* 全屏分屏容器 */
        .section {
            width: 100vw;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 60px 20px;
            position: relative;
            overflow: hidden;
        }

        /* 抖音风格背景光斑装饰 */
        .bg-decor {
            position: absolute;
            border-radius: 50%;
            filter: blur(80px);
            opacity: 0.3;
            z-index: 0;
        }
        .decor-red {
            width: 300px;
            height: 300px;
            background-color: var(--douyin-red);
            top: 10%;
            left: -10%;
        }
        .decor-cyan {
            width: 300px;
            height: 300px;
            background-color: var(--douyin-cyan);
            bottom: 10%;
            right: -10%;
        }

        /* 内容容器 */
        .content {
            width: 100%;
            max-width: 480px;
            z-index: 1;
            position: relative;
        }

        /* 抖音风格标题 */
        h1 {
            font-size: 44px;
            font-weight: 900;
            line-height: 1.2;
            margin-bottom: 16px;
            letter-spacing: -1px;
        }
        h2 {
            font-size: 32px;
            font-weight: 900;
            line-height: 1.2;
            margin-bottom: 20px;
        }
        .gradient-text {
            background: var(--douyin-gradient);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            display: inline-block;
        }

        /* 副标题&正文 */
        .subtitle {
            font-size: 18px;
            color: var(--douyin-gray);
            margin-bottom: 40px;
            line-height: 1.6;
        }
        .feature-desc {
            font-size: 16px;
            color: var(--douyin-gray);
            margin-bottom: 30px;
            line-height: 1.6;
        }
        .pain-point {
            font-size: 17px;
            color: var(--douyin-white);
            margin-bottom: 30px;
            line-height: 1.8;
            padding-left: 12px;
            border-left: 3px solid var(--douyin-red);
        }

        /* 抖音风格主按钮 */
        .main-btn {
            width: 100%;
            height: 56px;
            border-radius: 28px;
            background-color: var(--douyin-red);
            color: var(--douyin-white);
            font-size: 18px;
            font-weight: 700;
            border: none;
            cursor: pointer;
            transition: all 0.3s ease;
            margin-bottom: 20px;
        }
        .main-btn:hover {
            transform: scale(1.02);
            box-shadow: var(--shadow-gradient);
        }
        .secondary-btn {
            width: 100%;
            height: 56px;
            border-radius: 28px;
            background: transparent;
            color: var(--douyin-white);
            font-size: 18px;
            font-weight: 700;
            border: 2px solid var(--douyin-white);
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .secondary-btn:hover {
            background-color: var(--douyin-white);
            color: var(--douyin-black);
            transform: scale(1.02);
        }

        /* 抖音logo栏 */
        .logo-bar {
            display: flex;
            align-items: center;
            gap: 8px;
            margin-bottom: 40px;
        }
        .logo-icon {
            width: 36px;
            height: 36px;
            background: var(--douyin-gradient);
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 900;
            font-size: 18px;
        }
        .logo-text {
            font-size: 20px;
            font-weight: 700;
        }

        /* 手机mockup容器 */
        .phone-mockup {
            width: 100%;
            max-width: 280px;
            margin: 40px auto 0;
            position: relative;
        }
        .phone-frame {
            width: 100%;
            height: 560px;
            border: 12px solid var(--douyin-dark-gray);
            border-radius: 40px;
            background-color: var(--douyin-black);
            overflow: hidden;
            position: relative;
        }
        .phone-screen {
            width: 100%;
            height: 100%;
            background-color: var(--douyin-black);
            overflow: hidden;
        }

        /* 核心聊天界面mockup（主打树洞场景） */
        .mockup-chat {
            width: 100%;
            height: 100%;
            display: flex;
            flex-direction: column;
        }
        .mockup-topbar {
            height: 60px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 0 16px;
            border-bottom: 1px solid var(--douyin-dark-gray);
        }
        .mockup-title {
            font-size: 16px;
            font-weight: 700;
        }
        .chat-area {
            flex: 1;
            padding: 16px 12px;
            display: flex;
            flex-direction: column;
            gap: 16px;
            overflow-y: auto;
        }
        .chat-bubble {
            max-width: 80%;
            padding: 10px 14px;
            border-radius: 18px;
            font-size: 14px;
            line-height: 1.5;
        }
        .bubble-mine {
            align-self: flex-end;
            background-color: var(--douyin-red);
            color: var(--douyin-white);
        }
        .bubble-other {
            align-self: flex-start;
            background-color: var(--douyin-dark-gray);
            color: var(--douyin-white);
        }
        .chat-input-bar {
            height: 60px;
            border-top: 1px solid var(--douyin-dark-gray);
            display: flex;
            align-items: center;
            padding: 0 12px;
            gap: 8px;
        }
        .chat-input {
            flex: 1;
            height: 40px;
            background-color: var(--douyin-dark-gray);
            border-radius: 20px;
            border: none;
            outline: none;
            color: var(--douyin-white);
            padding: 0 16px;
            font-size: 14px;
        }
        .ai-btn {
            width: 36px;
            height: 36px;
            border-radius: 50%;
            background: var(--douyin-gradient);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 16px;
            font-weight: 700;
        }
        .send-btn {
            width: 36px;
            height: 36px;
            border-radius: 50%;
            background-color: var(--douyin-red);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 14px;
            font-weight: 700;
        }

        /* 卖点卡片 */
        .feature-card {
            width: 100%;
            padding: 24px;
            background-color: var(--douyin-dark-gray);
            border-radius: 20px;
            margin-bottom: 20px;
            transition: all 0.3s ease;
        }
        .feature-card:hover {
            transform: translateY(-4px);
            box-shadow: 0 10px 30px rgba(254, 44, 85, 0.2);
        }
        .feature-icon {
            width: 48px;
            height: 48px;
            border-radius: 12px;
            background: var(--douyin-gradient);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 24px;
            font-weight: 700;
            margin-bottom: 16px;
        }
        .feature-title {
            font-size: 22px;
            font-weight: 700;
            margin-bottom: 8px;
        }

        /* 对比表格（AI树洞vs同频聊） */
        .compare-table {
            width: 100%;
            border-radius: 20px;
            overflow: hidden;
            margin-bottom: 30px;
        }
        .table-header {
            display: grid;
            grid-template-columns: 1fr 1fr;
            background-color: var(--douyin-dark-gray);
            padding: 16px;
        }
        .table-header-item {
            font-weight: 700;
            font-size: 16px;
            text-align: center;
        }
        .table-header-item.gradient {
            color: var(--douyin-red);
        }
        .table-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            padding: 16px;
            border-bottom: 1px solid var(--douyin-dark-gray);
            font-size: 14px;
        }
        .table-item {
            color: var(--douyin-gray);
        }
        .table-item.highlight {
            color: var(--douyin-white);
            font-weight: 500;
        }

        /* 底部版权 */
        .footer {
            margin-top: 60px;
            text-align: center;
            color: var(--douyin-gray);
            font-size: 14px;
        }

        /* 滚动动画 */
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s ease;
        }
        .fade-in.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* 移动端适配 */
        @media (max-width: 768px) {
            h1 {
                font-size: 36px;
            }
            h2 {
                font-size: 28px;
            }
            .section {
                padding: 40px 16px;
            }
            .phone-mockup {
                max-width: 240px;
            }
            .phone-frame {
                height: 480px;
            }
        }
    </style>
</head>
<body>
    <!-- 首屏KV：直接戳AI树洞痛点，主打核心定位 -->
    <section class="section">
        <div class="bg-decor decor-red"></div>
        <div class="bg-decor decor-cyan"></div>
        <div class="content fade-in">
            <div class="logo-bar">
                <div class="logo-icon">抖</div>
                <div class="logo-text">抖音</div>
            </div>
            <h1>
                别再跟AI说心里话了<br>
                <span class="gradient-text">这里有真人的真心</span>
            </h1>
            <p class="subtitle">抖音全新「同频聊」，带AI安全垫的真人树洞，完美替代冰冷的AI树洞</p>
            
            <div class="pain-point">
                心里的话不敢跟熟人说？<br>
                对着AI树洞倾诉，翻来覆去都是模板化的假共情？<br>
                想找个人好好聊聊，又怕社恐、怕被评判、怕被冒犯？
            </div>

            <button class="main-btn">打开抖音，找个懂你的人说说话</button>

            <div class="phone-mockup">
                <div class="phone-frame">
                    <div class="phone-screen">
                        <div class="mockup-chat">
                            <div class="mockup-topbar">
                                <div class="mockup-title">同频树洞匹配中</div>
                            </div>
                            <div class="chat-area">
                                <div class="chat-bubble bubble-mine">
                                    最近工作压力好大，天天加班，感觉撑不下去了，又不敢跟家里人说
                                </div>
                                <div class="chat-bubble bubble-other">
                                    我太懂这种感觉了，上个月我也是连轴转了一个月，每天下班都在路边坐半小时才敢回家，怕一开口就哭出来
                                </div>
                                <div class="chat-bubble bubble-mine">
                                    对！就是这种感觉，怕身边人觉得我矫情，只能自己憋着
                                </div>
                                <div class="chat-bubble bubble-other">
                                    一点都不矫情，撑了这么久你已经超棒了，愿意跟我说说具体是哪件事压得你喘不过气吗？
                                </div>
                            </div>
                            <div class="chat-input-bar">
                                <input type="text" class="chat-input" placeholder="把想说的话打在这里，AI帮你温柔兜底">
                                <div class="ai-btn">AI</div>
                                <div class="send-btn">→</div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- 核心对比：AI树洞vs同频聊，直接打差异化 -->
    <section class="section">
        <div class="content fade-in">
            <h2><span class="gradient-text">同样是说心里话，我们和AI树洞完全不一样</span></h2>
            <div class="compare-table">
                <div class="table-header">
                    <div class="table-header-item">传统AI树洞</div>
                    <div class="table-header-item gradient">抖音同频聊</div>
                </div>
                <div class="table-row">
                    <div class="table-item">算法预测的模板话术，无灵魂假共情</div>
                    <div class="table-item highlight">真人真实经历的真心回应，有温度真共情</div>
                </div>
                <div class="table-row">
                    <div class="table-item">单向倾诉，永远得不到真实的双向回应</div>
                    <div class="table-item highlight">双向奔赴，你说的话有人懂，你的情绪有人接</div>
                </div>
                <div class="table-row">
                    <div class="table-item">聊完就空，永远无法建立真实的情感联结</div>
                    <div class="table-item highlight">从树洞到交心，循序渐进遇见真正同频的人</div>
                </div>
                <div class="table-row">
                    <div class="table-item">冰冷的文字，传递不了藏在话里的小情绪</div>
                    <div class="table-item highlight">鲜活的情绪表达，让你的每一份心意都被看见</div>
                </div>
            </div>
        </div>
    </section>

    <!-- 核心卖点1：AI安全垫，解决不敢说的痛点 -->
    <section class="section">
        <div class="content fade-in">
            <h2><span class="gradient-text">AI做安全兜底，想说就说，毫无顾忌</span></h2>
            <p class="feature-desc">不用怕说错话、不用怕被评判、不用怕社恐尴尬，AI给你做温柔的安全缓冲，像树洞一样安全，比树洞更贴心。</p>
            
            <div class="feature-card">
                <div class="feature-icon">🛡️</div>
                <div class="feature-title">红线内容前置拦截</div>
                <p class="feature-desc">从源头杜绝所有冒犯、评判、低俗、骚扰内容，你永远不会收到让你不适的回复，放心卸下所有防备。</p>
            </div>

            <div class="feature-card">
                <div class="feature-icon">💬</div>
                <div class="feature-title">一键AI润色，只去顾虑不改真心</div>
                <p class="feature-desc">嘴笨、怕表达不好、怕情绪太激动？AI帮你把心里话润得更温柔、更得体，完全保留你的真实情绪，只帮你卸下表达的顾虑。</p>
            </div>
        </div>
    </section>

    <!-- 核心卖点2：抖音大数据匹配，找真正懂你的人 -->
    <section class="section">
        <div class="content fade-in">
            <h2><span class="gradient-text">找真正懂你的人，不用鸡同鸭讲</span></h2>
            <p class="feature-desc">告别随机匹配的陌生人，基于抖音全场景真实行为数据，精准匹配和你三观契合、情绪同频的人，你说的话，他真的能懂。</p>
            
            <div class="feature-card">
                <div class="feature-icon">🎯</div>
                <div class="feature-title">抖音原生大数据，比标签更懂你</div>
                <p class="feature-desc">你刷过的每一条视频、藏在评论里的心里话、关注的每一个内容，都在帮你找到真正能共情、能听懂你的人，拒绝虚假标签，匹配更精准。</p>
            </div>
        </div>
    </section>

    <!-- 核心卖点3：三阶递进解锁，从树洞到交心，毫无压力 -->
    <section class="section">
        <div class="content fade-in">
            <h2><span class="gradient-text">循序渐进敞开心扉，节奏完全由你掌控</span></h2>
            <p class="feature-desc">严格遵循「AI纯润色安全树洞→真实原文试探→无AI纯聊交心」三阶递进模式，不用一上来就直面陌生人，从安全倾诉到深度交心，慢慢来。</p>
            
            <div class="feature-card">
                <div class="feature-icon">📶</div>
                <div class="feature-title">每一步解锁，都基于你的心意</div>
                <p class="feature-desc">只有双方匹配度达标、你主动确认，才能解锁下一阶段；前序历史消息永久保留纯润色版本，你永远有退路，永远有安全感。</p>
            </div>
        </div>
    </section>

    <!-- 核心卖点4：鲜活情绪表达，让心里话有温度 -->
    <section class="section">
        <div class="content fade-in">
            <h2><span class="gradient-text">藏在文字里的情绪，也能被看见</span></h2>
            <p class="feature-desc">告别AI树洞的冰冷文字，智能捕捉你打字时的犹豫、纠结、害羞与小委屈，可自主选择分享给对方，让你的倾诉不止有文字，更有真实的温度。</p>
            
            <div class="feature-card">
                <div class="feature-icon">🔥</div>
                <div class="feature-title">鲜活情绪伴生表达</div>
                <p class="feature-desc">可选择卡通小火人、专属表情包、极简文字后缀，同步传递你藏在文字背后的情绪，不用反复解释“我不是那个意思”，对方一眼就能懂你的真心。</p>
            </div>
        </div>
    </section>

    <!-- 尾屏CTA：强化行动号召 -->
    <section class="section">
        <div class="bg-decor decor-red"></div>
        <div class="bg-decor decor-cyan"></div>
        <div class="content fade-in">
            <h2>
                你的心里话<br>
                <span class="gradient-text">值得真人的真心回应</span>
            </h2>
            <p class="subtitle">抖音原生内置功能，无需跳转新APP，打开抖音就能用，给你的情绪找一个温柔的出口</p>
            <button class="main-btn">打开抖音 立即体验</button>
            <div class="footer">
                © 2024 抖音 版权所有
            </div>
        </div>
    </section>

    <script>
        // 滚动触发渐入动画
        const fadeElements = document.querySelectorAll('.fade-in');
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('active');
                }
            });
        }, {
            threshold: 0.2
        });

        fadeElements.forEach(element => {
            observer.observe(element);
        });

        // 按钮跳转逻辑
        document.querySelectorAll('.main-btn').forEach(btn => {
            btn.addEventListener('click', () => {
                // 可替换为抖音APP唤起链接/内部分发链接
                alert('请打开抖音APP，在消息页找到「同频聊」入口，开启你的真人树洞之旅');
            });
        });
    </script>
</body>
</html>
