[neuro_treatment_portal.html](https://github.com/user-attachments/files/27310612/neuro_treatment_portal.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>NeuroCore Treatment Portal — Synaptic Synchrotron</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Sans:ital,opsz,wght@0,9..40,300;0,9..40,400;0,9..40,500;1,9..40,300&display=swap" rel="stylesheet">
<style>
:root {
  --bg: #040d1a;
  --surface: #071428;
  --surface2: #0b1f3a;
  --border: #112844;
  --accent: #00d4ff;
  --accent2: #7b5ea7;
  --accent3: #00ff9d;
  --warn: #ff6b35;
  --text: #e8f4fd;
  --text-muted: #6b8caa;
  --text-dim: #3a5a78;
  --glow: rgba(0,212,255,0.15);
  --glow2: rgba(123,94,167,0.15);
}

*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

body {
  background: var(--bg);
  color: var(--text);
  font-family: 'DM Sans', sans-serif;
  font-size: 15px;
  min-height: 100vh;
  overflow-x: hidden;
}

/* ─── ANIMATED BACKGROUND ─── */
body::before {
  content: '';
  position: fixed; inset: 0; z-index: 0;
  background:
    radial-gradient(ellipse 60% 40% at 20% 10%, rgba(0,212,255,0.07) 0%, transparent 60%),
    radial-gradient(ellipse 50% 40% at 80% 80%, rgba(123,94,167,0.08) 0%, transparent 60%),
    radial-gradient(ellipse 30% 30% at 60% 30%, rgba(0,255,157,0.04) 0%, transparent 50%);
  pointer-events: none;
}

/* ─── HEADER ─── */
header {
  position: sticky; top: 0; z-index: 100;
  background: rgba(4,13,26,0.92);
  backdrop-filter: blur(20px);
  border-bottom: 1px solid var(--border);
  padding: 0 2rem;
  display: flex; align-items: center; justify-content: space-between;
  height: 64px;
}

.logo {
  display: flex; align-items: center; gap: 12px;
  font-family: 'Syne', sans-serif;
  font-weight: 800; font-size: 1.1rem; letter-spacing: -0.02em;
}

.logo-icon {
  width: 36px; height: 36px;
  background: linear-gradient(135deg, var(--accent), var(--accent2));
  border-radius: 10px;
  display: flex; align-items: center; justify-content: center;
  font-size: 1.1rem;
  box-shadow: 0 0 20px rgba(0,212,255,0.3);
}

.logo span { color: var(--accent); }

.header-badge {
  font-size: 0.7rem; font-weight: 500;
  background: rgba(255,107,53,0.15);
  border: 1px solid rgba(255,107,53,0.4);
  color: var(--warn);
  padding: 4px 10px; border-radius: 20px;
  animation: pulse-warn 2s ease infinite;
}

@keyframes pulse-warn {
  0%,100% { box-shadow: 0 0 0 0 rgba(255,107,53,0.3); }
  50% { box-shadow: 0 0 0 6px rgba(255,107,53,0); }
}

/* ─── DISCLAIMER BANNER ─── */
.disclaimer-banner {
  background: linear-gradient(90deg, rgba(255,107,53,0.12), rgba(255,107,53,0.06), rgba(255,107,53,0.12));
  border-bottom: 1px solid rgba(255,107,53,0.3);
  padding: 10px 2rem;
  display: flex; align-items: center; gap: 12px;
  font-size: 0.82rem;
  position: relative; z-index: 1;
}

.disclaimer-banner strong { color: var(--warn); }
.disclaimer-banner a { color: var(--accent); text-decoration: none; }
.disc-icon { font-size: 1rem; flex-shrink: 0; }

/* ─── HERO ─── */
.hero {
  position: relative; z-index: 1;
  text-align: center;
  padding: 5rem 2rem 3rem;
}

.hero-tag {
  display: inline-flex; align-items: center; gap: 8px;
  font-size: 0.72rem; font-weight: 600; letter-spacing: 0.12em; text-transform: uppercase;
  color: var(--accent);
  background: rgba(0,212,255,0.08);
  border: 1px solid rgba(0,212,255,0.2);
  padding: 6px 14px; border-radius: 20px;
  margin-bottom: 1.5rem;
}

.hero h1 {
  font-family: 'Syne', sans-serif;
  font-size: clamp(2.2rem, 5vw, 3.8rem);
  font-weight: 800; line-height: 1.1;
  letter-spacing: -0.03em;
  margin-bottom: 1rem;
}

.hero h1 .grad {
  background: linear-gradient(135deg, var(--accent) 0%, var(--accent2) 50%, var(--accent3) 100%);
  -webkit-background-clip: text; -webkit-text-fill-color: transparent;
}

.hero p {
  max-width: 560px; margin: 0 auto 2.5rem;
  color: var(--text-muted); font-size: 1rem; line-height: 1.7;
}

/* ─── SEARCH ─── */
.search-bar {
  max-width: 560px; margin: 0 auto;
  position: relative;
}

.search-bar input {
  width: 100%;
  background: var(--surface2);
  border: 1px solid var(--border);
  color: var(--text);
  padding: 14px 50px 14px 48px;
  border-radius: 14px;
  font-size: 0.95rem;
  font-family: 'DM Sans', sans-serif;
  outline: none;
  transition: border-color 0.2s, box-shadow 0.2s;
}

.search-bar input:focus {
  border-color: var(--accent);
  box-shadow: 0 0 0 3px rgba(0,212,255,0.1);
}

.search-bar input::placeholder { color: var(--text-dim); }
.search-icon { position: absolute; left: 16px; top: 50%; transform: translateY(-50%); font-size: 1rem; color: var(--text-muted); pointer-events: none; }

/* ─── CONDITION TABS ─── */
.tabs-section {
  position: relative; z-index: 1;
  padding: 2rem;
  max-width: 1300px; margin: 0 auto;
}

.tabs-label {
  font-size: 0.72rem; font-weight: 600; letter-spacing: 0.1em; text-transform: uppercase;
  color: var(--text-dim); margin-bottom: 1rem;
}

.tabs {
  display: flex; flex-wrap: wrap; gap: 8px;
}

.tab-btn {
  display: flex; align-items: center; gap: 8px;
  background: var(--surface);
  border: 1px solid var(--border);
  color: var(--text-muted);
  padding: 8px 16px; border-radius: 40px;
  font-size: 0.82rem; font-family: 'DM Sans', sans-serif;
  cursor: pointer;
  transition: all 0.2s;
}

.tab-btn:hover { border-color: var(--accent); color: var(--text); }
.tab-btn.active {
  background: linear-gradient(135deg, rgba(0,212,255,0.15), rgba(123,94,167,0.15));
  border-color: var(--accent);
  color: var(--accent);
  box-shadow: 0 0 16px rgba(0,212,255,0.12);
}

.tab-btn .dot {
  width: 6px; height: 6px; border-radius: 50%;
  background: currentColor; opacity: 0.6;
}

/* ─── MAIN LAYOUT ─── */
.main {
  max-width: 1300px; margin: 0 auto;
  padding: 0 2rem 4rem;
  position: relative; z-index: 1;
  display: grid;
  grid-template-columns: 1fr 320px;
  gap: 2rem;
}

/* ─── CONTENT PANEL ─── */
.condition-title {
  font-family: 'Syne', sans-serif;
  font-size: 1.6rem; font-weight: 800;
  letter-spacing: -0.02em;
  margin-bottom: 0.4rem;
  display: flex; align-items: center; gap: 12px;
}

.condition-title .icon { font-size: 1.4rem; }

.condition-desc {
  color: var(--text-muted); line-height: 1.7;
  margin-bottom: 2rem; font-size: 0.92rem;
}

/* ─── SECTION CARDS ─── */
.section-grid {
  display: grid; grid-template-columns: 1fr 1fr; gap: 1rem;
  margin-bottom: 1.5rem;
}

.card {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: 16px;
  padding: 1.5rem;
  transition: border-color 0.2s, box-shadow 0.2s;
}

.card:hover { border-color: rgba(0,212,255,0.3); box-shadow: 0 4px 24px rgba(0,212,255,0.06); }

.card-header {
  display: flex; align-items: center; gap: 10px;
  margin-bottom: 1rem;
}

.card-icon {
  width: 36px; height: 36px;
  border-radius: 10px;
  display: flex; align-items: center; justify-content: center;
  font-size: 1rem; flex-shrink: 0;
}

.card-icon.blue { background: rgba(0,212,255,0.12); }
.card-icon.purple { background: rgba(123,94,167,0.15); }
.card-icon.green { background: rgba(0,255,157,0.1); }
.card-icon.orange { background: rgba(255,107,53,0.12); }
.card-icon.pink { background: rgba(255,100,180,0.1); }

.card-title {
  font-family: 'Syne', sans-serif;
  font-size: 0.88rem; font-weight: 700;
  letter-spacing: 0.01em;
  color: var(--text);
}

.card ul { list-style: none; }
.card ul li {
  padding: 7px 0;
  border-bottom: 1px solid var(--border);
  font-size: 0.84rem; color: var(--text-muted);
  display: flex; align-items: flex-start; gap: 8px;
  line-height: 1.45;
}
.card ul li:last-child { border-bottom: none; }
.card ul li::before { content: '›'; color: var(--accent); flex-shrink: 0; font-weight: 700; }

.card.wide { grid-column: span 2; }
.card.surgery { border-color: rgba(255,107,53,0.25); }
.card.surgery .card-icon { background: rgba(255,107,53,0.1); }

/* ─── URGENCY NOTICE ─── */
.urgency {
  background: linear-gradient(135deg, rgba(255,107,53,0.1), rgba(255,107,53,0.05));
  border: 1px solid rgba(255,107,53,0.35);
  border-radius: 14px;
  padding: 1.2rem 1.5rem;
  display: flex; gap: 14px; align-items: flex-start;
  margin-bottom: 1.5rem;
}

.urgency-icon { font-size: 1.5rem; flex-shrink: 0; }
.urgency-text { font-size: 0.84rem; color: var(--text-muted); line-height: 1.6; }
.urgency-text strong { color: var(--warn); display: block; margin-bottom: 4px; font-size: 0.9rem; }

/* ─── SIDEBAR ─── */
.sidebar { display: flex; flex-direction: column; gap: 1rem; }

.side-card {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: 16px;
  padding: 1.3rem;
}

.side-title {
  font-family: 'Syne', sans-serif;
  font-size: 0.82rem; font-weight: 700; text-transform: uppercase;
  letter-spacing: 0.06em; color: var(--text-dim);
  margin-bottom: 1rem;
}

/* ─── QUICK STAT ─── */
.stats-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 8px; }
.stat-box {
  background: var(--surface2);
  border: 1px solid var(--border);
  border-radius: 10px;
  padding: 12px;
  text-align: center;
}
.stat-num {
  font-family: 'Syne', sans-serif;
  font-size: 1.3rem; font-weight: 800;
  color: var(--accent);
}
.stat-label { font-size: 0.7rem; color: var(--text-dim); margin-top: 2px; }

/* ─── EMERGENCY BOX ─── */
.emergency-box {
  background: linear-gradient(135deg, rgba(255,107,53,0.12), rgba(255,60,60,0.06));
  border: 1px solid rgba(255,107,53,0.4);
  border-radius: 16px;
  padding: 1.3rem;
}

.emergency-box .side-title { color: var(--warn); }

.em-contact {
  display: flex; align-items: center; gap: 10px;
  background: var(--surface2);
  border: 1px solid rgba(255,107,53,0.2);
  border-radius: 10px;
  padding: 12px;
  margin-bottom: 8px;
  text-decoration: none; color: var(--text);
  transition: border-color 0.2s;
}
.em-contact:hover { border-color: var(--warn); }
.em-contact .em-icon { font-size: 1.2rem; }
.em-contact .em-info strong { display: block; font-size: 0.88rem; color: var(--text); }
.em-contact .em-info span { font-size: 0.78rem; color: var(--text-muted); }

/* ─── SEVERITY METER ─── */
.severity { margin-bottom: 0.5rem; }
.sev-label { display: flex; justify-content: space-between; font-size: 0.78rem; color: var(--text-muted); margin-bottom: 6px; }
.sev-bar { height: 6px; background: var(--surface2); border-radius: 4px; overflow: hidden; }
.sev-fill { height: 100%; border-radius: 4px; transition: width 0.6s ease; }
.sev-fill.low { background: var(--accent3); width: 30%; }
.sev-fill.med { background: var(--accent); width: 60%; }
.sev-fill.high { background: var(--warn); width: 85%; }

/* ─── BRAND FOOTER ─── */
.brand-footer {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: 14px;
  padding: 1.2rem;
  text-align: center;
}
.brand-name {
  font-family: 'Syne', sans-serif;
  font-size: 0.85rem; font-weight: 800;
  color: var(--accent);
  margin-bottom: 4px;
}
.brand-sub { font-size: 0.72rem; color: var(--text-dim); }

/* ─── FOOTER ─── */
footer {
  position: relative; z-index: 1;
  border-top: 1px solid var(--border);
  padding: 1.5rem 2rem;
  text-align: center;
  font-size: 0.75rem; color: var(--text-dim);
}
footer strong { color: var(--accent3); }

/* ─── PULSE DOT ─── */
.live-dot {
  display: inline-block;
  width: 8px; height: 8px; border-radius: 50%;
  background: var(--accent3);
  animation: blink 1.4s ease infinite;
}
@keyframes blink {
  0%,100% { opacity: 1; }
  50% { opacity: 0.2; }
}

/* ─── HIDDEN / ACTIVE ─── */
.condition-panel { display: none; }
.condition-panel.active { display: block; }

/* ─── RESPONSIVE ─── */
@media (max-width: 900px) {
  .main { grid-template-columns: 1fr; }
  .section-grid { grid-template-columns: 1fr; }
  .card.wide { grid-column: span 1; }
}
@media (max-width: 600px) {
  .hero h1 { font-size: 2rem; }
  .tabs { gap: 6px; }
  .tab-btn { padding: 6px 12px; font-size: 0.78rem; }
}

/* ─── FADE IN ─── */
.condition-panel.active { animation: fadeIn 0.35s ease; }
@keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }
</style>
</head>
<body>

<!-- HEADER -->
<header>
  <div class="logo">
    <div class="logo-icon">🧠</div>
    Neuro<span>Core</span> Portal
  </div>
  <div class="header-badge">⚠ Medical Reference Only — Not a Substitute for Professional Care</div>
</header>

<!-- DISCLAIMER BANNER -->
<div class="disclaimer-banner">
  <span class="disc-icon">🚨</span>
  <div>
    <strong>EMERGENCY:</strong> Contact <strong>Dr. Rizvi</strong> at <a href="tel:03324552411">0332-4552411</a> &nbsp;|&nbsp; National Emergency: <a href="tel:911"><strong>911</strong></a> &nbsp;|&nbsp;
    This portal provides <strong>educational reference only</strong>. Always consult a licensed physician before beginning any treatment.
  </div>
</div>

<!-- HERO -->
<section class="hero">
  <div class="hero-tag"><span class="live-dot"></span> AI-Powered Neurological Reference</div>
  <h1>Comprehensive <span class="grad">Neurological<br>Treatment Portal</span></h1>
  <p>Explore evidence-based treatments, therapies, medications, exercises, and surgical options across 8 major neurological & psychiatric conditions.</p>
  <div class="search-bar">
    <span class="search-icon">🔍</span>
    <input type="text" id="searchInput" placeholder="Search conditions, medications, therapies..." oninput="handleSearch(this.value)">
  </div>
</section>

<!-- TABS -->
<section class="tabs-section">
  <div class="tabs-label">Select a Condition</div>
  <div class="tabs" id="tabsContainer">
    <button class="tab-btn active" onclick="showCondition('anxiety')" data-condition="anxiety"><span class="dot"></span>Anxiety Disorders</button>
    <button class="tab-btn" onclick="showCondition('depression')" data-condition="depression"><span class="dot"></span>Depression</button>
    <button class="tab-btn" onclick="showCondition('epilepsy')" data-condition="epilepsy"><span class="dot"></span>Epilepsy</button>
    <button class="tab-btn" onclick="showCondition('autism')" data-condition="autism"><span class="dot"></span>Autism Spectrum</button>
    <button class="tab-btn" onclick="showCondition('stress')" data-condition="stress"><span class="dot"></span>Chronic Stress</button>
    <button class="tab-btn" onclick="showCondition('addiction')" data-condition="addiction"><span class="dot"></span>Drug Addiction</button>
    <button class="tab-btn" onclick="showCondition('neuro')" data-condition="neuro"><span class="dot"></span>Neurodegenerative</button>
    <button class="tab-btn" onclick="showCondition('neurological')" data-condition="neurological"><span class="dot"></span>Neurological Problems</button>
  </div>
</section>

<!-- MAIN -->
<div class="main">
  <div class="content-area">

    <!-- ══════════════ ANXIETY ══════════════ -->
    <div class="condition-panel active" id="panel-anxiety">
      <div class="condition-title"><span class="icon">😰</span> Anxiety Disorders</div>
      <p class="condition-desc">Anxiety disorders include Generalized Anxiety Disorder (GAD), Panic Disorder, Social Anxiety, PTSD, and OCD. They involve excessive fear, worry, and physiological arousal that impairs daily functioning.</p>
      <div class="urgency">
        <div class="urgency-icon">⚠️</div>
        <div class="urgency-text"><strong>Seek Immediate Help If:</strong> You experience chest pain, inability to breathe, suicidal thoughts, or a panic attack lasting over 30 minutes. Call Dr. Rizvi at 0332-4552411 or 911.</div>
      </div>
      <div class="section-grid">
        <div class="card">
          <div class="card-header"><div class="card-icon blue">💊</div><div class="card-title">Medications (SSRIs / SNRIs)</div></div>
          <ul>
            <li>Sertraline (Zoloft) – First-line SSRI for GAD & PTSD</li>
            <li>Escitalopram (Lexapro) – GAD & social anxiety</li>
            <li>Paroxetine (Paxil) – Panic disorder & social phobia</li>
            <li>Venlafaxine (Effexor XR) – SNRI, GAD & panic</li>
            <li>Duloxetine (Cymbalta) – GAD with pain comorbidity</li>
            <li>Buspirone – Non-addictive anti-anxiety, GAD</li>
            <li>Clonazepam (Klonopin) – Short-term acute anxiety</li>
            <li>Alprazolam (Xanax) – Panic attacks (short-term use)</li>
            <li>Propranolol – Performance/situational anxiety</li>
          </ul>
        </div>
        <div class="card">
          <div class="card-header"><div class="card-icon purple">🧠</div><div class="card-title">Psychotherapies</div></div>
          <ul>
            <li>Cognitive Behavioral Therapy (CBT) – Gold standard</li>
            <li>Exposure & Response Prevention (ERP) – OCD specific</li>
            <li>EMDR – Trauma-related anxiety & PTSD</li>
            <li>Acceptance & Commitment Therapy (ACT)</li>
            <li>Dialectical Behavior Therapy (DBT)</li>
            <li>Mindfulness-Based Stress Reduction (MBSR)</li>
            <li>Psychodynamic therapy for deeper patterns</li>
            <li>Group therapy & support networks</li>
          </ul>
        </div>
        <div class="card">
          <div class="card-header"><div class="card-icon green">🏃</div><div class="card-title">Exercises & Lifestyle</div></div>
          <ul>
            <li>Aerobic exercise 30 min/day – reduces cortisol</li>
            <li>Yoga & breathing (4-7-8 technique, box breathing)</li>
            <li>Progressive Muscle Relaxation (PMR)</li>
            <li>Cold exposure therapy (Wim Hof method)</li>
            <li>Regular sleep schedule (7-9 hrs)</li>
            <li>Limit caffeine & alcohol intake</li>
            <li>Journaling & gratitude practice</li>
          </ul>
        </div>
        <div class="card">
          <div class="card-header"><div class="card-icon orange">⚡</div><div class="card-title">Advanced Treatments</div></div>
          <ul>
            <li>Transcranial Magnetic Stimulation (TMS)</li>
            <li>Ketamine infusion therapy (treatment-resistant)</li>
            <li>Neurofeedback training</li>
            <li>Virtual Reality Exposure Therapy (VRET)</li>
            <li>Biofeedback therapy</li>
            <li>Transcranial Direct Current Stimulation (tDCS)</li>
          </ul>
        </div>
        <div class="card wide surgery">
          <div class="card-header"><div class="card-icon orange">🔬</div><div class="card-title">Surgical Interventions (Severe / Refractory Cases Only)</div></div>
          <ul>
            <li>Deep Brain Stimulation (DBS) of the anterior limb of internal capsule – severe OCD & treatment-resistant GAD</li>
            <li>Anterior Cingulotomy – surgical lesioning for refractory OCD unresponsive to all pharmacotherapy</li>
            <li>Vagus Nerve Stimulation (VNS) – implanted device for refractory anxiety with depression</li>
            <li>Capsulotomy / Limbic leucotomy – last-resort neurosurgical options for debilitating OCD</li>
          </ul>
        </div>
      </div>
    </div>

    <!-- ══════════════ DEPRESSION ══════════════ -->
    <div class="condition-panel" id="panel-depression">
      <div class="condition-title"><span class="icon">🌧</span> Depression</div>
      <p class="condition-desc">Major Depressive Disorder (MDD), Persistent Depressive Disorder (Dysthymia), Bipolar Depression, and Postpartum Depression. Characterized by persistent sadness, anhedonia, fatigue, and cognitive impairment.</p>
      <div class="urgency">
        <div class="urgency-icon">⚠️</div>
        <div class="urgency-text"><strong>Crisis Alert:</strong> If experiencing suicidal ideation or self-harm thoughts — call Dr. Rizvi at 0332-4552411 or emergency services at 911 immediately.</div>
      </div>
      <div class="section-grid">
        <div class="card">
          <div class="card-header"><div class="card-icon blue">💊</div><div class="card-title">Medications</div></div>
          <ul>
            <li>Fluoxetine (Prozac) – SSRI, MDD & bulimia</li>
            <li>Sertraline (Zoloft) – Broad-spectrum SSRI</li>
            <li>Escitalopram (Lexapro) – Low side effects, MDD</li>
            <li>Bupropion (Wellbutrin) – NDRI, atypical depression</li>
            <li>Mirtazapine – Depression with insomnia/appetite loss</li>
            <li>Venlafaxine (Effexor) – SNRI for severe MDD</li>
            <li>Lithium – Bipolar depression, augmentation</li>
            <li>Quetiapine / Aripiprazole – Adjunct antipsychotics</li>
            <li>Esketamine (Spravato) – Nasal spray, treatment-resistant</li>
            <li>Tricyclics (Amitriptyline) – Older but effective</li>
          </ul>
        </div>
        <div class="card">
          <div class="card-header"><div class="card-icon purple">🧠</div><div class="card-title">Therapies</div></div>
          <ul>
            <li>Cognitive Behavioral Therapy (CBT)</li>
            <li>Interpersonal Therapy (IPT)</li>
            <li>Behavioral Activation (BA)</li>
            <li>Psychodynamic / psychoanalytic therapy</li>
            <li>MBSR – Mindfulness-Based Cognitive Therapy</li>
            <li>Problem-Solving Therapy (PST)</li>
            <li>Narrative Therapy</li>
            <li>Light therapy – Seasonal Affective Disorder</li>
          </ul>
        </div>
        <div class="card">
          <div class="card-header"><div class="card-icon green">🏃</div><div class="card-title">Exercise & Self-Care</div></div>
          <ul>
            <li>30-min daily aerobic exercise – elevates serotonin</li>
            <li>Resistance / strength training 3x/week</li>
            <li>Omega-3 fatty acids (EPA/DHA supplementation)</li>
            <li>Sunlight exposure 15–30 min daily</li>
            <li>Social engagement & meaningful activities</li>
            <li>Sleep hygiene: fixed wake times, no screens before bed</li>
            <li>Journaling & positive behavioral scheduling</li>
          </ul>
        </div>
        <div class="card">
          <div class="card-header"><div class="card-icon orange">⚡</div><div class="card-title">Neurostimulation</div></div>
          <ul>
            <li>Electroconvulsive Therapy (ECT) – Severe/psychotic depression</li>
            <li>Transcranial Magnetic Stimulation (TMS/rTMS)</li>
            <li>Theta Burst Stimulation (TBS)</li>
            <li>Transcranial Direct Current Stimulation (tDCS)</li>
            <li>Ketamine IV infusions – Rapid onset</li>
            <li>Psilocybin-Assisted Therapy (clinical trials)</li>
          </ul>
        </div>
        <div class="card wide surgery">
          <div class="card-header"><div class="card-icon orange">🔬</div><div class="card-title">Surgical Interventions (Treatment-Resistant Depression)</div></div>
          <ul>
            <li>Deep Brain Stimulation (DBS) – Targets subgenual cingulate cortex (Area 25) or nucleus accumbens for TRD</li>
            <li>Vagus Nerve Stimulation (VNS) – FDA-approved implantable device for chronic, treatment-resistant depression</li>
            <li>Anterior Cingulotomy / Subcaudate Tractotomy – Rare surgical ablation for severe, refractory MDD</li>
            <li>Responsive Neurostimulation (RNS) – Closed-loop brain stimulation under investigation for MDD</li>
          </ul>
        </div>
      </div>
    </div>

    <!-- ══════════════ EPILEPSY ══════════════ -->
    <div class="condition-panel" id="panel-epilepsy">
      <div class="condition-title"><span class="icon">⚡</span> Epilepsy</div>
      <p class="condition-desc">A chronic neurological disorder characterized by recurrent, unprovoked seizures caused by abnormal electrical brain activity. Includes focal, generalized, absence, tonic-clonic, and status epilepticus types.</p>
      <div class="urgency">
        <div class="urgency-icon">🚨</div>
        <div class="urgency-text"><strong>EMERGENCY — Status Epilepticus:</strong> Seizure lasting &gt;5 minutes is a medical emergency. Call 911 immediately. Do NOT restrain the patient. Turn them on their side to prevent aspiration.</div>
      </div>
      <div class="section-grid">
        <div class="card">
          <div class="card-header"><div class="card-icon blue">💊</div><div class="card-title">Antiepileptic Drugs (AEDs)</div></div>
          <ul>
            <li>Levetiracetam (Keppra) – Broad-spectrum, focal & generalized</li>
            <li>Valproate (Depakote) – Generalized epilepsy, absence</li>
            <li>Lamotrigine (Lamictal) – Focal & generalized, mood stabilizer</li>
            <li>Carbamazepine (Tegretol) – Focal seizures</li>
            <li>Phenytoin (Dilantin) – Status epilepticus IV</li>
            <li>Oxcarbazepine (Trileptal) – Focal seizures</li>
            <li>Topiramate (Topamax) – Focal, generalized, migraine</li>
            <li>Ethosuximide (Zarontin) – Absence seizures</li>
            <li>Brivaracetam (Briviact) – Focal-onset seizures</li>
            <li>Clobazam (Onfi) – Lennox-Gastaut syndrome</li>
            <li>Cannabidiol (Epidiolex) – Dravet & Lennox-Gastaut</li>
          </ul>
        </div>
        <div class="card">
          <div class="card-header"><div class="card-icon purple">🧠</div><div class="card-title">Therapies & Dietary</div></div>
          <ul>
            <li>Ketogenic Diet – High fat, low carb; reduces seizure frequency</li>
            <li>Modified Atkins Diet – Less strict ketogenic variant</li>
            <li>Low Glycemic Index Treatment (LGIT)</li>
            <li>Medium Chain Triglyceride (MCT) Oil Diet</li>
            <li>Cognitive Behavioral Therapy (seizure anxiety)</li>
            <li>Biofeedback & neurofeedback therapy</li>
            <li>Yoga & mindfulness (reduces seizure triggers)</li>
            <li>Seizure alert dogs (trained service animals)</li>
          </ul>
        </div>
        <div class="card">
          <div class="card-header"><div class="card-icon green">🏃</div><div class="card-title">Lifestyle Management</div></div>
          <ul>
            <li>Strict sleep schedule (sleep deprivation triggers seizures)</li>
            <li>Avoid alcohol & recreational drugs</li>
            <li>Stress management & relaxation techniques</li>
            <li>Moderate aerobic exercise (swimming with supervision)</li>
            <li>Seizure diary tracking (triggers, duration, postictal state)</li>
            <li>Medical alert bracelet usage</li>
          </ul>
        </div>
        <div class="card">
          <div class="card-header"><div class="card-icon orange">⚡</div><div class="card-title">Neurostimulation Devices</div></div>
          <ul>
            <li>Vagus Nerve Stimulation (VNS) – Implanted pulse generator</li>
            <li>Responsive Neurostimulation (RNS) – Detects & stops seizures</li>
            <li>Deep Brain Stimulation (DBS) – Anterior thalamic nucleus</li>
            <li>Transcranial Magnetic Stimulation (TMS) – Investigational</li>
          </ul>
        </div>
        <div class="card wide surgery">
          <div class="card-header"><div class="card-icon orange">🔬</div><div class="card-title">Surgical Interventions (Drug-Resistant Epilepsy)</div></div>
          <ul>
            <li>Temporal Lobectomy – Removal of seizure focus in temporal lobe; highest success rate (~70% seizure-free)</li>
            <li>Focal Cortical Resection – Removal of epileptogenic cortex identified by EEG/fMRI mapping</li>
            <li>Corpus Callosotomy – Severing corpus callosum to prevent seizure spread; used in drop attacks</li>
            <li>Hemispherectomy / Hemispherotomy – For hemispheric epilepsy syndromes in children</li>
            <li>Multiple Subpial Transections (MST) – Cuts seizure pathways in eloquent cortex</li>
            <li>Laser Interstitial Thermal Therapy (LITT) – MRI-guided minimally invasive ablation</li>
            <li>Stereoelectroencephalography (SEEG) – Diagnostic depth electrode implantation</li>
          </ul>
        </div>
      </div>
    </div>

    <!-- ══════════════ AUTISM ══════════════ -->
    <div class="condition-panel" id="panel-autism">
      <div class="condition-title"><span class="icon">🌈</span> Autism Spectrum Disorder</div>
      <p class="condition-desc">ASD is a neurodevelopmental condition affecting social communication, behavior, and sensory processing. It is a spectrum — from high-functioning (Level 1) to requiring substantial support (Level 3).</p>
      <div class="section-grid">
        <div class="card">
          <div class="card-header"><div class="card-icon blue">💊</div><div class="card-title">Medications (Symptom Management)</div></div>
          <ul>
            <li>Risperidone (Risperdal) – FDA-approved for irritability in ASD</li>
            <li>Aripiprazole (Abilify) – FDA-approved irritability & aggression</li>
            <li>Methylphenidate (Ritalin) – Comorbid ADHD in ASD</li>
            <li>Fluoxetine / Sertraline – Repetitive behaviors, anxiety</li>
            <li>Guanfacine / Clonidine – Hyperactivity & impulsivity</li>
            <li>Melatonin – Sleep disorders in ASD</li>
            <li>Oxytocin (nasal) – Investigational for social deficits</li>
          </ul>
        </div>
        <div class="card">
          <div class="card-header"><div class="card-icon purple">🧠</div><div class="card-title">Behavioral Therapies</div></div>
          <ul>
            <li>Applied Behavior Analysis (ABA) – Evidence-based core therapy</li>
            <li>Verbal Behavior Therapy (VBT) – ABA variant for communication</li>
            <li>Discrete Trial Training (DTT)</li>
            <li>Pivotal Response Treatment (PRT)</li>
            <li>Social Skills Training (SST) groups</li>
            <li>Cognitive Behavioral Therapy (for ASD with anxiety)</li>
            <li>DIR/Floortime developmental therapy</li>
            <li>PECS (Picture Exchange Communication System)</li>
          </ul>
        </div>
        <div class="card">
          <div class="card-header"><div class="card-icon green">🏃</div><div class="card-title">Developmental & Sensory</div></div>
          <ul>
            <li>Occupational Therapy (OT) – Sensory integration</li>
            <li>Speech-Language Therapy (SLP) – Communication</li>
            <li>Physical Therapy (PT) – Motor coordination</li>
            <li>Music Therapy – Social engagement & expression</li>
            <li>Art Therapy – Emotional regulation</li>
            <li>Equine-Assisted Therapy (horse therapy)</li>
            <li>Aquatic Therapy – Motor & social skills</li>
            <li>Sensory diets & weighted blankets</li>
          </ul>
        </div>
        <div class="card">
          <div class="card-header"><div class="card-icon orange">⚡</div><div class="card-title">Emerging Treatments</div></div>
          <ul>
            <li>Transcranial Magnetic Stimulation (TMS) – Research phase</li>
            <li>Neurofeedback training for attention</li>
            <li>GI microbiome intervention (gut-brain axis research)</li>
            <li>Social robots & AI-assisted learning tools</li>
            <li>Augmentative & Alternative Communication (AAC) devices</li>
          </ul>
        </div>
        <div class="card wide surgery">
          <div class="card-header"><div class="card-icon orange">🔬</div><div class="card-title">Surgical Considerations</div></div>
          <ul>
            <li>No curative surgery exists for ASD itself — surgery is reserved for comorbid conditions</li>
            <li>Epilepsy surgery – ASD has ~30% comorbid epilepsy; resective surgery may benefit both conditions</li>
            <li>Deep Brain Stimulation (DBS) – Experimental for self-injurious behavior in severe ASD</li>
            <li>Gastrointestinal surgery – For severe GI comorbidities impacting quality of life in ASD</li>
          </ul>
        </div>
      </div>
    </div>

    <!-- ══════════════ STRESS ══════════════ -->
    <div class="condition-panel" id="panel-stress">
      <div class="condition-title"><span class="icon">🔥</span> Chronic Stress</div>
      <p class="condition-desc">Chronic stress involves prolonged HPA-axis activation leading to elevated cortisol, immune suppression, cardiovascular strain, cognitive dysfunction, and increased risk of psychiatric disorders.</p>
      <div class="section-grid">
        <div class="card">
          <div class="card-header"><div class="card-icon blue">💊</div><div class="card-title">Pharmacological Support</div></div>
          <ul>
            <li>Ashwagandha (adaptogen) – Cortisol reduction (KSM-66)</li>
            <li>Rhodiola Rosea – Fatigue & stress resilience</li>
            <li>Buspirone – Anxiety-related stress</li>
            <li>Propranolol – Acute physical stress symptoms</li>
            <li>Low-dose SSRIs (if stress triggers anxiety/depression)</li>
            <li>Magnesium Glycinate – Relaxation, sleep quality</li>
            <li>L-Theanine + Caffeine – Alertness without jitteriness</li>
          </ul>
        </div>
        <div class="card">
          <div class="card-header"><div class="card-icon purple">🧠</div><div class="card-title">Psychological Therapies</div></div>
          <ul>
            <li>Mindfulness-Based Stress Reduction (MBSR) – 8-week program</li>
            <li>Cognitive Behavioral Therapy – Stress reframing</li>
            <li>Acceptance & Commitment Therapy (ACT)</li>
            <li>Solution-Focused Brief Therapy (SFBT)</li>
            <li>Relaxation Response training (Dr. Benson's method)</li>
            <li>Positive Psychology interventions</li>
            <li>Resilience coaching & life coaching</li>
          </ul>
        </div>
        <div class="card">
          <div class="card-header"><div class="card-icon green">🏃</div><div class="card-title">Exercises & Mind-Body</div></div>
          <ul>
            <li>Daily 30-min aerobic exercise (walking, cycling, swimming)</li>
            <li>Yoga (Hatha, Yin, Restorative) – HPA axis downregulation</li>
            <li>Tai Chi & Qigong – Moving meditation</li>
            <li>Diaphragmatic breathing – 5-min sessions 3x/day</li>
            <li>Cold shower therapy – Norepinephrine release</li>
            <li>Nature walks (forest bathing / Shinrin-yoku)</li>
            <li>Digital detox & boundary setting</li>
            <li>Proper sleep hygiene (8-hour fixed schedule)</li>
          </ul>
        </div>
        <div class="card">
          <div class="card-header"><div class="card-icon orange">⚡</div><div class="card-title">Advanced Modalities</div></div>
          <ul>
            <li>Heart Rate Variability (HRV) biofeedback</li>
            <li>Neurofeedback – Alpha brain wave training</li>
            <li>Float tank / sensory deprivation therapy</li>
            <li>Massage therapy – Cortisol & blood pressure reduction</li>
            <li>Acupuncture – Evidence-based stress relief</li>
            <li>Transcranial Direct Current Stimulation (tDCS)</li>
          </ul>
        </div>
      </div>
    </div>

    <!-- ══════════════ ADDICTION ══════════════ -->
    <div class="condition-panel" id="panel-addiction">
      <div class="condition-title"><span class="icon">🔗</span> Drug & Substance Addiction</div>
      <p class="condition-desc">Substance Use Disorders (SUD) involve compulsive drug-seeking behavior despite harmful consequences. Includes addiction to opioids, alcohol, stimulants, cannabis, benzodiazepines, and polysubstance use.</p>
      <div class="urgency">
        <div class="urgency-icon">🚨</div>
        <div class="urgency-text"><strong>Overdose Emergency:</strong> For opioid overdose — administer Naloxone (Narcan) if available. Call 911 immediately. Alcohol withdrawal delirium (DTs) is life-threatening — seek emergency care.</div>
      </div>
      <div class="section-grid">
        <div class="card">
          <div class="card-header"><div class="card-icon blue">💊</div><div class="card-title">Medications (MAT)</div></div>
          <ul>
            <li>Methadone – Opioid use disorder (OUD) — daily clinic</li>
            <li>Buprenorphine/Naloxone (Suboxone) – OUD, outpatient</li>
            <li>Naltrexone (Vivitrol) – Opioid & alcohol craving blockade</li>
            <li>Acamprosate (Campral) – Alcohol abstinence maintenance</li>
            <li>Disulfiram (Antabuse) – Alcohol aversion therapy</li>
            <li>Varenicline (Chantix) – Nicotine addiction</li>
            <li>Bupropion (Zyban) – Nicotine cessation</li>
            <li>Modafinil – Cocaine/stimulant use disorder (research)</li>
            <li>N-Acetylcysteine (NAC) – Cannabis & cocaine craving</li>
          </ul>
        </div>
        <div class="card">
          <div class="card-header"><div class="card-icon purple">🧠</div><div class="card-title">Behavioral Therapies</div></div>
          <ul>
            <li>Motivational Interviewing (MI) – Builds change motivation</li>
            <li>Cognitive Behavioral Therapy (CBT) – Relapse prevention</li>
            <li>Contingency Management (CM) – Positive reinforcement</li>
            <li>12-Step Facilitation (AA, NA programs)</li>
            <li>Community Reinforcement Approach (CRA)</li>
            <li>Dialectical Behavior Therapy (DBT)</li>
            <li>Family Behavior Therapy (FBT)</li>
            <li>Trauma-Informed Care (EMDR for co-occurring PTSD)</li>
          </ul>
        </div>
        <div class="card">
          <div class="card-header"><div class="card-icon green">🏃</div><div class="card-title">Recovery & Lifestyle</div></div>
          <ul>
            <li>Intensive Outpatient Programs (IOP)</li>
            <li>Residential rehabilitation (28-day / 90-day programs)</li>
            <li>Exercise therapy – Reduces cravings & improves mood</li>
            <li>Meditation & mindfulness (MBRP – Mindfulness Relapse Prevention)</li>
            <li>Peer recovery support services</li>
            <li>Vocational rehabilitation & employment support</li>
            <li>Nutrition restoration therapy</li>
          </ul>
        </div>
        <div class="card">
          <div class="card-header"><div class="card-icon orange">⚡</div><div class="card-title">Advanced & Emerging</div></div>
          <ul>
            <li>Ketamine-Assisted Therapy – Alcohol & opioid use disorder</li>
            <li>Psilocybin therapy – Alcohol & nicotine (clinical trials)</li>
            <li>Transcranial Magnetic Stimulation (TMS) – Craving reduction</li>
            <li>Deep Brain Stimulation (DBS) – Experimental for severe OUD</li>
            <li>Ibogaine therapy – Africa/clinics; powerful anti-craving</li>
          </ul>
        </div>
        <div class="card wide surgery">
          <div class="card-header"><div class="card-icon orange">🔬</div><div class="card-title">Surgical Interventions</div></div>
          <ul>
            <li>Deep Brain Stimulation (DBS) – Nucleus accumbens targeting for severe, treatment-refractory addiction; ongoing clinical trials</li>
            <li>Implantable Naltrexone (Vivitrol pellet) – Subcutaneous implant for sustained opioid receptor blockade (6 months)</li>
            <li>Vagus Nerve Stimulation (VNS) – Investigational for reducing addiction cravings and co-occurring depression</li>
          </ul>
        </div>
      </div>
    </div>

    <!-- ══════════════ NEURODEGENERATIVE ══════════════ -->
    <div class="condition-panel" id="panel-neuro">
      <div class="condition-title"><span class="icon">🧬</span> Neurodegenerative Diseases</div>
      <p class="condition-desc">Progressive disorders involving neuronal death. Includes Alzheimer's Disease, Parkinson's Disease, Huntington's, ALS (Lou Gehrig's), Multiple Sclerosis, and Frontotemporal Dementia.</p>
      <div class="section-grid">
        <div class="card">
          <div class="card-header"><div class="card-icon blue">💊</div><div class="card-title">Alzheimer's / Dementia</div></div>
          <ul>
            <li>Donepezil (Aricept) – AChE inhibitor, all stages</li>
            <li>Rivastigmine (Exelon) – Mild-moderate Alzheimer's & PD dementia</li>
            <li>Galantamine – Mild-moderate Alzheimer's</li>
            <li>Memantine (Namenda) – Moderate-severe Alzheimer's</li>
            <li>Lecanemab (Leqembi) – Anti-amyloid monoclonal antibody (FDA 2023)</li>
            <li>Donanemab – Anti-amyloid, early Alzheimer's (FDA 2024)</li>
          </ul>
        </div>
        <div class="card">
          <div class="card-header"><div class="card-icon purple">💊</div><div class="card-title">Parkinson's Disease</div></div>
          <ul>
            <li>Levodopa/Carbidopa (Sinemet) – Gold standard dopamine</li>
            <li>Pramipexole / Ropinirole – Dopamine agonists</li>
            <li>Selegiline / Rasagiline – MAO-B inhibitors</li>
            <li>Entacapone (Comtan) – COMT inhibitor, levodopa adjunct</li>
            <li>Amantadine – Dyskinesia control</li>
            <li>Apomorphine – Rescue injection for "off" periods</li>
            <li>Trihexyphenidyl – Tremor control</li>
          </ul>
        </div>
        <div class="card">
          <div class="card-header"><div class="card-icon green">💊</div><div class="card-title">ALS / MS / Huntington's</div></div>
          <ul>
            <li>Riluzole (Rilutek) – ALS; extends survival by months</li>
            <li>Edaravone (Radicava) – ALS neuroprotection</li>
            <li>Tofersen – SOD1-ALS (antisense oligonucleotide)</li>
            <li>Interferon-beta (Avonex, Betaseron) – Relapsing MS</li>
            <li>Natalizumab (Tysabri) – Moderate-severe MS</li>
            <li>Ocrelizumab (Ocrevus) – Primary progressive MS</li>
            <li>Tetrabenazine (Xenazine) – Huntington's chorea</li>
          </ul>
        </div>
        <div class="card">
          <div class="card-header"><div class="card-icon orange">🏃</div><div class="card-title">Therapies & Lifestyle</div></div>
          <ul>
            <li>Physical therapy – Gait, balance, motor function</li>
            <li>Occupational therapy – ADL independence</li>
            <li>Speech therapy – Dysphagia & dysarthria</li>
            <li>Cognitive rehabilitation & brain training</li>
            <li>Exercise: Tai Chi for PD balance; HIIT for neuroprotection</li>
            <li>Mediterranean diet – MIND diet for Alzheimer's prevention</li>
            <li>Palliative & supportive care planning</li>
          </ul>
        </div>
        <div class="card wide surgery">
          <div class="card-header"><div class="card-icon orange">🔬</div><div class="card-title">Surgical & Neuromodulation Interventions</div></div>
          <ul>
            <li>Deep Brain Stimulation (DBS) – Subthalamic nucleus or globus pallidus interna for Parkinson's; dramatically reduces tremor and motor fluctuations</li>
            <li>MRI-Guided Focused Ultrasound (FUS/HIFU) – Non-invasive thalamotomy for essential tremor & PD tremor; FDA-approved</li>
            <li>Gamma Knife Radiosurgery (Thalamotomy) – Non-invasive tremor treatment using focused radiation</li>
            <li>Stem Cell Therapy – Experimental; dopaminergic neuron transplants in Parkinson's (Phase I/II trials)</li>
            <li>Continuous Duodenal Levodopa Infusion (Duodopa pump) – Advanced PD with motor fluctuations</li>
            <li>Gene Therapy (AAV vectors) – Investigational for Parkinson's, ALS, Huntington's neuronal repair</li>
          </ul>
        </div>
      </div>
    </div>

    <!-- ══════════════ NEUROLOGICAL PROBLEMS ══════════════ -->
    <div class="condition-panel" id="panel-neurological">
      <div class="condition-title"><span class="icon">🔮</span> Neurological Problems</div>
      <p class="condition-desc">Covers a broad spectrum: Migraine, Traumatic Brain Injury (TBI), Stroke, Neuropathy, Multiple Sclerosis, Brain Tumors, Hydrocephalus, Movement Disorders, and Spinal Cord disorders.</p>
      <div class="urgency">
        <div class="urgency-icon">🚨</div>
        <div class="urgency-text"><strong>STROKE — Act FAST:</strong> Face drooping · Arm weakness · Speech difficulty · Time to call 911. Thrombolytic therapy (tPA) must be given within 4.5 hours of symptom onset.</div>
      </div>
      <div class="section-grid">
        <div class="card">
          <div class="card-header"><div class="card-icon blue">💊</div><div class="card-title">Key Medications</div></div>
          <ul>
            <li>Sumatriptan / Rizatriptan (Triptans) – Acute migraine</li>
            <li>Topiramate / Propranolol – Migraine prevention</li>
            <li>Erenumab (Aimovig) – CGRP antagonist, migraine prevention</li>
            <li>Aspirin / Clopidogrel – Stroke secondary prevention</li>
            <li>tPA (Alteplase) – Ischemic stroke thrombolysis</li>
            <li>Warfarin / Rivaroxaban – AF-related stroke prevention</li>
            <li>Gabapentin / Pregabalin – Neuropathic pain</li>
            <li>Baclofen – Spasticity in MS, TBI, SCI</li>
            <li>Dexamethasone – Brain tumor edema reduction</li>
            <li>Mannitol / Hypertonic Saline – Raised ICP</li>
          </ul>
        </div>
        <div class="card">
          <div class="card-header"><div class="card-icon purple">🧠</div><div class="card-title">Therapies</div></div>
          <ul>
            <li>Neurorehabilitation – Stroke recovery (constraint-induced movement therapy)</li>
            <li>Cognitive Rehabilitation – TBI, post-stroke memory</li>
            <li>Vestibular Rehabilitation – Balance & dizziness disorders</li>
            <li>Speech-Language Pathology – Aphasia, dysarthria</li>
            <li>Occupational Therapy – ADL retraining post-neuro insult</li>
            <li>TENS & Electrical Stimulation – Peripheral neuropathy</li>
            <li>Transcranial Magnetic Stimulation – Stroke neurorecovery</li>
          </ul>
        </div>
        <div class="card">
          <div class="card-header"><div class="card-icon green">🏃</div><div class="card-title">Exercise & Prevention</div></div>
          <ul>
            <li>Aerobic exercise – Stroke risk reduction, neurogenesis</li>
            <li>Balance training – Parkinson's, cerebellar disorders</li>
            <li>Resistance training – Neuropathy, MS fatigue</li>
            <li>Blood pressure control – Primary stroke prevention</li>
            <li>Diabetes & lipid management – Vascular neuropathy</li>
            <li>Helmet use – TBI prevention; no contact sports post-concussion until cleared</li>
            <li>Omega-3 DHA – Neuroprotective supplementation</li>
          </ul>
        </div>
        <div class="card">
          <div class="card-header"><div class="card-icon orange">⚡</div><div class="card-title">Neuromodulation</div></div>
          <ul>
            <li>Transcranial Magnetic Stimulation (TMS) – Post-stroke rehabilitation</li>
            <li>Epidural Spinal Cord Stimulation – Chronic pain, SCI recovery</li>
            <li>Peripheral Nerve Stimulation – Chronic headache, neuropathy</li>
            <li>Neurofeedback – TBI cognitive recovery</li>
            <li>Spinal Cord Stimulation (SCS) – Failed back surgery syndrome</li>
          </ul>
        </div>
        <div class="card wide surgery">
          <div class="card-header"><div class="card-icon orange">🔬</div><div class="card-title">Surgical Interventions</div></div>
          <ul>
            <li>Craniotomy for Brain Tumor – Resection of gliomas, meningiomas; may include intraoperative awake surgery for eloquent cortex mapping</li>
            <li>Mechanical Thrombectomy – Endovascular clot retrieval for large vessel occlusion stroke; up to 24-hour window</li>
            <li>Clipping / Coiling – Cerebral aneurysm treatment (open clip vs. endovascular coiling)</li>
            <li>VP Shunt (Ventriculoperitoneal) – Hydrocephalus; CSF diversion from ventricles to peritoneum</li>
            <li>Endoscopic Third Ventriculostomy (ETV) – Obstructive hydrocephalus alternative to shunt</li>
            <li>Spinal Decompression (Laminectomy) – Spinal stenosis, disc herniation causing neurological deficits</li>
            <li>Microvascular Decompression (MVD) – Trigeminal neuralgia; relieves vessel compression on CN V</li>
            <li>Gamma Knife / CyberKnife Radiosurgery – Non-invasive stereotactic radiation for tumors, AVM, trigeminal neuralgia</li>
            <li>Carotid Endarterectomy / Carotid Stenting – Stroke prevention in carotid artery stenosis &gt;70%</li>
            <li>Corpus Callosotomy / Hemispherectomy – Refractory epilepsy with neurological etiology</li>
          </ul>
        </div>
      </div>
    </div>

  </div><!-- end content-area -->

  <!-- SIDEBAR -->
  <aside class="sidebar">

    <div class="emergency-box">
      <div class="side-title">🚨 Emergency Contacts</div>
      <a class="em-contact" href="tel:03324552411">
        <span class="em-icon">👨‍⚕️</span>
        <div class="em-info">
          <strong>Dr. Rizvi</strong>
          <span>0332-4552411</span>
        </div>
      </a>
      <a class="em-contact" href="tel:911">
        <span class="em-icon">🚑</span>
        <div class="em-info">
          <strong>Emergency Services</strong>
          <span>Call 911</span>
        </div>
      </a>
    </div>

    <div class="side-card">
      <div class="side-title">📊 Condition Overview</div>
      <div style="margin-bottom:12px">
        <div class="severity">
          <div class="sev-label"><span>Anxiety</span><span>Moderate</span></div>
          <div class="sev-bar"><div class="sev-fill med"></div></div>
        </div>
        <div class="severity">
          <div class="sev-label"><span>Depression</span><span>High</span></div>
          <div class="sev-bar"><div class="sev-fill high"></div></div>
        </div>
        <div class="severity">
          <div class="sev-label"><span>Epilepsy</span><span>High</span></div>
          <div class="sev-bar"><div class="sev-fill high"></div></div>
        </div>
        <div class="severity">
          <div class="sev-label"><span>ASD</span><span>Variable</span></div>
          <div class="sev-bar"><div class="sev-fill med"></div></div>
        </div>
        <div class="severity">
          <div class="sev-label"><span>Stress</span><span>Low-Mod</span></div>
          <div class="sev-bar"><div class="sev-fill low"></div></div>
        </div>
        <div class="severity">
          <div class="sev-label"><span>Addiction</span><span>High</span></div>
          <div class="sev-bar"><div class="sev-fill high"></div></div>
        </div>
        <div class="severity">
          <div class="sev-label"><span>Neurodegeneration</span><span>Very High</span></div>
          <div class="sev-bar"><div class="sev-fill high" style="width:95%;background:linear-gradient(90deg,#ff6b35,#ff3c3c)"></div></div>
        </div>
      </div>
    </div>

    <div class="side-card">
      <div class="side-title">📈 Portal Stats</div>
      <div class="stats-grid">
        <div class="stat-box"><div class="stat-num">8</div><div class="stat-label">Conditions</div></div>
        <div class="stat-box"><div class="stat-num">80+</div><div class="stat-label">Medications</div></div>
        <div class="stat-box"><div class="stat-num">50+</div><div class="stat-label">Therapies</div></div>
        <div class="stat-box"><div class="stat-num">25+</div><div class="stat-label">Surgeries</div></div>
      </div>
    </div>

    <div class="side-card">
      <div class="side-title">⚠️ Important Disclaimer</div>
      <p style="font-size:0.8rem;color:var(--text-muted);line-height:1.6">
        This portal is for <strong style="color:var(--text)">educational reference only</strong>. It does not constitute medical advice, diagnosis, or treatment. Always consult a licensed neurologist, psychiatrist, or physician before starting any medication, therapy, or surgical procedure. Drug dosages, interactions, and contraindications must be verified by a qualified healthcare provider.
      </p>
    </div>

    <div class="brand-footer">
      <div class="brand-name">⚡ Synaptic Synchrotron</div>
      <div class="brand-sub">Neuro Intelligence Portal v2.0</div>
      <div style="font-size:0.68rem;color:var(--text-dim);margin-top:6px">© 2025 All Rights Reserved</div>
    </div>

  </aside>
</div>

<!-- FOOTER -->
<footer>
  Designed by <strong>Synaptic Synchrotron</strong> &nbsp;|&nbsp; Emergency: <a href="tel:03324552411" style="color:var(--accent)">Dr. Rizvi — 0332-4552411</a> &nbsp;|&nbsp; <a href="tel:911" style="color:var(--warn)">911</a> &nbsp;|&nbsp;
  <span style="color:var(--text-dim)">For educational reference only. Not a substitute for professional medical advice.</span>
</footer>

<script>
function showCondition(id) {
  document.querySelectorAll('.condition-panel').forEach(p => p.classList.remove('active'));
  document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
  const panel = document.getElementById('panel-' + id);
  if (panel) panel.classList.add('active');
  document.querySelectorAll('[data-condition="' + id + '"]').forEach(b => b.classList.add('active'));
}

function handleSearch(val) {
  val = val.toLowerCase().trim();
  if (!val) return;

  const map = {
    anxiety: ['anxiety','anxious','panic','phobia','ocd','ptsd','worry','fear'],
    depression: ['depress','sad','mood','mdd','bipolar','postpartum','dysthymia'],
    epilepsy: ['epilepsy','seizure','convulsion','absence','keppra','valproate'],
    autism: ['autism','asd','asperger','spectrum','aba','social skill'],
    stress: ['stress','cortisol','burnout','tension','overwhelm'],
    addiction: ['addiction','drug','substance','alcohol','opioid','heroin','meth','cocaine','nicotine','craving','naltrexone'],
    neuro: ['alzheimer','parkinson','huntington','als','dementia','neurodegenerat','lewy'],
    neurological: ['stroke','migraine','tumor','headache','neuropath','ms','multiple sclerosis','tbi','spinal','brain','nerve','tremor']
  };

  for (const [cond, keywords] of Object.entries(map)) {
    if (keywords.some(k => val.includes(k))) {
      showCondition(cond);
      return;
    }
  }
}

document.getElementById('searchInput').addEventListener('keydown', function(e) {
  if (e.key === 'Enter') handleSearch(this.value);
});
</script>
</body>
</html>
