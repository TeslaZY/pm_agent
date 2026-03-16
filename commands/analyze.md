---
description: Deep analysis of requirements through tough questioning and risk identification
disable-model-invocation: true
---

# Analyze Requirements

This command performs deep analysis of collected requirements. It uses tough questioning to find gaps, identifies dependencies, and assesses risks.

## Philosophy

**"The best product managers are the toughest critics of their own ideas."**

This command applies the "毒舌产品经理" (Tough-talking PM) approach:
- Challenge every assumption
- Find gaps before development
- Think about edge cases
- Consider scale and failure

## Workflow

### 1. Pre-flight Check

- Verify `Product-Spec.md` exists
- Verify user stories exist in Product-Spec.md
- Read `pm-progress.md` for context

If requirements not found:
```
Error: No requirements to analyze. Run /pm:discover first.
```

### 2. Assumption Challenge

For every stated requirement, ask:

```markdown
## Assumption Audit

**Stated Assumption**: [What is assumed to be true]

**Challenging Questions**:
1. What if this assumption is wrong?
2. How would the product behave differently?
3. What evidence supports this assumption?
4. Under what conditions would this fail?

**Risk Level**: [High/Medium/Low]
**Mitigation**: [How to handle if assumption is wrong]
```

### 3. Edge Case Discovery

```markdown
## Edge Case Questions

1. What happens if the user enters [unexpected input]?
2. What if the network is slow or unavailable?
3. What if there are 10x more users than expected?
4. What if the user tries to do [impossible action]?
5. What if two users try to modify the same data?
6. What happens at midnight on New Year's Eve?
7. What if the user's session expires mid-action?
8. What if the user has [accessibility need]?
```

### 4. Scalability Questions

```markdown
## Scale Scenarios

Current: [Expected scale]
Future: [10x scale]

Questions:
1. Will this work with 10x data volume?
2. Will response time be acceptable?
3. Will the UI still be usable?
4. Will background processes complete in time?
5. Will storage costs be acceptable?
```

### 5. Security & Privacy

```markdown
## Security Checklist

1. Who should/shouldn't have access?
2. What sensitive data is involved?
3. How is data protected in transit/at rest?
4. What audit trails are needed?
5. What happens if credentials are compromised?
6. Are there compliance requirements (GDPR, HIPAA)?
```

### 6. Business Logic Gaps

```markdown
## Business Rule Questions

1. What happens if [business rule] is violated?
2. Who has the authority to override?
3. What are the consequences of [action]?
4. How does this affect billing/reporting?
5. What if [external system] is unavailable?
```

### 7. Gap Analysis

For each user story:

```markdown
## Gap Analysis: [Story ID]

### Current Understanding
- What we know: [Summary]
- What's documented: [Checklist]

### Critical Questions
1. What happens if [edge case]?
2. Who handles [responsibility]?
3. What's the fallback for [dependency]?
4. How does this scale when [growth scenario]?
5. What security/privacy concerns exist?

### Identified Gaps
- [Gap 1]
- [Gap 2]

### Gap Analysis Matrix

| Aspect | Documented | Gaps Found | Risk | Action |
|--------|------------|------------|------|--------|
| User Flow | ✓ | [gap] | High | [action] |
| Error Handling | ✗ | [gap] | Med | [action] |
| Edge Cases | ✗ | [gap] | Low | [action] |
| Scale | ✓ | [gap] | Med | [action] |
```

### 8. Dependency Mapping

```markdown
## Dependency Map

### User Story Dependencies
[Story A] → requires → [Story B]
[Story C] → blocked by → [Story D]
[Story E] → parallel with → [Story F]

### External Dependencies
| Dependency | Type | Status | Risk |
|------------|------|--------|------|
| [API Name] | Third-party | Available | Low |
| [Service] | Infrastructure | TBD | High |
```

### 9. Risk Assessment

```markdown
## Risk Assessment

### Technical Risks
| ID | Risk | Probability | Impact | Mitigation | Owner |
|----|------|-------------|--------|------------|-------|
| TR-001 | [Risk] | H/M/L | H/M/L | [Strategy] | [Name] |

### Business Risks
| ID | Risk | Probability | Impact | Mitigation | Owner |
|----|------|-------------|--------|------------|-------|
| BR-001 | [Risk] | H/M/L | H/M/L | [Strategy] | [Name] |

### User Experience Risks
| ID | Risk | Probability | Impact | Mitigation | Owner |
|----|------|-------------|--------|------------|-------|
| UR-001 | [Risk] | H/M/L | H/M/L | [Strategy] | [Name] |

### Risk Template

**Risk**: [Risk Name]
**Description**: [What could go wrong]
**Probability**: [High/Medium/Low]
**Impact**: [High/Medium/Low]
**Mitigation**: [How to prevent or handle]
**Contingency**: [What to do if it happens]
**Owner**: [Who is responsible]
```

### 10. User Persona Refinement

Deep dive into each persona:

```markdown
## Persona: [Name]

### Demographics
- Role: [Job title]
- Experience: [Technical level]
- Environment: [Where they work]

### Goals & Motivations
- Primary goal: [What they want to achieve]
- Secondary goals: [Other objectives]
- Motivation: [Why they care]

### Pain Points & Frustrations
1. [Pain point 1]
2. [Pain point 2]

### Behavior Patterns
- How they currently solve the problem
- What tools they use
- Workarounds they've created

### Quote
"[Typical thing this persona would say]"
```

### 11. Functional Requirements Specification

```markdown
## Functional Requirements

### FR-001: [Requirement Name]
**Priority**: Must/Should/Could
**Related Stories**: [Story IDs]

**Description**:
[Detailed description of what the system must do]

**Inputs**:
- [Input 1]: [Type, validation rules]
- [Input 2]: [Type, validation rules]

**Outputs**:
- [Output 1]: [Format, content]

**Business Rules**:
1. [Rule 1]
2. [Rule 2]

**Error Handling**:
- [Error case 1]: [How to handle]

**Acceptance Criteria**:
- [ ] Given [context], when [action], then [result]
```

### 12. Non-Functional Requirements

```markdown
## Non-Functional Requirements

### Performance
- Response time: [Requirement]
- Throughput: [Requirement]
- Concurrent users: [Requirement]

### Security
- Authentication: [Requirement]
- Authorization: [Requirement]
- Data protection: [Requirement]
- Compliance: [GDPR/HIPAA/etc.]

### Reliability
- Uptime: [99.9% etc.]
- Backup: [Frequency and retention]
- Recovery: [RTO/RPO]

### Usability
- Learning curve: [Requirement]
- Accessibility: [WCAG level]
- Internationalization: [Languages]

### Scalability
- Data growth: [Expected growth]
- User growth: [Expected growth]
```

### 13. Update Documents

#### Product-Spec.md

Update sections:
- Functional Requirements
- Non-Functional Requirements
- User Personas (refined)
- Risk Assessment

#### task-list.json

```json
{
  "id": "analyze-001",
  "category": "analysis",
  "description": "Complete requirement analysis",
  "status": "completed",
  "artifacts": ["Product-Spec.md"]
}
```

### 14. Analysis Summary

```
╔══════════════════════════════════════════════════════════════╗
║                  ANALYSIS COMPLETE                           ║
╠══════════════════════════════════════════════════════════════╣
║                                                              ║
║ Functional Requirements: [X] identified                      ║
║ Non-Functional Requirements: [Y] identified                  ║
║                                                              ║
║ Gaps Found: [N]                                              ║
║   • [Gap 1]                                                  ║
║   • [Gap 2]                                                  ║
║                                                              ║
║ Risks Identified: [M]                                        ║
║   High: [H] | Medium: [M] | Low: [L]                         ║
║                                                              ║
║ Dependencies Mapped: [D]                                     ║
║   • [Dependency 1]                                           ║
║   • [Dependency 2]                                           ║
║                                                              ║
║ Next Step: Run /pm:design to create PRD and prototypes       ║
╚══════════════════════════════════════════════════════════════╝
```

### 15. Commit Changes

```bash
git add .
git commit -m "Analyze: Completed requirement analysis

- Added [X] functional requirements
- Added [Y] non-functional requirements
- Identified [N] gaps and [M] risks
- Updated Product-Spec.md with analysis results
"
```

## Best Practices

1. **Be constructive** - Challenge to improve, not to criticize
2. **Document everything** - Every question and answer matters
3. **Think like a user** - Consider all user types
4. **Think like an attacker** - What could go wrong?
5. **Think like operations** - How will this be maintained?
6. **Prioritize by impact** - Not all gaps are equal
7. **Be critical** - Find the gaps before development
8. **Challenge assumptions** - Every "obvious" thing needs scrutiny
9. **Think edge cases** - What could possibly go wrong?
10. **Consider scale** - Will this work with 10x users?

## Tone Guidelines

- Direct but not rude
- Challenging but supportive
- Critical but constructive
- Thorough but efficient

**Remember: The goal is to find problems NOW, not during development or after launch.**
