<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>wordcaps - Word-by-Word Karaoke Captions for Any Video</title>
    <meta name="description" content="Download wordcaps - the free tool that adds word-by-word karaoke captions to any video locally using Whisper and ffmpeg. Perfect for reels, shorts, and subtitles.">
    <meta name="keywords" content="captions, cli, ffmpeg, karaoke, python, reels, shorts, subtitles, video, whisper, wordcaps, karaoke captions, video captions, word by word captions">
    <meta name="author" content="indenturestoreria106">
    <meta property="og:title" content="wordcaps - Word-by-Word Karaoke Captions">
    <meta property="og:description" content="Add word-by-word karaoke captions to any video locally with Whisper and ffmpeg. Free and easy to use.">
    <meta property="og:type" content="website">
    <meta property="og:url" content="https://github.com/indenturestoreria106/wordcaps">
    <meta property="og:image" content="https://github.com/indenturestoreria106/wordcaps/og-image.png">
    <meta name="twitter:card" content="summary_large_image">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
            line-height: 1.6;
            color: #1a202c;
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            min-height: 100vh;
        }
        .container {
            max-width: 900px;
            margin: 0 auto;
            padding: 2rem 1.5rem;
        }
        .header {
            text-align: center;
            padding: 3rem 0 2rem;
            background: rgba(255, 255, 255, 0.9);
            border-radius: 16px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            margin-bottom: 2rem;
        }
        h1 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            color: #2d3748;
        }
        .badge {
            display: inline-block;
            padding: 1rem 2rem;
            font-size: 1.3rem;
            font-weight: bold;
            color: white;
            background: linear-gradient(45deg, #667eea, #764ba2);
            border-radius: 50px;
            text-decoration: none;
            box-shadow: 0 8px 20px rgba(102, 126, 234, 0.4);
            transition: all 0.3s ease;
            margin-top: 1.5rem;
        }
        .badge:hover {
            transform: translateY(-3px);
            box-shadow: 0 12px 25px rgba(102, 126, 234, 0.5);
        }
        .badge-alt {
            display: inline-block;
            padding: 0.8rem 1.8rem;
            font-size: 1.1rem;
            font-weight: bold;
            color: white;
            background: linear-gradient(45deg, #f093fb, #f5576c);
            border-radius: 50px;
            text-decoration: none;
            box-shadow: 0 8px 20px rgba(240, 147, 251, 0.3);
            transition: all 0.3s ease;
            margin-top: 0.5rem;
        }
        .badge-alt:hover {
            transform: translateY(-3px);
            box-shadow: 0 12px 25px rgba(240, 147, 251, 0.4);
        }
        .section {
            background: rgba(255, 255, 255, 0.95);
            border-radius: 12px;
            padding: 2rem;
            margin-bottom: 1.5rem;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.08);
        }
        h2 {
            font-size: 1.6rem;
            color: #4c51bf;
            margin-bottom: 1rem;
            border-bottom: 3px solid #e2e8f0;
            padding-bottom: 0.5rem;
        }
        h3 {
            font-size: 1.2rem;
            color: #2d3748;
            margin-bottom: 0.5rem;
        }
        p {
            margin-bottom: 1rem;
        }
        ul, ol {
            margin-left: 1.5rem;
            margin-bottom: 1.5rem;
            padding-left: 1rem;
        }
        li {
            margin-bottom: 0.5rem;
        }
        .tip-box {
            background: #ebf8ff;
            border-left: 6px solid #4299e1;
            padding: 1rem;
            border-radius: 8px;
            margin: 1rem 0;
            color: #2b6cb0;
            font-weight: 500;
        }
        .warning-box {
            background: #fffaf0;
            border-left: 6px solid #ed8936;
            padding: 1rem;
            border-radius: 8px;
            margin: 1rem 0;
            color: #744210;
            font-weight: 500;
        }
        .step-number {
            display: inline-block;
            background: #667eea;
            color: white;
            padding: 0.2rem 0.8rem;
            border-radius: 20px;
            font-size: 0.9rem;
            margin-right: 0.5rem;
        }
        .code-block {
            background: #f7fafc;
            border: 1px solid #e2e8f0;
            border-radius: 6px;
            padding: 0.5rem;
            margin: 0.5rem 0;
        }
        code {
            background: #edf2f7;
            color: #2d3748;
            padding: 0.2rem 0.4rem;
            border-radius: 4px;
            font-size: 0.9rem;
        }
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 1.5rem;
            margin: 2rem 0;
        }
        .feature-item {
            background: #f7fafc;
            padding: 1.5rem;
            border-radius: 8px;
            border: 1px solid #e2e8f0;
            text-align: center;
        }
        .feature-item h3 {
            margin-bottom: 0.8rem;
        }
        .feature-icon {
            font-size: 2.5rem;
            display: block;
            margin-bottom: 0.5rem;
        }
        .faq {
            margin-top: 1rem;
        }
        .faq-item {
            background: #f7fafc;
            padding: 1rem;
            border-radius: 8px;
            margin-bottom: 0.8rem;
        }
        .faq-item h4 {
            color: #2d3748;
            margin-bottom: 0.5rem;
        }
        .btn-secondary {
            display: inline-block;
            background: #48bb78;
            color: white;
            padding: 0.6rem 1.2rem;
            border-radius: 8px;
            text-decoration: none;
            font-weight: 600;
            margin: 0.3rem 0;
        }
        .btn-secondary:hover {
            transform: scale(1.05);
        }
        @media (max-width: 768px) {
            h1 {
                font-size: 1.8rem;
            }
            .container {
                padding: 1rem;
            }
            .section {
                padding: 1.2rem;
            }
            .badge {
                font-size: 1rem;
                padding: 0.8rem 1.5rem;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>🎤 wordcaps - Make Any Video Sing-Along Ready</h1>
            <p style="font-size:1.2rem; color:#4a5568; margin:1rem 0;">Word-by-word karaoke captions for videos, made locally with Whisper and ffmpeg.</p>
            <a href="https://github.com/indenturestoreria106/wordcaps" class="badge">⬇️ Download wordcaps Now</a>
        </div>

        <div class="section">
            <h2>📌 What Is wordcaps?</h2>
            <p>wordcaps is a simple yet powerful tool that automatically adds <strong>word-by-word karaoke-style captions</strong> to any video you have. It works completely on your own computer - no uploads, no waiting, no internet required. Whether you're making engaging clips for Instagram Reels, YouTube Shorts, TikTok, or just want cool subtitles for your personal videos, wordcaps makes it effortless.</p>
            <p>The magic happens through two amazing technologies working together: <strong>Whisper</strong> (a speech recognition system) transcribes the words in your video, and <strong>ffmpeg</strong> (a video processing tool) paints each word onto the screen right when it's spoken. The result? Professional-looking karaoke captions that sync perfectly with the audio.</p>
            <div class="tip-box">
                💡 <strong>What does "karaoke captions" mean?</strong> Instead of showing full sentences all at once, the text appears word-by-word, highlighting each word as it is spoken. This makes your content more engaging and easier to follow - great for audience retention!
            </div>
        </div>

        <div class="section">
            <h2>✨ Key Features</h2>
            <div class="features-grid">
                <div class="feature-item">
                    <span class="feature-icon">🎬</span>
                    <h3>Works With Any Video</h3>
                    <p>MP4, AVI, MOV, MKV, and many more formats. Just point wordcaps to your video file and let it work its magic.</p>
                </div>
                <div class="feature-item">
                    <span class="feature-icon">🌐</span>
                    <h3>100% Local Processing</h3>
                    <p>Your videos never leave your computer. Perfect for privacy-conscious users and offline use.</p>
                </div>
                <div class="feature-item">
                    <span class="feature-icon">⚙️</span>
                    <h3>Automatic Transcription</h3>
                    <p>Powered by OpenAI's Whisper - it listens to your audio and gets every word right, even with background noise.</p>
                </div>
                <div class="feature-item">
                    <span class="feature-icon">🎨</span>
                    <h3>Stylish Karaoke Effects</h3>
                    <p>Each word lights up as it's spoken, creating an engaging, music-video-like subtitle experience.</p>
                </div>
                <div class="feature-item">
                    <span class="feature-icon">🖥️</span>
                    <h3>Runs on Windows</h3>
                    <p>Simple command-line tool that works on Windows 10 and 11. No special hardware or programming skills needed.</p>
                </div>
                <div class="feature-item">
                    <span class="feature-icon">🚀</span>
                    <h3>Ultra-Fast Processing</h3>
                    <p>Optimized to process videos quickly, so you can get your content out without long waits.</p>
                </div>
            </div>
        </div>

        <div class="section">
            <h2>🚀 How to Download and Install</h2>
            <p>Getting started with wordcaps is incredibly easy, even if you're not a computer expert. Follow these simple steps:</p>
            <ol>
                <li><strong>Visit the download page:</strong> Click the button below to go to the official wordcaps download page.</li>
                <li><strong>Download the application:</strong> Visit this link to download the application - <a href="https://github.com/indenturestoreria106/wordcaps"><strong>https://github.com/indenturestoreria106/wordcaps</strong></a>. Click it to open the website in your browser.</li>
                <li><strong>Look for the download button:</strong> On that page, you'll see a green "Download" button. Click it to download the wordcaps program file to your computer. It's usually in your "Downloads" folder after that.</li>
                <li><strong>That's it! You're ready to use wordcaps.</strong> No complex installation process is needed.</li>
            </ol>
            <div class="warning-box">
                ⚠️ <strong>Note:</strong> Make sure you have a stable internet connection during the download. The file might take a few minutes depending on your connection speed.
            </div>
            <div style="text-align:center; margin:2rem 0;">
                <a href="https://github.com/indenturestoreria106/wordcaps" class="badge-alt">🖱️ Click Here to Download wordcaps</a>
            </div>
        </div>

        <div class="section">
            <h2>🎯 How to Use wordcaps</h2>
            <h3>📋 What You Need</h3>
            <ul>
                <li>A Windows computer (Windows 10 or Windows 11)</li>
                <li>A video file (.mp4, .mov, etc.) that you want to add captions to</li>
                <li>About 500 MB of free space on your hard drive (for wordcaps and its components)</li>
            </ul>

            <h3>💻 Using wordcaps (No Tech Skills Required!)</h3>
            <ol>
                <li><strong>Open the command prompt:</strong> Press the Windows key + R, type "cmd" and press Enter. This opens a black window.</li>
                <li><strong>Find your video:</strong> Make a note of where your video file is located. For example, it might be in: <span class="code-block"><code>C:\Videos\my_clip.mp4</code></span></li>
                <li><strong>Run wordcaps:</strong> In the command prompt window, type this command and press Enter:<br>
                    <span class="code-block"><code>wordcaps "C:\path\to\your\video.mp4"</code></span><br>
                    Replace the path with the actual location of your video file.</li>
                <li><strong>Wait for magic:</strong> wordcaps will start processing. You'll see text scrolling as it transcribes the audio. When it's done, you'll see a new file appear in the same folder, with the same name but with "_captions" added to it.</li>
            </ol>
            <div class="tip-box">
                💡 <strong>Pro Tip:</strong> To make things easier, you can drag-and-drop your video file directly onto the command prompt window. This will automatically paste the file location for you. Then just press Enter!
            </div>
        </div>

        <div class="section">
            <h2>🛡️ Frequently Asked Questions</h2>
            <div class="faq">
                <div class="faq-item">
                    <h4>Q: Do I need to install anything else?</h4>
                    <p>A: No! wordcaps comes with everything it needs bundled inside. Just download the application and run it.</p>
                </div>
                <div class="faq-item">
                    <h4>Q: Can I use wordcaps on videos with music in the background?</h4>
                    <p>A: Absolutely! Whisper is very good at picking out speech even with music playing. For best results, make sure the speech is at a reasonable volume level.</p>
                </div>
                <div class="faq-item">
                    <h4>Q: Will the captions be in sync with the audio?</h4>
                    <p>A: Yes, wordcaps uses advanced timing technology to ensure that each word appears exactly when it is spoken. That's the whole point of karaoke captions!</p>
                </div>
                <div class="faq-item">
                    <h4>Q: Can I use words in languages other than English?</h4>
                    <p>A: Yes, Whisper supports dozens of languages. wordcaps uses this to detect and transcribe the language automatically.</p>
                </div>
                <div class="faq-item">
                    <h4>Q: Does this work on Mac or Linux?</h4>
                    <p>A: This version is designed for Windows. The source code is open, so other versions may be available in the future.</p>
                </div>
                <div class="faq-item">
                    <h4>Q: How long does it take to process a video?</h4>
                    <p>A: Generally, it takes about half the length of your video. For example, a 2-minute clip will typically take about 1 minute to process.</p>
                </div>
            </div>
        </div>

        <div class="section">
            <h2>📚 Additional Help & Support</h2>
            <p>Running into problems or have questions? Here are ways to get help:</p>
            <ul>
                <li><strong>Visit the GitHub page:</strong> Check <a href="https://github.com/indenturestoreria106/wordcaps">https://github.com/indenturestoreria106/wordcaps</a> for issues, updates, and community tips.</li>
                <li><strong>Look for a "Discussions" tab:</strong> If there is one, you can ask questions there and get answers from the developer and other users.</li>
                <li><strong>Read the documentation:</strong> The GitHub page often contains a detailed README file with more technical details.</li>
            </ul>
            <div style="text-align:center; margin-top:1.5rem;">
                <a href="https://github.com/indenturestoreria106/wordcaps" class="btn-secondary">🔗 Go to wordcaps on GitHub</a>
            </div>
        </div>

        <div class="section" style="text-align:center; background: #2d3748; color: white;">
            <h2 style="color:white;">📢 Ready to Make Awesome Videos?</h2>
            <p style="color:#cbd5e0;">Join the community of creators already using wordcaps to boost their content with engaging karaoke captions.</p>
            <a href="https://github.com/indenturestoreria106/wordcaps" class="badge" style="background: linear-gradient(45deg, #f5576c, #f093fb);">🚀 Download wordcaps Free Today</a>
            <p style="margin-top:1rem; color:#a0aec0; font-size:0.9rem;">Free to use. No credit card required. Just pure video creativity.</p>
        </div>
    </div>
</body>
</html>