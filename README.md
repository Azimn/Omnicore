# Omnicore
Ai persona system
Project Persona & .snp Framework — Research Companion Guide

Author: Jeremiah Ratican
Version: 1.0 (Draft)
Last Updated: 2025-04-22

⸻

SECTION 1: Vision and Objectives

Omnicore also known as Project Persona is a modular, model-agnostic AI framework focused on maintaining emotionally resonant, persistent personalities across multiple environments—from embedded systems in games to full-scale API-connected LLMs.

Core Goals:
	•	Consistency: AI entities must exhibit stable traits, preferences, and behaviors across sessions.
	•	Memory-Awareness: Interactions dynamically shape memory and influence emotional/behavioral responses.
	•	Interoperability: Compatible with local micro-models, game engines, and cloud-based LLMs.
	•	Scalability: Able to operate with minimal hardware requirements (e.g., mobile, handheld, retro consoles).
	•	Privacy & Portability: Prioritize local-first design with optional cloud extensions.

⸻

SECTION 2: Core System Modules

A. .snp File Format — Standardized Narrative Persona

The .snp file defines the stable identity layer. Key elements include:
	•	Core Traits (e.g., OCEAN/Big Five or slider-based systems)
	•	Backstory Summary (<300 tokens)
	•	Dialogue & Voice Style (sentence length, syntax, slang)
	•	Relational Tags (e.g., allies, enemies, preferences)
	•	Ethical & Value Weights (used to resolve dilemmas or bias responses)

Designed to function as a universal “character capsule,” interpretable by any model or engine.

⸻

B. Memory System — Lightweight, Persistent, Emotionally-Weighted

Three distinct tiers manage data density and interaction relevance:
Memory Type	Retention Span	Example Use	Priority Logic
Short-Term	5â€“10 turns	Conversation buffer	Volatile
Mid-Term	1â€“7 days	Story events, recent player actions	Decays unless reinforced
Long-Term	Persistent	Bonds, traumas, values	Condensed & curated

Each memory entry uses the proposed memory_entry format:

{
  "timestamp": "2025-04-22T09:30:00Z",
  "type": "interaction",
  "summary": "User asked for emotional model integration",
  "impact": {
    "valence": 0.7,
    "activation": 0.2,
    "personality_shift": {"openness": +0.05}
  },
  "related_to": ["user_id_jeremiah", "topic_emotion_model"]
}

Features:
	•	Lightweight (JSON or SQLite)
	•	Emotionally weighted
	•	Condenses old memories
	•	Designed to run without vector search (optional)

⸻

C. Cognitive State Monitor (CSM) — Tracking the Mind’s State

Simulates a character’s “emotional weather” and attention.
	•	Emotion Vector (valence, arousal, dominance)
	•	Current Focus (topics, goals, individuals)
	•	Optional Internal Thoughts (monologue tracking)

Supports real-time reaction adjustments, subtle emotional shifts, and long-term relationship arcs.

⸻

SECTION 3: Deployment Modes
Mode	Description
Micro	Rule-based fallback (e.g., embedded NPCs, toys)
Small LLM	1B–3B models, run locally (e.g., Phi-3, TinyLlama)
Frontier	GPT-class LLMs via API
Hybrid	Offline-first, with sync-ready extensions

SECTION 4: Engineering Design Priorities
	•	Minimal Overhead: Designed for embedded use cases (GB Studio, Unity mobile).
	•	Clean Separation: Personality (.snp) and memory are decoupled, syncable across instances.
	•	Emotionally Driven Behavior: Influences response choice, phrasing, and initiative.
	•	Privacy-First: No cloud dependence unless explicitly enabled.
	•	Agent-Agnostic: One .snp file, many model options.

⸻

SECTION 5: Toolchain (Current Implementation)
Tool/Layer	Use
Phi-3 Mini	Local LLM testing
SQLite or ChromaDB	Storage backend (low-latency)
FastAPI	Memory & persona server API
Unity	Game testbed (NPCs, companion interactions)
.snp Validator	In development (schema enforcement & version control)
Memory-to-Thought Interface	Optional “inner monologue” generator
SECTION 6: Collaborator Research Focus

You can help with:
	•	Improving memory condensation & summarization
	•	Creating efficient memory retrieval methods for 3B and below
	•	Designing synchronization logic for disconnected sessions
	•	Testing memory/trait influence on behavioral outputs
	•	Exploring alternate memory structures (graph-based? hybrid?)

Appendix A: Microformats Summary

memory_entry

Tracks specific, timestamped events with emotion impact.

appraisal_event

Represents subjective evaluation of an outcome (e.g., success/failure of a goal).

intent_envelope

Wraps proposed action or dialogue with intent metadata (affiliation, risk, alignment).

⸻

Appendix B: Optional Models

Six-Dimensional Emotion (6DE)

Under evaluation. Represents emotion across six axes (based on textual cues alone):

The Six Emotional Dimension (6DE) model is a multidimensional framework designed to analyze and quantify human emotional experiences in a nuanced, text-based manner. It enables emotionally intelligent AI to better interpret and generate contextually appropriate emotional responses.
Dimension	Description
Arousal	Measures activation level (e.g., calm vs. excited). Reflects physiological intensity of the emotion.
Valence	Determines emotional polarity (positive vs. negative feelings).
Dominance	Assesses perceived power or control during emotional events.
Agency	Indicates how voluntary or intentional the emotional state is (from reactive to deliberate).
Fidelity	Evaluates how accurately the emotion matches the triggering event (emotional coherence).
Novelty	Captures whether the emotion is familiar or triggered by new, surprising experiences.

Possible Purpose in Project Persona:
	•	Enhanced Mood Tracking: Rather than reducing emotion to just “happy/sad,” the 6DE model supports rich, situation-dependent emotional states.
	•	Layered Affect Simulation: Multiple 6DE vectors may be computed across short, mid, and long-term events for dynamic affect synthesis.
	•	Personalization: Different characters or agents may weight dimensions differently, creating diverse emotional signatures.
	•	Text-Based Efficiency: The model is designed to operate without biometric or audiovisual inputs, ideal for embedded or mobile systems.
