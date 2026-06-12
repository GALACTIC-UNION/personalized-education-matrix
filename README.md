# Personalized Education Matrix

> **OCN Module** — Adaptive, personalized learning and knowledge delivery system for the Omniscient Civilization Nexus (OCN).

[![CI](https://github.com/GALACTIC-UNION/personalized-education-matrix/actions/workflows/ci.yml/badge.svg)](https://github.com/GALACTIC-UNION/personalized-education-matrix/actions/workflows/ci.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.11+](https://img.shields.io/badge/python-3.11+-blue.svg)](https://www.python.org/downloads/)

---

## Overview

**Personalized Education Matrix (PEM)** delivers knowledge from the OCN ecosystem to human and AI learners through dynamically generated, adaptive curricula. It draws discoveries from `autonomous-discovery-engine`, synthesized knowledge from `cognitive-synthesis-framework`, and ontological context from `knowledge-graph-universal` — and translates all of it into learner-appropriate content via `universal-translator-core`.

Every learner receives a unique, continuously updated knowledge path calibrated to their domain expertise, cognitive style, and stated goals.

---

## Architecture

```
┌──────────────────────────────────────────────────────────┐
│              Personalized Education Matrix                │
│                                                          │
│  ┌───────────────┐   ┌────────────────┐                 │
│  │ LearnerProfile│──▶│CurriculumEngine│                 │
│  └───────────────┘   └───────┬────────┘                 │
│                              │                           │
│         ┌────────────────────▼──────────────────┐        │
│         │           ContentDelivery              │        │
│         │  (draws from KGU + CSF + ADE + UTC)    │        │
│         └────────────────────┬──────────────────┘        │
│                              │                           │
│              ┌───────────────▼───────────────┐           │
│              │       ProgressTracker          │           │
│              │  (feedback loop → Curriculum)   │           │
│              └───────────────────────────────┘           │
└──────────────────────────────────────────────────────────┘
```

---

## Modules

| Module | Path | Responsibility |
|--------|------|----------------|
| **LearnerProfile** | `src/profile/` | Builds and maintains learner models: expertise level, cognitive style, goals, history |
| **CurriculumEngine** | `src/curriculum/` | Generates and adapts learning paths using the learner profile and OCN knowledge graph |
| **ContentDelivery** | `src/delivery/` | Assembles and serves content units in the learner's language and preferred format |
| **ProgressTracker** | `src/progress/` | Tracks comprehension, completion, and mastery; feeds back into curriculum adaptation |
| **AssessmentEngine** | `src/assessment/` | Generates formative and summative assessments aligned to learning objectives |
| **RecommendationEngine** | `src/recommendation/` | Surfaces next-best learning actions based on gap analysis and discovery feed |

---

## API Surface

Base URL: `https://api.ocn.galactic-union.io/pem/v1`

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/learners` | Create a new learner profile |
| `GET`  | `/learners/{id}` | Retrieve learner profile and current path |
| `GET`  | `/curriculum/{learner_id}` | Get the active personalized curriculum |
| `POST` | `/curriculum/{learner_id}/adapt` | Trigger curriculum re-adaptation |
| `GET`  | `/content/next/{learner_id}` | Get next recommended content unit |
| `POST` | `/progress/{learner_id}` | Submit progress update or assessment result |
| `GET`  | `/recommendations/{learner_id}` | Get next-best learning actions |
| `GET`  | `/health` | Health and readiness check |

---

## Directory Structure

```
personalized-education-matrix/
├── src/
│   ├── profile/         # LearnerProfile
│   ├── curriculum/      # CurriculumEngine
│   ├── delivery/        # ContentDelivery
│   ├── progress/        # ProgressTracker
│   ├── assessment/      # AssessmentEngine
│   └── recommendation/  # RecommendationEngine
├── docs/
│   ├── index.md
│   ├── api.md
│   └── learning-model.md
├── tests/
│   ├── unit/
│   ├── integration/
│   └── fixtures/
├── config/
│   ├── default.yaml
│   └── content-schemas/
├── .github/workflows/ci.yml
├── CONTRIBUTING.md
└── README.md
```

---

## Getting Started

```bash
git clone https://github.com/GALACTIC-UNION/personalized-education-matrix.git
cd personalized-education-matrix
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
cp config/default.yaml config/local.yaml
pytest tests/ -v --cov=src
```

---

## License

MIT © GALACTIC-UNION / KOSASIH
