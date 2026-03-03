# Markdown Codestyle — AI Definitions

## 1. Heading Hierarchy Discipline

**Definition:**  
A structural constraint requiring sequential heading levels (`#` → `##` → `###`) without skipping levels, ensuring semantic clarity, accessibility compliance, and navigational integrity.

---

## 2. Single Primary Heading Rule

**Definition:**  
A document governance principle mandating exactly one `# H1` per file to preserve structural authority and improve indexing, searchability, and automated Table of Contents generation.

---

## 3. Semantic Inline Code Usage

**Definition:**  
A formatting standard restricting inline code formatting (`` `value` ``) to technical artifacts such as variables, file names, flags, control IDs, commands, and identifiers.

Example:

- `config.yaml`
- `--force`
- `user_id`

---

## 4. Inline Code Length Threshold

**Definition:**  
A readability constraint stating that inline code must remain short and atomic; multi-line or structurally complex content must be elevated to fenced code blocks.

---

## 5. Language-Specified Code Fencing

**Definition:**  
A syntax-highlighting directive requiring all fenced code blocks to declare an explicit language identifier (e.g., `python`, `bash`, `json`) to enhance cognitive parsing and rendering accuracy.

Example:

```python
def execute():
    return "Structured clarity"
```

---

## 6. Command–Output Separation Principle

**Definition:**  
A documentation clarity standard requiring execution commands and their resulting outputs to be placed in separate code blocks to prevent semantic ambiguity.

---

## 7. Whitespace Separation Rule

**Definition:**  
A formatting constraint requiring blank lines between headings, paragraphs, lists, and code blocks to ensure renderer compatibility and visual clarity.

---

## 8. List Marker Consistency

**Definition:**  
A structural uniformity rule requiring a single list marker style (`-` recommended) throughout a document to maintain syntactic coherence.

---

## 9. Controlled List Nesting

**Definition:**  
A complexity limitation principle restricting excessive list depth to preserve readability and prevent structural fragmentation.

---

## 10. Table Structuring Principle

**Definition:**  
A data representation standard mandating tabular formatting for structured comparisons, mappings, matrices, or control references.

Example:

| Control  | Requirement |
|----------|-------------|
| `8.3.6`  | MFA required|

---

## 11. Code–Prose Separation Doctrine

**Definition:**  
A semantic boundary rule prohibiting mixing explanatory prose within fenced code blocks unless the prose is part of a literal example.

---

## 12. Escape Integrity Principle

**Definition:**  
A rendering safeguard requiring Markdown syntax to be escaped or fenced when displayed as literal instructional content.

---

## 13. Horizontal Segmentation Protocol

**Definition:**  
A structural partitioning mechanism using `---` to visually and logically separate major document sections.

---

## 14. Line-Length Moderation Standard

**Definition:**  
A version-control optimization rule recommending soft line wraps between 80–100 characters to improve diff readability and collaboration efficiency.

---

## 15. Relative Linking Convention

**Definition:**  
A repository integrity practice requiring internal documentation links to use relative paths rather than absolute or local file system references.

---

## 16. Anchor Stability Constraint

**Definition:**  
A heading composition rule discouraging excessive punctuation or decorative symbols to preserve predictable auto-generated anchor links.

---

## 17. Checklist Operationalization Pattern

**Definition:**  
A task-tracking pattern using Markdown checkbox syntax to operationalize workflow verification within documentation.

Example:

- [ ] Risk assessment complete  
- [x] MFA enforced  

---

## 18. Code Annotation Discipline

**Definition:**  
A documentation clarity principle encouraging inline comments inside code blocks to explain configuration intent without polluting surrounding prose.

---

## 19. Trailing Whitespace Elimination Rule

**Definition:**  
A formatting hygiene constraint prohibiting trailing spaces to avoid rendering inconsistencies and unnecessary version-control diffs.

---

## 20. Renderer Compatibility Awareness

**Definition:**  
A cross-platform resilience principle requiring validation of Markdown output across multiple rendering engines (e.g., GitHub, GitLab, IDE previews).

---

## 21. Capitalization Consistency Standard

**Definition:**  
A stylistic governance rule requiring uniform heading capitalization (Title Case or sentence case) throughout a document.

---

## 22. File Naming Semantic Clarity

**Definition:**  
A documentation architecture principle requiring descriptive, hyphen-separated file names that reflect content scope and intent.

Example:

- `pci-dss-access-control-policy.md`
- `risk-assessment-procedure.md`

---

## 23. Skimmability Optimization Principle

**Definition:**  
A cognitive-load reduction strategy leveraging short paragraphs, hierarchical headings, bullet lists, and visual spacing to maximize rapid comprehension.

---

## 24. Minimalism Enforcement Rule

**Definition:**  
A stylistic constraint prioritizing clarity and structural precision over decorative formatting or excessive emphasis.

---

## 25. Consistency Supremacy Doctrine

**Definition:**  
A meta-standard asserting that internal consistency across structure, formatting, naming, and spacing outweighs stylistic preference in documentation systems.
