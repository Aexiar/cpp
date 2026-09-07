<script setup lang="ts">
import { ArrowRight, Braces, Boxes, Cpu, GitBranch, House, Sparkles, Terminal } from '@lucide/vue'
import { withBase } from 'vitepress'

const topics = [
  { number: '01', icon: Braces, title: '夯实语言基础', en: 'LANGUAGE', description: '掌握现代 C++ 的语法、内存与抽象，理解表达背后的规则。', tags: ['C 语言', '现代 C++', '数据结构'], color: 'rose' },
  { number: '02', icon: Cpu, title: '理解系统底层', en: 'SYSTEM', description: '串联组成原理、操作系统与网络，看清代码如何真正运行。', tags: ['操作系统', '计算机网络', 'Linux'], color: 'cyan' },
  { number: '03', icon: Boxes, title: '走向工程实践', en: 'ENGINEERING', description: '熟悉构建、调试与协作工具，交付清晰可靠的软件。', tags: ['CMake', 'Git', '工程实践'], color: 'amber' },
]

const nodes = [
  { icon: Braces, title: '语言核心', detail: 'C · Modern C++', position: 'language' },
  { icon: Cpu, title: '系统原理', detail: 'OS · Network', position: 'system' },
  { icon: Terminal, title: '开发工具', detail: 'Compiler · Debugger', position: 'tooling' },
  { icon: GitBranch, title: '工程协作', detail: 'Build · Git', position: 'engineering' },
]

const flowPaths = [
  'M110 96 H174 Q198 96 198 120 V161 Q198 175 218 175 H250',
  'M110 256 H174 Q198 256 198 232 V203 Q198 189 218 189 H250',
  'M310 175 H345 Q370 175 370 151 V120 Q370 96 394 96 H450',
  'M310 189 H345 Q370 189 370 213 V232 Q370 256 394 256 H450',
]
</script>

<template>
  <div class="cpp-home">
    <section class="cpp-hero" aria-labelledby="cpp-title">
      <div class="cpp-intro">
        <p class="cpp-eyebrow"><i /> 在这里，读懂代码与计算机</p>
        <h1 id="cpp-title">走进 C++ 的世界<br><span>让知识，编译成能力。</span></h1>
        <p class="cpp-description">从第一行代码，到每一个完整项目。<br>系统学习 C/C++、计算机基础与工程实践。</p>
        <div class="cpp-actions">
          <a class="cpp-secondary" :href="withBase('/')"><House :size="17" />首页</a>
          <a class="cpp-primary" :href="withBase('/00.计算机背景知识/01.计算机软件常识')">开启学习之旅<ArrowRight :size="17" /></a>
        </div>
        <div class="cpp-notes"><span>系统梳理</span><span>原理驱动</span><span>持续实践</span></div>
      </div>

      <div class="cpp-visual" role="img" aria-label="C++ 知识体系：以语言核心为中心，连接系统原理、开发工具与工程协作。">
        <div class="visual-label"><span><i /> THE C++ JOURNEY</span><span>从语法到工程</span></div>
        <div class="cpp-orbit orbit-one" /><div class="cpp-orbit orbit-two" />
        <svg class="cpp-connectors" viewBox="0 0 560 350" fill="none" aria-hidden="true">
          <g v-for="(path, index) in flowPaths" :key="path"><path :d="path" /><path class="cpp-flow" :d="path" pathLength="100" :style="{ animationDelay: `${index * -0.8}s` }" /></g>
        </svg>
        <div v-for="node in nodes" :key="node.position" class="cpp-node" :class="node.position"><component :is="node.icon" :size="24" :stroke-width="1.6" /><strong>{{ node.title }}</strong><small>{{ node.detail }}</small></div>
        <div class="cpp-core"><Braces :size="43" :stroke-width="1.4" /><strong>C++</strong><small>理解 · 构建 · 优化</small></div>
        <div class="visual-caption"><Sparkles :size="14" /> 从底层原理出发，写出清晰可靠的代码</div>
      </div>
    </section>

    <div class="cpp-stack"><span>构建你的知识体系</span><div><b>C</b><i /><b>C++</b><i /><b>Data Structure</b><i /><b>Linux</b><i /><b>Toolchain</b></div><span>保持思考 · 动手验证</span></div>
    <section class="cpp-learning" aria-labelledby="learning-title">
      <div class="learning-heading"><div><p>LEARN · UNDERSTAND · BUILD</p><h2 id="learning-title">每一层理解，都让下一次编码更从容</h2></div><span>循序渐进，建立完整的计算机知识体系</span></div>
      <div class="cpp-topics">
        <article v-for="topic in topics" :key="topic.number" class="cpp-topic" :class="topic.color"><div class="topic-top"><div class="topic-icon"><component :is="topic.icon" :size="23" :stroke-width="1.7" /></div><span>{{ topic.number }} / {{ topic.en }}</span></div><h3>{{ topic.title }}</h3><p>{{ topic.description }}</p><div class="topic-tags"><span v-for="tag in topic.tags" :key="tag">{{ tag }}</span></div></article>
      </div>
    </section>
    <p class="cpp-closing"><span />保持好奇，让每一行代码都通向更深的理解<span /></p>
  </div>
</template>

<style scoped>
.cpp-home { --cpp-text: #29252d; --cpp-muted: #716b78; --cpp-accent: #b83256; --cpp-line: #e3dfe4; --cpp-surface: rgb(255 255 255 / 76%); max-width: 1200px; margin: 0 auto; padding: clamp(24px, 4vh, 40px) 32px 16px; color: var(--cpp-text); line-height: 1.5; }
.cpp-hero { display: grid; grid-template-columns: 1fr 1fr; align-items: center; gap: 48px; padding: 8px 0 clamp(20px, 3vh, 28px); }
.cpp-eyebrow { display: flex; align-items: center; gap: 10px; color: var(--cpp-accent); font-size: 12px; letter-spacing: 2px; margin: 0 0 10px; }
.cpp-eyebrow i, .visual-label i { display: inline-block; width: 6px; height: 6px; border-radius: 50%; background: #d04b6d; box-shadow: 0 0 0 4px rgb(184 50 86 / 10%); }
.cpp-intro h1 { padding: 0; text-align: left; font-size: clamp(30px, 3vw, 40px); line-height: 1.3; letter-spacing: 0; font-weight: 750; margin: 0; }
.cpp-intro h1::after { display: none; }.cpp-intro h1 span { color: var(--cpp-accent); background: linear-gradient(110deg, #a72d50, #c04462 58%, #8d476e); background-clip: text; -webkit-text-fill-color: transparent; }
.cpp-description { margin: 10px 0 14px; font-size: 15px; line-height: 1.6; color: var(--cpp-muted); }
.cpp-actions { display: flex; flex-wrap: wrap; gap: 12px; }.cpp-actions a { display: inline-flex; align-items: center; justify-content: center; gap: 14px; padding: 10px 18px; border-radius: 8px; font-size: 13px; line-height: 24px; font-weight: 600; transition: transform .2s, box-shadow .2s; }.cpp-actions a:hover { transform: translateY(-2px); box-shadow: 0 6px 16px rgb(184 50 86 / 18%); }.cpp-actions a:focus-visible { outline: 3px solid var(--cpp-accent); outline-offset: 4px; }
.cpp-primary { background: linear-gradient(110deg, #a72d50, #c04462); color: white; }.cpp-secondary { background: rgb(184 50 86 / 6%); border: 1px solid #ddbac5; color: var(--cpp-accent); }
.cpp-notes { display: flex; gap: 22px; margin-top: 12px; color: var(--cpp-muted); font-size: 11px; }.cpp-notes span::before { content: '•'; color: #c391a0; margin-right: 7px; }
.cpp-visual { position: relative; width: 100%; aspect-ratio: 560 / 350; background-image: radial-gradient(rgb(127 88 108 / 14%) .8px, transparent .8px); background-size: 18px 18px; }.visual-label { position: absolute; inset: 0 0 auto; display: flex; justify-content: space-between; color: var(--cpp-muted); font-size: 9px; letter-spacing: 1.8px; }.visual-label i { margin-right: 9px; }.visual-label > span:last-child { letter-spacing: 0; }
.cpp-connectors { position: absolute; inset: 0; width: 100%; height: 100%; stroke: #c9a8b4; stroke-width: 1.2; }.cpp-orbit { position: absolute; border: 1px solid rgb(184 50 86 / 10%); border-radius: 50%; top: 52%; left: 50%; transform: translate(-50%, -50%); aspect-ratio: 1; }.orbit-one { width: 44%; }.orbit-two { width: 60%; }
.cpp-node { position: absolute; width: 23%; height: 25%; display: flex; flex-direction: column; align-items: center; justify-content: center; gap: 6px; background: var(--cpp-surface); border: 1px solid #ddbcc6; border-radius: 8px; color: #a72d50; }.cpp-node strong { color: var(--cpp-text); font-size: 12px; }.cpp-node small { color: var(--cpp-muted); font-size: 9px; }.language { left: 2%; top: 15%; }.system { left: 2%; bottom: 14%; border-color: #b8d2d8; color: #14758a; }.tooling { right: 2%; top: 15%; border-color: #cfc2db; color: #76578a; }.engineering { right: 2%; bottom: 14%; border-color: #dfc99c; color: #a46a16; }
.cpp-core { position: absolute; top: 52%; left: 50%; transform: translate(-50%, -50%); width: 24%; height: 37%; display: flex; flex-direction: column; align-items: center; justify-content: center; gap: 10px; border: 1px solid #d6a5b4; border-radius: 8px; background: linear-gradient(140deg, #f8e8ed, #eee7f0); box-shadow: 0 0 0 7px rgb(255 255 255 / 42%), 0 12px 35px rgb(184 50 86 / 11%); color: #a72d50; }.cpp-core strong { font-size: 20px; letter-spacing: 4px; font-weight: 500; }.cpp-core small { font-size: 9px; letter-spacing: 1px; }.visual-caption { position: absolute; bottom: 0; width: 100%; display: flex; align-items: center; justify-content: center; gap: 7px; color: var(--cpp-muted); font-size: 10px; }
.cpp-stack { display: flex; align-items: center; justify-content: space-between; gap: 20px; padding: 12px 0; border-block: 1px solid var(--cpp-line); color: var(--cpp-muted); font-size: 11px; }.cpp-stack > div { display: flex; align-items: center; gap: 25px; }.cpp-stack b { font-size: 16px; font-weight: 600; line-height: 24px; letter-spacing: 0; }.cpp-stack i { width: 3px; height: 3px; background: #c6adb6; border-radius: 50%; }
.cpp-learning { padding-top: clamp(20px, 3vh, 28px); }.learning-heading { display: flex; justify-content: space-between; align-items: flex-end; gap: 16px; margin-bottom: 18px; }.learning-heading p { font-size: 9px; letter-spacing: 2px; color: var(--cpp-accent); margin: 0 0 8px; }.learning-heading h2 { padding: 0; border: 0; font-size: 20px; font-weight: 650; line-height: 1.5; letter-spacing: 0; margin: 0; }.learning-heading > span { font-size: 11px; color: var(--cpp-muted); }
.cpp-topics { display: grid; grid-template-columns: repeat(3, 1fr); gap: 18px; }.cpp-topic { --topic-color: #a72d50; --topic-border: #ddbcc6; --topic-tint: rgb(184 50 86 / 7%); position: relative; overflow: hidden; border: 1px solid var(--topic-border); border-radius: 8px; padding: 20px; background: var(--cpp-surface); }.cpp-topic::before { content: ''; position: absolute; top: 0; left: 18px; right: 18px; height: 2px; background: linear-gradient(90deg, var(--topic-color), transparent); opacity: .6; }.cyan { --topic-color: #14758a; --topic-border: #bad2d8; --topic-tint: rgb(20 117 138 / 7%); }.amber { --topic-color: #9a681d; --topic-border: #dfcca9; --topic-tint: rgb(154 104 29 / 7%); }
.topic-top { display: flex; align-items: center; gap: 12px; color: var(--topic-color); }.topic-top > span { line-height: 24px; font-size: 9px; letter-spacing: 1px; }.topic-icon { padding: 7px; border-radius: 8px; background: var(--topic-tint); }.cpp-topic h3 { font-size: 17px; font-weight: 650; margin: 8px 0 5px; }.cpp-topic p { font-size: 12px; line-height: 1.9; color: var(--cpp-muted); margin: 0; }.topic-tags { margin-top: 10px; display: flex; flex-wrap: wrap; gap: 7px; }.topic-tags span { color: var(--topic-color); background: var(--topic-tint); border-radius: 4px; padding: 2px 8px; font-size: 10px; line-height: 16px; }
.cpp-closing { display: flex; align-items: center; justify-content: center; gap: 14px; margin: clamp(18px, 2.5vh, 24px) 0 0; font-size: 11px; color: var(--cpp-muted); }.cpp-closing span { width: 24px; height: 1px; background: var(--cpp-line); }
:global(.is-home-page .Layout:has(.cpp-home)) { background-image: radial-gradient(ellipse at 72% 18%, rgb(177 222 204 / 23%), transparent 46%), linear-gradient(150deg, rgb(226 244 235 / 72%), transparent 58%), linear-gradient(215deg, rgb(229 239 246 / 58%), transparent 58%); background-size: auto; }:global(.VPHome:has(.cpp-home)) { margin-bottom: 0; }:global(.Layout:has(.cpp-home) .VPFooter) { padding: 16px 24px; }
:global(.dark .cpp-home) { --cpp-text: #dcebe4; --cpp-muted: #a7bbb2; --cpp-accent: #5bd69a; --cpp-line: #31483e; --cpp-surface: rgb(24 40 34 / 84%); }:global(.dark .is-home-page .Layout:has(.cpp-home)), :global(.dark.is-home-page .Layout:has(.cpp-home)) { background-image: radial-gradient(ellipse at 70% 18%, rgb(42 113 82 / 24%), transparent 50%), linear-gradient(145deg, rgb(28 75 68 / 30%), transparent 65%); }:global(.dark .cpp-home .cpp-core) { background: linear-gradient(140deg, #183f32, #24453e); color: #8de1b5; border-color: #467d65; box-shadow: 0 0 0 7px rgb(93 167 133 / 8%); }:global(.dark .cpp-home .cpp-topic) { --topic-border: #3a5549; --topic-color: #a6d3bf; }:global(.dark .cpp-home .blue) { --topic-border: #3b5965; --topic-color: #8cc7d8; }:global(.dark .cpp-home .amber) { --topic-border: #615438; --topic-color: #dec28d; }
.cpp-flow { stroke: var(--cpp-accent); stroke-width: 2; stroke-linecap: round; stroke-dasharray: 5 95; animation: cpp-flow 4s linear infinite; }.cpp-core::before { content: ''; position: absolute; inset: -8px; border: 1px solid rgb(41 151 100 / 34%); border-radius: 12px; animation: cpp-pulse 4s ease-out infinite; pointer-events: none; }.cpp-core > svg { animation: cpp-float 5s ease-in-out infinite; }.visual-label i { animation: cpp-beacon 3s ease-in-out infinite; }
@keyframes cpp-flow { to { stroke-dashoffset: -100; } } @keyframes cpp-pulse { 0% { transform: scale(1); opacity: .65; } 85%, 100% { transform: scale(1.25); opacity: 0; } } @keyframes cpp-float { 0%, 100% { transform: translateY(0); } 50% { transform: translateY(-4px); } } @keyframes cpp-beacon { 0%, 100% { opacity: 1; } 50% { opacity: .4; } }
@media (max-width: 960px) { .cpp-hero { gap: 24px; }.cpp-stack > span:last-child, .learning-heading > span { display: none; }.cpp-stack > div { gap: 18px; }.cpp-core { gap: 5px; }.cpp-core svg { width: 32px; } }
@media (max-width: 700px) { .cpp-home { padding: 32px 24px 20px; }.cpp-hero { grid-template-columns: 1fr; gap: 36px; padding-bottom: 30px; }.cpp-intro { text-align: center; }.cpp-eyebrow, .cpp-actions, .cpp-notes { justify-content: center; }.cpp-intro h1 { text-align: center; font-size: clamp(27px, 6vw, 38px); line-height: 1.4; }.cpp-description { font-size: 13px; line-height: 1.8; }.cpp-visual { max-width: 520px; margin: auto; }.cpp-stack { flex-direction: column; gap: 12px; }.cpp-stack > div { gap: 12px; }.cpp-stack b { font-size: 12px; }.cpp-learning { padding-top: 30px; }.learning-heading h2 { font-size: 18px; }.cpp-topics { grid-template-columns: 1fr; gap: 14px; }.cpp-topic { padding: 20px; }.cpp-topic h3 { font-size: 15px; line-height: 22px; }.cpp-topic p { line-height: 1.6; }.cpp-closing { font-size: 10px; gap: 8px; }.cpp-closing span { width: 12px; }.cpp-node { gap: 4px; }.cpp-node > svg { width: 19px; height: 19px; flex-shrink: 0; }.cpp-node strong { font-size: 10px; line-height: 1.4; }.cpp-node small { font-size: 7px; line-height: 1.4; white-space: nowrap; }.cpp-core { gap: 4px; }.cpp-core > svg { width: 28px; height: 28px; flex-shrink: 0; }.cpp-core strong { font-size: 16px; letter-spacing: 2px; }.cpp-core small { font-size: 7px; letter-spacing: 0; } }
@media (min-width: 961px) and (max-height: 900px) { .cpp-home { padding-top: 16px; padding-bottom: 12px; }.cpp-hero { padding-bottom: 16px; }.cpp-visual { max-width: 408px; justify-self: end; }.cpp-intro h1 { font-size: 32px; }.cpp-eyebrow { margin-bottom: 8px; }.cpp-description { margin: 12px 0; line-height: 1.7; }.cpp-actions a { padding: 10px 16px; }.cpp-notes { margin-top: 8px; }.cpp-learning { padding-top: 16px; }.learning-heading h2 { font-size: 18px; }.learning-heading p { margin-bottom: 5px; }.cpp-topic h3 { margin-top: 10px; margin-bottom: 6px; }.cpp-topic p { margin-bottom: 10px; }.learning-heading { margin-bottom: 12px; }.cpp-topic { padding: 16px; }.cpp-closing { margin-top: 18px; }:global(.Layout:has(.cpp-home) .VPFooter) { padding: 12px 24px; } }
@media (prefers-reduced-motion: reduce) { .cpp-flow, .cpp-core::before, .cpp-core > svg, .visual-label i { animation: none; }.cpp-flow, .cpp-core::before { opacity: 0; }.cpp-actions a { transition: none; }.cpp-actions a:hover { transform: none; } }
</style>
