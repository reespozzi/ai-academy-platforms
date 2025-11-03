# Task 4: Image Version Control

## Objective

Learn how to version your Docker images using semantic versioning and understand why versioning matters in production.

Remember, you may need to explain this at the end!

---

## Part A: Understanding Semantic Versioning

**Semantic versioning:** `MAJOR.MINOR.PATCH` (e.g., `v1.2.3`)

- **MAJOR:** Breaking changes (v2.0.0)
- **MINOR:** New features, backwards compatible (v1.3.0)
- **PATCH:** Bug fixes (v1.2.4)

---

## Part B: Tag & Push Multiple Versions

**Your task:**
Tag your image with multiple versions and push to ACR

**Your goal:** Push your image with all 4 version tags and verify they appear

---

## Part C: Other Versioning Strategies

**Your objective:**
Understand that semantic versioning isn't the only approach - you could use different strategies.

**Common strategies to explore:**

### 1. Git Commit SHA
Tags like: `abc123f` or `main-abc123f`
- **Pros:** Direct link to code, easy to trace
- **Cons:** Not human-readable, doesn't show importance of changes

### 2. Timestamp-based
Tags like: `2025-10-14` or `20251014-103045`
- **Pros:** Easy to see when it was built
- **Cons:** Doesn't indicate what changed or compatibility

### 3. Build Number
Tags like: `build-456` or `jenkins-789`
- **Pros:** Simple, incremental, works well with CI/CD
- **Cons:** No semantic meaning about the changes

### 4. Environment-based
Tags like: `dev`, `staging`, `production-2025-10-14`
- **Pros:** Clear deployment target
- **Cons:** Mutable tags, risky for production

### 5. Hybrid Approaches
Tags like: `v1.2.3-abc123f` or `v1.2.3-build.456`
- **Pros:** Combines semantic meaning with traceability
- **Cons:** More complex, longer tag names

--- 

## Part D: Version Control Best Practices

**Your objective:**
Understand production-ready versioning strategies.

**Ask AI about:**
- "What are Docker image versioning best practices?"
- "Why is :latest dangerous in production?"
- "What are immutable tags?"
- "Should I delete old image versions?"
- "How do companies handle versioning for microservices?"

**Key concepts to understand:**
- **Immutable tags:** Version tags that never change (v1.2.3)
- **Mutable tags:** Tags that can change (latest, dev)
- **Image digests:** Cryptographic hash that's always unique
- **Rollback strategy:** How to revert to previous versions