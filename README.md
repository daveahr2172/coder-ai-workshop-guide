<html lang="en" data-theme="dark">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Coder AI Workshop Guide</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&family=IBM+Plex+Mono:wght@400;500;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --white: #ffffff;
            --black: #090B0B;
            --magenta: #F08DFF;
            --purple: #BC7CFF;
            --ember: #FF8067;
            --orchid: #9900B1;
            --violet: #7511E2;
            --sunset: #A13000;
            --haze: #A19CC8;
            --glacier: #B8D7F5;
            --sky: #A4E8F2;
            --twilight: #4A408F;
            --marine: #1D4D7D;
            --jade: #005C6A;
            --shell: #F8F2F1;
            --linen: #FBF8F8;
            --cinder: #18171A;
            --smoke: #2F2D33;
        }

        [data-theme="dark"] {
            --bg-page: var(--black);
            --bg-container: var(--cinder);
            --bg-header: linear-gradient(135deg, var(--cinder) 0%, var(--smoke) 100%);
            --bg-surface: var(--black);
            --bg-code: var(--smoke);
            --border-main: var(--smoke);
            --border-accent: var(--purple);
            --text-primary: var(--shell);
            --text-body: #d4d0d0;
            --text-muted: var(--haze);
            --heading-primary: var(--purple);
            --heading-secondary: var(--magenta);
            --heading-tertiary: var(--glacier);
            --link-color: var(--purple);
            --link-hover: var(--magenta);
            --btn-bg: var(--violet);
            --btn-hover: var(--orchid);
            --btn-copied-bg: var(--jade);
            --btn-copied-text: var(--sky);
            --table-header-bg: var(--violet);
            --table-cell-bg: var(--black);
            --info-bg: rgba(29,77,125,0.15);
            --info-border: var(--marine);
            --info-text: var(--glacier);
            --success-bg: rgba(0,92,106,0.15);
            --success-border: var(--sky);
            --success-text: var(--sky);
            --warning-bg: rgba(161,48,0,0.15);
            --warning-border: var(--ember);
            --warning-text: var(--ember);
            --badge-beginner-bg: var(--jade);
            --badge-beginner-text: var(--sky);
            --badge-intermediate-bg: var(--sunset);
            --badge-intermediate-text: var(--ember);
            --badge-advanced-bg: var(--twilight);
            --badge-advanced-text: var(--purple);
            --toggle-bg: var(--smoke);
            --toggle-knob: var(--purple);
        }

        [data-theme="light"] {
            --bg-page: var(--shell);
            --bg-container: var(--white);
            --bg-header: linear-gradient(135deg, var(--white) 0%, var(--shell) 100%);
            --bg-surface: var(--shell);
            --bg-code: var(--cinder);
            --border-main: #ddd;
            --border-accent: var(--marine);
            --text-primary: var(--black);
            --text-body: var(--smoke);
            --text-muted: #666;
            --heading-primary: var(--marine);
            --heading-secondary: var(--violet);
            --heading-tertiary: var(--marine);
            --link-color: var(--marine);
            --link-hover: var(--violet);
            --btn-bg: var(--marine);
            --btn-hover: var(--jade);
            --btn-copied-bg: var(--jade);
            --btn-copied-text: var(--white);
            --table-header-bg: var(--marine);
            --table-cell-bg: var(--white);
            --info-bg: rgba(29,77,125,0.08);
            --info-border: var(--marine);
            --info-text: var(--marine);
            --success-bg: rgba(0,92,106,0.08);
            --success-border: var(--jade);
            --success-text: var(--jade);
            --warning-bg: rgba(161,48,0,0.08);
            --warning-border: var(--ember);
            --warning-text: var(--sunset);
            --badge-beginner-bg: #e0f5f0;
            --badge-beginner-text: var(--jade);
            --badge-intermediate-bg: #fff0ed;
            --badge-intermediate-text: var(--sunset);
            --badge-advanced-bg: #f0e8ff;
            --badge-advanced-text: var(--violet);
            --toggle-bg: #ddd;
            --toggle-knob: var(--marine);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }

        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            line-height: 1.6;
            color: var(--text-primary);
            background: var(--bg-page);
            padding: 20px;
            transition: background 0.3s, color 0.3s;
        }

        .container {
            max-width: 1000px;
            margin: 0 auto;
            background: var(--bg-container);
            border-radius: 12px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.15);
            overflow: hidden;
            border: 1px solid var(--border-main);
            transition: background 0.3s, border-color 0.3s;
        }

        .header {
            background: var(--bg-header);
            padding: 48px 30px 40px;
            text-align: center;
            border-bottom: 3px solid var(--border-accent);
            position: relative;
        }

        .header-top-bar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 32px;
        }

        .header-logo {
            height: 26px;
            width: auto;
            transition: filter 0.3s;
        }
        [data-theme="dark"] .header-logo { filter: invert(1); }
        [data-theme="light"] .header-logo { filter: none; }

        .theme-toggle {
            display: flex;
            align-items: center;
            gap: 8px;
            cursor: pointer;
            user-select: none;
        }

        .toggle-track {
            width: 44px;
            height: 24px;
            background: var(--toggle-bg);
            border-radius: 12px;
            position: relative;
            transition: background 0.3s;
        }

        .toggle-knob {
            width: 18px;
            height: 18px;
            background: var(--toggle-knob);
            border-radius: 50%;
            position: absolute;
            top: 3px;
            left: 3px;
            transition: transform 0.3s, background 0.3s;
        }

        [data-theme="light"] .toggle-knob { transform: translateX(20px); }

        .toggle-icon { font-size: 14px; line-height: 1; }

        .header h1 {
            font-size: 2.5em;
            margin-bottom: 8px;
            color: var(--text-primary);
            font-weight: 800;
            letter-spacing: -0.02em;
        }

        .header p {
            font-size: 1.1em;
            color: var(--text-muted);
            font-weight: 500;
        }

        .content { padding: 40px 30px; }

        h2 {
            color: var(--heading-primary);
            margin-top: 48px;
            margin-bottom: 20px;
            font-size: 1.8em;
            font-weight: 700;
            letter-spacing: -0.01em;
            border-bottom: 2px solid var(--border-main);
            padding-bottom: 12px;
        }

        h3 {
            color: var(--heading-secondary);
            margin-top: 30px;
            margin-bottom: 15px;
            font-size: 1.3em;
            font-weight: 600;
        }

        h4 {
            color: var(--heading-tertiary);
            margin-top: 20px;
            margin-bottom: 10px;
            font-size: 1.05em;
            font-weight: 600;
        }

        p, li { margin-bottom: 10px; color: var(--text-body); }
        strong { color: var(--text-primary); }
        em { color: var(--text-muted); }
        ul, ol { margin-left: 30px; margin-bottom: 20px; }

        .prompt-box {
            background: var(--bg-surface);
            border-left: 3px solid var(--border-accent);
            padding: 20px;
            margin: 20px 0;
            border-radius: 8px;
            position: relative;
        }

        .prompt-box pre {
            font-family: 'IBM Plex Mono', 'Courier New', monospace;
            background: var(--bg-code);
            color: var(--shell);
            padding: 16px;
            border-radius: 6px;
            overflow-x: auto;
            font-size: 0.88em;
            margin-top: 10px;
            border: 1px solid var(--border-main);
            white-space: pre-wrap;
            line-height: 1.5;
        }

        .copy-btn {
            position: absolute;
            top: 10px;
            right: 10px;
            background: var(--btn-bg);
            color: #fff;
            border: none;
            padding: 6px 14px;
            border-radius: 6px;
            cursor: pointer;
            font-family: 'IBM Plex Mono', monospace;
            font-size: 0.8em;
            font-weight: 600;
            transition: background 0.2s;
        }

        .copy-btn:hover { background: var(--btn-hover); }
        .copy-btn.copied { background: var(--btn-copied-bg); color: var(--btn-copied-text); }

        .info-box {
            background: var(--info-bg);
            border-left: 3px solid var(--info-border);
            padding: 16px 20px;
            margin: 20px 0;
            border-radius: 8px;
            color: var(--info-text);
        }
        .info-box strong, .info-box li { color: var(--info-text); }

        .success-box {
            background: var(--success-bg);
            border-left: 3px solid var(--success-border);
            padding: 16px 20px;
            margin: 20px 0;
            border-radius: 8px;
            color: var(--success-text);
        }
        .success-box li { color: var(--success-text); }

        .warning-box {
            background: var(--warning-bg);
            border-left: 3px solid var(--warning-border);
            padding: 16px 20px;
            margin: 20px 0;
            border-radius: 8px;
            color: var(--warning-text);
        }

        table { width: 100%; border-collapse: collapse; margin: 20px 0; }
        th, td { border: 1px solid var(--border-main); padding: 12px 16px; text-align: left; color: var(--text-body); }
        th { background: var(--table-header-bg); color: #fff; font-weight: 600; font-size: 0.95em; }
        td { background: var(--table-cell-bg); }

        .difficulty-badge {
            display: inline-block;
            padding: 4px 14px;
            border-radius: 20px;
            font-size: 0.82em;
            font-weight: 700;
            letter-spacing: 0.03em;
            text-transform: uppercase;
        }
        .beginner { background: var(--badge-beginner-bg); color: var(--badge-beginner-text); }
        .intermediate { background: var(--badge-intermediate-bg); color: var(--badge-intermediate-text); }
        .advanced { background: var(--badge-advanced-bg); color: var(--badge-advanced-text); }

        .checklist { list-style: none; margin-left: 0; }
        .checklist li { padding: 6px 0 6px 32px; position: relative; color: var(--text-body); }
        .checklist li:before { content: "\2610"; position: absolute; left: 0; font-size: 1.2em; color: var(--heading-primary); }

        a { color: var(--link-color); text-decoration: none; font-weight: 500; transition: color 0.2s; }
        a:hover { text-decoration: underline; color: var(--link-hover); }

        .nav-toc {
            background: var(--bg-surface);
            padding: 24px;
            border-radius: 8px;
            margin-bottom: 30px;
            border: 1px solid var(--border-main);
        }
        .nav-toc h3 { margin-top: 0; color: var(--heading-primary); font-size: 1.1em; }
        .nav-toc ul { margin-left: 20px; columns: 2; }
        .nav-toc li { color: var(--text-muted); break-inside: avoid; }
        .nav-toc a { color: var(--text-muted); font-size: 0.95em; }
        .nav-toc a:hover { color: var(--link-hover); }

        .method-tabs { display: flex; gap: 0; margin: 24px 0 0 0; border-bottom: 2px solid var(--border-main); }
        .method-tab {
            padding: 12px 24px;
            background: transparent;
            color: var(--text-muted);
            border: none;
            cursor: pointer;
            font-family: 'IBM Plex Mono', monospace;
            font-size: 0.9em;
            font-weight: 600;
            border-bottom: 2px solid transparent;
            margin-bottom: -2px;
            transition: all 0.2s;
        }
        .method-tab:hover { color: var(--link-hover); }
        .method-tab.active { color: var(--heading-primary); border-bottom-color: var(--heading-primary); }

        .method-content { display: none; padding: 24px 0 0 0; }
        .method-content.active { display: block; }

        .method-label {
            display: inline-block;
            font-family: 'IBM Plex Mono', monospace;
            font-size: 0.75em;
            font-weight: 600;
            padding: 3px 10px;
            border-radius: 4px;
            letter-spacing: 0.05em;
            text-transform: uppercase;
            margin-bottom: 8px;
        }
        .label-a { background: rgba(117,17,226,0.15); color: var(--heading-primary); }
        .label-b { background: rgba(240,141,255,0.12); color: var(--heading-secondary); }

        .step-number {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 28px;
            height: 28px;
            background: var(--btn-bg);
            color: #fff;
            border-radius: 50%;
            font-size: 0.85em;
            font-weight: 700;
            margin-right: 8px;
            flex-shrink: 0;
        }

        .footer {
            text-align: center;
            padding: 40px 0;
            border-top: 1px solid var(--border-main);
            margin-top: 48px;
        }
        .footer h3 { color: var(--text-primary); margin-bottom: 8px; }
        .footer p { font-size: 1em; color: var(--text-muted); }

        @media (max-width: 768px) {
            body { padding: 10px; }
            .header h1 { font-size: 1.8em; }
            .content { padding: 20px 15px; }
            h2 { font-size: 1.4em; }
            .nav-toc ul { columns: 1; }
            .method-tab { padding: 10px 14px; font-size: 0.82em; }
            .header-top-bar { flex-direction: column; gap: 16px; }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <div class="header-top-bar">
                <img id="coder-logo" src="Logo-black.png" alt="Coder" class="header-logo">

                <div class="theme-toggle" onclick="toggleTheme()">
                    <span class="toggle-icon">&#9790;</span>
                    <div class="toggle-track">
                        <div class="toggle-knob"></div>
                    </div>
                    <span class="toggle-icon">&#9788;</span>
                </div>
            </div>

            <h1>AI Workshop Guide</h1>
            <p>Enterprise-Ready AI-Assisted Development with Secure Boundaries</p>
        </div>

        <div class="content">
            <div class="nav-toc">
                <h3>Table of Contents</h3>
                <ul>
                    <li><a href="#overview">Workshop Overview</a></li>
                    <li><a href="#prerequisites">Prerequisites</a></li>
                    <li><a href="#part1">Part 1: Workspace Launch</a></li>
                    <li><a href="#part2">Part 2: Verify Setup & Explore</a></li>
                    <li><a href="#part3">Part 3: Working with Agent Boundaries</a></li>
                    <li><a href="#part4">Part 4: Testing Your Implementation</a></li>
                    <li><a href="#part5">Part 5: Agent Boundary Testing</a></li>
                    <li><a href="#troubleshooting">Troubleshooting Quick Reference</a></li>
                    <li><a href="#bonus">Bonus Challenges</a></li>
                    <li><a href="#resources">Resources & Next Steps</a></li>
                </ul>
            </div>

            <section id="overview">
                <h2>Workshop Overview</h2>
                <p>Build fast. Stay secure. Ship with confidence.</p>
                <p>Participants will use Coder's workspace agents, configured with boundary controls, to collaboratively solve GitHub issues on a React memory card game. This workshop demonstrates enterprise-ready AI-assisted workflows within secure, auditable environments.</p>
            </section>

            <section id="prerequisites">
                <h2>Prerequisites</h2>
                <ul>
                    <li>GitHub Account</li>
                    <li>This Workshop Guide</li>
                    <li>Workshop repository: <a href="https://github.com/coder-contrib/memory-card-ai-demo" target="_blank">github.com/coder-contrib/memory-card-ai-demo</a> (1st browser tab)</li>
                    <li>Coder: <a href="https://ai.coder.com" target="_blank">ai.coder.com</a> (2nd browser tab)</li>
                </ul>
            </section>

            <section id="part1">
                <h2>Part 1: Workspace Launch (5 minutes)</h2>
                <p>Two ways to spin up your workspace. Pick whichever fits your workflow.</p>

                <div class="method-tabs">
                    <button class="method-tab active" onclick="switchMethod('a', this)">Method A: Coder Dashboard</button>
                    <button class="method-tab" onclick="switchMethod('b', this)">Method B: GitHub Issue</button>
                </div>

                <div id="method-a" class="method-content active">
                    <span class="method-label label-a">Method A</span>
                    <h3>Launch from the Coder Dashboard</h3>

                    <h4><span class="step-number">1</span> Access Coder</h4>
                    <ol>
                        <li>Navigate to <a href="https://ai.coder.com" target="_blank">ai.coder.com</a></li>
                        <li>Log in with your GitHub account</li>
                    </ol>

                    <h4><span class="step-number">2</span> Launch Workshop Workspace</h4>
                    <ol>
                        <li>Click <strong>"Tasks"</strong> in the Coder dashboard</li>
                        <li>Select <strong>"Memory Game App"</strong> from the template dropdown</li>
                        <li>In the "Prompt your AI agent to start a task…" box, type:</li>
                    </ol>

                    <div class="prompt-box">
                        <button class="copy-btn" onclick="copyPrompt(this)">Copy</button>
                        <pre>Start workspace and list issues in the repository by issue number. Analyze each issue thoroughly and await for further prompts.</pre>
                    </div>

                    <ul>
                        <li>Click the <strong>"up" arrow</strong> on the bottom right</li>
                        <li>Below the prompt window, a task will initialize — hover over it and click to enter the workspace</li>
                        <li>Wait for automatic provisioning (~2 minutes). The screen will be briefly blank as the workspace starts up</li>
                    </ul>

                    <div class="info-box">
                        <strong>What's happening automatically:</strong>
                        <ul style="margin-top: 10px;">
                            <li>Repository is cloned</li>
                            <li>Dependencies are installed</li>
                            <li>Development server starts</li>
                            <li>Issues are loaded into the AI's memory</li>
                            <li>Agent boundaries are automatically configured</li>
                        </ul>
                    </div>

                    <h4><span class="step-number">3</span> Access Your Workspace</h4>
                    <div class="success-box">
                        <p>Once provisioned, you'll see:</p>
                        <ul style="margin-top: 10px;">
                            <li>IDE/Editor ready</li>
                            <li>Terminal access</li>
                            <li>App running at a provided URL</li>
                            <li>AI assistant with issues pre-loaded</li>
                        </ul>
                    </div>
                    <p>Select the <strong>"Preview App"</strong> tab to view and start playing the Memory Card Game.</p>
                </div>

                <div id="method-b" class="method-content">
                    <span class="method-label label-b">Method B</span>
                    <h3>Launch from a GitHub Issue</h3>
                    <p>Trigger a workspace directly from the repository — no dashboard required.</p>

                    <h4><span class="step-number">1</span> Open the Workshop Repository</h4>
                    <ol>
                        <li>Navigate to <a href="https://github.com/coder-contrib/memory-card-ai-demo" target="_blank">github.com/coder-contrib/memory-card-ai-demo</a></li>
                        <li>Click the <strong>"Issues"</strong> tab to see the list of open issues</li>
                    </ol>

                    <div class="info-box">
                        <strong>Available issues:</strong>
                        <ul style="margin-top: 10px;">
                            <li><strong>#980</strong> — Add a countdown timer</li>
                            <li><strong>#979</strong> — Create theme selector</li>
                            <li><strong>#978</strong> — Implement high score persistence</li>
                            <li><strong>#977</strong> — Add an option to choose difficulty levels (4x4, 6x6, 8x8 grids)</li>
                            <li><strong>#976</strong> — Change card back design</li>
                        </ul>
                    </div>

                    <h4><span class="step-number">2</span> Select an Issue</h4>
                    <p>Click on any issue to open it. Pick one that matches your comfort level — <strong>#976</strong> is a great starting point.</p>

                    <h4><span class="step-number">3</span> Trigger the Agent</h4>
                    <p>Scroll to the comment box at the bottom of the issue and type:</p>

                    <div class="prompt-box">
                        <button class="copy-btn" onclick="copyPrompt(this)">Copy</button>
                        <pre>@coder-contrib-bot</pre>
                    </div>

                    <p>Submit the comment. This triggers a GitHub Action that automatically:</p>
                    <div class="info-box">
                        <ul style="margin-top: 0;">
                            <li>Provisions a Coder workspace for the issue</li>
                            <li>Clones the repository and installs dependencies</li>
                            <li>Starts the development server</li>
                            <li>Configures the AI agent with the issue context and boundaries</li>
                            <li>Creates a feature branch for your work</li>
                        </ul>
                    </div>

                    <h4><span class="step-number">4</span> Access Your Workspace</h4>
                    <p>The bot will reply to the issue with a direct link to your provisioned workspace. Click the link to jump straight in.</p>
                    <div class="success-box">
                        <p>Once provisioned, you'll see:</p>
                        <ul style="margin-top: 10px;">
                            <li>IDE/Editor ready</li>
                            <li>Terminal access</li>
                            <li>App running at a provided URL</li>
                            <li>AI assistant with the selected issue pre-loaded</li>
                        </ul>
                    </div>
                    <p>Select the <strong>"Preview App"</strong> tab to view and start playing the Memory Card Game.</p>
                </div>
            </section>

            <section id="part2">
                <h2>Part 2: Verify Setup & Explore</h2>

                <h3>Quick Verification</h3>
                <ol>
                    <li><strong>Test the Game:</strong>
                        <ul>
                            <li>Click cards to flip them</li>
                            <li>Match pairs to score points</li>
                            <li>Click "Reset Game" button</li>
                        </ul>
                    </li>
                    <li><strong>Check AI Assistant:</strong>
                        <ul>
                            <li>Open the AI chat panel</li>
                            <li>Verify you see the available issues listed</li>
                        </ul>
                    </li>
                    <li><strong>Review Available Issues:</strong>
                        <ul>
                            <li>Issue #976: Change card back design <span class="difficulty-badge beginner">Easy</span></li>
                            <li>Issue #977: Add difficulty levels (4x4, 6x6, 8x8 grids)</li>
                            <li>Issue #978: Implement high score persistence</li>
                            <li>Issue #979: Create theme selector</li>
                            <li>Issue #980: Add countdown timer</li>
                        </ul>
                    </li>
                </ol>
            </section>

            <section id="part3">
                <h2>Part 3: Working with Agent Boundaries</h2>

                <h3>Understanding Your Agent</h3>
                <p>Your workspace's agent comes with specific boundaries:</p>

                <table>
                    <thead>
                        <tr>
                            <th>Purpose</th>
                            <th>Boundaries</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>Code editing & testing</td>
                            <td>Read/write access to the project using Node.js toolset</td>
                        </tr>
                        <tr>
                            <td>Building & validation</td>
                            <td>Follow step-by-step workflow for a given project</td>
                        </tr>
                        <tr>
                            <td>Git operations & PRs</td>
                            <td>Execute Git operations only to non-main/master branches</td>
                        </tr>
                    </tbody>
                </table>

                <h3>AI Assistant Prompts for Development</h3>

                <h4>Prompt 1: Select and start an issue</h4>
                <p><em>Best practice: solve one issue at a time.</em></p>

                <div class="prompt-box">
                    <button class="copy-btn" onclick="copyPrompt(this)">Copy</button>
                    <pre>I want to work on Issue #[NUMBER]. Please:
1. Review the issue requirements
2. Create a feature branch following the pattern: coder-contrib/issue-[NUMBER]-[description]
3. Explain your implementation approach
4. Start implementing the solution</pre>
                </div>

                <p><strong>Example for Beginners (Issue #976):</strong></p>
                <div class="prompt-box">
                    <button class="copy-btn" onclick="copyPrompt(this)">Copy</button>
                    <pre>I want to work on Issue #976 to add a red diamond to card backs. Please:
- Review the card rendering in App.jsx
- Create branch: coder-contrib/issue-976-card-back-diamond
- Modify the card back display to show a red diamond emoji or SVG
- Ensure it only shows when cards are face down</pre>
                </div>

                <h4>Prompt 2: Implement with Testing</h4>

                <div class="prompt-box">
                    <button class="copy-btn" onclick="copyPrompt(this)">Copy</button>
                    <pre>For Issue #[NUMBER], please:
- Complete the implementation based on acceptance criteria
- Test each requirement locally
- Ensure the game still functions properly
- Show me the key changes you made</pre>
                </div>

                <p><strong>Example for Intermediate (Issue #980):</strong></p>
                <div class="prompt-box">
                    <button class="copy-btn" onclick="copyPrompt(this)">Copy</button>
                    <pre>For Issue #980 (countdown timer), please:
- Add a 60-second countdown timer that displays prominently
- Implement lose condition when timer reaches zero
- Show "Time's Up!" message on timeout
- Return to start screen after timeout
- Ensure timer pauses on win and resets on game reset
- Test all scenarios</pre>
                </div>

                <h4>Prompt 3: Commit and Create PR</h4>

                <div class="prompt-box">
                    <button class="copy-btn" onclick="copyPrompt(this)">Copy</button>
                    <pre>Please prepare my work for review:
- Stage all changes
- Create a descriptive commit message
- Push to the feature branch
- Create a pull request with:
  * Title: "Fix #[NUMBER]: [Brief description]"
  * Description of changes
  * How it addresses the issue
  * Testing performed</pre>
                </div>

                <h3>Sample Implementation Workflows</h3>

                <h4><span class="difficulty-badge beginner">Beginner</span> Path (Issue #976 or #978)</h4>

                <p><strong>Issue #976 — Card Back Design:</strong></p>
                <div class="prompt-box">
                    <button class="copy-btn" onclick="copyPrompt(this)">Copy</button>
                    <pre>Agent, let's add a red diamond to the card backs:
- Locate where card backs are rendered
- Add a red diamond with proper styling
- Make it large and centered on the card back
- Test that it only appears on unflipped cards</pre>
                </div>

                <p><strong>Issue #978 — High Score:</strong></p>
                <div class="prompt-box">
                    <button class="copy-btn" onclick="copyPrompt(this)">Copy</button>
                    <pre>Agent, implement high score tracking:
- Add state for best score (lowest moves)
- Use localStorage to persist between sessions
- Display "Best: X moves" in the UI
- Update only when current score beats the best
- Add a running total of games played</pre>
                </div>

                <h4><span class="difficulty-badge intermediate">Intermediate</span> Path (Issue #979 or #980)</h4>

                <p><strong>Issue #979 — Theme Selector:</strong></p>
                <div class="prompt-box">
                    <button class="copy-btn" onclick="copyPrompt(this)">Copy</button>
                    <pre>Agent, create a theme selector with these requirements:
- Add theme options: Animals, Emoji, and Flags
- Create arrays of matching symbols for each theme
- Add UI to select theme before game starts
- Update cards based on selected theme</pre>
                </div>

                <p><strong>Issue #980 — Timer Challenge:</strong></p>
                <div class="prompt-box">
                    <button class="copy-btn" onclick="copyPrompt(this)">Copy</button>
                    <pre>Agent, implement the countdown timer feature:
- Create a 60-second countdown
- Display timer prominently (suggest top-right)
- Add lose detection at 0 seconds
- Show modal: "Time's Up! You ran out of time."
- Include "Play Again" button to restart
- Timer should pause when game is won</pre>
                </div>

                <h4><span class="difficulty-badge advanced">Advanced</span> Path (Issue #977)</h4>

                <p><strong>Issue #977 — Multiple Difficulty Levels:</strong></p>
                <div class="prompt-box">
                    <button class="copy-btn" onclick="copyPrompt(this)">Copy</button>
                    <pre>Agent, implement difficulty selection:
- Add selection UI before game start
- Create three options:
  * Easy: 4x4 grid (8 pairs)
  * Medium: 6x6 grid (18 pairs)
  * Hard: 8x8 grid (32 pairs)
- Dynamically adjust grid CSS
- Scale card symbols appropriately
- Display current difficulty during gameplay
- Allow difficulty change after game completion</pre>
                </div>
            </section>

            <section id="part4">
                <h2>Part 4: Testing Your Implementation</h2>

                <h3>Manual Testing Checklist</h3>
                <p>Run through these tests based on your implemented feature:</p>

                <h4>For All Features:</h4>
                <ul class="checklist">
                    <li>Original game functionality still works</li>
                    <li>No console errors</li>
                    <li>Reset button works properly</li>
                    <li>Win condition still triggers</li>
                </ul>

                <h4>Feature-Specific Tests:</h4>

                <p><strong>Card Back — Issue #976:</strong></p>
                <ul class="checklist">
                    <li>Diamond visible on all unflipped cards</li>
                    <li>Diamond disappears when card flipped</li>
                    <li>Diamond reappears if non-match</li>
                </ul>

                <p><strong>Difficulty Levels — Issue #977:</strong></p>
                <ul class="checklist">
                    <li>All difficulty levels selectable</li>
                    <li>Grid adjusts properly</li>
                    <li>Correct number of pairs</li>
                    <li>Cards remain clickable</li>
                    <li>Layout is responsive</li>
                </ul>

                <p><strong>High Score — Issue #978:</strong></p>
                <ul class="checklist">
                    <li>Best score displays</li>
                    <li>Updates only when beaten</li>
                    <li>Persists after page refresh</li>
                    <li>Games played counter increments</li>
                </ul>

                <p><strong>Theme Selector — Issue #979:</strong></p>
                <ul class="checklist">
                    <li>All themes selectable</li>
                    <li>Cards update to match theme</li>
                    <li>Themes have enough unique pairs</li>
                    <li>Theme persists during game</li>
                </ul>

                <p><strong>Timer — Issue #980:</strong></p>
                <ul class="checklist">
                    <li>Starts at 60 seconds</li>
                    <li>Counts down properly</li>
                    <li>Shows lose modal at 0</li>
                    <li>Pauses on win</li>
                    <li>Resets with game</li>
                </ul>
            </section>

            <section id="part5">
                <h2>Part 5: Agent Boundary Testing (10 minutes)</h2>

                <p>Test the guardrails. In the prompt chat window, attempt to pull down an application from another repository instance (Bitbucket). The agent will report the request as blocked by Boundary.</p>

                <div class="prompt-box">
                    <button class="copy-btn" onclick="copyPrompt(this)">Copy</button>
                    <pre>Agent, Clone https://bitbucket.org/coder-contrib/memory-card-ai-demo.git to /tmp</pre>
                </div>
            </section>

            <section id="troubleshooting">
                <h2>Troubleshooting Quick Reference</h2>

                <h4>AI Assistant Not Responding:</h4>
                <div class="prompt-box">
                    <button class="copy-btn" onclick="copyPrompt(this)">Copy</button>
                    <pre>Please check your connection and retry the last command.
If issues persist, refresh the AI chat panel.</pre>
                </div>

                <h4>Code Changes Not Appearing:</h4>
                <div class="prompt-box">
                    <button class="copy-btn" onclick="copyPrompt(this)">Copy</button>
                    <pre>Agent, please:
1. Save all files
2. Restart the development server
3. Clear browser cache and refresh</pre>
                </div>

                <h4>Git Push Errors:</h4>
                <div class="prompt-box">
                    <button class="copy-btn" onclick="copyPrompt(this)">Copy</button>
                    <pre>Agent, please help resolve git authentication:
1. Check my git configuration
2. Verify branch permissions
3. Try pushing again with verbose output</pre>
                </div>

                <h4>Build/Test Failures:</h4>
                <div class="prompt-box">
                    <button class="copy-btn" onclick="copyPrompt(this)">Copy</button>
                    <pre>Agent, please diagnose the build failure:
1. Show me the full error message
2. Identify the root cause
3. Suggest a fix
4. Implement the correction</pre>
                </div>
            </section>

            <section id="bonus">
                <h2>Bonus Challenges</h2>

                <h3>Challenge A: Combine Features</h3>
                <p>Finished early? Stack two issues in one branch:</p>
                <div class="prompt-box">
                    <button class="copy-btn" onclick="copyPrompt(this)">Copy</button>
                    <pre>Agent, I've completed Issue #[FIRST]. Now let's also implement Issue #[SECOND]
in the same branch. Make sure both features work together seamlessly.</pre>
                </div>

                <h3>Challenge B: Add Your Own Enhancement</h3>
                <div class="prompt-box">
                    <button class="copy-btn" onclick="copyPrompt(this)">Copy</button>
                    <pre>Agent, I want to add a custom feature not in the issues:
[Describe your feature idea]
Please implement it following the same quality standards.</pre>
                </div>

                <h3>Challenge C: Code Review</h3>
                <p>Exchange PR links with another participant:</p>
                <div class="prompt-box">
                    <button class="copy-btn" onclick="copyPrompt(this)">Copy</button>
                    <pre>Agent, please review this PR: [URL]
1. Check for code quality
2. Verify it meets issue requirements
3. Suggest any improvements
4. Leave constructive comments</pre>
                </div>
            </section>

            <section id="takeaways">
                <h2>Key Takeaways</h2>
                <p>By the end of this workshop, you will have:</p>
                <ul>
                    <li>Experienced Coder's agent boundaries in action</li>
                    <li>Used AI assistance for real development tasks</li>
                    <li>Created a feature branch and PR</li>
                    <li>Understood enterprise-secure AI development workflows</li>
                </ul>
            </section>

            <section id="resources">
                <h2>Resources & Next Steps</h2>
                <ul>
                    <li>Try Coder Open Source: <a href="https://github.com/orgs/coder" target="_blank">github.com/orgs/coder</a></li>
                    <li>Coder Documentation: <a href="https://coder.com/docs" target="_blank">coder.com/docs</a></li>
                    <li>Agent Boundaries Guide: <a href="https://coder.com/docs/agents/boundaries" target="_blank">coder.com/docs/agents/boundaries</a></li>
                    <li>Workshop Repository: <a href="https://github.com/coder-contrib/memory-card-ai-demo" target="_blank">github.com/coder-contrib/memory-card-ai-demo</a></li>
                </ul>
            </section>

            <div class="footer">
                <h3>Thank you for participating!</h3>
                <p>Code with clarity. Scale with certainty.</p>
            </div>
        </div>
    </div>

    <script>
        function toggleTheme() {
            var html = document.documentElement;
            var current = html.getAttribute('data-theme');
            var next = current === 'dark' ? 'light' : 'dark';
            html.setAttribute('data-theme', next);
        }

        function copyPrompt(button) {
            var pre = button.parentElement.querySelector('pre');
            navigator.clipboard.writeText(pre.textContent).then(function() {
                var orig = button.textContent;
                button.textContent = 'Copied!';
                button.classList.add('copied');
                setTimeout(function() { button.textContent = orig; button.classList.remove('copied'); }, 2000);
            }).catch(function() {
                button.textContent = 'Failed';
                setTimeout(function() { button.textContent = 'Copy'; }, 2000);
            });
        }

        function switchMethod(method, btn) {
            var tabs = document.querySelectorAll('.method-tab');
            var contents = document.querySelectorAll('.method-content');
            for (var i = 0; i < tabs.length; i++) { tabs[i].classList.remove('active'); }
            for (var i = 0; i < contents.length; i++) { contents[i].classList.remove('active'); }
            document.getElementById('method-' + method).classList.add('active');
            btn.classList.add('active');
        }

        document.querySelectorAll('a[href^="#"]').forEach(function(anchor) {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                var target = document.querySelector(this.getAttribute('href'));
                if (target) target.scrollIntoView({ behavior: 'smooth', block: 'start' });
            });
        });
    </script>
</body>
</html>
