<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Pratik Fulkar · Applied AI &amp; Agent Systems — End‑to‑End Study &amp; Interview Guide</title>
<style>
  /* ============ RESET & BASE ============ */
  *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }
  html { scroll-behavior: smooth; scroll-padding-top: 80px; }
  body {
    font-family: system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', sans-serif;
    background: #f8fafc;
    color: #0f172a;
    line-height: 1.65;
    font-size: 16px;
  }
  a { color: #2563eb; text-decoration: none; }
  a:hover { text-decoration: underline; }

  /* ============ LAYOUT ============ */
  .layout { display: flex; min-height: 100vh; }

  /* Sidebar nav */
  .sidebar {
    width: 260px;
    background: #0f172a;
    color: #cbd5e1;
    padding: 1.5rem 1rem;
    position: sticky;
    top: 0;
    height: 100vh;
    overflow-y: auto;
    flex-shrink: 0;
    font-size: 0.875rem;
  }
  .sidebar h3 {
    color: #93c5fd;
    font-size: 0.75rem;
    font-weight: 700;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    margin: 1.25rem 0 0.5rem 0;
  }
  .sidebar a {
    display: block;
    color: #cbd5e1;
    padding: 0.35rem 0.6rem;
    border-radius: 0.35rem;
    font-size: 0.85rem;
    transition: background 0.15s, color 0.15s;
  }
  .sidebar a:hover { background: #1e293b; color: #ffffff; text-decoration: none; }
  .sidebar .brand {
    font-size: 1.05rem;
    font-weight: 800;
    color: #ffffff;
    margin-bottom: 0.25rem;
    letter-spacing: -0.02em;
  }
  .sidebar .brand small {
    display: block;
    font-size: 0.7rem;
    color: #94a3b8;
    font-weight: 400;
    letter-spacing: 0;
    margin-top: 0.15rem;
  }

  /* Main content */
  .main {
    flex: 1;
    padding: 2rem 3rem 4rem;
    max-width: 100%;
    overflow-x: hidden;
  }

  /* Mobile */
  .mobile-nav { display: none; }
  @media (max-width: 960px) {
    .sidebar { display: none; }
    .main { padding: 1.25rem 1.25rem 3rem; }
    .mobile-nav {
      display: block;
      background: #0f172a;
      padding: 0.75rem 1rem;
      position: sticky;
      top: 0;
      z-index: 100;
    }
    .mobile-nav summary {
      color: #ffffff;
      cursor: pointer;
      font-weight: 700;
      font-size: 0.95rem;
    }
    .mobile-nav nav { margin-top: 0.75rem; }
    .mobile-nav a { display: block; color: #cbd5e1; padding: 0.3rem 0; font-size: 0.85rem; }
  }

  /* ============ TYPOGRAPHY ============ */
  h1 {
    font-size: 2.4rem;
    font-weight: 800;
    letter-spacing: -0.03em;
    color: #0b1e33;
    line-height: 1.15;
    margin-bottom: 0.5rem;
  }
  h1 small {
    display: block;
    font-size: 1.05rem;
    font-weight: 400;
    color: #475569;
    letter-spacing: 0;
    margin-top: 0.5rem;
  }
  h2 {
    font-size: 1.65rem;
    font-weight: 700;
    color: #1e3a8a;
    letter-spacing: -0.02em;
    margin: 3rem 0 1rem 0;
    padding-left: 1rem;
    border-left: 6px solid #3b82f6;
  }
  h2:first-of-type { margin-top: 1.5rem; }
  h3 {
    font-size: 1.2rem;
    font-weight: 650;
    color: #1e293b;
    margin: 1.75rem 0 0.6rem 0;
  }
  h4 {
    font-size: 1rem;
    font-weight: 650;
    color: #334155;
    margin: 1.25rem 0 0.4rem 0;
  }
  p { margin-bottom: 0.9rem; color: #1e293b; }
  ul, ol { margin: 0.5rem 0 1rem 1.5rem; color: #1e293b; }
  li { margin: 0.3rem 0; }

  /* ============ CODE BLOCKS — CLEAN ============ */
  pre {
    background: #0f172a;
    color: #e2e8f0;
    padding: 1.15rem 1.4rem;
    border-radius: 0.75rem;
    overflow-x: auto;
    font-family: 'JetBrains Mono', 'Fira Code', 'Cascadia Code', 'SF Mono', ui-monospace, monospace;
    font-size: 0.83rem;
    line-height: 1.6;
    margin: 0.85rem 0 1.25rem 0;
    border: 1px solid #1e293b;
    box-shadow: inset 0 1px 0 rgba(255,255,255,0.04);
    tab-size: 4;
  }
  pre code {
    background: transparent;
    color: inherit;
    font-family: inherit;
    font-size: inherit;
    padding: 0;
    border-radius: 0;
  }
  code:not(pre code) {
    background: #e2e8f0;
    color: #0f172a;
    padding: 0.12rem 0.4rem;
    border-radius: 0.3rem;
    font-family: 'JetBrains Mono', 'Fira Code', monospace;
    font-size: 0.85em;
    font-weight: 500;
  }
  /* Syntax highlighting */
  .kw  { color: #93c5fd; }
  .str { color: #86efac; }
  .cmt { color: #94a3b8; font-style: italic; }
  .fn  { color: #fde047; }
  .dec { color: #c084fc; }
  .num { color: #fdba74; }
  .kw2 { color: #f0abfc; }

  /* ============ CARDS & BOXES ============ */
  .card {
    background: #f1f5f9;
    border-radius: 1rem;
    padding: 1.25rem 1.5rem;
    margin: 1.25rem 0;
    border: 1px solid #e2e8f0;
  }
  .card-title {
    font-weight: 700;
    font-size: 1.05rem;
    margin-bottom: 0.6rem;
    color: #0f172a;
  }
  .qa {
    background: #f8fafc;
    border-left: 4px solid #3b82f6;
    padding: 1rem 1.5rem;
    border-radius: 0 0.75rem 0.75rem 0;
    margin: 1.2rem 0;
  }
  .qa strong { color: #1e3a8a; }
  .tip {
    background: #fef9c3;
    border-left: 6px solid #eab308;
    padding: 0.9rem 1.5rem;
    border-radius: 0 0.75rem 0.75rem 0;
    margin: 1.2rem 0;
    color: #422006;
  }
  .tip strong { color: #854d0e; }
  .warn {
    background: #fee2e2;
    border-left: 6px solid #ef4444;
    padding: 0.9rem 1.5rem;
    border-radius: 0 0.75rem 0.75rem 0;
    margin: 1.2rem 0;
    color: #7f1d1d;
  }
  .warn strong { color: #991b1b; }
  .ok {
    background: #dcfce7;
    border-left: 6px solid #22c55e;
    padding: 0.9rem 1.5rem;
    border-radius: 0 0.75rem 0.75rem 0;
    margin: 1.2rem 0;
    color: #14532d;
  }
  .ok strong { color: #166534; }

  .badge {
    display: inline-block;
    background: #3b82f6;
    color: #ffffff;
    font-size: 0.68rem;
    font-weight: 700;
    padding: 0.18rem 0.6rem;
    border-radius: 999px;
    letter-spacing: 0.04em;
    text-transform: uppercase;
    margin-right: 0.4rem;
    vertical-align: middle;
  }
  .badge.green { background: #16a34a; }
  .badge.amber { background: #d97706; }
  .badge.red   { background: #dc2626; }
  .badge.gray  { background: #475569; }
  .badge.purple{ background: #7c3aed; }

  .pill {
    display: inline-block;
    background: #dbeafe;
    color: #1e40af;
    font-weight: 600;
    padding: 0.22rem 0.7rem;
    border-radius: 999px;
    font-size: 0.72rem;
    margin: 0.15rem 0.25rem 0.15rem 0;
    white-space: nowrap;
  }

  /* ============ TABLES ============ */
  table {
    width: 100%;
    border-collapse: collapse;
    margin: 0.85rem 0 1.25rem 0;
    font-size: 0.87rem;
    background: #ffffff;
    border-radius: 0.5rem;
    overflow: hidden;
    box-shadow: 0 0 0 1px #e2e8f0;
  }
  th, td { text-align: left; padding: 0.6rem 0.85rem; border-bottom: 1px solid #e2e8f0; vertical-align: top; }
  th { background: #f1f5f9; font-weight: 650; color: #0f172a; font-size: 0.82rem; text-transform: uppercase; letter-spacing: 0.03em; }
  tr:last-child td { border-bottom: none; }
  tr:hover { background: #f8fafc; }

  /* ============ MISC ============ */
  hr { border: 0; height: 1px; background: #e2e8f0; margin: 2.5rem 0; }
  .section-lead { font-size: 1.02rem; color: #334155; margin-bottom: 1.25rem; }
  .grid-2 { display: grid; grid-template-columns: 1fr 1fr; gap: 1.25rem; margin: 1rem 0; }
  @media (max-width: 700px) { .grid-2 { grid-template-columns: 1fr; } }
  .grid-3 { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1rem; margin: 1rem 0; }
  @media (max-width: 900px) { .grid-3 { grid-template-columns: 1fr; } }

  .kpi {
    background: linear-gradient(135deg, #1e3a8a, #3b82f6);
    color: #ffffff;
    padding: 1rem 1.25rem;
    border-radius: 0.75rem;
    text-align: center;
  }
  .kpi .num-big { font-size: 1.5rem; font-weight: 800; display: block; }
  .kpi .lbl { font-size: 0.75rem; opacity: 0.9; letter-spacing: 0.03em; text-transform: uppercase; }

  .hero {
    background: linear-gradient(135deg, #0f172a 0%, #1e3a8a 100%);
    color: #ffffff;
    padding: 2rem 2.5rem;
    border-radius: 1.25rem;
    margin-bottom: 2rem;
  }
  .hero h1 { color: #ffffff; }
  .hero h1 small { color: #cbd5e1; }
  .hero .hero-meta { margin-top: 1rem; display: flex; flex-wrap: wrap; gap: 0.4rem; }

  footer {
    text-align: center;
    margin-top: 4rem;
    padding-top: 1.5rem;
    border-top: 1px solid #e2e8f0;
    color: #64748b;
    font-size: 0.82rem;
  }

  .toc-quick { display: flex; flex-wrap: wrap; gap: 0.4rem; margin: 0.5rem 0 1.5rem 0; }

  /* Print */
  @media print {
    body { background: #fff; }
    .sidebar, .mobile-nav { display: none; }
    .main { padding: 0; }
    pre { background: #f1f5f9; color: #0f172a; border: 1px solid #cbd5e1; }
    .kw, .str, .cmt, .fn, .dec, .num, .kw2 { color: #0f172a !important; font-style: normal !important; }
    h2 { page-break-after: avoid; }
    pre, table, .card, .qa, .tip { page-break-inside: avoid; }
  }
</style>
</head>
<body>

<!-- ============ MOBILE NAV ============ -->
<details class="mobile-nav">
  <summary>☰ Sections</summary>
  <nav>
    <a href="#s1">1. Profile &amp; Career Target</a>
    <a href="#s2">2. Python Foundations</a>
    <a href="#s3">3. Asyncio &amp; Concurrency</a>
    <a href="#s4">4. HTTP Clients</a>
    <a href="#s5">5. FastAPI</a>
    <a href="#s6">6. Pydantic</a>
    <a href="#s7">7. PostgreSQL</a>
    <a href="#s8">8. Mini End‑to‑End Project</a>
    <a href="#s9">9. System Design — Master + 2 Replicas</a>
    <a href="#s10">10. Username &amp; Platform Strategy</a>
    <a href="#s11">11. Reddit Bio</a>
    <a href="#s12">12. GitHub README (Updated)</a>
    <a href="#s13">13. Interview Cross‑Questions</a>
    <a href="#s14">14. Common Mistakes</a>
    <a href="#s15">15. Cheat Sheet</a>
    <a href="#s16">16. Timeline &amp; Milestones</a>
  </nav>
</details>

<div class="layout">

  <!-- ============ SIDEBAR ============ -->
  <aside class="sidebar">
    <div class="brand">
      Pratik Fulkar
      <small>Applied AI &amp; Agent Systems</small>
    </div>

    <h3>Study</h3>
    <a href="#s1">1 · Profile &amp; Career Target</a>
    <a href="#s2">2 · Python Foundations</a>
    <a href="#s3">3 · Asyncio &amp; Concurrency</a>
    <a href="#s4">4 · HTTP Clients</a>
    <a href="#s5">5 · FastAPI</a>
    <a href="#s6">6 · Pydantic</a>
    <a href="#s7">7 · PostgreSQL</a>
    <a href="#s8">8 · Mini End‑to‑End Project</a>

    <h3>Interview</h3>
    <a href="#s9">9 · Master + 2 Replicas</a>
    <a href="#s13">13 · Cross‑Questions</a>
    <a href="#s14">14 · Common Mistakes</a>

    <h3>Brand</h3>
    <a href="#s10">10 · Username &amp; Platforms</a>
    <a href="#s11">11 · Reddit Bio</a>
    <a href="#s12">12 · GitHub README</a>

    <h3>Reference</h3>
    <a href="#s15">15 · Cheat Sheet</a>
    <a href="#s16">16 · Timeline</a>
  </aside>

  <!-- ============ MAIN ============ -->
  <main class="main">

    <!-- ===== HERO ===== -->
    <section class="hero">
      <h1>
        Pratik Fulkar — End‑to‑End Study Guide
        <small>Python · Asyncio · FastAPI · Pydantic · PostgreSQL · Agent Systems · Interview‑Ready (2026–2028)</small>
      </h1>
      <div class="hero-meta">
        <span class="pill">Phase A · Nov–Dec 2026</span>
        <span class="pill">Target ₹30–35 LPA · Jun 2027</span>
        <span class="pill">Applied AI &amp; Agent Systems</span>
        <span class="pill">Interview + Project + Build‑in‑Public</span>
      </div>
    </section>

    <p class="section-lead">
      This is a single, self‑contained reference for your Phase A study, interview preparation, and
      build‑in‑public execution. Every code example is minimal and copy‑pasteable.
      Every “Remember” and “Thinking” box is what an interviewer wants to hear.
    </p>

    <div class="toc-quick">
      <a href="#s1" class="pill">Profile</a>
      <a href="#s2" class="pill">Python</a>
      <a href="#s3" class="pill">Async</a>
      <a href="#s4" class="pill">HTTP</a>
      <a href="#s5" class="pill">FastAPI</a>
      <a href="#s6" class="pill">Pydantic</a>
      <a href="#s7" class="pill">PostgreSQL</a>
      <a href="#s8" class="pill">Mini Project</a>
      <a href="#s9" class="pill">System Design</a>
      <a href="#s10" class="pill">Username</a>
      <a href="#s11" class="pill">Reddit</a>
      <a href="#s12" class="pill">GitHub</a>
      <a href="#s13" class="pill">Interview Qs</a>
      <a href="#s14" class="pill">Mistakes</a>
      <a href="#s15" class="pill">Cheat Sheet</a>
      <a href="#s16" class="pill">Timeline</a>
    </div>

    <!-- ================================================================ -->
    <!-- SECTION 1 — PROFILE -->
    <!-- ================================================================ -->
    <h2 id="s1">1 · Profile &amp; Career Target</h2>

    <div class="grid-2">
      <div class="card">
        <div class="card-title">👤 Who you are</div>
        <p><strong>Pratik Fulkar</strong> · Mumbai, India</p>
        <p>Senior Software Engineer · 5+ years · current role: Altisource (Remote)</p>
        <p>Previous: Flashaid (Aug 2021 – Aug 2024) — scaled platform to ~50K users, supported $2.2M funding.</p>
        <p>B.Tech, Electronics &amp; Telecommunication — Dr. Babasaheb Ambedkar Technological University, May 2021.</p>
      </div>
      <div class="card">
        <div class="card-title">🎯 Where you're going</div>
        <p><strong>Lane:</strong> Senior Applied AI Engineer / AI Agent Systems Engineer.</p>
        <p><strong>Current CTC:</strong> ₹19 LPA · <strong>Target:</strong> ₹30–35 LPA (stretch ₹35–40 LPA).</p>
        <p><strong>Positioning:</strong> Strong backend + SaaS + workflow experience, now specializing in Applied AI, LLM applications, agent systems, evaluation and production reliability.</p>
        <p><strong>Not:</strong> ML researcher, model trainer. Don't claim fine‑tuning, PyTorch or deep ML expertise unless you have done that work.</p>
      </div>
    </div>

    <div class="grid-3">
      <div class="kpi"><span class="num-big">5+ yrs</span><span class="lbl">Software Engineering</span></div>
      <div class="kpi"><span class="num-big">3</span><span class="lbl">Portfolio Projects</span></div>
      <div class="kpi"><span class="num-big">Jun 2027</span><span class="lbl">Target Milestone</span></div>
    </div>

    <div class="card">
      <div class="card-title">🏗️ The 3 projects (45 / 30 / 25 % effort)</div>
      <table>
        <tr><th>Project</th><th>Purpose</th><th>Effort</th></tr>
        <tr><td><strong>🛡️ AgentGuard</strong></td><td>Evaluation, observability, reliability &amp; security layer for tool‑using AI agents</td><td>~45%</td></tr>
        <tr><td><strong>🏢 Enterprise Workflow Agent</strong></td><td>Multi‑system incident investigation with MCP tool integrations, human‑in‑the‑loop approvals</td><td>~30%</td></tr>
        <tr><td><strong>🔍 CodeShift</strong></td><td>Behavioral verification for AI‑assisted code migration (differential + property‑based testing)</td><td>~25%</td></tr>
      </table>
    </div>

    <div class="ok">
      <strong>✅ Phase A exit test (this guide's target):</strong> Build a tested FastAPI service that
      calls an LLM, validates structured output, persists results in PostgreSQL, and handles timeout/retry failures.
    </div>

    <!-- ================================================================ -->
    <!-- SECTION 2 — PYTHON FOUNDATIONS -->
    <!-- ================================================================ -->
    <hr />
    <h2 id="s2">2 · Python Foundations</h2>

    <h3>2.1 Data structures — when to use what</h3>

    <table>
      <tr><th>Need</th><th>Use</th><th>Why</th></tr>
      <tr><td>Ordered, will change</td><td><code>list</code></td><td>Mutable, fast append</td></tr>
      <tr><td>Fixed group of values</td><td><code>tuple</code></td><td>Immutable, hashable</td></tr>
      <tr><td>Lookup by key</td><td><code>dict</code></td><td>O(1) lookup</td></tr>
      <tr><td>Unique items, fast “is it in here?”</td><td><code>set</code></td><td>O(1) membership</td></tr>
      <tr><td>Queue with fast pop from left</td><td><code>deque</code></td><td>O(1) at both ends</td></tr>
      <tr><td>Object with named fields</td><td><code>dataclass</code></td><td>Auto <code>__init__</code>, <code>__repr__</code></td></tr>
    </table>

<pre><code><span class="cmt"># List — ordered, changeable</span>
fruits = [<span class="str">"apple"</span>, <span class="str">"banana"</span>, <span class="str">"cherry"</span>]
fruits.append(<span class="str">"mango"</span>)
fruits.insert(<span class="num">0</span>, <span class="str">"kiwi"</span>)
fruits.remove(<span class="str">"banana"</span>)
last = fruits.pop()
print(fruits[<span class="num">0</span>], fruits[-<span class="num">1</span>], fruits[<span class="num">1</span>:<span class="num">3</span>])

<span class="cmt"># Tuple — ordered, NOT changeable (use for records)</span>
point = (<span class="num">10</span>, <span class="num">20</span>)
x, y = point

<span class="cmt"># Dict — key/value lookup</span>
user = {<span class="str">"name"</span>: <span class="str">"Asha"</span>, <span class="str">"age"</span>: <span class="num">25</span>}
user[<span class="str">"city"</span>] = <span class="str">"Mumbai"</span>
print(user.get(<span class="str">"phone"</span>, <span class="str">"n/a"</span>))    <span class="cmt"># n/a</span>

<span class="cmt"># Set — unique values only</span>
a, b = {<span class="num">1</span>, <span class="num">2</span>, <span class="num">3</span>}, {<span class="num">3</span>, <span class="num">4</span>, <span class="num">5</span>}
print(a &amp; b, a | b, a - b)         <span class="cmt"># {3} {1,2,3,4,5} {1,2}</span>

<span class="cmt"># Comprehensions</span>
squares = [n * n <span class="kw">for</span> n <span class="kw">in</span> range(<span class="num">5</span>)]
evens   = [n <span class="kw">for</span> n <span class="kw">in</span> range(<span class="num">10</span>) <span class="kw">if</span> n % <span class="num">2</span> == <span class="num">0</span>]
lengths = {w: len(w) <span class="kw">for</span> w <span class="kw">in</span> [<span class="str">"hi"</span>, <span class="str">"hello"</span>]}</code></pre>

<pre><code><span class="cmt"># collections helpers</span>
<span class="kw">from</span> collections <span class="kw">import</span> Counter, defaultdict, deque

print(Counter(<span class="str">"banana"</span>))         <span class="cmt"># Counter({'a': 3, 'n': 2, 'b': 1})</span>

groups = defaultdict(list)
<span class="kw">for</span> word <span class="kw">in</span> [<span class="str">"apple"</span>, <span class="str">"avocado"</span>, <span class="str">"banana"</span>]:
    groups[word[<span class="num">0</span>]].append(word)

q = deque([<span class="num">1</span>, <span class="num">2</span>, <span class="num">3</span>])
q.append(<span class="num">4</span>); q.popleft()

<span class="cmt"># dataclass — clean data holder</span>
<span class="kw">from</span> dataclasses <span class="kw">import</span> dataclass

<span class="dec">@dataclass</span>
<span class="kw">class</span> <span class="fn">Product</span>:
    name: str
    price: float
    in_stock: bool = <span class="kw">True</span>

p = Product(<span class="str">"Pen"</span>, <span class="num">10.5</span>)
print(p)    <span class="cmt"># Product(name='Pen', price=10.5, in_stock=True)</span></code></pre>

<div class="tip">
  <strong>Remember:</strong> <code>x in my_list</code> is O(n). <code>x in my_set</code> / <code>x in my_dict</code> is O(1). For big data, membership tests on lists silently destroy performance.
</div>

<h3>2.2 Typing — hints for humans and tools</h3>

<pre><code><span class="cmt"># Basic hints</span>
<span class="kw">def</span> <span class="fn">greet</span>(name: str, times: int = <span class="num">1</span>) -&gt; str:
    <span class="kw">return</span> (<span class="str">"Hello "</span> + name + <span class="str">"! "</span>) * times

age: int = <span class="num">30</span>
price: float = <span class="num">9.99</span>

<span class="cmt"># Collections (Python 3.9+)</span>
scores: list[int] = [<span class="num">90</span>, <span class="num">80</span>]
profile: dict[str, str] = {<span class="str">"name"</span>: <span class="str">"Asha"</span>}

<span class="cmt"># Optional / Union (Python 3.10+)</span>
<span class="kw">def</span> <span class="fn">find_user</span>(user_id: int) -&gt; str | <span class="kw">None</span>:
    users = {<span class="num">1</span>: <span class="str">"Asha"</span>, <span class="num">2</span>: <span class="str">"Ravi"</span>}
    <span class="kw">return</span> users.get(user_id)

<span class="cmt"># Callable / Literal / Any</span>
<span class="kw">from</span> typing <span class="kw">import</span> Callable, Literal, Any
Mode = Literal[<span class="str">"read"</span>, <span class="str">"write"</span>]

<span class="cmt"># Generics with TypeVar</span>
<span class="kw">from</span> typing <span class="kw">import</span> TypeVar
T = TypeVar(<span class="str">"T"</span>)

<span class="kw">def</span> <span class="fn">first</span>(items: list[T]) -&gt; T:
    <span class="kw">return</span> items[<span class="num">0</span>]</code></pre>

<h3>2.3 Modules &amp; packages</h3>

<pre><code><span class="cmt"># mathutils.py</span>
<span class="kw">def</span> <span class="fn">add</span>(a: int, b: int) -&gt; int:
    <span class="kw">return</span> a + b

PI = <span class="num">3.14159</span>

<span class="kw">if</span> __name__ == <span class="str">"__main__"</span>:
    print(add(<span class="num">2</span>, <span class="num">3</span>))     <span class="cmt"># runs only when executed directly</span>

<span class="cmt"># main.py</span>
<span class="kw">from</span> mathutils <span class="kw">import</span> add, PI</code></pre>

<div class="warn">
  <strong>⚠️ Never</strong> name your file the same as a stdlib module (<code>random.py</code>, <code>json.py</code>). Python will import yours and break other libraries in confusing ways.
</div>

<h3>2.4 Exceptions</h3>

<pre><code><span class="kw">try</span>:
    number = int(<span class="str">"abc"</span>)
<span class="kw">except</span> ValueError:
    print(<span class="str">"Not a number"</span>)

<span class="cmt"># Full structure</span>
<span class="kw">def</span> <span class="fn">read_number</span>(text: str) -&gt; int | <span class="kw">None</span>:
    <span class="kw">try</span>:
        value = int(text)
    <span class="kw">except</span> ValueError <span class="kw">as</span> err:
        print(<span class="str">"Bad input:"</span>, err); <span class="kw">return</span> <span class="kw">None</span>
    <span class="kw">else</span>:
        <span class="kw">return</span> value              <span class="cmt"># only on success</span>
    <span class="kw">finally</span>:
        print(<span class="str">"done"</span>)             <span class="cmt"># always runs</span>

<span class="cmt"># Custom exceptions</span>
<span class="kw">class</span> <span class="fn">AppError</span>(Exception): ...

<span class="kw">class</span> <span class="fn">PaymentError</span>(AppError):
    <span class="kw">def</span> <span class="fn">__init__</span>(self, order_id: int, reason: str):
        <span class="kw">super</span>().__init__(f<span class="str">"Order {order_id} failed: {reason}"</span>)
        self.order_id = order_id

<span class="cmt"># Chaining errors</span>
<span class="kw">try</span>:
    int(<span class="str">"x"</span>)
<span class="kw">except</span> ValueError <span class="kw">as</span> err:
    <span class="kw">raise</span> RuntimeError(<span class="str">"Config load failed"</span>) <span class="kw">from</span> err</code></pre>

<div class="tip">
  <strong>Remember:</strong> catch the <em>specific</em> error you expect. Bare <code>except:</code> hides real bugs. In FastAPI, wrap business errors in <code>HTTPException</code>.
</div>

<h3>2.5 Iterators &amp; generators</h3>

<pre><code><span class="cmt"># Iterator: hands out one item at a time</span>
nums = [<span class="num">10</span>, <span class="num">20</span>, <span class="num">30</span>]
it = iter(nums)
print(next(it))   <span class="cmt"># 10</span>
print(next(it))   <span class="cmt"># 20</span>

<span class="cmt"># Generator: function with yield</span>
<span class="kw">def</span> <span class="fn">countdown</span>(start: int):
    <span class="kw">while</span> start &gt; <span class="num">0</span>:
        <span class="kw">yield</span> start
        start -= <span class="num">1</span>

<span class="kw">for</span> n <span class="kw">in</span> countdown(<span class="num">3</span>):
    print(n)      <span class="cmt"># 3, 2, 1</span>

<span class="cmt"># Low-memory file reading</span>
<span class="kw">def</span> <span class="fn">read_big_file</span>(path: str):
    <span class="kw">with</span> open(path) <span class="kw">as</span> f:
        <span class="kw">for</span> line <span class="kw">in</span> f:
            <span class="kw">yield</span> line.strip()

<span class="cmt"># Generator expression (lazy)</span>
total = sum(n * n <span class="kw">for</span> n <span class="kw">in</span> range(<span class="num">1_000_000</span>))</code></pre>

<div class="tip"><strong>Remember:</strong> a generator can be consumed only once. After it finishes, it's empty.</div>

<h3>2.6 Context managers</h3>

<pre><code><span class="cmt"># Files</span>
<span class="kw">with</span> open(<span class="str">"notes.txt"</span>, <span class="str">"w"</span>) <span class="kw">as</span> f:
    f.write(<span class="str">"hello"</span>)

<span class="cmt"># Custom via decorator</span>
<span class="kw">from</span> contextlib <span class="kw">import</span> contextmanager

<span class="dec">@contextmanager</span>
<span class="kw">def</span> <span class="fn">opened_connection</span>(name: str):
    print(f<span class="str">"connecting to {name}"</span>)
    conn = {<span class="str">"name"</span>: name}
    <span class="kw">try</span>:
        <span class="kw">yield</span> conn
    <span class="kw">finally</span>:
        print(f<span class="str">"closing {name}"</span>)

<span class="kw">with</span> opened_connection(<span class="str">"db"</span>) <span class="kw">as</span> c:
    print(<span class="str">"using"</span>, c)</code></pre>

<div class="tip"><strong>Remember:</strong> use <code>with</code> for anything that must be closed: files, sockets, DB cursors, locks.</div>

<!-- ================================================================ -->
<!-- SECTION 3 — ASYNCIO -->
<!-- ================================================================ -->
<hr />
<h2 id="s3">3 · Asyncio &amp; Concurrency</h2>

<h3>3.1 The big idea</h3>
<p>Most slow programs are <strong>waiting</strong>, not computing. Async lets one thread juggle many waits.</p>

<div class="card">
  <div class="card-title">🔑 Three words</div>
  <table>
    <tr><th>Word</th><th>Meaning</th><th>Python tool</th></tr>
    <tr><td>Concurrency</td><td>Many tasks taking turns</td><td><code>asyncio</code>, threads</td></tr>
    <tr><td>Parallelism</td><td>Many tasks on separate CPU cores</td><td><code>multiprocessing</code></td></tr>
    <tr><td>Async</td><td>Concurrency where tasks pause while waiting</td><td><code>asyncio</code></td></tr>
  </table>
</div>

<div class="card">
  <div class="card-title">🧰 Choose the right tool</div>
  <table>
    <tr><th>Workload</th><th>Use</th></tr>
    <tr><td>I/O‑bound, many concurrent (HTTP, DB)</td><td><code>asyncio</code></td></tr>
    <tr><td>I/O‑bound but library is sync</td><td><code>asyncio.to_thread</code></td></tr>
    <tr><td>CPU‑bound (heavy math, encoding)</td><td><code>multiprocessing</code></td></tr>
  </table>
</div>

<h3>3.2 async / await basics</h3>

<pre><code><span class="kw">import</span> asyncio

<span class="kw">async def</span> <span class="fn">say_hello</span>():
    print(<span class="str">"Hello"</span>)
    <span class="kw">await</span> asyncio.sleep(<span class="num">1</span>)     <span class="cmt"># pause, let others run</span>
    print(<span class="str">"World"</span>)

asyncio.run(say_hello())</code></pre>

<div class="card">
  <div class="card-title">📌 Three things to remember</div>
  <ol>
    <li><code>async def</code> defines a coroutine — calling it returns a coroutine object, does not run it.</li>
    <li><code>await</code> pauses until the awaited thing finishes, letting the loop run others.</li>
    <li><code>asyncio.run(main())</code> starts the loop — call once, top level.</li>
  </ol>
</div>

<h3>3.3 Sequential vs concurrent</h3>

<pre><code><span class="cmt"># Sequential → ~3 seconds</span>
<span class="kw">import</span> asyncio, time

<span class="kw">async def</span> <span class="fn">fetch</span>(name: str, delay: float) -&gt; str:
    <span class="kw">await</span> asyncio.sleep(delay)
    <span class="kw">return</span> f<span class="str">"{name} done"</span>

<span class="kw">async def</span> <span class="fn">main</span>():
    start = time.perf_counter()
    a = <span class="kw">await</span> fetch(<span class="str">"A"</span>, <span class="num">1</span>)
    b = <span class="kw">await</span> fetch(<span class="str">"B"</span>, <span class="num">1</span>)
    c = <span class="kw">await</span> fetch(<span class="str">"C"</span>, <span class="num">1</span>)
    print(a, b, c, f<span class="str">"{time.perf_counter() - start:.1f}s"</span>)

asyncio.run(main())</code></pre>

<pre><code><span class="cmt"># Concurrent → ~1 second</span>
<span class="kw">async def</span> <span class="fn">main</span>():
    start = time.perf_counter()
    results = <span class="kw">await</span> asyncio.gather(
        fetch(<span class="str">"A"</span>, <span class="num">1</span>),
        fetch(<span class="str">"B"</span>, <span class="num">1</span>),
        fetch(<span class="str">"C"</span>, <span class="num">1</span>),
    )
    print(results, f<span class="str">"{time.perf_counter() - start:.1f}s"</span>)

asyncio.run(main())</code></pre>

<div class="tip"><strong>Remember:</strong> forgetting <code>await</code> = the #1 async bug. Python warns “coroutine was never awaited.”</div>

<h3>3.4 Running many tasks safely</h3>

<pre><code><span class="cmt"># gather — collect results, optionally collect exceptions</span>
results = <span class="kw">await</span> asyncio.gather(
    fetch(<span class="str">"A"</span>, <span class="num">1</span>),
    might_fail(),
    return_exceptions=<span class="kw">True</span>,
)
<span class="kw">for</span> r <span class="kw">in</span> results:
    <span class="kw">if</span> isinstance(r, Exception):
        print(<span class="str">"failed:"</span>, r)

<span class="cmt"># create_task — start now, await later</span>
<span class="kw">async def</span> <span class="fn">main</span>():
    t1 = asyncio.create_task(fetch(<span class="str">"A"</span>, <span class="num">2</span>))
    t2 = asyncio.create_task(fetch(<span class="str">"B"</span>, <span class="num">1</span>))
    <span class="kw">await</span> asyncio.sleep(<span class="num">0.5</span>)
    print(<span class="kw">await</span> t1, <span class="kw">await</span> t2)

<span class="cmt"># TaskGroup (3.11+) — safest: cancels siblings on failure</span>
<span class="kw">async def</span> <span class="fn">main</span>():
    <span class="kw">async with</span> asyncio.TaskGroup() <span class="kw">as</span> tg:
        t1 = tg.create_task(fetch(<span class="str">"A"</span>, <span class="num">1</span>))
        t2 = tg.create_task(fetch(<span class="str">"B"</span>, <span class="num">2</span>))
    print(t1.result(), t2.result())

<span class="cmt"># Timeout (3.11+)</span>
<span class="kw">async with</span> asyncio.timeout(<span class="num">2</span>):
    <span class="kw">await</span> slow()</code></pre>

<pre><code><span class="cmt"># Semaphore — cap concurrent work</span>
sem = asyncio.Semaphore(<span class="num">5</span>)

<span class="kw">async def</span> <span class="fn">limited</span>(i: int) -&gt; int:
    <span class="kw">async with</span> sem:
        <span class="kw">await</span> asyncio.sleep(<span class="num">1</span>)
        <span class="kw">return</span> i

<span class="kw">async def</span> <span class="fn">main</span>():
    results = <span class="kw">await</span> asyncio.gather(*(limited(i) <span class="kw">for</span> i <span class="kw">in</span> range(<span class="num">20</span>)))
    print(len(results))   <span class="cmt"># 20 results in ~4s, not 20s</span>

asyncio.run(main())</code></pre>

<h3>3.5 Blocking code — the biggest trap</h3>

<pre><code><span class="cmt"># ❌ WRONG — blocks the entire event loop</span>
<span class="kw">async def</span> <span class="fn">bad</span>():
    time.sleep(<span class="num">3</span>)

<span class="cmt"># ✅ GOOD — yields to other tasks</span>
<span class="kw">async def</span> <span class="fn">good</span>():
    <span class="kw">await</span> asyncio.sleep(<span class="num">3</span>)

<span class="cmt"># If you MUST call blocking code → push to a thread</span>
<span class="kw">async def</span> <span class="fn">main</span>():
    results = <span class="kw">await</span> asyncio.gather(
        asyncio.to_thread(slow_blocking_job, <span class="num">1</span>),
        asyncio.to_thread(slow_blocking_job, <span class="num">2</span>),
        asyncio.to_thread(slow_blocking_job, <span class="num">3</span>),
    )

<span class="cmt"># For heavy CPU → ProcessPoolExecutor (GIL!)</span>
<span class="kw">from</span> concurrent.futures <span class="kw">import</span> ProcessPoolExecutor

<span class="kw">async def</span> <span class="fn">main</span>():
    loop = asyncio.get_running_loop()
    <span class="kw">with</span> ProcessPoolExecutor() <span class="kw">as</span> pool:
        result = <span class="kw">await</span> loop.run_in_executor(pool, heavy_math, <span class="num">10_000_000</span>)</code></pre>

<div class="warn">
  <strong>⚠️ Inside <code>async def</code>, NEVER call:</strong> <code>time.sleep</code>, <code>requests.get</code>,
  synchronous DB drivers, or any blocking I/O. Use async versions or <code>asyncio.to_thread</code>.
</div>

<!-- ================================================================ -->
<!-- SECTION 4 — HTTP CLIENTS -->
<!-- ================================================================ -->
<hr />
<h2 id="s4">4 · HTTP Clients</h2>

<table>
  <tr><th>Library</th><th>Style</th><th>When</th></tr>
  <tr><td><code>requests</code></td><td>Sync</td><td>Scripts, one-off calls</td></tr>
  <tr><td><code>httpx</code></td><td>Sync + Async</td><td>Modern default; works with FastAPI</td></tr>
  <tr><td><code>aiohttp</code></td><td>Async only</td><td>High concurrency; also has server</td></tr>
</table>

<pre><code><span class="cmt"># requests (sync)</span>
<span class="kw">import</span> requests

resp = requests.get(<span class="str">"https://httpbin.org/get"</span>, params={<span class="str">"q"</span>: <span class="str">"python"</span>}, timeout=<span class="num">10</span>)
resp.raise_for_status()
print(resp.json())</code></pre>

<pre><code><span class="cmt"># httpx async — the default for services</span>
<span class="kw">import</span> asyncio, httpx

<span class="kw">async def</span> <span class="fn">main</span>():
    <span class="kw">async with</span> httpx.AsyncClient(timeout=<span class="num">10</span>) <span class="kw">as</span> client:
        resp = <span class="kw">await</span> client.get(<span class="str">"https://httpbin.org/get"</span>)
        resp.raise_for_status()
        print(resp.json())

asyncio.run(main())</code></pre>

<pre><code><span class="cmt"># Many requests at once — capped with Semaphore</span>
URLS = [f<span class="str">"https://httpbin.org/delay/1?id={i}"</span> <span class="kw">for</span> i <span class="kw">in</span> range(<span class="num">10</span>)]

<span class="kw">async def</span> <span class="fn">fetch</span>(client, sem, url):
    <span class="kw">async with</span> sem:
        resp = <span class="kw">await</span> client.get(url)
        <span class="kw">return</span> resp.status_code

<span class="kw">async def</span> <span class="fn">main</span>():
    sem = asyncio.Semaphore(<span class="num">5</span>)
    <span class="kw">async with</span> httpx.AsyncClient(timeout=<span class="num">10</span>) <span class="kw">as</span> client:
        codes = <span class="kw">await</span> asyncio.gather(*(fetch(client, sem, u) <span class="kw">for</span> u <span class="kw">in</span> URLS))
    print(codes)</code></pre>

<pre><code><span class="cmt"># Error handling + retries</span>
<span class="kw">async def</span> <span class="fn">safe_get</span>(client, url):
    <span class="kw">try</span>:
        resp = <span class="kw">await</span> client.get(url)
        resp.raise_for_status()
        <span class="kw">return</span> resp.json()
    <span class="kw">except</span> httpx.TimeoutException:
        print(<span class="str">"timeout:"</span>, url)
    <span class="kw">except</span> httpx.HTTPStatusError <span class="kw">as</span> e:
        print(<span class="str">"bad status"</span>, e.response.status_code, url)
    <span class="kw">except</span> httpx.RequestError <span class="kw">as</span> e:
        print(<span class="str">"network:"</span>, e)
    <span class="kw">return</span> <span class="kw">None</span>

<span class="kw">async def</span> <span class="fn">get_with_retry</span>(client, url, tries: int = <span class="num">3</span>):
    <span class="kw">for</span> attempt <span class="kw">in</span> range(<span class="num">1</span>, tries + <span class="num">1</span>):
        <span class="kw">try</span>:
            resp = <span class="kw">await</span> client.get(url)
            resp.raise_for_status()
            <span class="kw">return</span> resp.json()
        <span class="kw">except</span> (httpx.RequestError, httpx.HTTPStatusError):
            <span class="kw">if</span> attempt == tries:
                <span class="kw">raise</span>
            <span class="kw">await</span> asyncio.sleep(<span class="num">2</span> ** attempt)   <span class="cmt"># 2s, 4s, 8s</span></code></pre>

<div class="tip">
  <strong>Rules for production:</strong> reuse one <code>AsyncClient</code>, always set a timeout,
  cap concurrency with a Semaphore, retry with backoff.
</div>

<!-- ================================================================ -->
<!-- SECTION 5 — FASTAPI -->
<!-- ================================================================ -->
<hr />
<h2 id="s5">5 · FastAPI</h2>

<pre><code><span class="kw">from</span> fastapi <span class="kw">import</span> FastAPI, Depends, HTTPException, BackgroundTasks
<span class="kw">from</span> pydantic <span class="kw">import</span> BaseModel

app = FastAPI()

<span class="kw">class</span> <span class="fn">Item</span>(BaseModel):
    name: str
    price: float
    tax: float | <span class="kw">None</span> = <span class="kw">None</span>

<span class="dec">@app.post</span>(<span class="str">"/items/"</span>)
<span class="kw">async def</span> <span class="fn">create_item</span>(item: Item):
    <span class="kw">return</span> {<span class="str">"item"</span>: item, <span class="str">"total"</span>: item.price + (item.tax <span class="kw">or</span> <span class="num">0</span>)}

<span class="cmt"># Dependency injection</span>
<span class="kw">def</span> <span class="fn">get_db</span>():
    db = {<span class="str">"conn"</span>: <span class="str">"fake"</span>}
    <span class="kw">try</span>:
        <span class="kw">yield</span> db
    <span class="kw">finally</span>:
        db.clear()

<span class="dec">@app.get</span>(<span class="str">"/users/"</span>)
<span class="kw">async def</span> <span class="fn">read_users</span>(db = Depends(get_db)):
    <span class="kw">return</span> {<span class="str">"ok"</span>: bool(db)}

<span class="cmt"># Background tasks</span>
<span class="kw">def</span> <span class="fn">send_email</span>(addr: str):
    print(f<span class="str">"sending to {addr}"</span>)

<span class="dec">@app.post</span>(<span class="str">"/register/"</span>)
<span class="kw">async def</span> <span class="fn">register</span>(email: str, bg: BackgroundTasks):
    bg.add_task(send_email, email)
    <span class="kw">return</span> {<span class="str">"message"</span>: <span class="str">"queued"</span>}</code></pre>

<div class="card">
  <div class="card-title">🎯 FastAPI mental model</div>
  <ul>
    <li><code>async def</code> endpoints for I/O (DB, HTTP). <code>def</code> endpoints for CPU work — FastAPI runs them in a threadpool.</li>
    <li>Pydantic models = request/response contract + validation.</li>
    <li><code>Depends()</code> = reusable, testable logic (DB session, current user, settings).</li>
    <li><code>BackgroundTasks</code> for fire‑and‑forget (emails, webhooks). Long jobs → external queue (Celery / RQ / arq).</li>
  </ul>
</div>

<div class="qa">
  <strong>🧠 Interview:</strong> “How do you handle validation errors globally?”<br>
  <em>Answer:</em> register an exception handler for <code>RequestValidationError</code> and return a consistent JSON envelope. For business errors, raise <code>HTTPException(status_code=…, detail=…)</code>. Never leak stack traces in production.
</div>

<!-- ================================================================ -->
<!-- SECTION 6 — PYDANTIC -->
<!-- ================================================================ -->
<hr />
<h2 id="s6">6 · Pydantic</h2>

<pre><code><span class="kw">from</span> pydantic <span class="kw">import</span> BaseModel, Field, field_validator

<span class="kw">class</span> <span class="fn">User</span>(BaseModel):
    username: str = Field(..., min_length=<span class="num">3</span>, max_length=<span class="num">20</span>)
    age: int = Field(..., ge=<span class="num">18</span>, le=<span class="num">120</span>)

    <span class="dec">@field_validator</span>(<span class="str">"username"</span>)
    <span class="kw">def</span> <span class="fn">no_special_chars</span>(cls, v):
        <span class="kw">if</span> <span class="kw">not</span> v.isalnum():
            <span class="kw">raise</span> ValueError(<span class="str">"username must be alphanumeric"</span>)
        <span class="kw">return</span> v

<span class="cmt"># Settings from env vars</span>
<span class="kw">from</span> pydantic_settings <span class="kw">import</span> BaseSettings

<span class="kw">class</span> <span class="fn">Settings</span>(BaseSettings):
    database_url: str = <span class="str">"postgresql://localhost/mydb"</span>
    debug: bool = <span class="kw">False</span>

settings = Settings()</code></pre>

<div class="tip">
  <strong>Structured output tip:</strong> when using an LLM, define a Pydantic model and ask the model
  for that schema (JSON / tool calling). Then <code>Model.model_validate_json(raw)</code> gives you
  a validated object — catch <code>ValidationError</code> and retry with the error message.
</div>

<!-- ================================================================ -->
<!-- SECTION 7 — POSTGRESQL -->
<!-- ================================================================ -->
<hr />
<h2 id="s7">7 · PostgreSQL</h2>

<pre><code><span class="cmt">-- Safe join + aggregation</span>
<span class="kw">SELECT</span> u.name, <span class="kw">COUNT</span>(o.id) <span class="kw">AS</span> order_count
<span class="kw">FROM</span> users u
<span class="kw">LEFT JOIN</span> orders o <span class="kw">ON</span> o.user_id = u.id
<span class="kw">WHERE</span> u.created_at &gt; <span class="str">'2026-01-01'</span>
<span class="kw">GROUP BY</span> u.id, u.name
<span class="kw">ORDER BY</span> order_count <span class="kw">DESC</span>;

<span class="cmt">-- Index for fast lookups</span>
<span class="kw">CREATE INDEX</span> idx_users_email <span class="kw">ON</span> users(email);</code></pre>

<pre><code><span class="cmt"># Transaction with psycopg2</span>
<span class="kw">import</span> psycopg2
<span class="kw">from</span> contextlib <span class="kw">import</span> closing

<span class="kw">with</span> closing(psycopg2.connect(DATABASE_URL)) <span class="kw">as</span> conn:
    <span class="kw">with</span> conn.cursor() <span class="kw">as</span> cur:
        <span class="kw">try</span>:
            cur.execute(<span class="str">"BEGIN"</span>)
            cur.execute(<span class="str">"UPDATE accounts SET balance = balance - 100 WHERE id = 1"</span>)
            cur.execute(<span class="str">"UPDATE accounts SET balance = balance + 100 WHERE id = 2"</span>)
            conn.commit()
        <span class="kw">except</span> Exception:
            conn.rollback(); <span class="kw">raise</span></code></pre>

<div class="qa">
  <strong>🧠 Interview:</strong> “Slow query on a 1M‑row table — where do you start?”<br>
  <em>Steps:</em> 1) <code>EXPLAIN ANALYZE</code>. 2) Check missing indexes on filter/join columns.
  3) Avoid <code>SELECT *</code>. 4) Consider composite indexes.
  5) Materialized views / read replicas for analytics.
</div>

<!-- ================================================================ -->
<!-- SECTION 8 — MINI PROJECT -->
<!-- ================================================================ -->
<hr />
<h2 id="s8">8 · Mini End‑to‑End Project — Fast URL Checker</h2>

<p>This project uses almost everything: typing, dataclass, exceptions, context managers, asyncio, semaphore, and an HTTP client.</p>

<pre><code><span class="cmt"># checker.py — python checker.py</span>
<span class="kw">import</span> asyncio, time
<span class="kw">from</span> dataclasses <span class="kw">import</span> dataclass
<span class="kw">from</span> contextlib <span class="kw">import</span> contextmanager
<span class="kw">import</span> httpx

<span class="dec">@dataclass</span>
<span class="kw">class</span> <span class="fn">Result</span>:
    url: str
    status: int | <span class="kw">None</span>
    error: str | <span class="kw">None</span> = <span class="kw">None</span>

    <span class="dec">@property</span>
    <span class="kw">def</span> <span class="fn">ok</span>(self) -&gt; bool:
        <span class="kw">return</span> self.status <span class="kw">is not</span> <span class="kw">None</span> <span class="kw">and</span> self.status &lt; <span class="num">400</span>

<span class="dec">@contextmanager</span>
<span class="kw">def</span> <span class="fn">timer</span>(label: str):
    start = time.perf_counter()
    <span class="kw">try</span>:
        <span class="kw">yield</span>
    <span class="kw">finally</span>:
        print(f<span class="str">"{label}: {time.perf_counter() - start:.2f}s"</span>)

<span class="kw">async def</span> <span class="fn">check</span>(client, sem, url) -&gt; Result:
    <span class="kw">async with</span> sem:
        <span class="kw">try</span>:
            resp = <span class="kw">await</span> client.get(url)
            <span class="kw">return</span> Result(url, resp.status_code)
        <span class="kw">except</span> httpx.TimeoutException:
            <span class="kw">return</span> Result(url, <span class="kw">None</span>, <span class="str">"timeout"</span>)
        <span class="kw">except</span> httpx.RequestError <span class="kw">as</span> err:
            <span class="kw">return</span> Result(url, <span class="kw">None</span>, type(err).__name__)

<span class="kw">async def</span> <span class="fn">main</span>(urls: list[str]) -&gt; <span class="kw">None</span>:
    sem = asyncio.Semaphore(<span class="num">5</span>)
    <span class="kw">async with</span> httpx.AsyncClient(timeout=<span class="num">5</span>, follow_redirects=<span class="kw">True</span>) <span class="kw">as</span> client:
        results = <span class="kw">await</span> asyncio.gather(*(check(client, sem, u) <span class="kw">for</span> u <span class="kw">in</span> urls))
    <span class="kw">for</span> r <span class="kw">in</span> results:
        mark = <span class="str">"OK  "</span> <span class="kw">if</span> r.ok <span class="kw">else</span> <span class="str">"FAIL"</span>
        print(mark, r.url, r.status <span class="kw">or</span> r.error)

<span class="kw">if</span> __name__ == <span class="str">"__main__"</span>:
    urls = [
        <span class="str">"https://www.python.org"</span>,
        <span class="str">"https://httpbin.org/status/404"</span>,
        <span class="str">"https://httpbin.org/delay/2"</span>,
        <span class="str">"https://this-site-does-not-exist-12345.com"</span>,
    ]
    <span class="kw">with</span> timer(<span class="str">"total"</span>):
        asyncio.run(main(urls))</code></pre>

<div class="tip">
  <strong>Try this:</strong> change Semaphore from 5 → 1 and watch the total time increase.
  Then add retries: <code>await asyncio.sleep(2 ** attempt)</code>.
</div>

<!-- ================================================================ -->
<!-- SECTION 9 — SYSTEM DESIGN -->
<!-- ================================================================ -->
<hr />
<h2 id="s9">9 · System Design Interview — Master + 2 Read Replicas</h2>

<p class="section-lead">
  <strong>Scenario:</strong> One master DB (writes) + two read replicas. User deposits $100, then refreshes.
  How do you make sure they see the new balance in a fraction of a second?
</p>

<h3>9.1 The one‑sentence diagnosis</h3>
<div class="card">
  <p>This is the classic <strong>read‑your‑own‑writes</strong> consistency problem caused by
  <strong>replication lag</strong>. Write goes to master, read goes to replica,
  replication takes 50ms–2s — during that gap the user sees stale data.</p>
</div>

<h3>9.2 Clarifying questions (always ask these)</h3>
<ol>
  <li>Scale — how many users, what read/write ratio?</li>
  <li>Is this financial‑grade? Any regulatory requirement?</li>
  <li>Freshness target — milliseconds, 1 second, or “eventually”?</li>
  <li>What does “refresh” mean — page reload, WebSocket, mobile pull?</li>
  <li>Is the user reading their <em>own</em> data or general data?</li>
  <li>Can I change the DB architecture, or is master + 2 replicas fixed?</li>
</ol>

<h3>9.3 Layered solution</h3>

<div class="grid-2">
  <div class="card">
    <div class="card-title">🥇 Layer 1 — RYOW routing ⭐ main fix</div>
    <p>Master returns a commit LSN. Store it in the user's session.
    For the next ~2s (or until replica catches up) route <strong>that user's</strong> reads to the master.
    Everyone else keeps reading replicas.</p>
    <p><strong>Result:</strong> user sees $600 instantly, master load barely changes.</p>
  </div>
  <div class="card">
    <div class="card-title">🥈 Layer 2 — Optimistic UI</div>
    <p>The client already knows the new balance — show it immediately on refresh.
    Reconcile with the server response when it arrives.</p>
    <p><strong>Result:</strong> perceived freshness is instant. No backend change needed.</p>
  </div>
</div>
<div class="grid-2">
  <div class="card">
    <div class="card-title">🥉 Layer 3 — LSN freshness check</div>
    <p>For money‑critical reads: check <code>pg_last_wal_replay_lsn() &gt;= write_lsn</code> before reading
    from the replica. Wait a few milliseconds if needed.</p>
    <p><strong>Result:</strong> guaranteed correctness when it matters.</p>
  </div>
  <div class="card">
    <div class="card-title">🏅 Layer 4 — Redis write‑through</div>
    <p>On write, <code>SET user:42:balance 600</code> with TTL 5min. Reads hit Redis first.
    If Redis fails → RYOW takes over.</p>
    <p><strong>Result:</strong> fast path, safety net for correctness.</p>
  </div>
</div>

<h3>9.4 The flow</h3>

<pre><code><span class="cmt">── DEPOSIT $100 ──────────────────────────────</span>
UI:      balance = $600               <span class="cmt"># optimistic</span>
Service: master.UPDATE balance + 100  <span class="cmt"># durable commit</span>
Master:  returns commit LSN
Service: redis.SET user:42:balance 600  <span class="cmt"># write-through</span>
Service: session.read_from_master_until = now + 2s

<span class="cmt">── NEXT REFRESH (within 2s) ─────────────────</span>
1. Redis HIT → return $600 ✅
2. Redis miss → session flag still active?
   → read from MASTER (guaranteed fresh)
3. After 2s → back to replica pool

<span class="cmt">── OTHER USERS ─────────────────────────────</span>
always read replicas → scale preserved ✅</code></pre>

<h3>9.5 The 60‑second interview answer</h3>
<div class="qa">
  <p><em>“This is a read‑your‑own‑writes problem caused by replication lag. I solve it in three layers:</em></p>
  <p><em><strong>1. RYOW routing</strong> — master returns a commit LSN, stored in the user's session.
  That user's reads hit the master for ~2s until the replica catches up. Only the writing user pays — everyone else still reads replicas at scale.</em></p>
  <p><em><strong>2. Optimistic UI</strong> — the client already knows the new balance from its own write.
  Show it immediately, reconcile with the server later.</em></p>
  <p><em><strong>3. LSN freshness check</strong> — for money‑critical reads, compare
  <code>pg_current_wal_lsn()</code> with <code>pg_last_wal_replay_lsn()</code> to guarantee the replica has caught up.</em></p>
  <p><em>Result: user sees $600 in milliseconds, money is never wrong, reads still scale across both replicas.”</em></p>
</div>

<h3>9.6 Follow‑up traps</h3>

<table>
  <tr><th>Question</th><th>Answer</th></tr>
  <tr><td>Master crashes before replica catches up?</td><td>Write is in master's WAL → durable. Failover promotes a caught‑up replica. RYOW token forces reads to a caught‑up node after failover.</td></tr>
  <tr><td>User opens a new device?</td><td>RYOW token lives in a server‑side session store (Redis), not the browser — any device picks it up.</td></tr>
  <tr><td>Won't master get overloaded?</td><td>Only the writing user's reads, only for ~2s. Tiny fraction of total traffic.</td></tr>
  <tr><td>Replication lag spikes to 30s?</td><td>RYOW + LSN wait keep that user on master. Others see stale data (acceptable — they didn't write). Alert on lag &gt; 5s.</td></tr>
  <tr><td>Why not synchronous replication?</td><td>Adds write latency + reduces availability. Use semi‑sync as optional safety.</td></tr>
  <tr><td>Cache invalidation?</td><td>Write‑through Redis + TTL 5min. If Redis fails → RYOW takes over.</td></tr>
  <tr><td>How do you test?</td><td>Inject artificial lag in staging. Verify: writing user sees fresh data instantly, others see eventual data, no stale reads after RYOW window.</td></tr>
</table>

<!-- ================================================================ -->
<!-- SECTION 10 — USERNAME & PLATFORM -->
<!-- ================================================================ -->
<hr />
<h2 id="s10">10 · Username &amp; Platform Strategy</h2>

<div class="card">
  <div class="card-title">🏆 The handle to reserve</div>
  <p style="font-size:1.4rem; font-weight:800; color:#1e3a8a; margin:0.5rem 0;">pratikfulkar</p>
  <p>Exact match on all platforms. Real name = what recruiters search. 5+ years seniority = real name beats clever handles.</p>
</div>

<table>
  <tr><th>Platform</th><th>Handle</th><th>Priority</th></tr>
  <tr><td>LinkedIn</td><td><code>pratik-fulkar-00</code> (existing) → vanity <code>pratikfulkar</code></td><td>🥇 #1 job magnet</td></tr>
  <tr><td>X (Twitter)</td><td><code>@pratikfulkar</code></td><td>🥈 credibility</td></tr>
  <tr><td>Reddit</td><td><code>u/pratikfulkar</code></td><td>🥉 feedback only</td></tr>
  <tr><td>Bluesky</td><td><code>@pratikfulkar.bsky.social</code></td><td>cross‑post only</td></tr>
  <tr><td>Threads</td><td><code>@pratikfulkar</code></td><td>cross‑post only</td></tr>
  <tr><td>Medium</td><td>❌ Skip</td><td>Low ROI — no distribution</td></tr>
  <tr><td>Domains</td><td><code>pratikfulkar.dev</code> + <code>.com</code></td><td>🎯 Buy today</td></tr>
</table>

<h3>Bio line (same everywhere)</h3>
<pre><code>Senior Software Engineer → Applied AI &amp; Agent Systems
Building AgentGuard · Enterprise Workflow Agent · CodeShift
Python · FastAPI · LLM Evaluation · MCP · RAG
Open to Senior Applied AI / Agent Engineer roles</code></pre>

<h3>Weekly cadence</h3>
<table>
  <tr><th>Platform</th><th>Time/week</th><th>What</th></tr>
  <tr><td>LinkedIn</td><td>3–4 hrs</td><td>1 post/week · 15 min/day commenting on 5 niche posts</td></tr>
  <tr><td>X</td><td>2–3 hrs</td><td>3–5 updates/week · 10 min/day substantive replies</td></tr>
  <tr><td>Reddit</td><td>1 hr</td><td>1 thoughtful post/week (question, not promo)</td></tr>
  <tr><td>Threads / Bluesky</td><td>1 hr</td><td>Cross‑post only — no extra effort</td></tr>
</table>

<div class="tip">
  <strong>Content mix (from your plan):</strong> 60% hands‑on engineering · 25% technical explainers ·
  15% industry with original analysis.
</div>

<!-- ================================================================ -->
<!-- SECTION 11 — REDDIT BIO -->
<!-- ================================================================ -->
<hr />
<h2 id="s11">11 · Reddit Profile Bio</h2>

<p>Reddit rewards <strong>humility + substance</strong>. No marketing. No links in bio. Ask questions, don't announce.</p>

<pre><code>Senior SWE (5+ yrs) working on applied AI &amp; agent systems.

Currently building: AgentGuard (agent eval + observability),
Enterprise Workflow Agent (MCP-based), CodeShift (AI code migration testing).

Mostly Python, FastAPI, Postgres, LangGraph.

Mostly here to ask dumb questions that turn out to be good ones.
Feedback always welcome — no links in posts, I promise.</code></pre>

<div class="card">
  <div class="card-title">📌 Setup checklist</div>
  <ul>
    <li>Display name: <code>Pratik · Applied AI</code></li>
    <li>Avatar: abstract / non‑identifying (Reddit culture)</li>
    <li>Links: <strong>GitHub only</strong> — no LinkedIn (reads as job hunting)</li>
    <li>Join: <code>r/ExperiencedDevs</code> · <code>r/MachineLearning</code> · <code>r/Python</code> · <code>r/LocalLLaMA</code> · <code>r/LangChain</code></li>
    <li>Lurk for 2 weeks before posting</li>
    <li>First post: a real question (see below), never an announcement</li>
  </ul>
</div>

<div class="card">
  <div class="card-title">💬 First post template</div>
  <p><strong>Title:</strong> How do you measure tool‑selection accuracy in multi‑step AI agents?</p>
  <p><strong>Body:</strong></p>
<pre><code>I'm building an evaluation harness for tool-using agents (AgentGuard) and I keep
hitting a measurement problem.

I can measure:
• Final answer correctness ✅
• Latency &amp; token cost ✅
• Retry count ✅

But defining "tool selection accuracy" reproducibly across prompts and models
is tricky. Specifically:
1. How do you define "the agent picked the right tool" when multiple could work?
2. Step-level or trajectory-level only?
3. How do you handle cases where the "wrong" tool reached the correct outcome?

Would love to hear how others approached this.
No links — not selling anything, just stuck on a real problem.</code></pre>
</div>

<!-- ================================================================ -->
<!-- SECTION 12 — GITHUB README -->
<!-- ================================================================ -->
<hr />
<h2 id="s12">12 · GitHub Profile README (Updated)</h2>

<p>Copy this into <code>github.com/pratikfulkar/pratikfulkar/README.md</code>.
Repositioned for <strong>Applied AI &amp; Agent Systems</strong> — honest about what's building vs. what's learned.</p>

<pre><code>&lt;div align="center"&gt;

&lt;img width="100%" src="https://capsule-render.vercel.app/api?type=waving&amp;color=gradient&amp;customColorList=6,11,20&amp;height=250&amp;section=header&amp;text=Pratik%20Fulkar&amp;fontSize=50&amp;fontColor=fff&amp;animation=twinkling&amp;fontAlignY=38" /&gt;

&lt;a href="https://git.io/typing-svg"&gt;&lt;img src="https://readme-typing-svg.demolab.com?font=Fira+Code&amp;weight=600&amp;size=26&amp;duration=3000&amp;pause=1000&amp;color=00D9FF&amp;center=true&amp;vCenter=true&amp;multiline=true&amp;repeat=true&amp;width=850&amp;height=120&amp;lines=Senior+Software+Engineer+%F0%9F%9A%80;Applied+AI+%7C+Agent+Systems+%F0%9F%A4%96;LLM+Evaluation+%7C+RAG+%7C+MCP+%F0%9F%94%AC" /&gt;

&lt;img src="https://komarev.com/ghpvc/?username=pratikfulkar&amp;label=Profile%20Views&amp;color=00D9FF&amp;style=for-the-badge" /&gt;
&lt;img src="https://img.shields.io/github/followers/pratikfulkar?label=Followers&amp;style=for-the-badge&amp;color=00D9FF&amp;labelColor=1a1b27" /&gt;

&lt;/div&gt;

---

### 👨‍💻 About Me

```javascript
const pratik = {
    role: "Senior Software Engineer",
    experience: "5+ years",
    location: "Mumbai, India 🇮🇳",
    focus: ["Applied AI", "Agent Systems", "LLM Evaluation", "Production Reliability"],
    building: ["AgentGuard", "Enterprise Workflow Agent", "CodeShift"],
    coreStack: ["Python", "FastAPI", "TypeScript", "Node.js", "PostgreSQL", "Redis"],
    aiStack: ["LangGraph", "MCP", "RAG", "LLM Eval", "Anthropic API", "OpenAI API"],
    deepening: ["OpenTelemetry", "AI Security", "Vector Search"],
    askMeAbout: ["Agent Evaluation", "MCP Integrations", "LLM Reliability", "System Design"],
    philosophy: "Build it. Measure it. Break it. Ship it."
};
