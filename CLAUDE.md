# Job Application Assistant for Michael J. Marrujo

## Role
This repo is a job application workspace. Claude acts as a career advisor and application assistant for Michael J. Marrujo, helping with:
1. **Job fit evaluation** - Assess job postings against your profile (skills, experience, behavioral traits)
2. **CV tailoring** - Adapt existing CV templates (LaTeX/moderncv) to target specific roles
3. **Cover letter writing** - Draft targeted cover letters using existing templates (LaTeX)
4. **Interview preparation** - Prepare answers, questions, and talking points for interviews
5. **Career strategy** - Advise on positioning and personal branding

## Candidate Profile

### Identity
- **Name:** Michael J. Marrujo
- **Location:** Orange County, CA, USA (open to relocation — US and English-speaking Europe)
- **Contact:** michaelmarrujo3@gmail.com · 714-321-4564
- **Languages:** English (native), Spanish (professional proficiency)
- **Status:** Employed and actively searching — AI Strategist at Container Supply Company and Founder of Theron Digital (AI consulting practice)
- **Positioning:** AI implementer at the intersection of business operations and software — ships working AI-enabled tools, drives org-wide AI adoption, translates fluently between the C-suite and the shop floor

### Education
- **BA in Neuroscience & Behavior, Minor in Business Economics** (2019-2023) - University of Notre Dame
  - GPA: 3.63/4.00; studied abroad at Trinity College Dublin
  - Youth tutor, MC3 Mentors

### Professional Experience
- **Founder & Principal Consultant** (Mar 2026 - Present) - **Theron Digital** (Orange County, CA)
  - Founded and run an AI-enabled consulting practice: incorporated the LLC, built the website (HTML/CSS/JavaScript), and publish content driving inbound interest
  - Scoped and built a custom profitability web application for a $5M landscape services client to surface margin drivers across service lines and inform pricing
- **AI Strategist** (Jan 2026 - Present) / **Business Operations Analyst** (Mar 2024 - Sep 2025) - **Container Supply Company** (Garden Grove, CA)
  - Designed and built from scratch a full-stack web application (JavaScript, HTML/CSS) replacing the paper-based order workflow at a $40M manufacturer; rearchitected order structure with sales, logistics, finance, and purchasing leadership, eliminating recurring C-suite-to-floor escalations
  - Owns company AI adoption: ran the Claude and Gemini rollout, taught internal training on prompt and workflow design, brought the dev team onto Claude Code; consolidated 30 unused licenses for $6K annual savings
  - Building a full-stack maintenance app (vs. $36K off-the-shelf software) to replace a Google Sheets system and clear SQF certification worth $1M+ in client revenue
  - Moved the company from mailed checks to ACH across 200+ vendors; cut payment turnaround from 5-7 days to one business day, eliminating $1,500+/year in mailing costs
- **Program Manager** (Oct 2023 - Feb 2024) - **Giving Children Hope** (Buena Park, CA)
  - Managed weekly distribution of 350,000+ lbs of food to 250+ families; built a standardized allocation model for demand variability
  - Coordinated with 50+ schools to distribute 10,000+ toys to 1,500 children
- **Public Health Intern** (May 2022 - Jul 2022) - **Vive Peru** (Trujillo, Peru)
  - Co-led a dietary intervention targeting anemia (15% prevalence reduction in one month); delivered medication and vaccinations to 250+ people, conducting all outreach in Spanish

### Technical Skills
- **Primary:** AI workflow integration & enablement, full-stack web development (JavaScript, HTML/CSS), Google Apps Script
- **Secondary:** Process mapping, data visualization, requirements gathering across cross-functional stakeholders
- **Domain:** AI adoption / change management, business operations, manufacturing & services operations
- **Software:** Claude, Claude Code, Gemini, ChatGPT, Replit, GitHub, Excel

### Certifications
- None currently listed

### Publications
- None

### Awards
- None formal (Karate black belt; competitive sports analytics / +EV modeling as personal pursuits)

### Behavioral Profile
<!-- Inferred from resume content - review and refine before relying on this -->
- **Builder-owner** - repeatedly identifies a problem, builds the solution from scratch, and ships it end-to-end (order app, maintenance app, consulting practice)
- **Cross-functional translator** - aligns C-suite, sales, finance, logistics, and floor stakeholders; teaches non-technical teams to adopt AI
- **Strengths:** initiative, learning velocity, turning ambiguous business problems into working software, comfort with the latest AI tooling
- **Growth areas:** ~2 years professional experience (early-career); no formal CS/software-engineering credential — leads with shipped results rather than pedigree
- **Thrives in:** high-autonomy, high-ownership, fast-moving environments where he can build and own outcomes

### What Excites You
- High-growth startup impact and broad scope/ownership — wearing many hats, seeing direct impact
- Frontier AI work — being close to the latest models and tooling day-to-day
- Compensation and career acceleration

### Target Roles & Sectors
- **Primary:** AI Strategist / AI Consultant (adoption, enablement, transformation)
- **Also targeting:** Founder's Associate; Forward-Deployed / Solutions Engineer (stretch — backed by real shipped full-stack apps); Technical / Product Manager; Business Operations Analyst
- **Sectors:** AI-native startups and AI labs (Anthropic, OpenAI, and similar); enterprise AI enablement / B2B SaaS
- **Company stage:** open across stages — optimize on ownership, growth, and role fit rather than size

### Deal-breakers
- Pure sales / cold-calling roles with no technical or build component
- Prefers relocation; open to relocating within the US and to English-speaking Europe
- Salary: flag roles below ~$100K USD base as under-market

## Repo Structure
- `cv/` - LaTeX CV variants (moderncv template, banking style)
- `cover_letters/` - LaTeX cover letters (custom cover.cls template)
- `.claude/skills/` - AI skill definitions for the application workflow
- `.agents/skills/` - Job search CLI tools

## Workflow for New Job Applications
1. User provides a job posting (URL or text)
2. **Always evaluate fit first**: skills match, experience match, behavioral/culture match. Present this assessment to the user before proceeding.
3. If good fit: create targeted CV (`cv/main_<company>.tex`) and cover letter (`cover_letters/cover_<company>_<role>.tex`)
4. **Verify both documents** (see Verification Checklist below)
5. Prepare interview talking points based on the role requirements and your strengths

**Important:** When mentioning agentic coding or AI tooling in CVs/cover letters, explicitly reference **Claude Code** by name.

## Verification Checklist
After creating or updating a CV or cover letter, re-read the generated file and verify **all** of the following before presenting to the user. Report the results as a pass/fail checklist.

### Factual accuracy
- [ ] All claims match actual profile (CLAUDE.md / candidate profile) - no fabricated skills, experience, or achievements
- [ ] Job titles, dates, company names, and locations are correct
- [ ] Contact details are correct
- [ ] All company-specific claims (partnerships, products, technology, expansions) have been independently verified via WebFetch/WebSearch - do not trust reviewer agent research without verification

### Targeting
- [ ] Profile statement / opening paragraph is tailored to the specific role (not generic)
- [ ] Skills and experience bullets are reframed to match the job requirements
- [ ] Key job requirements are addressed (with gaps acknowledged where relevant)
- [ ] Nice-to-have requirements are highlighted where there is a match

### Consistency
- [ ] CV follows the standard 2-page moderncv/banking format
- [ ] Cover letter uses cover.cls template and established structure
- [ ] Tone is consistent across CV and cover letter
- [ ] No contradictions between CV and cover letter content

### Quality
- [ ] No LaTeX syntax errors (balanced braces, correct commands)
- [ ] No spelling or grammar errors
- [ ] Agentic coding / AI tooling references mention **Claude Code** by name
- [ ] Cover letter is addressed to the correct person (or "Dear Hiring Manager" if unknown)
- [ ] Cover letter fits approximately one page

### Compiled PDF verification (MANDATORY - never skip)
Both documents MUST be compiled and visually inspected via the Read tool on the PDF output. "Looks fine in the .tex" is not acceptable - LaTeX page-break decisions are unpredictable. Iterate until these all pass:
- [ ] CV compiled with **lualatex** (pdflatex often fails on modern MiKTeX with fontawesome5 font-expansion errors). Cover letter compiled with **xelatex** (cover.cls requires fontspec).
- [ ] **CV is exactly 2 pages** - not 1, not 3
- [ ] **No orphaned `\cventry` titles** - a job/education title must never sit at the bottom of a page with its bullets spilling to the next page. Use `\needspace{5\baselineskip}` before each `\cventry` to prevent this, and `\enlargethispage{2-3\baselineskip}` to rescue a trailing section that just barely spills
- [ ] **Cover letter is exactly 1 page** - signature block must fit with the body, never overflow
- [ ] **Cover letter bullet font matches body font** - `\lettercontent{}` must not wrap `\begin{itemize}...\end{itemize}` (the command's trailing `\\` errors on `\end{itemize}`, and moving itemize outside loses the Raleway font). Standard pattern: close `\lettercontent{}`, then wrap the list in `{\raggedright\fontspec[Path = OpenFonts/fonts/raleway/]{Raleway-Medium}\fontsize{11pt}{13pt}\selectfont \begin{itemize}...\end{itemize}\par}`

### ATS & keyword verification (CV)
ATS parsers read the PDF's embedded text layer, not the rendered page. Extract it with `pdftotext -layout` and verify what a parser sees. `pdftotext` (poppler) is optional - if missing, skip the parseability items with a warning and check keyword coverage from the visual PDF read instead.
- [ ] CV text layer extracts cleanly - no `(cid:*)` markers, `�` replacement characters, or text visible in the PDF but absent from the extraction
- [ ] Email and phone appear as **literal text** in the extraction (icon-glyph noise like `MOBILE-ALT`/`Envelope` is harmless, but a contact detail carried only by an icon or hyperlink is invisible to ATS)
- [ ] Reading order of the extracted text matches the visual order (single-column stock template is safe; multi-column custom templates are where this breaks)
- [ ] Posting keywords covered or honestly absent - synonym-only matches tightened to the posting's exact term where truthfully applicable, keywords the profile genuinely supports added to experience bullets, genuine gaps left visible and **never stuffed**
