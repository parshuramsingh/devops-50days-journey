# 🚀 Day 5 – YAML Basics & Validation (DevOps 50 Days Journey)

Today, I explored **YAML (YAML Ain’t Markup Language)** — a human-readable data serialization format heavily used in **DevOps tools** like Kubernetes, Docker Compose, Ansible, and CI/CD pipelines. YAML makes configurations more **clean, structured, and easy to manage**.

---

## 📌 Topics Covered

### 🔹 1. Why YAML?
- More readable than JSON/XML.  
- Standard for DevOps tools (Kubernetes, Ansible, GitHub Actions).  
- Supports comments with `#`.  
- Lightweight and indentation-based (no braces, no semicolons).  

---

### �� 2. Basic Syntax Rules
- **Case-sensitive**.  
- Indentation uses **spaces only** (no tabs).  
- Key-value pairs use `:` (colon + space).  
- Lists use `-` (dash + space).  
- Strings may not require quotes unless they contain special characters.  

```yaml
name: Parshuram
role: DevOps Engineer
experience: 0-1 years

🔹 3. Nested Data Structures

user:
  name: Parshuram
  skills:
    - Linux
    - Git
    - Docker

🔹 4. Lists of Objects

employees:
  - name: Alice
    role: Developer
  - name: Bob
    role: Tester

🔹 5. Scalars & Data Types

    Strings: "Hello", 'Hi', plain words.

    Numbers: 10, 3.14.

    Booleans: true, false.

    Nulls: null or ~.

🔹 6. Multi-line Strings

description: |
  This is a multi-line
  string example

oneline: >
  This will be folded
  into a single line

🔹 7. Anchors & Aliases (Reusability)

defaults: &defaults
  role: Developer
  active: true

employee1:
  <<: *defaults
  name: Alice

🔹 8. Comments

# This is a comment
version: 1.0

🔹 9. Validation

To validate YAML syntax:

yamllint file.yaml

Or use online validators (YAML Lint, CodeBeautify).
🔹 10. YAML vs JSON
Feature	YAML	JSON
Readability	Human-friendly	Strict
Syntax	Indentation	Braces & Quotes
Comments	✅ Supported	❌ Not supported
Usage	DevOps configs	APIs & Web apps
🔹 11. Real-World Usage

    Kubernetes → deployment.yaml, service.yaml

    Docker Compose → docker-compose.yaml

    CI/CD → .github/workflows/*.yaml, .gitlab-ci.yml

    Ansible Playbooks → Infrastructure automation

🔹 12. Best Practices

    Always use 2 spaces for indentation.

    Use anchors & aliases for repetitive values.

    Add comments for clarity.

    Validate before applying in production.

✅ Key Takeaways

    YAML is the backbone of DevOps configurations.

    Supports clean, readable, reusable structures.

    Validation ensures error-free automation.

    Essential for tools like Kubernetes, Docker, Ansible, and CI/CD.
