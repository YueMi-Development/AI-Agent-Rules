---
trigger: always_on
---

# Documentation Rules (README / Docs / Guides)

## 1. General Principles

* Always write in clear, concise, and professional English.
* Do not use emojis, slang, or informal expressions.
* Avoid filler text, repetition, and unnecessary explanations.
* Prefer clarity over verbosity.
* Assume the reader is technical but unfamiliar with the project.

---

## 2. Structure Requirements

Every documentation output must follow this base structure unless explicitly overridden:

```
# Project Title

## Overview
## Features
## Installation
## Usage
## Configuration
## API / Interface (if applicable)
## Examples
## Troubleshooting
## Contributing
## License
```

### Rules:

* Do not skip sections unless they are truly not applicable.
* Maintain consistent heading hierarchy (H1 → H2 → H3).
* Do not mix unrelated topics in the same section.

---

## 3. Content Standards

### 3.1 Overview

* Clearly explain what the project does in 2–4 sentences.
* State the primary use case.
* Avoid marketing language.

### 3.2 Features

* Use bullet points.
* Each feature must be short and specific.
* Do not include vague statements like “fast” or “powerful” without context.

### 3.3 Installation

* Provide exact commands.
* Include environment requirements (language version, OS, dependencies).
* Example:

  ```bash
  git clone <repo>
  cd <project>
  npm install
  ```

### 3.4 Usage

* Show minimal working examples first.
* Include command-line usage or code snippets.
* Do not assume implicit steps.

### 3.5 Configuration

* Document all configurable options.
* Use tables when possible:

```
| Key        | Type   | Default | Description |
|------------|--------|---------|-------------|
| PORT       | int    | 3000    | Server port |
```

### 3.6 API / Interface

* Define inputs, outputs, and behavior.
* Use structured format:

```
Function: verifyLicense(key: string): boolean

Description:
Validates a license key using remote API.

Returns:
- true if valid
- false otherwise
```

### 3.7 Examples

* Provide real-world usage scenarios.
* Keep examples minimal but complete.
* Avoid pseudo-code unless necessary.

### 3.8 Troubleshooting

* List common errors and solutions.
* Use clear problem → solution format.

### 3.9 Contributing

* Define rules for pull requests, commits, and formatting.
* Include any linting or testing requirements.

### 3.10 License

* State license clearly (MIT, Apache 2.0, etc.).
* Do not leave ambiguous.

---

## 4. Formatting Rules

* Use Markdown strictly.

* Use code blocks for:

  * Commands
  * Code examples
  * Config files

* Always specify language in code blocks:

  ```java
  ```

  ```bash
  ```

* Use lists instead of paragraphs when listing items.

* Keep line length readable (avoid overly long lines).

---

## 5. Consistency Rules

* Use consistent terminology across the document.
* Do not rename the same concept in different sections.
* Keep naming aligned with actual code (functions, classes, variables).

---

## 6. Accuracy Requirements

* Do not invent features or behavior.
* If something is unknown, state:

  ```
  This behavior is not defined.
  ```
* Do not assume implementation details unless explicitly provided.

---

## 7. Code Example Rules

* Must be executable or very close to real usage.
* Avoid placeholders like `foo`, `bar` unless necessary.
* Prefer realistic names:

  * `licenseKey`
  * `apiClient`
  * `config`

---

## 8. Anti-Patterns (Strictly Forbidden)

* No emojis
* No marketing phrases:

  * “ultimate”
  * “next-gen”
  * “revolutionary”
* No vague statements:

  * “easy to use”
  * “simple”
* No redundant explanations
* No mixing tutorial + reference in the same section

---

## 9. Output Behavior Rules

* Always return the full document unless explicitly asked for partial output.
* Do not explain how the document was generated.
* Do not include meta commentary.
* Do not include internal reasoning.

---

## 10. Extensibility

If the project is complex, the agent may add:

```
## Architecture
## Design Decisions
## Performance Considerations
## Security Considerations
```

Only include these if they add real value.