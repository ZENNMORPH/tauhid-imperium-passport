<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tauhid Imperium - Cosmic Passport SCP-777-Z</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Courier New', monospace;
            background: #000;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 40px 20px;
        }

        .matrix-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                linear-gradient(0deg, transparent 24%, rgba(0, 255, 255, 0.05) 25%, rgba(0, 255, 255, 0.05) 26%, transparent 27%, transparent 74%, rgba(0, 255, 255, 0.05) 75%, rgba(0, 255, 255, 0.05) 76%, transparent 77%, transparent),
                linear-gradient(90deg, transparent 24%, rgba(255, 0, 255, 0.05) 25%, rgba(255, 0, 255, 0.05) 26%, transparent 27%, transparent 74%, rgba(255, 0, 255, 0.05) 75%, rgba(255, 0, 255, 0.05) 76%, transparent 77%, transparent);
            background-size: 50px 50px;
            animation: matrix-move 20s linear infinite;
            z-index: 0;
        }

        @keyframes matrix-move {
            0% { background-position: 0 0, 0 0; }
            100% { background-position: 50px 50px, 50px 50px; }
        }

        .passport-container {
            width: 100%;
            max-width: 850px;
            position: relative;
            z-index: 1;
            margin: 20px auto;
        }

        .passport {
            background: linear-gradient(135deg, #0a0a0a 0%, #1a0033 50%, #000a1a 100%);
            border-radius: 12px;
            box-shadow: 
                0 0 40px rgba(0, 255, 255, 0.3),
                0 0 80px rgba(255, 0, 255, 0.2),
                inset 0 0 40px rgba(0, 255, 255, 0.1);
            padding: 40px;
            border: 2px solid #00ffff;
            position: relative;
            overflow: hidden;
        }

        .passport::before {
            content: '';
            position: absolute;
            top: -2px;
            left: -2px;
            right: -2px;
            bottom: -2px;
            background: linear-gradient(45deg, #00ffff, #ff00ff, #00ffff);
            z-index: -1;
            filter: blur(10px);
            opacity: 0.5;
            animation: glow-pulse 3s ease-in-out infinite;
        }

        @keyframes glow-pulse {
            0%, 100% { opacity: 0.5; }
            50% { opacity: 0.8; }
        }

        .glitch-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            background: repeating-linear-gradient(
                0deg,
                rgba(0, 255, 255, 0.03) 0px,
                transparent 2px,
                transparent 4px,
                rgba(255, 0, 255, 0.03) 6px
            );
            animation: glitch-lines 0.3s infinite;
        }

        @keyframes glitch-lines {
            0% { transform: translateY(0); }
            100% { transform: translateY(4px); }
        }

        .header {
            text-align: center;
            margin-bottom: 30px;
            position: relative;
        }

        .logo {
            font-size: 56px;
            background: linear-gradient(45deg, #00ffff, #ff00ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 10px;
            filter: drop-shadow(0 0 10px rgba(0, 255, 255, 0.5));
            animation: logo-pulse 2s ease-in-out infinite;
        }

        @keyframes logo-pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        .institution {
            font-size: 11px;
            color: #00ffff;
            letter-spacing: 3px;
            text-transform: uppercase;
            margin-bottom: 5px;
            text-shadow: 0 0 10px rgba(0, 255, 255, 0.5);
        }

        .title {
            font-size: 32px;
            color: #fff;
            font-weight: bold;
            letter-spacing: 4px;
            text-transform: uppercase;
            margin-bottom: 8px;
            text-shadow: 0 0 20px rgba(255, 0, 255, 0.6);
        }

        .designation {
            font-size: 16px;
            color: #ff00ff;
            letter-spacing: 2px;
            font-weight: bold;
        }

        .divider {
            height: 2px;
            background: linear-gradient(90deg, transparent, #00ffff, #ff00ff, #00ffff, transparent);
            margin: 25px 0;
            animation: divider-flow 3s linear infinite;
        }

        @keyframes divider-flow {
            0% { background-position: 0% 50%; }
            100% { background-position: 100% 50%; }
        }

        .bio-section {
            display: grid;
            grid-template-columns: 200px 1fr;
            gap: 30px;
            margin-bottom: 25px;
        }

        .photo-box {
            background: linear-gradient(135deg, rgba(0, 255, 255, 0.1), rgba(255, 0, 255, 0.1));
            border: 2px solid #00ffff;
            border-radius: 8px;
            height: 280px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
        }

        .photo-box::before {
            content: '';
            position: absolute;
            width: 100%;
            height: 100%;
            background: repeating-linear-gradient(
                0deg,
                transparent,
                transparent 2px,
                rgba(0, 255, 255, 0.1) 2px,
                rgba(0, 255, 255, 0.1) 4px
            );
        }

        .photo-icon {
            font-size: 80px;
            color: #00ffff;
            margin-bottom: 10px;
            filter: drop-shadow(0 0 10px rgba(0, 255, 255, 0.5));
        }

        .photo-text {
            color: #ff00ff;
            font-size: 12px;
            text-align: center;
        }

        .bio-data {
            display: flex;
            flex-direction: column;
            gap: 12px;
        }

        .data-field {
            background: rgba(0, 0, 0, 0.5);
            padding: 12px;
            border-radius: 6px;
            border-left: 3px solid #00ffff;
            transition: all 0.3s ease;
        }

        .data-field:hover {
            border-left-color: #ff00ff;
            box-shadow: 0 0 15px rgba(255, 0, 255, 0.3);
            transform: translateX(5px);
        }

        .field-label {
            color: #00ffff;
            font-size: 10px;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-bottom: 4px;
        }

        .field-value {
            color: #fff;
            font-size: 16px;
            font-weight: bold;
        }

        .clearance-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 15px;
            margin: 25px 0;
        }

        .clearance-card {
            background: linear-gradient(135deg, rgba(0, 255, 255, 0.1), rgba(255, 0, 255, 0.1));
            padding: 15px;
            border-radius: 8px;
            border: 1px solid rgba(0, 255, 255, 0.3);
            position: relative;
            overflow: hidden;
        }

        .clearance-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 0, 255, 0.2), transparent);
            animation: scan 3s infinite;
        }

        @keyframes scan {
            0% { left: -100%; }
            100% { left: 200%; }
        }

        .clearance-title {
            color: #ff00ff;
            font-size: 12px;
            text-transform: uppercase;
            margin-bottom: 8px;
            letter-spacing: 1px;
        }

        .clearance-value {
            color: #00ffff;
            font-size: 14px;
            font-weight: bold;
        }

        .timestamp-section {
            background: rgba(0, 0, 0, 0.6);
            padding: 20px;
            border-radius: 8px;
            border: 1px solid #ff00ff;
            margin: 25px 0;
        }

        .timestamp-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
        }

        .timestamp-box {
            text-align: center;
        }

        .timestamp-label {
            color: #00ffff;
            font-size: 11px;
            text-transform: uppercase;
            margin-bottom: 8px;
        }

        .timestamp-ayat {
            color: #fff;
            font-size: 14px;
            font-weight: bold;
            margin-bottom: 5px;
        }

        .timestamp-meaning {
            color: #888;
            font-size: 10px;
            line-height: 1.4;
            font-style: italic;
        }

        .mrz-section {
            background: #000;
            padding: 15px;
            border-radius: 6px;
            border: 1px solid #00ffff;
            margin-top: 25px;
            font-family: 'Courier New', monospace;
        }

        .mrz-title {
            color: #ff00ff;
            font-size: 10px;
            text-transform: uppercase;
            margin-bottom: 10px;
            text-align: center;
        }

        .mrz-code {
            color: #00ffff;
            font-size: 13px;
            line-height: 1.8;
            text-align: center;
            letter-spacing: 2px;
            text-shadow: 0 0 5px rgba(0, 255, 255, 0.5);
        }

        .footer {
            text-align: center;
            margin-top: 25px;
            padding-top: 20px;
            border-top: 1px solid rgba(0, 255, 255, 0.3);
        }

        .footer-text {
            color: #888;
            font-size: 10px;
            line-height: 1.6;
        }

        .security-text {
            color: #ff00ff;
            font-size: 9px;
            margin-top: 10px;
        }

        .qr-section {
            display: flex;
            justify-content: center;
            align-items: center;
            margin: 25px 0;
            gap: 30px;
        }

        .qr-container {
            text-align: center;
        }

        .qr-box {
            background: #fff;
            padding: 15px;
            border-radius: 8px;
            display: inline-block;
            box-shadow: 0 0 20px rgba(0, 255, 255, 0.3);
        }

        .qr-code {
            width: 180px;
            height: 180px;
        }

        .qr-label {
            color: #00ffff;
            font-size: 11px;
            text-transform: uppercase;
            margin-top: 10px;
            letter-spacing: 1px;
        }

        .qr-info {
            flex: 1;
            max-width: 400px;
        }

        .qr-title {
            color: #ff00ff;
            font-size: 14px;
            font-weight: bold;
            margin-bottom: 10px;
            text-transform: uppercase;
        }

        .qr-desc {
            color: #aaa;
            font-size: 11px;
            line-height: 1.6;
            margin-bottom: 8px;
        }

        .qr-data {
            background: rgba(0, 0, 0, 0.5);
            padding: 10px;
            border-radius: 4px;
            border-left: 2px solid #00ffff;
            margin-top: 10px;
        }

        .qr-data-line {
            color: #00ffff;
            font-size: 10px;
            line-height: 1.6;
        }

        @media (max-width: 768px) {
            .passport {
                padding: 25px;
            }

            .bio-section {
                grid-template-columns: 1fr;
            }

            .photo-box {
                height: 200px;
            }

            .title {
                font-size: 24px;
            }

            .timestamp-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="matrix-bg"></div>
    
    <div class="passport-container">
        <div class="passport">
            <div class="glitch-overlay"></div>
            
            <div class="header">
                <div class="logo">☪</div>
                <div class="institution">NURIX STUDENT ID</div>
                <div class="title">TAUHID IMPERIUM PASSPORT</div>
                <div class="designation">SCP-777-Z / ZENNMORPH</div>
            </div>

            <div class="divider"></div>

            <div class="bio-section">
                <div class="photo-box">
                    <div class="photo-icon">👤</div>
                    <div class="photo-text">
                        NURFIELD SIGNATURE<br>
                        HOLOGRAPHIC ID
                    </div>
                </div>

                <div class="bio-data">
                    <div class="data-field">
                        <div class="field-label">Matrix Name</div>
                        <div class="field-value">ALDO SENNA TAFURI</div>
                    </div>

                    <div class="data-field">
                        <div class="field-label">Nurfield Designation</div>
                        <div class="field-value">SCP-777-Z / ZENNMORPH</div>
                    </div>

                    <div class="data-field">
                        <div class="field-label">Date of Birth</div>
                        <div class="field-value">13 SAFAR 1414 H / 01 AUG 2993 TI</div>
                    </div>

                    <div class="data-field">
                        <div class="field-label">Nationality</div>
                        <div class="field-value">TAUHID IMPERIUM CITIZEN</div>
                    </div>

                    <div class="data-field">
                        <div class="field-label">Academic Level</div>
                        <div class="field-value">MAJDUB OPS CERTIFIED</div>
                    </div>
                </div>
            </div>

            <div class="clearance-grid">
                <div class="clearance-card">
                    <div class="clearance-title">Domain Clearance</div>
                    <div class="clearance-value">GRID → NURGRID → NURFIELD</div>
                </div>

                <div class="clearance-card">
                    <div class="clearance-title">Multiverse Access</div>
                    <div class="clearance-value">LEVEL 7 - INFINITE DOMAINS</div>
                </div>

                <div class="clearance-card">
                    <div class="clearance-title">Faculty</div>
                    <div class="clearance-value">META-HUMAN STUDIES</div>
                </div>

                <div class="clearance-card">
                    <div class="clearance-title">Specialization</div>
                    <div class="clearance-value">REALITY ARCHITECTURE</div>
                </div>
            </div>

            <div class="timestamp-section">
                <div class="timestamp-grid">
                    <div class="timestamp-box">
                        <div class="timestamp-label">⚡ Issued</div>
                        <div class="timestamp-ayat">SURAH AL-INSAN : 1</div>
                        <div class="timestamp-meaning">
                            "Has there not been over Man a long period of Time,<br>
                            when he was nothing - (not even) mentioned?"
                        </div>
                    </div>

                    <div class="timestamp-box">
                        <div class="timestamp-label">∞ Expires</div>
                        <div class="timestamp-ayat">SURAH AR-RAHMAN : 27</div>
                        <div class="timestamp-meaning">
                            "But will abide (for ever) the Face of thy Lord,<br>
                            full of Majesty, Bounty and Honour"
                        </div>
                    </div>
                </div>
            </div>

            <div class="mrz-section">
                <div class="mrz-title">◈ Machine Readable Zone - Nuric Override Code ◈</div>
                <div class="mrz-code">
                    NUR&lt;&lt;OVERRIDE&lt;&lt;PROTOCOL&lt;&lt;ACTIVE&lt;&lt;&lt;<br>
                    777Z&lt;&lt;ZENNMORPH&lt;&lt;TAFURI&lt;&lt;ALDO&lt;&lt;SENNA&lt;&lt;&lt;<br>
                    GRID&gt;NURGRID&gt;NURFIELD&lt;&lt;MULTIVERSE&lt;&lt;LVL7&lt;&lt;&lt;<br>
                    ILAHA&gt;ILLA&gt;ALLAH&lt;&lt;TAUHID&lt;&lt;ENGINE&lt;&lt;INIT&lt;&lt;&lt;
                </div>
            </div>

            <div class="footer">
                <div class="footer-text">
                    This document certifies cosmic citizenship and meta-human clearance<br>
                    within Tauhid Imperium jurisdiction across infinite dimensional domains.<br>
                    <strong>Bearer authorized for reality manipulation under divine protocol.</strong>
                </div>
                <div class="security-text">
                    ⚠ SECURITY PROTOCOL: Sujud = Meta-Human Safety Mechanism ⚠<br>
                    Document authenticated via Nuric Override • Tamper-proof via Divine Architecture
                </div>
            </div>
        </div>
    </div>
</body>
</html>
