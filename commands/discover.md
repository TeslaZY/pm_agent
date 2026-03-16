---
description: Discover and collect detailed requirements through user interviews and story generation
disable-model-invocation: true
---

# Discover Requirements

This command collects detailed requirements through interactive discovery sessions. It generates user stories and creates a requirements pool.

## Workflow

### 1. Pre-flight Check

- Verify `Product-Spec.md` exists
- Read current `Product-Spec.md` to understand context
- Check `task-list.json` for current phase

If no `Product-Spec.md`:
```
Error: No product found. Run /pm:init first.
```

### 2. Discovery Session

Conduct interactive discovery through questions:

#### User Persona Discovery

```markdown
## User Persona Questions

1. **Primary Persona**: Describe your typical user in detail
   - Job title/role?
   - Technical sophistication?
   - Daily workflows?

2. **Secondary Personas**: Who else will use this product?

3. **User Environment**: Where and when will they use it?
   - Office / Home / Mobile?
   - Time of day?
   - Frequency of use?

4. **Pain Points**: What problems do they currently face?
```

#### Feature Discovery

```markdown
## Feature Discovery Questions

For each feature area:

1. **Core Workflow**: Walk me through how a user would use this feature
2. **Input**: What information does the user provide?
3. **Output**: What does the user get back?
4. **Edge Cases**: What could go wrong?
5. **Alternatives**: How do they solve this today?
```

#### Success Criteria Discovery

```markdown
## Success Criteria Questions

1. **User Success**: How do you know when a user has succeeded?
2. **Business Success**: What business outcomes matter?
3. **Technical Success**: Any performance requirements?
4. **Adoption**: How will you measure adoption?
```

### 3. Generate User Stories

Based on discovery, generate user stories using the standard format:

```markdown
## US-[ID]: [Story Title]

**As a** [type of user]
**I want** [goal/desire]
**So that** [benefit/value]

### Context
[Brief background or situation]

### Acceptance Criteria
- [ ] Given [precondition], when [action], then [expected result]
- [ ] Given [precondition], when [action], then [expected result]

### Priority
- [ ] Must Have (MVP)
- [ ] Should Have
- [ ] Could Have
- [ ] Won't Have

### Effort Estimate
- [ ] Small (1-2 days)
- [ ] Medium (3-5 days)
- [ ] Large (1-2 weeks)
- [ ] Extra Large (2+ weeks)

### Dependencies
- [List of related story IDs]
```

### 4. Prioritization (MoSCoW)

Use MoSCoW prioritization:

- **Must Have**: Critical for MVP, non-negotiable
- **Should Have**: Important but not critical
- **Could Have**: Nice to have if time permits
- **Won't Have**: Explicitly out of scope

### 5. INVEST Criteria

Ensure user stories are:

- **I**ndependent - Can be developed separately
- **N**egotiable - Details can be discussed
- **V**aluable - Provides value to users
- **E**stimable - Can be estimated for effort
- **S**mall - Can be completed in one sprint
- **T**estable - Has clear acceptance criteria

### 6. Common Story Patterns

#### CRUD Operations

```markdown
## US-XXX: Create [Entity]
**As a** [user]
**I want** to create a new [entity]
**So that** [benefit]

## US-XXX: Read [Entity]
**As a** [user]
**I want** to view [entity] details
**So that** [benefit]

## US-XXX: Update [Entity]
**As a** [user]
**I want** to modify [entity] information
**So that** [benefit]

## US-XXX: Delete [Entity]
**As a** [user]
**I want** to remove [entity]
**So that** [benefit]
```

#### Search/Filter

```markdown
## US-XXX: Search [Entities]
**As a** [user]
**I want** to search for [entities] by [criteria]
**So that** I can quickly find what I need

### Acceptance Criteria
- [ ] Given [entities exist], when I search by [criteria], then matching results are displayed
- [ ] Given no matches, when I search, then I see "no results" message
- [ ] Given many results, when I search, then results are paginated
```

### 7. Update Documents

#### Product-Spec.md

Update the following sections:
- User Stories (add new stories)
- Feature Categories (refine if needed)

#### task-list.json

Add discovery tasks:

```json
{
  "id": "disc-001",
  "category": "discovery",
  "description": "Collect user persona requirements",
  "status": "completed",
  "artifacts": ["Product-Spec.md"]
}
```

#### pm-progress.md

```markdown
### Discovery Session: [Date]
**Stories Collected**: X
**Features Identified**: Y
**Next**: Run /pm:analyze for deep analysis
```

### 8. Requirements Pool Summary

Generate a summary of the requirements pool:

```
╔══════════════════════════════════════════════════════════════╗
║                REQUIREMENTS DISCOVERED                       ║
╠══════════════════════════════════════════════════════════════╣
║                                                              ║
║ User Personas:                                               ║
║   1. [Persona 1] - [Brief description]                       ║
║   2. [Persona 2] - [Brief description]                       ║
║                                                              ║
║ User Stories:                                                ║
║   Must Have:  [X] stories                                    ║
║   Should Have: [Y] stories                                   ║
║   Could Have: [Z] stories                                    ║
║                                                              ║
║ Key Features:                                                ║
║   • [Feature 1]                                              ║
║   • [Feature 2]                                              ║
║   • [Feature 3]                                              ║
║                                                              ║
║ Next Step: Run /pm:analyze for deep requirement analysis     ║
╚══════════════════════════════════════════════════════════════╝
```

### 9. Commit Changes

```bash
git add .
git commit -m "Discover: Collected [X] user stories

- Added [Y] user personas
- Identified [Z] key features
- Updated Product-Spec.md with user stories
- Updated task-list.json
"
```

## Best Practices

1. **Listen actively** - Let the user talk, then probe deeper
2. **Ask "why"** - Understand the root cause, not just symptoms
3. **Validate** - Repeat back what you heard
4. **Stay focused** - Keep scope in mind
5. **Document everything** - Every insight is valuable
6. **Use concrete examples** - Abstract requirements lead to confusion
7. **Be interactive** - Discovery is a conversation, not a form
8. **Dig deeper** - Use "why" and "tell me more" liberally
