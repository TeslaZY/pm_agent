---
description: Create comprehensive PRD and interactive prototypes using Pencil MCP
disable-model-invocation: true
---

# Design PRD & Prototype

This command creates a complete Product Requirements Document (PRD) and generates interactive prototypes using Pencil MCP.

## Workflow

### 1. Pre-flight Check

- Verify `Product-Spec.md` exists with analyzed requirements
- Read `pm-progress.md` to confirm analysis phase is complete
- Check for functional requirements in Product-Spec.md

If analysis not complete:
```
Warning: Requirements not fully analyzed. Consider running /pm:analyze first.
Continue? [Y/n]
```

### 2. PRD Document Generation

Generate a comprehensive PRD with the following structure:

```markdown
# Product Requirements Document

## Document Control

| Field | Value |
|-------|-------|
| Product Name | [Name] |
| Version | 1.0.0 |
| Status | Draft |
| Author | [Name] |
| Date Created | [Date] |
| Last Updated | [Date] |

### Revision History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0.0 | [Date] | [Name] | Initial draft |

---

## 1. Executive Summary

[2-3 paragraphs summarizing the product, its purpose, and key benefits]

---

## 2. Product Vision

### 2.1 Vision Statement

[One compelling sentence describing the future state]

### 2.2 Mission

[What the product aims to achieve]

### 2.3 Goals

1. [Goal 1 - make it SMART: Specific, Measurable, Achievable, Relevant, Time-bound]
2. [Goal 2]
3. [Goal 3]

### 2.4 Non-Goals

1. [Explicitly out of scope for this version]
2. [Future consideration, not current focus]

---

## 3. Target Users

### 3.1 Primary Persona

**Name**: [Persona Name]

| Attribute | Description |
|-----------|-------------|
| Role | [Job title] |
| Demographics | [Age, location, company size] |
| Goals | [What they want to achieve] |
| Pain Points | [Current frustrations] |
| Technical Level | [Novice/Intermediate/Expert] |
| Primary Tasks | [Daily activities] |

**Quote**: "[Something this persona would typically say]"

**Scenario**: [Brief narrative of a typical use case]

### 3.2 Secondary Personas

[Repeat persona structure for additional user types]

---

## 4. User Stories

### 4.1 Must Have (MVP)

| ID | User Story | Effort | Priority |
|----|------------|--------|----------|
| US-001 | As a [user], I want [goal], so that [benefit] | M | Must |

### 4.2 Should Have

| ID | User Story | Effort | Priority |
|----|------------|--------|----------|
| US-XXX | [Story] | L | Should |

### 4.3 Could Have

| ID | User Story | Effort | Priority |
|----|------------|--------|----------|
| US-XXX | [Story] | S | Could |

### 4.4 Won't Have (This Version)

| ID | User Story | Notes |
|----|------------|-------|
| US-XXX | [Story] | [Reason for deferral] |

---

## 5. Functional Requirements

### 5.1 [Feature Category]

#### FR-001: [Requirement Name]

| Field | Value |
|-------|-------|
| Priority | Must/Should/Could |
| Related Stories | US-XXX |
| Description | [Detailed description] |

**Business Rules**:
1. [Rule 1]
2. [Rule 2]

**Inputs**:
- [Input field 1]: [Type, validation]
- [Input field 2]: [Type, validation]

**Outputs**:
- [Output 1]: [Format, content]

**Acceptance Criteria**:
- [ ] Given [context], when [action], then [result]
- [ ] Given [context], when [action], then [result]

**Error Handling**:
- [Error case 1]: [How to handle]

---

## 6. Non-Functional Requirements

### 6.1 Performance

| Metric | Requirement |
|--------|-------------|
| Response Time | < 2 seconds for 95% of requests |
| Page Load Time | < 3 seconds on 4G connection |
| Throughput | [requests/second] |
| Concurrent Users | [number] |

### 6.2 Security

| Area | Requirement |
|------|-------------|
| Authentication | [Method] |
| Authorization | [RBAC/ABAC/etc.] |
| Data Protection | [Encryption at rest/transit] |
| Session Management | [Timeout, refresh] |
| Compliance | [GDPR/HIPAA/SOC2/etc.] |

### 6.3 Reliability

| Metric | Requirement |
|--------|-------------|
| Availability | 99.9% uptime |
| Backup Frequency | [Daily/hourly] |
| Recovery Time Objective (RTO) | [hours] |
| Recovery Point Objective (RPO) | [minutes] |

### 6.4 Usability

| Area | Requirement |
|------|-------------|
| Accessibility | WCAG 2.1 AA |
| Supported Languages | [List] |
| Browser Support | [Chrome, Firefox, Safari, Edge] |
| Learning Curve | [Time to proficiency] |

### 6.5 Scalability

| Metric | Current | 1 Year | 3 Year |
|--------|---------|--------|--------|
| Users | [N] | [N] | [N] |
| Data Volume | [N] | [N] | [N] |
| Transactions | [N/day] | [N/day] | [N/day] |

---

## 7. UI/UX Specifications

### 7.1 Design Principles

1. [Principle 1]
2. [Principle 2]
3. [Principle 3]

### 7.2 Screen Inventory

| Screen | Purpose | Priority |
|--------|---------|----------|
| Home | Landing page | Must |
| [Screen 2] | [Purpose] | [Priority] |

### 7.3 Key User Flows

**Flow 1: [Flow Name]**
1. User lands on [screen]
2. User clicks [element]
3. System displays [result]
4. User completes [action]

### 7.4 Design Tokens

**Colors**:
- Primary: #[Hex]
- Secondary: #[Hex]
- Success: #[Hex]
- Warning: #[Hex]
- Error: #[Hex]

**Typography**:
- Heading: [Font], [Size]
- Body: [Font], [Size]
- Caption: [Font], [Size]

**Spacing**:
- Base unit: 8px
- Gap sizes: 4, 8, 16, 24, 32, 48

---

## 8. Technical Constraints

### 8.1 Platform Requirements

- [ ] Web Application
- [ ] Mobile (iOS)
- [ ] Mobile (Android)
- [ ] Desktop

### 8.2 Browser Support

| Browser | Version |
|---------|---------|
| Chrome | Last 2 versions |
| Firefox | Last 2 versions |
| Safari | Last 2 versions |
| Edge | Last 2 versions |

### 8.3 Integration Requirements

| System | Purpose | Type | Status |
|--------|---------|------|--------|
| [Name] | [Purpose] | [API/Webhook/etc.] | [Ready/Pending] |

### 8.4 Technical Stack

| Layer | Technology |
|-------|------------|
| Frontend | [Framework] |
| Backend | [Framework] |
| Database | [Type] |
| Hosting | [Provider] |
| CI/CD | [Tools] |

---

## 9. Dependencies

### 9.1 Internal Dependencies

| Dependency | Team | Status | Risk | Contact |
|------------|------|--------|------|---------|
| [Name] | [Team] | [Status] | [H/M/L] | [Person] |

### 9.2 External Dependencies

| Dependency | Vendor | Status | Risk | SLA |
|------------|--------|--------|------|-----|
| [Service] | [Vendor] | [Status] | [H/M/L] | [SLA] |

---

## 10. Risks & Mitigations

| Risk | Probability | Impact | Mitigation | Contingency | Owner |
|------|-------------|--------|------------|-------------|-------|
| [Risk description] | H/M/L | H/M/L | [Prevention] | [Plan B] | [Name] |

---

## 11. Success Metrics

### 11.1 Business Metrics

| Metric | Target | Measurement Method |
|--------|--------|-------------------|
| [Metric] | [Target] | [How to measure] |

### 11.2 User Metrics

| Metric | Target | Measurement Method |
|--------|--------|-------------------|
| [Metric] | [Target] | [How to measure] |

### 11.3 Technical Metrics

| Metric | Target | Measurement Method |
|--------|--------|-------------------|
| [Metric] | [Target] | [How to measure] |

---

## 12. Timeline & Milestones

### 12.1 Project Phases

| Phase | Duration | Start | End | Key Deliverables |
|-------|----------|-------|-----|------------------|
| Discovery | 2 weeks | [Date] | [Date] | Requirements |
| Design | 3 weeks | [Date] | [Date] | PRD, Prototypes |

### 12.2 Milestones

| Milestone | Date | Deliverable | Owner |
|-----------|------|-------------|-------|
| M1: Requirements Complete | [Date] | Signed-off PRD | [Name] |
| M2: Design Complete | [Date] | Approved prototypes | [Name] |

---

## Appendix

### A. Glossary

| Term | Definition |
|------|------------|
| [Term] | [Definition] |

### B. References

1. [Document name] - [Link]
2. [Document name] - [Link]

---

*Document generated by PM Agent*
```

### 3. Prototype Generation (Pencil MCP)

#### 3.1 Prepare Design Context

```
Read Product-PRD.md
Extract:
- Screen inventory
- User flows
- Design tokens
- UI specifications
```

#### 3.2 Get Design Guidelines

```javascript
// Get Pencil MCP guidelines
mcp__pencil__get_guidelines({topic: "landing-page"})
// or "design-system" for app design
```

#### 3.3 Create Design Tokens

Use Pencil MCP variables for consistent design:

```javascript
mcp__pencil__set_variables({
  variables: {
    // Colors
    "primary-500": "#3B82F6",
    "primary-600": "#2563EB",
    "secondary": "#10B981",
    "success": "#10B981",
    "warning": "#F59E0B",
    "error": "#EF4444",
    "background": "#FFFFFF",
    "text-primary": "#1F2937",
    "text-secondary": "#6B7280",

    // Typography
    "font-heading": "Inter",
    "font-body": "Inter",
    "text-sm": "14px",
    "text-base": "16px",
    "text-lg": "18px",
    "text-xl": "20px",
    "text-2xl": "24px",

    // Spacing
    "spacing-unit": "8",
    "border-radius": "8"
  }
})
```

#### 3.4 Create Screens

For each screen in the inventory:

```javascript
// Get editor state
mcp__pencil__get_editor_state({include_schema: true})

// Create screen frame
mcp__pencil__batch_design({
  operations: `
    // Create main screen
    screen=I(document, {
      type: "frame",
      name: "[Screen Name]",
      width: 1440,
      height: 900,
      fill: "#FFFFFF"
    })

    // Add header
    header=I(screen, {
      type: "frame",
      name: "Header",
      layout: "horizontal",
      width: "fill_container",
      height: 64,
      padding: [0, 32],
      fill: "#FFFFFF"
    })

    // Add logo placeholder
    logo=I(header, {
      type: "text",
      content: "[Product Name]",
      fontSize: 20,
      fontWeight: "bold"
    })

    // Add navigation
    nav=I(header, {
      type: "frame",
      layout: "horizontal",
      gap: 24
    })

    // Add main content area
    content=I(screen, {
      type: "frame",
      name: "Content",
      layout: "vertical",
      width: "fill_container",
      padding: 32,
      gap: 24
    })
  `
})
```

#### 3.5 Common Components

**Button**:
```javascript
button=I(parent, {
  type: "frame",
  width: "auto",
  height: 40,
  padding: [0, 16],
  fill: "#3B82F6",
  cornerRadius: [8],
  layout: "horizontal",
  alignItems: "center",
  justifyContent: "center"
})
buttonText=I(button, {
  type: "text",
  content: "Button",
  fill: "#FFFFFF",
  fontSize: 14,
  fontWeight: "medium"
})
```

**Input Field**:
```javascript
inputGroup=I(parent, {
  type: "frame",
  layout: "vertical",
  gap: 8
})
label=I(inputGroup, {
  type: "text",
  content: "Label",
  fontSize: 14,
  fontWeight: "medium",
  fill: "#374151"
})
input=I(inputGroup, {
  type: "frame",
  width: "fill_container",
  height: 40,
  padding: [0, 12],
  fill: "#FFFFFF",
  stroke: "#D1D5DB",
  strokeWidth: 1,
  cornerRadius: [8]
})
```

**Card**:
```javascript
card=I(parent, {
  type: "frame",
  width: "fill_container",
  padding: 24,
  fill: "#FFFFFF",
  cornerRadius: [12],
  stroke: "#E5E7EB",
  strokeWidth: 1
})
```

#### 3.6 Page Layout Patterns

**Landing Page**:
```
┌─────────────────────────────────────┐
│            Navigation               │
├─────────────────────────────────────┤
│                                     │
│           Hero Section              │
│    [Title] [Description] [CTA]      │
│                                     │
├─────────────────────────────────────┤
│                                     │
│         Features Section            │
│   [Feature 1] [Feature 2] [Feat 3]  │
│                                     │
├─────────────────────────────────────┤
│            Footer                   │
└─────────────────────────────────────┘
```

**Dashboard**:
```
┌────────┬────────────────────────────┐
│        │         Header             │
│  Side  ├────────────────────────────┤
│  Bar   │                            │
│        │       Main Content         │
│  Nav   │    [Cards / Charts]        │
│        │                            │
└────────┴────────────────────────────┘
```

#### 3.7 Validate with Screenshots

```javascript
// Get screenshot for review
mcp__pencil__get_screenshot({
  nodeId: screen
})
```

### 4. Update Documents

#### Product-Spec.md

Add PRD section reference.

#### task-list.json

```json
{
  "id": "design-001",
  "category": "design",
  "description": "Create PRD and prototypes",
  "status": "completed",
  "artifacts": ["Product-PRD.md", "prototypes/"]
}
```

### 5. Design Summary

```
╔══════════════════════════════════════════════════════════════╗
║                  DESIGN COMPLETE                             ║
╠══════════════════════════════════════════════════════════════╣
║                                                              ║
║ PRD Generated:                                               ║
║   ✓ Product-PRD.md                                           ║
║   ✓ 12 sections completed                                    ║
║                                                              ║
║ Prototypes Created:                                          ║
║   ✓ [N] screens                                              ║
║   ✓ Interactive navigation                                   ║
║   ✓ Design tokens defined                                    ║
║                                                              ║
║ Files:                                                       ║
║   • Product-PRD.md                                           ║
║   • prototypes/[product-name].pen                            ║
║                                                              ║
║ Next Step: Review with stakeholders, then iterate            ║
╚══════════════════════════════════════════════════════════════╝
```

### 6. Commit Changes

```bash
git add .
git commit -m "Design: Created PRD and prototypes

- Generated comprehensive PRD document
- Created [N] prototype screens
- Defined design tokens and components
- Ready for stakeholder review
"
```

## Best Practices

### PRD
1. **Be specific** - Avoid vague language
2. **Be complete** - Cover all aspects
3. **Be measurable** - Use concrete metrics
4. **Be realistic** - Account for constraints
5. **Be visual** - Include diagrams where helpful
6. **Be organized** - Use consistent structure

### Prototypes
1. **Start with structure** - Create frames first, then add content
2. **Use design tokens** - Maintain consistency with variables
3. **Validate frequently** - Check screenshots after each section
4. **Think responsive** - Consider different screen sizes
5. **Add annotations** - Use notes for specifications
6. **Create variations** - Show different states (hover, active, error)
7. **Complete PRD first** - Document before designing
8. **Use design system** - Consistent tokens across screens
9. **Interactive prototypes** - Show real user flows
10. **Export for sharing** - Make prototypes accessible
