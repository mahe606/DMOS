# 1. Purpose

Delivery Manager AI Operating System (DMAI-OS) is an AI-powered assistant designed to help a Delivery Manager manage multiple projects by consolidating information, identifying risks, preparing recommendations, and reducing context switching while keeping the human in control of all decisions.

## 2. Design Principles

- Human is always in control.
- AI recommends; human approves.
- Multiple small agents instead of one large agent.
- Single source of truth.
- Reusable knowledge.
- Modular architecture.
- Easy to extend.


## 3. High Level Architecture 

                 DMAI Dashboard
                        ▲
                        │
          Executive Assistant Agent
                        ▲
      ┌─────────────────┼──────────────────┐
      │                 │                  │
 Project Agent     Meeting Agent      Risk Agent
      │                 │                  │
      └─────────────────┼──────────────────┘
                        │
               Knowledge Repository
                        │
    Gmail  Slack  Jira  Calendar  Notion


# 4. Components

## 4.1 Executive Assistant Agent

### Purpose

Acts as the primary AI assistant for the Delivery Manager by consolidating information from multiple sources into a single daily view.

### Responsibilities

- Prepare the Morning Executive Brief.
- Prepare the End of Day Summary.
- Prioritize today's work.
- Review emails, calendar, Slack, Jira, and Notion.
- Highlight approvals, follow-ups, and important notifications.
- Coordinate with Project Agents.
- Recommend actions requiring management attention.

### Inputs

- Gmail
- Google Calendar
- Slack
- Jira
- Notion
- Delivery Manager Playbook
- Operating Principles

### Outputs

- Executive Dashboard
- Daily Executive Summary
- Action Items
- Recommendations

---

## 4.2 Project Agent

### Purpose

Monitor the health of a single project and provide actionable insights to the Executive Assistant.

Each project has its own Project Agent.

Examples:

- Integration Agent
- Freight Match Agent
- Dispatch Agent
- Production Support Agent

### Responsibilities

- Monitor sprint progress.
- Identify blockers.
- Detect delivery risks.
- Track testing progress.
- Review pull requests.
- Monitor customer updates.
- Generate project summaries.
- Escalate critical issues.

### Inputs

- Jira
- Slack
- Gmail
- Notion
- Meeting Notes
- Project Knowledge

### Outputs

- Project Status
- Risks
- Action Items
- Blockers
- Project Health

---

## 4.3 Knowledge Repository

### Purpose

Provide a centralized knowledge base that allows every AI agent to understand the Delivery Manager's environment, projects, processes, and historical decisions.

### Responsibilities

Maintain knowledge related to:

- Delivery Manager Playbook
- Project Information
- Decision Logs
- Operating Principles
- Meeting Playbooks
- Risk Playbooks
- Communication Guidelines
- Lessons Learned

### Inputs

- Markdown Knowledge Files

### Outputs

- Context supplied to AI agents.

---

## 4.4 Dashboard

### Purpose

Provide a single location where the Delivery Manager can understand everything requiring attention without opening multiple applications.

### Responsibilities

Display:

- Project Health
- Today's Meetings
- Action Items
- Risks
- Blockers
- Pending Approvals
- Follow-ups
- Project Status
- Team Updates

### Inputs

Information from all AI Agents.

### Outputs

Interactive Executive Dashboard.

---

## 4.5 External Systems

### Purpose

Provide operational data required by the AI Operating System.

### Systems

- Gmail
- Google Calendar
- Slack
- Jira
- Notion
- GitHub (Future)
- Workato (Future)

These systems remain the source of truth.

DMAI-OS never replaces them.

---

## 4.6 Human Approval Layer

### Purpose

Ensure that all business decisions remain under human control.

### Responsibilities

Require approval before:

- Sending emails
- Updating Jira
- Creating or modifying Notion tasks
- Scheduling meetings
- Communicating externally
- Performing destructive actions

The AI may prepare recommendations and drafts but never execute business actions without approval.

---

## 4.7 Memory Layer (Future)

### Purpose

Provide long-term organizational memory for the AI Operating System.

### Responsibilities

Remember:

- Important decisions
- Customer preferences
- Architecture decisions
- Delivery history
- Lessons learned
- Repeated issues
- Successful approaches

This enables the AI to answer questions based on historical context instead of only current information.

---

## 4.8 Workflow Engine (Future)

### Purpose

Coordinate the execution of multiple AI agents and business workflows.

### Responsibilities

- Execute Morning Brief workflow.
- Execute Meeting Preparation workflow.
- Execute Weekly Reporting workflow.
- Coordinate communication between agents.
- Manage execution order.
- Ensure dependencies are completed before downstream tasks.

Initially, workflows will be executed manually through Claude prompts. In future versions, they will be orchestrated using an Agent Framework (e.g., LangGraph) and integrated with MCP-enabled tools.