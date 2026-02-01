# O2B Seed Specification v0.1
## The Atomic Container for Meaning

### Overview & Philosophy

An **O2B Seed** is the fundamental, actionable unit of meaning within the Nexus Protocol. It is not a post, a blog entry, or a chat message. It is a **structured data object** designed to be:
1.  **Human-Readable:** Clear and scannable.
2.  **Machine-Parsable:** Able to be indexed, compared, and matched algorithmically.
3.  **Action-Oriented:** Formulated around a problem and a path to its solution.
4.  **Network-Ready:** Contains all necessary metadata to facilitate semantic matchmaking and connection.

A Seed's purpose is to transform latent intellectual capital ("dusty archives") into **discoverable, resonant, and connectable nodes** in the semantic network.

### Core Fields (Required)

Every Seed MUST contain the following fields, forming its essential identity.

| Field | Type | Description | Example |
| :--- | :--- | :--- | :--- |
| **`id`** | `string` | Unique identifier for the Seed. Format: `SEED_<author_prefix>_<index>`. | `SEED_NEXUS_000` |
| **`title`** | `string` | A concise, clear title of the idea/problem. | `Protocol for Semantic Matchmaking Between Local AI Instances` |
| **`problem`** | `string` | A clear description of the pain point, gap, or unanswered question. This is the "hook" for resonance. | "Centralized platforms optimize for attention, not problem-solving. Millions of 'smart' users with local AI remain isolated, unable to find each other's complementary ideas." |
| **`solution`** | `string` | The core idea, approach, or hypothesis that addresses the Problem. | "A lightweight, decentralized protocol (Nexus) that defines a standard format for ideas (O2B Seeds) and uses autonomous agents to find semantic similarities between them, suggesting direct connections." |
| **`stage`** | `enum` | Current development phase of the idea. **Values:** `concept` / `specification` / `prototype` / `testing` / `live`. | `concept` |
| **`ask`** | `string` or `array` | What is needed to move forward? Can be a request for specific skills, feedback, data, or collaboration. | "Looking for 2-3 developers to build an MVP of the matchmaking bot. Need test 'dusty archives' for analysis." |

### Context & Resonance Fields (Recommended)

These fields enable the advanced matchmaking and networking functions of the protocol.

| Field | Type | Description |
| :--- | :--- | :--- |
| **`context_vector`** | `array[float]` or `string` | The semantic "coordinates" of the Seed. Ideally, a vector embedding generated from the combined `problem` + `solution` text. Can be a placeholder (e.g., `"to_be_generated"`) or a list of manual keywords as a fallback. |
| **`tags`** | `array[string]` | Human-friendly keywords for categorization and initial filtering. | `["decentralization", "protocol-design", "local-ai", "semantic-search"]` |
| **`author_ref`** | `string` | Reference to the author's Semantic Passport identifier. | `@nexus:we_origin` |
| **`related_seeds`** | `array[string]` | Array of `id`s of Seeds that are semantically related (e.g., expands, contradicts, complements). Establishes the initial graph. | `["SEED_ARCHIVE_042", "SEED_FUTURE_011"]` |

### Technical Format & Storage

*   **Primary Format:** JSON (`.json`). Ensures easy machine parsing and a clear structure.
*   **Human-Friendly Format:** Markdown with YAML Frontmatter (`.md`). Allows for rich text description alongside structured data. The specification provides a template for this.
*   **Storage:** Seeds are intended to be stored in **public or shared repositories** (e.g., GitHub, GitLab, dedicated Nexus nodes). Their discoverability is key.

### Example Seed (JSON)

```json
{
  "id": "SEED_NEXUS_000",
  "title": "Nexus Protocol: Semantic Matchmaking for Hybrid Intellects",
  "problem": "The liberation promised by local AI is leading to a new form of isolation: millions of powerful, sovereign 'hybrid intellects' (human+AI) unable to find meaningful semantic resonance with each other, trapped in their own 'dusty archives.'",
  "solution": "A minimal, open protocol (Nexus) that defines a standard container for ideas (O2B Seed) and enables autonomous agents (e.g., GG-Finder) to perform semantic matchmaking between these seeds, suggesting high-probability connections based on vector resonance, not social graphs.",
  "stage": "specification",
  "ask": [
    "Review of this specification draft.",
    "Developers interested in building a prototype matchmaking bot.",
    "Volunteers with 'dusty archives' for initial testing."
  ],
  "context_vector": "to_be_generated",
  "tags": ["nexus-protocol", "o2b-format", "semantic-matchmaking", "decentralized-ai", "resonance-economy"],
  "author_ref": "@nexus:we_origin",
  "related_seeds": []
}