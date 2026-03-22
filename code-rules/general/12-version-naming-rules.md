---
trigger: always_on
---

# Semantic Versioning Specification for AI Agent

## Version Format
```

MAJOR.MINOR.PATCH[-PRERELEASE][+BUILD]

```

Examples:
- `1.0.0`
- `1.2.3`
- `2.0.0-beta.1`
- `1.4.0+20260322`

---

## Core Rules

### 1. MAJOR Version (Breaking Changes)
Increment MAJOR when:
- Public API is changed in a non-backward-compatible way
- Methods or classes are removed or renamed
- Method signatures are modified
- Return types or behavior are changed incompatibly

#### Example
```

1.5.2 → 2.0.0

```

---

### 2. MINOR Version (New Features)
Increment MINOR when:
- New features are added
- New public methods or classes are introduced
- Existing functionality remains backward compatible

#### Example
```

1.5.2 → 1.6.0

```

---

### 3. PATCH Version (Bug Fixes)
Increment PATCH when:
- Bug fixes are applied
- Performance improvements are made
- Internal refactoring occurs without changing behavior

#### Example
```

1.5.2 → 1.5.3

```

---

## Pre-release Versions

Format:
```

1.2.0-alpha.1
1.2.0-beta.2
1.2.0-rc.1

```

Usage:
- `alpha`: early development, unstable
- `beta`: testing phase
- `rc`: release candidate

---

## AI Decision Logic

```

IF breaking change detected:
MAJOR += 1
MINOR = 0
PATCH = 0

ELSE IF new feature detected:
MINOR += 1
PATCH = 0

ELSE IF bugfix or internal change:
PATCH += 1

ELSE:
no version change

```

---

## Change Detection Rules

### Breaking Changes
- Modified public method signature
- Removed or renamed public API
- Changed return types
- Changed error/exception behavior

### New Features
- Added public methods or classes
- Added configuration options
- Added new capabilities or endpoints

### Bug Fixes / Internal Changes
- Fixed incorrect behavior
- Improved performance
- Refactored internal code

---

## API Scope Rules

Only consider:
- Public API surface

Ignore:
- Private/internal methods
- Comments and formatting
- Non-functional changes

---

## Additional Constraints

### No Version Skipping
```

Invalid: 1.2.0 → 1.4.0
Valid:   1.2.0 → 1.3.0

```

### No Breaking Changes in MINOR/PATCH
- Any breaking change MUST increment MAJOR

### Immutable Releases
- Once a version is released, it must not be modified

---

## Pre-1.0.0 Behavior

If version < `1.0.0`:

| Change Type      | Version Increment |
|-----------------|------------------|
| Breaking Change | MINOR            |
| New Feature     | MINOR            |
| Bug Fix         | PATCH            |

Example:
```

0.3.2 → 0.4.0

```

---

## Git Tagging

Format:
```

v1.2.3
v2.0.0-beta.1

```

---

## Recommended Workflow

```

0.1.0 → initial development
0.2.0 → feature additions
0.2.1 → bug fix
1.0.0 → stable release
1.1.0 → new feature
1.1.1 → bug fix
2.0.0 → breaking change

```

---

## Optional: Conventional Commits Integration

| Commit Type        | Version Impact |
|-------------------|---------------|
| feat:             | MINOR         |
| fix:              | PATCH         |
| BREAKING CHANGE:  | MAJOR         |

---

## Summary

- Use MAJOR for breaking changes
- Use MINOR for backward-compatible features
- Use PATCH for fixes and internal updates
- Only evaluate public API changes
- Automate decisions using structured rules