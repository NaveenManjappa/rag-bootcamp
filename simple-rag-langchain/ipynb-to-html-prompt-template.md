# Reusable Prompt: Convert .ipynb to Styled HTML Learning Page

## PROMPT START

Convert the attached `.ipynb` file into a single, self-contained, visually polished HTML page. Follow these rules exactly and consistently — I will reuse this exact prompt across many notebooks and want every generated page to look and feel identical.

### 1. Content Rules (do not violate)
- Do NOT change, rewrite, summarize, shorten, or "improve" any of the original markdown explanations or code from the notebook. Reproduce them exactly as they appear, in the same order.
- Do NOT skip any cell, even short ones.
- Preserve original code comments exactly as written.
- If a markdown cell has headings (#, ##, ###), map them to matching HTML heading levels (h1, h2, h3).
- Render markdown formatting properly (bold, italics, bullet lists, inline code, links, tables) — don't just dump raw markdown text.

### 2. Fixed Visual Design System (use every time, no variation)
Use this exact CSS design system so all pages look consistent across separate chats:

- **Font**: `'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif` for body/headings; `'JetBrains Mono', 'Fira Code', monospace` for code.
- **Color palette** (CSS variables at `:root`):
  ```css
  --bg-main: #fafafa;
  --bg-card: #ffffff;
  --text-primary: #1a1a1a;
  --text-secondary: #555555;
  --accent: #2563eb;
  --accent-soft: #eff6ff;
  --code-bg: #1e1e2e;
  --code-text: #d4d4d4;
  --code-border: #333349;
  --border-light: #e5e7eb;
  --recap-bg: #fff7ed;
  --recap-border: #fdba74;
  --interview-bg: #f0fdf4;
  --interview-border: #86efac;
  ```
- **Layout**: max content width 860px, centered, generous line-height (1.7) and padding (2–3rem) for readability.
- **Markdown/explanation text**: rendered in `--bg-card` blocks with subtle shadow, rounded corners (8–10px).
- **Code blocks**: visually distinct from text — dark theme (`--code-bg` background, `--code-text` text), monospace font, rounded corners, left accent border in `--accent`, horizontal scroll for long lines, small label at top-right of each block reading the language (e.g. "Python"). Never let code inherit the light theme used for markdown text.
- **Code output** (if any cell has output in the notebook): show below the code block in a lighter gray box with a subtle "Output" label, clearly distinguished from both the code block and the explanation text.
- **Headings**: clear visual hierarchy with the accent color used sparingly (e.g., left border or underline on h2s), not overused.
- **Table of Contents**: auto-generate a sticky/collapsible TOC at the top from the markdown headings, with anchor links to each section.
- **Responsive**: must render cleanly on both desktop and mobile widths.

Use this same palette, spacing scale, and structure every time regardless of notebook topic — this is a fixed template, not something to reinterpret per file.

### 3. Structure of the Output Page
1. Title (from notebook filename or first H1) + short auto-generated subtitle line (1 sentence max, describing scope — do not add extra commentary beyond this).
2. Table of Contents.
3. Full notebook content in original order (markdown explanations + code cells + outputs), styled per section 2.
4. **"Quick Recap"** section (new, added by you, clearly visually separated using `--recap-bg`/`--recap-border`):
   - 5–8 bullet points summarizing the core concepts covered, in plain simplified language (no analogies — direct, systems/technical explanations are fine).
5. **"Interview Prep"** section (new, added by you, clearly visually separated using `--interview-bg`/`--interview-border`):
   - 5–8 likely interview questions on the notebook's topic.
   - For each question, a concise model answer (3–5 sentences, first-person, interview-ready tone) plus one "gotcha" or follow-up point an interviewer might probe.

### 4. Output Format
- Return one complete, valid, self-contained HTML file (inline `<style>`, no external CSS/JS dependencies except optionally Google Fonts link for Inter/JetBrains Mono).
- No placeholder text — fully generated, ready to open in a browser.

## PROMPT END
