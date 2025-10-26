# Reddit Sentiment Analysis - Usage Examples

## Example 1: Gaming Sentiment Analysis

### User Request
"Analyze what gamers are saying about Baldur's Gate 3 on Reddit"

### Agent Execution

**Step 1: Create Analysis Plan**
```javascript
TodoWrite([
  "Identify relevant gaming subreddits",
  "Collect hot posts about Baldur's Gate 3",
  "Collect top posts from past month",
  "Fetch detailed comments from top discussions",
  "Classify sentiment across all content",
  "Extract game aspects (combat, story, performance, etc.)",
  "Aggregate likes, dislikes, and wishes",
  "Generate comprehensive summary report"
])
```

**Step 2: Parallel Data Collection**
```javascript
[Single Message - All Data Collection]:
  mcp__reddit__get_subreddit_hot_posts({subreddit_name: "BaldursGate3", limit: 25})
  mcp__reddit__get_subreddit_top_posts({subreddit_name: "BaldursGate3", time: "month", limit: 25})
  mcp__reddit__get_subreddit_hot_posts({subreddit_name: "gaming", limit: 20})
  mcp__reddit__get_subreddit_top_posts({subreddit_name: "Games", time: "month", limit: 20})
```

**Step 3: Extract Top Post IDs and Fetch Comments**
```javascript
// From results, identify top 15 posts by engagement
[Single Message - Parallel Comment Fetching]:
  mcp__reddit__get_post_content({post_id: "18abc123", comment_depth: 3, comment_limit: 25})
  mcp__reddit__get_post_content({post_id: "18def456", comment_depth: 3, comment_limit: 25})
  mcp__reddit__get_post_content({post_id: "18ghi789", comment_depth: 3, comment_limit: 25})
  // ... 12 more posts
```

**Step 4: Sentiment Classification**
```
Analyzing 15 posts + 375 comments...

POSITIVE SIGNALS FOUND (342 instances):
- "best RPG in years" (87 mentions)
- "incredible writing" (64 mentions)
- "choices actually matter" (52 mentions)
- "combat is fantastic" (39 mentions)

NEGATIVE SIGNALS FOUND (89 instances):
- "Act 3 performance issues" (31 mentions)
- "bugs in multiplayer" (28 mentions)
- "inventory management clunky" (18 mentions)

WISH SIGNALS FOUND (67 instances):
- "wish for more romance options" (23 mentions)
- "need better inventory UI" (19 mentions)
- "want DLC with more content" (15 mentions)
```

**Step 5: Generate Report**
```markdown
# Sentiment Analysis: Baldur's Gate 3

**Analysis Period**: January 20-26, 2025
**Subreddits Analyzed**: r/BaldursGate3, r/gaming, r/Games
**Posts Analyzed**: 90
**Comments Analyzed**: 375

## Overall Sentiment Score
- Positive: 79%
- Negative: 14%
- Neutral: 5%
- Mixed: 2%

## What People LIKE
1. **Writing and Story** (mentioned 142 times, 96% positive)
   - "The writing in this game is absolutely phenomenal"
   - "Best story in a game I've played in the last decade"
   - Common themes: Character depth, meaningful choices, dialogue quality

2. **Player Agency and Consequences** (mentioned 89 times, 94% positive)
   - "Your choices actually matter and have real consequences"
   - "So many ways to solve each quest"
   - Common themes: Multiple solutions, branching paths, replay value

[... continues with full analysis ...]
```

---

## Example 2: Product Brand Analysis

### User Request
"What's the sentiment on Reddit about the iPhone 15 Pro?"

### Agent Execution

**Step 1: Identify Relevant Subreddits**
- r/apple
- r/iphone
- r/smartphones
- r/technology

**Step 2: Collect Product Discussions**
```javascript
[Single Message]:
  mcp__reddit__get_subreddit_hot_posts({subreddit_name: "apple", limit: 30})
  mcp__reddit__get_subreddit_top_posts({subreddit_name: "iphone", time: "month", limit: 30})
  mcp__reddit__get_subreddit_hot_posts({subreddit_name: "smartphones", limit: 20})
```

**Step 3: Filter for iPhone 15 Pro Mentions**
```
Found 47 posts mentioning "iPhone 15 Pro"
Selected top 20 by engagement for detailed analysis
```

**Step 4: Sentiment Analysis Results**
```markdown
# Sentiment Analysis: iPhone 15 Pro

**Analysis Period**: January 2025
**Subreddits Analyzed**: r/apple, r/iphone, r/smartphones
**Posts Analyzed**: 47
**Comments Analyzed**: 284

## Overall Sentiment Score
- Positive: 61%
- Negative: 28%
- Neutral: 9%
- Mixed: 2%

## What People LIKE
1. **Camera Quality** (mentioned 76 times, 89% positive)
   - "Camera is absolutely incredible, especially in low light"
   - "Video quality blows away my old phone"
   - Common themes: Low-light performance, ProRAW, action button for quick camera access

2. **Performance and Chip** (mentioned 54 times, 92% positive)
   - "A17 Pro is ridiculously fast"
   - "Gaming performance is console-level"
   - Common themes: Speed, efficiency, sustained performance

## What People DISLIKE
1. **Pricing** (mentioned 89 times, 94% negative)
   - "Way too expensive for incremental upgrade"
   - "$1200 is hard to justify"
   - Common complaints: High cost, trade-in values, regional pricing differences
   - Severity: HIGH

2. **Battery Life** (mentioned 42 times, 71% negative)
   - "Battery drains faster than my 14 Pro"
   - "Doesn't last a full day with heavy use"
   - Common complaints: Worse than previous gen, inconsistent performance
   - Severity: MEDIUM

## What People WISH FOR
1. **Better Battery Life** (mentioned 38 times)
   - "Wish they prioritized battery over being thin"
   - "Should have a 4500+ mAh battery"
   - Common requests: Larger battery, better optimization
   - Urgency: HIGH

2. **USB-C Improvements** (mentioned 27 times)
   - "Wish USB-C was faster than Lightning speeds"
   - "Should support USB 3.2 across all models"
   - Common requests: Faster data transfer, better cable quality
   - Urgency: MEDIUM

## Competitor Mentions
- **Samsung Galaxy S24 Ultra**: Mixed sentiment, praised for battery and S Pen, criticized for software
- **Google Pixel 8 Pro**: Positive for camera AI, negative for hardware reliability concerns
```

---

## Example 3: Competitive Gaming Analysis

### User Request
"Compare sentiment for Call of Duty vs Battlefield across Reddit"

### Agent Execution

**Step 1: Parallel Competitive Data Collection**
```javascript
[Single Message - Both Games]:
  // Call of Duty data
  mcp__reddit__get_subreddit_hot_posts({subreddit_name: "CallOfDuty", limit: 25})
  mcp__reddit__get_subreddit_top_posts({subreddit_name: "ModernWarfareIII", time: "month", limit: 25})

  // Battlefield data
  mcp__reddit__get_subreddit_hot_posts({subreddit_name: "Battlefield", limit: 25})
  mcp__reddit__get_subreddit_top_posts({subreddit_name: "battlefield2042", time: "month", limit: 25})

  // General gaming discussions
  mcp__reddit__get_subreddit_hot_posts({subreddit_name: "gaming", limit: 30})
```

**Step 2: Generate Comparative Analysis**
```markdown
# Competitive Sentiment Analysis: Call of Duty vs Battlefield

## Call of Duty: Modern Warfare III
**Overall Sentiment**: 52% Positive, 38% Negative, 10% Neutral

### Top Likes:
1. Gunplay and weapon feel (82% positive)
2. Map design in multiplayer (69% positive)
3. Customization options (71% positive)

### Top Dislikes:
1. SBMM (Skill-based matchmaking) (91% negative)
2. Monetization and bundles (87% negative)
3. Lack of content at launch (73% negative)

---

## Battlefield 2042
**Overall Sentiment**: 43% Positive, 47% Negative, 10% Neutral

### Top Likes:
1. Large-scale battles (78% positive)
2. Vehicle gameplay (72% positive)
3. Portal mode (68% positive)

### Top Dislikes:
1. Lack of features from previous games (89% negative)
2. Specialist system (84% negative)
3. Map design (76% negative)

---

## Head-to-Head Comparison

| Aspect | Call of Duty | Battlefield |
|--------|--------------|-------------|
| Overall Sentiment | 52% Positive | 43% Positive |
| Gameplay Feel | Winner | Competitive |
| Content Volume | Competitive | Loser |
| Community Trust | Mixed | Recovering |
| Long-term Support | Stable | Improving |

## Key Insights:
- CoD maintains slight edge in positive sentiment but faces heavy criticism for monetization
- Battlefield recovering from rough launch but still rebuilding community trust
- Both games criticized for removing beloved features from franchises
- CoD has more consistent community, BF has more passionate but smaller fanbase
```

---

## Example 4: Emerging Product Analysis

### User Request
"What are early adopters saying about the Vision Pro on Reddit?"

### Execution Strategy

**Data Collection Focus:**
- r/VisionPro (primary source)
- r/apple (mainstream perspective)
- r/virtualreality (competitive context)
- r/technology (tech enthusiast view)

**Analysis Approach:**
```markdown
# Sentiment Analysis: Apple Vision Pro (Early Adopters)

**Analysis Period**: First 2 weeks post-launch
**Subreddits Analyzed**: 4
**Posts Analyzed**: 67
**Comments Analyzed**: 428

## Overall Sentiment Score
- Positive: 68%
- Negative: 19%
- Neutral: 11%
- Mixed: 2%

## What Early Adopters LIKE
1. **Display Quality** (mentioned 94 times, 97% positive)
   - "Display is absolutely mind-blowing, nothing comes close"
   - "Clarity is unreal, text is perfectly readable"
   - Common themes: Resolution, color accuracy, eye tracking precision

2. **Passthrough AR** (mentioned 71 times, 89% positive)
   - "Passthrough is so good I forget I'm wearing a headset"
   - "AR integration is seamless"
   - Common themes: Real-world blending, spatial awareness

## What Early Adopters DISLIKE
1. **Weight and Comfort** (mentioned 82 times, 88% negative)
   - "Too heavy for extended use, neck strain after 30 mins"
   - "Front-heavy design causes discomfort"
   - Severity: HIGH

2. **App Ecosystem** (mentioned 59 times, 76% negative)
   - "Not enough native apps yet"
   - "Missing key productivity apps"
   - Severity: MEDIUM

## What Early Adopters WISH FOR
1. **Lighter Design** (mentioned 47 times)
   - "Needs to lose at least 100g for all-day comfort"
   - Urgency: CRITICAL

2. **More Native Apps** (mentioned 63 times)
   - "Waiting for Netflix, YouTube, major productivity apps"
   - Urgency: HIGH

## Trend Analysis
- **Week 1**: 75% positive (novelty effect)
- **Week 2**: 68% positive (comfort concerns emerging)
- **Prediction**: Sentiment stabilizing around 65% as realistic expectations set in
```

---

## Example 5: Time-Series Sentiment Tracking

### User Request
"Track how sentiment changed for Cyberpunk 2077 from launch to now"

### Execution Strategy

**Temporal Analysis:**
```javascript
[Single Message - Multi-Period Analysis]:
  // Launch period (Dec 2020)
  mcp__reddit__get_subreddit_top_posts({subreddit_name: "cyberpunkgame", time: "year", limit: 50})

  // Recovery period (2021-2022)
  mcp__reddit__get_subreddit_top_posts({subreddit_name: "cyberpunkgame", time: "month", limit: 30})

  // Current period (2025)
  mcp__reddit__get_subreddit_hot_posts({subreddit_name: "cyberpunkgame", limit: 30})
```

**Output:**
```markdown
# Sentiment Evolution: Cyberpunk 2077 (2020-2025)

## Launch Period (December 2020)
**Overall Sentiment**: 31% Positive, 61% Negative, 8% Neutral

### Dominant Themes:
- Bugs and performance issues (347 mentions, 96% negative)
- Broken promises (89 mentions, 94% negative)
- Last-gen console state (127 mentions, 98% negative)

---

## Recovery Period (2021-2022)
**Overall Sentiment**: 54% Positive, 32% Negative, 14% Neutral

### Dominant Themes:
- Patches improving stability (78 mentions, 87% positive)
- Still lacking promised features (43 mentions, 79% negative)
- PC version solid (56 mentions, 91% positive)

---

## Current Period (2025)
**Overall Sentiment**: 77% Positive, 14% Negative, 9% Neutral

### Dominant Themes:
- Phantom Liberty expansion (94 mentions, 92% positive)
- "Redemption arc complete" (67 mentions, 89% positive)
- 2.0 update transformed game (81 mentions, 94% positive)

---

## Sentiment Journey Visualization

```
Positive Sentiment %
100% |
 75% |                                    ●───●
 50% |                        ●───●───●
 25% |        ●───●───●───●
  0% |____●___|___|___|___|___|___|___|___
     Dec  Jan  Jun  Dec  Jun  Dec  Jun  Jan
     2020 2021 2021 2021 2022 2022 2023 2025
```

## Key Insights:
- Sentiment improved 46 percentage points from launch to current
- 2.0 update + Phantom Liberty marked turning point
- Community sentiment now comparable to well-received AAA titles
- "No Man's Sky" style comeback narrative frequently mentioned
- Trust in CDPR partially restored but cautious optimism remains
```

---

## Tips for Effective Sentiment Analysis

### 1. Subreddit Selection
- **Dedicated subs**: Deep insights but potential echo chamber
- **General subs**: Broader perspective but less detailed
- **Balance both** for comprehensive view

### 2. Time Periods
- **Hot posts**: Current trending discussions
- **Top posts (month)**: Quality content with community validation
- **Top posts (year)**: Historical perspective

### 3. Comment Depth
- **Depth 1-2**: Quick surface analysis
- **Depth 3**: Balanced detail vs. time
- **Depth 4+**: Deep dive but time-intensive

### 4. Sample Size
- **Minimum**: 10 posts, 100 comments
- **Recommended**: 20-30 posts, 300-500 comments
- **Comprehensive**: 50+ posts, 800+ comments

### 5. Evidence Quality
- Always include direct quotes
- Quantify mentions (X times, Y% positive)
- Note severity/urgency for actionability
