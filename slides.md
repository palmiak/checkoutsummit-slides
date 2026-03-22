---
theme: default
title: 'WooCommerce Hosts Promise "Advanced Security". But Do They Deliver?'
highlighter: shiki
canvasWidth: 1920
transition: fade
layout: default
class: title-slide
---

<CircuitBg />
<div class="body">
  <div class="title-prompt">
    $ ./pentest <span style="color:var(--purple);">--target</span>="woocommerce-hosts" <span style="color:var(--purple);">--exploits</span>="20+"
  </div>
  <div class="title-main">
    WooCommerce Hosts Promise<br>
    <em style="color:var(--purple);">"Advanced Security."</em><span class="cursor" style="background:var(--purple);"></span>
  </div>
  <div class="title-sub">
    But Do They Deliver? We Tested 20+ Providers Using Real Exploits.
  </div>
</div>
<div class="title-event">Checkout Summit 2026</div>

---
layout: image-only
---

<img src="/matt-tweet.png" style="max-width:88%;max-height:78vh;object-fit:contain;" />

---
layout: image-only
---

<img src="/mj-took-it-personally.png" style="max-width:88%;max-height:78vh;object-fit:contain;" />

---
layout: chapter
color: purple
---

<CrosshairBg />
<ChapterBg num="01" />
<div class="body">
  <div class="chapter-eyebrow">Chapter 01</div>
  <div class="chapter-title">The Threat<br><em>Landscape</em></div>
</div>

---
layout: content
gutter: Market Dominance
---

<div class="content-headline">WooCommerce is a<br><em>massive target</em></div>
<Blocks>
  <BlocksRow>
    <Block label="WordPress market share">
      <div style="font-family:var(--mono);font-size:clamp(28px,4vw,52px);font-weight:300;color:var(--text-1);margin-bottom:4px;">43%</div>
      <div class="block-text">of all websites</div>
    </Block>
    <Block label="WooCommerce share">
      <div style="font-family:var(--mono);font-size:clamp(28px,4vw,52px);font-weight:300;color:var(--text-1);margin-bottom:4px;">~40%</div>
      <div class="block-text">of all online stores</div>
    </Block>
  </BlocksRow>
  <Block>
    <div class="block-text">One exploit technique = thousands of potential targets. High-value payload: payment data, customer records, admin access.</div>
  </Block>
</Blocks>

---
layout: stat
---

<StatContent
  label="WordPress vulnerabilities — 2025"
  number="11,334"
  sublabel="new vulnerabilities disclosed in a single year"
  sub="+42% year-over-year"
/>

---
layout: stat
---

<StatContent
  label="Where the risk lives"
  number="91%"
  numberColor="danger"
  sublabel="of vulnerabilities are in plugins — not core"
  sub="Only 6 CVEs found in WordPress core in 2025"
/>

---
layout: stat
---

<StatContent
  label="Exploitation speed"
  number="~5 hrs"
  numberColor="danger"
  numberSize="clamp(72px,15vw,200px)"
  sublabel="median time from public disclosure to mass exploitation"
  sub="You don't have days to respond. You have hours."
/>

---
layout: stat
---

<StatContent
  label="The patch gap"
  number="46%"
  numberColor="danger"
  sublabel="of vulnerabilities had no patch at time of disclosure"
  sub="&quot;Keep plugins updated&quot; isn't enough on its own"
/>

---
layout: content
gutter: CVSS 10.0
---

<div class="content-headline">This is the entire attack</div>
<CodeBlock title="HTTP REQUEST — Modular DS / January 2026">GET /wp-admin/admin-ajax.php?action=mo_login&amp;origin=mo&amp;type=xxx</CodeBlock>
<Block variant="red" label="Result" labelAccent="red">
  <div class="block-text"><strong>Instant admin access.</strong> No username. No password. No complexity. One URL, full control.</div>
</Block>

---
layout: content
gutter: Case Study
---

<div class="content-headline">Modular DS — January 2026</div>
<Blocks>
  <Block label="Scope">
    <div class="block-text"><strong>40,000+ active installations.</strong> CVSS <span class="red">10.0</span> — maximum severity.</div>
  </Block>
  <Block label="Timeline">
    <div class="block-text">
      <strong>2 AM</strong> — mass attacks detected<br>
      <strong>+31 hours</strong> — patch released<br>
      <strong>+2 days</strong> — second attack vector discovered
    </div>
  </Block>
  <Block variant="red" label="The twist" labelAccent="red">
    <div class="block-text">Attackers installed the old vulnerable version as a <strong>permanent backdoor</strong> on compromised sites.</div>
  </Block>
</Blocks>

---
layout: chapter
color: purple
---

<BrokenLockBg />
<ChapterBg num="02" />
<div class="body">
  <div class="chapter-eyebrow">Chapter 02</div>
  <div class="chapter-title">What Your<br>Clients <em>Face</em></div>
</div>

---
layout: content
gutter: Financial Impact
---

<div class="content-headline">Chargebacks &amp;<br>payment processor <em>risk</em></div>
<Blocks>
  <Block>
    <div class="block-text">Fraudulent orders via stolen admin access. Chargebacks trigger processor fraud flags.</div>
  </Block>
  <Block>
    <div class="block-text">Rebuilding payment processing relationships takes months — if it's even possible.</div>
  </Block>
  <Block variant="red" label="Worst case" labelAccent="red">
    <div class="block-text"><strong>Merchant account suspension or permanent ban.</strong> Revenue stops cold.</div>
  </Block>
</Blocks>

---
layout: content
gutter: Legal Impact
---

<div class="content-headline">PCI DSS &amp; GDPR<br><em>violations</em></div>
<Blocks>
  <Block>
    <div class="block-text">Payment breach → PCI DSS non-compliance → forensic audits, remediation plans, quarterly scans.</div>
  </Block>
  <Block>
    <div class="block-text">GDPR mandates breach notification within <strong>72 hours.</strong> Regulators act fast on payment data.</div>
  </Block>
  <BlocksRow>
    <Block variant="red" label="GDPR max fine" labelAccent="red">
      <div class="block-text" style="font-size:clamp(14px,1.8vw,22px);font-weight:500;color:var(--text-1);">€20M or 4% of annual revenue</div>
    </Block>
    <Block label="And who gets the call?">
      <div class="block-text" style="font-size:clamp(14px,1.8vw,22px);font-weight:500;color:var(--text-1);">You.</div>
    </Block>
  </BlocksRow>
</Blocks>

---
layout: content
gutter: Reputational Impact
---

<div class="content-headline">Customer trust —<br>nearly impossible to <em>rebuild</em></div>
<Blocks>
  <Block>
    <div class="block-text">GDPR requires public disclosure. The breach becomes news. Customers leave. Reviews accumulate for years.</div>
  </Block>
  <Block>
    <div class="block-text">Competitors absorb the lost customer base. Customer acquisition costs spike while the store rebuilds.</div>
  </Block>
  <Block variant="red" label="The reality" labelAccent="red">
    <div class="block-text"><strong>For small and mid-size stores, this is often fatal.</strong></div>
  </Block>
</Blocks>

---
layout: statement
---

<div class="statement-text">
  A hacked WooCommerce store is a <em>business crisis.</em>
</div>

---
layout: chapter
color: purple
---

<TerminalBg />
<ChapterBg num="03" />
<div class="body">
  <div class="chapter-eyebrow">Chapter 03</div>
  <div class="chapter-title">Testing the<br><em>Claims</em></div>
</div>

---
layout: content
gutter: The Claim
---

<div class="content-headline" style="margin-bottom:clamp(28px,5vw,52px);">Some hosts tell you not to<br>install security plugins</div>
<QuoteBlock source="— Kinsta documentation">
  &ldquo;If your site is hosted at Kinsta, you don&apos;t need to install a third-party security plugin because we have many popular security features built into our infrastructure.&rdquo;
</QuoteBlock>

---
layout: content
gutter: Methodology
---

<div class="content-headline">We didn't take<br>their word for it</div>
<BulletList>
  <li><span>Real WordPress installations, real vulnerable plugins</span></li>
  <li><span>Public proof-of-concept exploits — no obfuscation, no evasion</span></li>
  <li><span><em>All available security features enabled</em> on every provider</span></li>
  <li><span>Same test setup across all providers, independent observers</span></li>
  <li><span>WooCommerce-specific plugins included</span></li>
</BulletList>

---
layout: stat
---

<StatContent
  label="The main study"
  number="18 hosts"
  numberSize="clamp(64px,13vw,160px)"
  sublabel="tested across different tiers and regions"
  sub="30 vulnerabilities · all security features enabled on every provider"
/>

---
layout: stat
---

<StatContent
  label="Average block rate — 18 providers"
  number="26%"
  numberColor="danger"
  sublabel="of attacks blocked on average"
  sub="74% getting through — with all defenses active"
/>

---
layout: stat
---

<StatContent
  label="Privilege escalation attacks blocked"
  number="12%"
  numberColor="danger"
  sublabel="of the attacks that hand an attacker full admin access"
  sub="Nearly 9 out of 10 got through — across all 18 providers"
/>

---
layout: stat
---

<StatContent
  label="Arbitrary file upload attacks blocked"
  number="60%"
  numberColor="green"
  sublabel="the one category where hosting security held up"
  sub="WAFs recognize classic attack patterns — just not WordPress-specific ones"
/>

---
layout: stat
---

<StatContent
  label="Earlier pilot study"
  number="87.8%"
  numberColor="danger"
  numberSize="clamp(72px,15vw,190px)"
  sublabel="of attacks bypassed defenses in our pilot"
  sub="5 providers · 11 vulnerabilities · this is what motivated the main study"
/>

---
layout: chapter
color: purple
---

<LayerStackBg />
<ChapterBg num="04" />
<div class="body">
  <div class="chapter-eyebrow">Chapter 04</div>
  <div class="chapter-title">Why Protection<br><em>Fails</em></div>
</div>

---
layout: content
gutter: The Mismatch
---

<div class="content-headline">WAFs see packets.<br>WordPress attacks hide in <em>application logic.</em></div>
<CompareGrid
  leftLabel="What WAFs were built for"
  leftTitle="Generic attacks"
  :leftItems="['SQL injection in URL parameters', 'XSS in form fields', 'Path traversal in file requests']"
  rightLabel="What WordPress attacks look like"
  rightTitle="Normal traffic"
  :rightItems="['Valid admin-ajax.php call with malicious payload', 'Legitimate plugin endpoint exploited through its own logic', 'Privilege escalation via plugin authentication flow']"
/>

---
layout: content
gutter: Transparency
---

<div class="content-headline">Why we didn't<br>name the hosts</div>
<Blocks>
  <Block>
    <div class="block-text">Naming hosts creates false safety — <strong>&ldquo;my host isn&apos;t on the list, I&apos;m fine.&rdquo;</strong> That&apos;s not true.</div>
  </Block>
  <Block>
    <div class="block-text">We tested additional providers privately. Same results. The tools are industry-standard: Cloudflare, Imunify360, ModSecurity.</div>
  </Block>
  <Block variant="red" label="The finding" labelAccent="red">
    <div class="block-text">Different hosts running the <strong>same tools</strong> showed the <strong>same gaps.</strong> This is a structural problem, not a vendor problem.</div>
  </Block>
</Blocks>

---
layout: image-only
---

<div style="font-family:var(--mono);font-size:clamp(18px,3vw,36px);font-weight:400;letter-spacing:-0.02em;color:var(--text-1);margin-bottom:clamp(20px,3vw,32px);text-align:center;">
  We notified the hosts.<br>Many did nothing.
</div>
<img src="/this-is-fine.jpg" style="max-width:min(680px,86%);max-height:420px;object-fit:contain;" />

---
layout: image-only
---

<img src="/grus-plan.png" style="max-width:min(780px,88%);max-height:540px;object-fit:contain;" />

---
layout: chapter
color: purple
---

<ShieldBg />
<ChapterBg num="05" />
<div class="body">
  <div class="chapter-eyebrow">Chapter 05</div>
  <div class="chapter-title">The<br><em>Solution</em></div>
</div>

---
layout: cheese
gutter: Defense in Depth
---

<template #diagram>
  <SwissCheese :activeLayer="1" />
</template>

<template #info>
  <div class="cheese-layer-tag">Layer 01 / Network</div>
  <div class="content-headline" style="font-size:clamp(22px,3vw,38px);margin-bottom:clamp(20px,3vw,32px);">Your host&apos;s<br>first line of defence</div>
  <Blocks>
    <Block>
      <div class="block-text">Host WAF, DDoS protection, IP reputation filtering. Handles volumetric attacks and known bad actors well.</div>
    </Block>
    <Block variant="red" label="But" labelAccent="red">
      <div class="block-text"><strong>Blocks ~26% of WordPress-specific attacks.</strong> The other 74% pass straight through the holes.</div>
    </Block>
  </Blocks>
</template>


---
layout: cheese
gutter: Defense in Depth
---

<template #diagram>
  <SwissCheese :activeLayer="2" />
</template>

<template #info>
  <div class="cheese-layer-tag">Layer 02 / Application</div>
  <div class="content-headline" style="font-size:clamp(22px,3vw,38px);margin-bottom:clamp(20px,3vw,32px);">WordPress-aware<br>protection</div>
  <Blocks>
    <Block>
      <div class="block-text">A WordPress-aware firewall understands plugin request context — it catches what network WAFs can&apos;t see.</div>
    </Block>
    <Block label="Virtual patching">
      <div class="block-text">Blocks known exploits <strong>before a code fix exists</strong> — closing the gap between disclosure and patch.</div>
    </Block>
    <Block variant="red" label="But" labelAccent="red">
      <div class="block-text">Still has holes. <strong>Zero-days and unknown plugins</strong> can slip through.</div>
    </Block>
  </Blocks>
</template>


---
layout: cheese
gutter: Defense in Depth
---

<template #diagram>
  <SwissCheese :activeLayer="3" />
</template>

<template #info>
  <div class="cheese-layer-tag">Layer 03 / Operational</div>
  <div class="content-headline" style="font-size:clamp(22px,3vw,38px);margin-bottom:clamp(20px,3vw,32px);">Every layer has holes.<br><em style="color:var(--green);">Together they don&apos;t.</em></div>
  <Blocks>
    <Block>
      <div class="block-text">Vulnerability monitoring, fast patching cadence, incident response plan. Shrinks the window between disclosure and defence.</div>
    </Block>
    <Block>
      <div class="block-text">No single layer blocks everything. The Swiss cheese model works because the <strong>holes never align</strong> across all three.</div>
    </Block>
  </Blocks>
</template>


---
layout: content
gutter: Action Items
---

<div class="content-headline">What you tell<br>your clients <em style="color:var(--amber);">now</em></div>
<BulletList color="green">
  <li><span>The host is not enough — you now have the <em>data to prove it</em></span></li>
  <li><span><em>Virtual patching</em> should ship with every WooCommerce project you deliver</span></li>
  <li><span><em>Vulnerability monitoring</em> is a default recommendation, not an afterthought</span></li>
</BulletList>

---
layout: conclusion
---

<div class="s-label accent-green">Conclusion</div>
<div class="conclusion-title">You know what<br>to <em style="color:var(--green);">tell them.</em></div>
<div class="conclusion-sub">Their host won&apos;t save them. But you can.</div>

---
layout: thanks
---

<div class="thanks-word">Thank<br>you.</div>

---
layout: content
gutter: One More Thing
---

<div class="kicker-text">
  <p>The plugins your clients install next year? Many won&apos;t be in any vulnerability database.</p>
  <p>Vibecoded, AI-assisted, shipped fast. Security researchers won&apos;t know they exist until after they&apos;re exploited.</p>
</div>
<div class="kicker-warning">
  The same AI writing that code<br>is already writing the exploits.
</div>

---
layout: thanks
---

<div class="thanks-word">What questions<br>do you <em style="color:var(--green);font-style:normal;">have?</em></div>
