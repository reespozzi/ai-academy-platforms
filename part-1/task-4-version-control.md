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

**Ask AI:**
- "What is semantic versioning for Docker images?"
- "When should I bump major vs minor vs patch versions?"
- "Why shouldn't I use :latest in production?"
- "What problems does versioning solve?"

**Real-world scenarios:**
- You fix a security bug → What version?
- You add a new feature that doesn't break existing functionality → What version?
- You change your API in a breaking way → What version?

---

## Part B: Tag & Push Multiple Versions

**Your task:**
Tag your image with multiple versions and push to GHCR.

**Key concept:**
The same image can have multiple tags for flexibility:
- `v1.0.0` (specific version - most precise)
- `v1.0` (latest patch in 1.0.x)
- `v1` (latest minor in 1.x)
- `latest` (latest overall - not recommended for production!)

**Ask AI to help you:**
- "How do I tag a Docker image with multiple versions?"
- "How do I push multiple tags to GHCR?"
- "Why would I tag the same image multiple times?"
- "What's the difference between v1, v1.0, and v1.0.0 tags?"

**Your goal:** Push your image with all 4 version tags and verify they appear in GHCR.

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

**Ask AI:**
- "What are different Docker image versioning strategies?"
- "When would I use Git SHA instead of semantic versioning?"
- "What's a hybrid versioning approach?"
- "How do large companies version their container images?"


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

**Discussion scenarios:**
1. You deploy v1.2.3 and find a critical bug - what now?
2. You have 10 microservices - how do you coordinate versions?
3. Someone accidentally overwrites your :latest tag - what happens?

---

## Success Criteria

✅ Understand semantic versioning (MAJOR.MINOR.PATCH)  
✅ Tagged and pushed multiple versions of your image
✅ Understand the difference between tags and digests  
✅ Understand tagging strategies for different environments  
✅ Can explain why :latest is problematic in production  
✅ Know best practices for image versioning and traceability

---

## Discussion Points

Be ready to discuss:

1. **When would you bump a MAJOR vs MINOR vs PATCH version?**
2. **Which registry would you choose for an open source project? Why?**
3. **Which registry would you choose for a startup? An enterprise?**
4. **Why is image traceability important for debugging?**
5. **How do you prevent accidentally deploying dev images to production?**
6. **What's the problem with :latest tags in production?**
---
