# PM Mentality Community Health Monitoring Framework

## Core Health Indicators Dashboard

This framework creates a holistic view of community health beyond simple engagement metrics, allowing you to identify trends and intervention needs early.

| Health Dimension | Key Indicators | Warning Thresholds | Healthy Thresholds | Data Sources |
|------------------|----------------|-------------------|-------------------|--------------|
| **Engagement Vitality** | • Active member % (weekly)<br>• Contribution rate<br>• Response time to posts<br>• New discussion initiation rate | • <15% weekly activity<br>• <5% contribution rate<br>• >24hr avg response<br>• <3 new discussions/week | • >35% weekly activity<br>• >15% contribution rate<br>• <4hr avg response<br>• >10 new discussions/week | • Platform analytics<br>• Post tracking<br>• Member login data |
| **Community Culture** | • Sentiment score<br>• Inclusivity rating<br>• Psychological safety score<br>• "PM Mentality" values alignment | • <3.5/5 sentiment<br>• <70% feel included<br>• <65% feel safe to share<br>• <60% values alignment | • >4.2/5 sentiment<br>• >85% feel included<br>• >80% feel safe to share<br>• >85% values alignment | • Feedback surveys<br>• Content analysis<br>• Pulse checks |
| **Knowledge Exchange** | • Resource utilization<br>• Question resolution rate<br>• Knowledge application<br>• Content quality ratings | • <25% resource use<br>• <70% questions resolved<br>• <40% apply learnings<br>• <3.8/5 content ratings | • >60% resource use<br>• >90% questions resolved<br>• >75% apply learnings<br>• >4.5/5 content ratings | • Resource analytics<br>• Topic tracking<br>• Feedback surveys<br>• Application reports |
| **Member Journey** | • Onboarding completion<br>• New-to-active conversion<br>• Retention rate (30/60/90 day)<br>• Member progression rate | • <60% complete onboarding<br>• <40% become active<br>• <70% 90-day retention<br>• <10% role progression | • >85% complete onboarding<br>• >70% become active<br>• >85% 90-day retention<br>• >25% role progression | • Onboarding tracking<br>• Engagement patterns<br>• Cohort analysis<br>• Member profiles |
| **Leadership Health** | • Mentor engagement<br>• Knowledge-sharing ratio<br>• Leadership pipeline<br>• Response quality ratings | • <40% mentor activity<br>• <1:5 sharing ratio<br>• <3 potential leaders<br>• <4.0/5 quality ratings | • >75% mentor activity<br>• >1:2 sharing ratio<br>• >10 potential leaders<br>• >4.5/5 quality ratings | • Mentor tracking<br>• Contribution analysis<br>• Leadership assessment<br>• Peer ratings |

## Health Score Calculation

**The Community Health Index (CHI)** provides a single metric to track overall community wellbeing while acknowledging the multidimensional nature of community health.

### Calculation Method:

1. **Dimension Scores:**
   - Convert each indicator to 0-100 scale based on:
     - `Score = ((Current Value - Warning Threshold) / (Healthy Threshold - Warning Threshold)) × 100`
   - Cap values between 0-100
   - Calculate dimension average from its indicators

2. **Weighted Index:**
   - Engagement Vitality: 25%
   - Community Culture: 25%
   - Knowledge Exchange: 20%
   - Member Journey: 15%
   - Leadership Health: 15%

3. **Overall CHI:**
   - Weighted average of all dimension scores
   - Represented as 0-100

### Interpretation Scale:

| Score Range | Health Status | General Interpretation |
|-------------|---------------|------------------------|
| 85-100 | Thriving | Community exceeding expectations across dimensions |
| 70-84 | Healthy | Strong foundation with some optimization opportunities |
| 55-69 | Stable | Functioning adequately but with clear improvement areas |
| 40-54 | Vulnerable | Multiple concerning indicators requiring attention |
| <40 | At Risk | Significant intervention needed across multiple dimensions |

## Early Warning System

### Trigger Points for Intervention

| Warning Type | Trigger Conditions | Suggested Response |
|--------------|-------------------|---------------------|
| **Engagement Drop** | • 15%+ drop in weekly engagement<br>• 30%+ drop in new discussions<br>• Response times double | • Content refresh initiative<br>• Targeted re-engagement campaign<br>• Special community event |
| **Culture Concern** | • 10%+ drop in sentiment<br>• Multiple reports of negative interactions<br>• "Values alignment" drops below 65% | • Community values refresh<br>• Moderation review<br>• Community building activities |
| **Knowledge Stagnation** | • Resource utilization drops 20%+<br>• Question resolution rate below 75%<br>• Content ratings drop below 3.5/5 | • Knowledge audit<br>• Expert Q&A sessions<br>• Resource optimization |
| **Retention Risk** | • New member conversion drops 15%+<br>• 30-day retention falls below 80%<br>• Onboarding completion below 70% | • Onboarding journey review<br>• Exit interview analysis<br>• Value reinforcement campaign |
| **Leadership Gap** | • Mentor activity drops below 50%<br>• Knowledge-sharing ratio below 1:10<br>• Quality ratings drop below 3.8/5 | • Mentor appreciation initiative<br>• Leadership development program<br>• New mentor recruitment |

### Weekly Health Check Routine

1. **Data Collection:** Monday morning automated reports
2. **Analysis:**