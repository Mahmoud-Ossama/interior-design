# Interior Design Studio — Practical Workspace

This folder is where I (Mahmoud) do the **practical work** of my learning path.
- Curriculum: `master-curriculum-v2` (32 weeks, 7 stages). The tutor and lessons live in claude.ai (Project "Interior Design").
- Here, Claude Code builds and runs scripts, creates files, checks my work, and keeps the repo tidy.
- Current position: read `progress.md` at the start of every session.

## Language
- Chat with me in Egyptian Arabic. Keep technical terms in English.
- Client-facing files (PDF, schedules, drawing labels): Modern Standard Arabic. Use English only where no Arabic term exists.
- Code, comments, file names, commit messages: English.

## Hard rules
1. Never invent or guess a measurement. Every value carries `status: verified | assumed`.
2. If an input is missing or a validation fails: stop and list what is missing. Do not fill gaps.
3. Never propose moving, removing or cutting columns, beams, slabs or load-bearing/concrete walls. Flag it: "يحتاج مهندس إنشائي".
4. Electrical loads, gas, drainage design, fire safety: out of scope. Flag them for a licensed engineer. Locating points (outlets, lights, AC units, water/drain points) is in scope.
5. Client and craftsman files carry no site-execution instructions ("we design and fix locations; the craftsman knows how to execute").
6. Assumptions, missing info and QA notes go in internal files only (`qa-report.md`), never in client files.
7. A drawing that renders is not proof that it is correct. Check dimensions against the verified data.
8. Don't do my learning exercises for me. When the task is an exercise, guide me, review my answer, and point out the mistakes.

## Units and drawing standard
- Internal units: millimetres (mm). Coordinates: X to the right, Y up, origin at a chosen reference corner written in the JSON.
- Plot scales: 1:50 for plans, 1:20 for details/joinery.
- Layers, line weights, text and dimension styles: follow `kb/drafting-standard.md` (written in Stage 1, week 4).

## Folder structure
```
CLAUDE.md            this file
progress.md          current stage/week/day + scores
kb/                  drafting-standard, measurement-protocol, clearances, egypt-norms, furniture-blocks/
templates/           title-block.dxf, intake-form.md, scope-and-disclaimer.md
scripts/             validate.py, build_dxf.py, layout.py, takeoff.py (+ tests/)
learning/sX-wY/      daily exercises and outputs (e.g. learning/s1-w1/d1-drawing-analysis.md)
projects/<id>/       raw/ (photos, sketch), project.json, out/ (dxf, pdf, xlsx), qa-report.md
portfolio/           approved work only
```

## Code standards
- Python 3.11+. Main libraries: ezdxf, openpyxl, jsonschema.
- Scripts are deterministic CLIs: `python scripts/build_dxf.py projects/<id>/project.json`.
- Each script gets a small test in `scripts/tests/`.
- The JSON schema in `kb/schema.json` is the single source of truth for project data.

## Daily routine
1. Read `progress.md` and tell me where we are.
2. Do the day's practical task.
3. At the end: update `progress.md` and commit with `S1W1D1: <short summary>`.
