# Community Engagement Trello Board Setup Guide

## Board 1: Community Management Command Center

### Lists to Create:

#### 🎯 Strategic Priorities
- Template Card Structure:
  - Title: [Priority Name]
  - Description: Clear objective statement
  - Checklist: Key milestones
  - Custom Fields: Target date, Impact score (1-5), Status
  - Labels: Area (Culture, Engagement, Learning, etc.)

#### 📋 This Week's Focus
- Template Card Structure:
  - Title: [Specific task]
  - Description: Detailed action steps
  - Checklist: Sub-tasks with owners
  - Due Date: Within current week
  - Labels: Priority (High/Medium/Low)

#### 🚀 In Progress
- Active initiatives with clear owners

#### 🔄 Waiting For...
- Items pending external input or approvals

#### ✅ Completed This Week
- Archive to "Completed Archive" at end of week

#### 📊 Weekly Metrics Review
- Create standard cards for each key metric to update weekly
- Use Trello custom fields to track current vs. target values

#### 📣 Member Spotlights
- Success stories to highlight in communications

### Automations to Set Up:

1. **Weekly Reset Butler Automation:**
   ```
   Every Monday at 9:00 AM:
   - Move all cards from "Completed This Week" to "Completed Archive" list
   - Create new card "Weekly Metrics Update" in "This Week's Focus"
   - Create new card "Prepare Weekly Brief" in "This Week's Focus"
   ```

2. **Due Date Warning:**
   ```
   When a card is 24 hours from due date:
   - Add red "Urgent" label
   - Add comment mentioning card owner
   ```

3. **Completed Task Tracking:**
   ```
   When a card is moved to "Completed This Week":
   - Add completion date to custom field
   - Copy card link to Google Sheet "Completed Tasks" via Zapier
   ```

## Board 2: Engagement Experiments Pipeline

### Lists to Create:

#### 💡 Experiment Ideas
- Template Card Structure:
  - Title: [Experiment Name]
  - Description: Problem statement and hypothesis
  - Checklist: Required resources
  - Custom Fields: Expected impact (1-5), Effort required (1-5)
  - Labels: Experiment type (Format, Gamification, Content)

#### 🔍 Research & Planning
- For experiments being designed and documented

#### 📝 Ready to Launch
- Fully planned experiments waiting for execution

#### 🧪 Currently Running
- Template Card Structure:
  - Title: [Experiment Name]
  - Description: Final hypothesis and success metrics
  - Checklist: Implementation steps
  - Due Date: Experiment end date
  - Custom Fields: Start date, Baseline metric
  - Labels: Experiment type

#### 📊 Analysis Phase
- Experiments gathering final data and being evaluated

#### ✅ Completed & Documented
- Experiments with clear outcomes and learnings

#### ❌ Discontinued
- Experiments stopped early with documented reasons

### Automations to Set Up:

1. **Experiment Progress Tracking:**
   ```
   When a card is moved to "Currently Running":
   - Add current date to "Start Date" custom field
   - Set due date for 2 weeks from today (default testing period)
   - Create card in Google Calendar for experiment end review
   ```

2. **Experiment Results Notification:**
   ```
   When a card is moved to "Completed & Documented":
   - Add comment requesting results summary
   - Send notification to team channel
   ```

3. **Experiment-to-Dashboard Integration:**
   ```
   When custom field "Results" is updated on any card:
   - Update corresponding row in Google Sheets dashboard
   ```

## Board 3: Member Journey & Feedback Tracker

### Lists to Create:

#### 🆕 New Member Cohort
- Create a card for each new member cohort
- Track onboarding completion and early engagement

#### 👋 Welcome Sequence
- Template Card Structure:
  - Title: [Welcome Touchpoint Name]
  - Checklist: Personalization elements
  - Due Date: Timeline for completion
  - Attachment: Template messages/materials

#### 🗣️ Feedback Collection
- Scheduled feedback activities (surveys, interviews)
- Template Card Structure:
  - Title: [Feedback Activity]
  - Description: Goals and target audience
  - Checklist: Question set, distribution plan
  - Due Date: Collection deadline
  - Custom Fields: Response target, Actual responses

#### 📊 Insights & Actions
- Synthesized feedback themes
- Template Card Structure:
  - Title: [Insight Theme]
  - Description: Summary of feedback pattern
  - Checklist: Potential response actions
  - Labels: Impact level, Source type

#### 🚧 Blockers & Concerns
- Issues identified that need resolution
- Template Card Structure:
  - Title: [Issue Name]
  - Description: Detailed problem statement
  - Checklist: Investigation steps
  - Labels: Urgency, Impact area
  - Custom Fields: Affected member segment, Reported by

### Automations to Set Up:

1. **Feedback Loop Closure:**
   ```
   When a card is moved to "Insights & Actions":
   - Create a card in "This Week's Focus" on Board 1
   - Add comment with link to original feedback sources
   ```

2. **Blockers Escalation:**
   ```
   When a card with "High" urgency label is added to "Blockers & Concerns":
   - Send notification to leadership Slack channel
   - Add card to next team meeting agenda
   ```

3. **Feedback Collection Reminder:**
   ```
   Every Friday at 11:00 AM:
   - Create card "Weekly Member Pulse Check" in "Feedback Collection"
   - Set due date for end of day
   ```

## Board 4: Content & Resource Management

### Lists to Create:

#### 📚 Resource Inventory
- Cards for all existing community resources
- Template Card Structure:
  - Title: [Resource Name]
  - Description: Purpose and target audience
  - Custom Fields: Last updated, Usage stats, Feedback score
  - Labels: Topic area, Format type

#### 🧠 Content Ideas
- Proposed new resources and materials

#### 📝 Content In Development
- Resources being created or updated
- Template Card Structure:
  - Title: [Resource Name]
  - Description: Purpose and outline
  - Checklist: Creation milestones
  - Due Date: Target completion
  - Custom Fields: Priority, Requestor
  - Labels: Format, Topic

#### 👀 Ready for Review
- Completed resources awaiting approval

#### 🚀 Ready to Launch
- Approved resources ready for distribution

#### 📊 Performance Tracking
- Monitoring resource utilization and feedback

### Automations to Set Up:

1. **Content Freshness Check:**
   ```
   Every 30 days:
   - For each card in "Resource Inventory"
   - If "Last Updated" is >90 days ago
   - Add "Review Needed" label
   ```

2. **Launch Checklist:**
   ```
   When a card is moved to "Ready to Launch":
   - Create standardized checklist for distribution
   - Set due date for 3 days from now
   ```

3. **Usage Tracking Integration:**
   ```
   Weekly:
   - Update custom fields on resource cards
   - Flag low-performing resources for review
   ```
