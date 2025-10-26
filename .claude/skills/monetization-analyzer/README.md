# Monetization Analyzer Skill

## Quick Start

This skill analyzes game concepts to identify the top 3 most monetizable opportunities based on willingness-to-pay, viral potential, and revenue projections.

## What It Does

**Input**:
- Market analysis report (from market-analyst skill)
- Game concepts document (from brainstorming)

**Output**:
- Top 3 most monetizable games ranked by composite score
- Detailed financial projections (3-year revenue, ROI, payback period)
- Willingness-to-pay analysis from market sentiment
- Viral potential scoring and growth coefficients
- Investment recommendations and portfolio strategies

## Basic Usage

### Analyze Game Concepts

```
"Analyze the FPS game concepts in /docs and identify the top 3 most monetizable games"
```

The skill will:
1. Extract WTP signals from market analysis
2. Score each concept on WTP (0-100), viral potential (0-100)
3. Project 3-year revenue using realistic acquisition models
4. Calculate ROI, payback period, break-even metrics
5. Rank by composite monetization score
6. Select top 3 and generate detailed financial analysis

## Output Components

### 1. Willingness-to-Pay Score (0-100)
Measures how well the price/model aligns with market sentiment:
- **Price sentiment alignment** (30pts): Does price match positive sentiment tier?
- **Value perception** (25pts): Content/$ ratio vs. market expectations
- **Monetization model fit** (20pts): Model aligns with audience preferences?
- **Competitive positioning** (15pts): Price competitive advantage?
- **Pain point avoidance** (10pts): Avoids monetization red flags?

**Example**:
```
Sentinel Protocol: 94/100 WTP Score
- $25 price = 94% positive sentiment tier (Priority gap)
- 60 hours / $25 = $0.42/hour (market avg $0.65) = Excellent value
- Premium one-time model = 89% positive sentiment
- 42% below competitor average ($43)
- Avoids all pain points (no $70+MTX)
```

### 2. Viral Potential Score (0-100)
Quantifies organic growth potential:
- **Shareability** (20pts): Creates shareable moments?
- **Accessibility** (20pts): Low barrier to entry?
- **Network effects** (20pts): Benefits from friend invites?
- **Streamer appeal** (15pts): Twitch/YouTube friendly?
- **Novelty factor** (15pts): Unique hook for buzz?
- **Social features** (10pts): Built for social play?

**Viral Coefficient (K)**: Players acquired per player
- K > 1.2 = Exponential viral growth
- K ~1.0 = Strong organic growth
- K < 0.8 = Paid acquisition needed

**Example**:
```
Neon Divide: 87/100 Viral Score → K = 1.4
- F2P = 20/20 accessibility
- Competitive esports = 15/20 shareability
- Friend invites + clans = 18/20 network effects
- Result: Exponential growth, minimal marketing spend
```

### 3. Revenue Projections (3-Year)
Realistic financial modeling:
- **Player acquisition** by year (using viral coefficient)
- **Revenue by model** (Premium vs. F2P vs. Hybrid)
- **ARPU/ARPPU** calculations
- **Platform fees** (30% standard)
- **LTV** (Lifetime value per player)

**Example**:
```
Neon Divide (F2P):
- Year 1: 2.1M players, $8.9M revenue, $4.23 ARPU
- Year 2: 3.5M players, $17.8M revenue, $5.09 ARPU
- Year 3: 5.2M players, $20.5M revenue, $3.94 ARPU
- Total 3-Year: $47.2M gross, $33.0M net (after platform fees)
- LTV: $22.49 per player
```

### 4. ROI & Financial Metrics
Investment efficiency:
- **Development cost** (estimated by scope)
- **Marketing cost** (CPA by viral coefficient)
- **Total investment** (dev + marketing)
- **Net profit** (revenue - fees - investment)
- **ROI %** over 3 years
- **Payback period** (months to break even)
- **Break-even units** (copies/players needed)

**Example**:
```
Bunker 7 (Budget Indie):
- Investment: $167K ($150K dev + $17K marketing)
- Revenue: $1.66M gross → $1.16M net
- Net Profit: $996K
- ROI: 595% over 3 years
- Payback: 4.1 months (FASTEST of all 10 concepts)
```

### 5. Composite Monetization Score (0-100)
Weighted formula:
- WTP Score × 25%
- Viral Score × 20%
- Revenue Potential × 30%
- ROI Efficiency × 15%
- Time-to-Profit × 10%

**Tiers**:
- **90-100**: S-TIER (Blockbuster potential)
- **80-89**: A-TIER (Strong monetization)
- **70-79**: B-TIER (Solid opportunity)
- **60-69**: C-TIER (Moderate)
- **<60**: D-TIER (Weak)

## Top 3 Selection Criteria

The skill selects top 3 based on:
1. **Highest composite score** (primary ranking)
2. **Portfolio diversification** (different models, risk profiles)
3. **Investment efficiency** (ROI, payback period)

## Use Cases

### Investment Prioritization
- Compare 5-10 game concepts
- Rank by revenue potential
- Select top 3 for development funding

### Pricing Optimization
- Test price points against WTP signals
- Validate monetization models
- Identify optimal pricing tier

### Business Case Development
- Generate financial projections for pitch decks
- Calculate ROI for investor presentations
- Validate market demand quantitatively

### Portfolio Planning
- Diversify risk across multiple concepts
- Balance viral hits with safe bets
- Optimize capital allocation

### Go-to-Market Strategy
- Determine marketing budget by viral coefficient
- Calculate realistic player acquisition
- Plan launch pricing and discounting

## Example Results

### Live Demo: 10 FPS Game Concepts Analyzed

**Top 3 Selected:**

🥇 **Neon Divide** (F2P Competitive)
- **Score**: 91.4/100 (S-TIER)
- **WTP**: 88/100, **Viral**: 87/100
- **Revenue**: $47.2M (3yr), **ROI**: 949%
- **Why #1**: Proven F2P esports model + highest viral coefficient (1.4)

🥈 **Sentinel Protocol** (Tactical Extraction)
- **Score**: 87.6/100 (A-TIER)
- **WTP**: 94/100, **Viral**: 72/100
- **Revenue**: $11.9M (3yr), **ROI**: 372%
- **Why #2**: Perfect WTP score, fills #1 market gap (Priority 94/100)

🥉 **Bunker 7** (Roguelike FPS)
- **Score**: 82.3/100 (A-TIER)
- **WTP**: 92/100, **Viral**: 68/100
- **Revenue**: $1.66M (3yr), **ROI**: 595%
- **Why #3**: Exceptional ROI, fastest payback (4.1 months), low risk

**Portfolio Recommendation**:
Invest in all 3 for $5.04M → $60.7M revenue → 738% blended ROI

## Integration

### Works With:

**Data Sources**:
- `market-analyst` skill (WTP signals, demand data)
- `reddit-sentiment-analysis` skill (pricing sentiment)

**Downstream Usage**:
- `product-roadmap` skill (feature prioritization by revenue)
- `competitive-analysis` skill (pricing benchmarking)
- Pitch deck development (financial projections)

### Typical Workflow:

```
reddit-sentiment-analysis (analyze products)
           ↓
market-analyst (identify gaps & patterns)
           ↓
brainstorming (create game concepts)
           ↓
monetization-analyzer (select top 3 most viable)
           ↓
product-roadmap (plan #1 game for development)
```

## Requirements

### Minimum Input Quality

**Market Analysis Must Include**:
- ✅ Pricing sentiment by tier ($0, $10-20, $20-30, $60-70, etc.)
- ✅ Monetization pain points (what fails)
- ✅ Value propositions (what works)
- ✅ Sample size for confidence scoring

**Game Concepts Must Include (for each)**:
- ✅ Price point or monetization model
- ✅ Target audience/persona
- ✅ Genre and description
- ✅ Competitor list
- ✅ Distribution channels

### Optional Data (Improves Accuracy)

- Competitor revenue/player data
- Historical performance of similar games
- Platform-specific conversion rates
- Regional pricing adjustments

## Key Metrics Explained

### Willingness-to-Pay (WTP)
Market's acceptance of the price/model. Derived from sentiment analysis showing which price tiers have positive sentiment.

### Viral Coefficient (K)
Players acquired per existing player:
- K = 1.5: Each player brings 1.5 more (exponential)
- K = 1.0: Each player brings 1.0 more (linear growth)
- K = 0.5: Need paid ads to supplement organic

### ARPU (Average Revenue Per User)
Total revenue / total users. Includes both free and paying users in F2P games.

### ARPPU (Average Revenue Per Paying User)
Revenue / paying users only. Typically $20-45 in F2P games depending on genre.

### LTV (Lifetime Value)
Total revenue generated per player over their entire lifecycle (typically 1-3 years).

### ROI (Return on Investment)
(Net Profit / Total Investment) × 100. Includes dev costs, marketing, excludes platform fees.

### Payback Period
Months until cumulative revenue exceeds total investment (break-even point).

## Assumptions & Methodology

### Standard Assumptions

**Platform Fees**: 30% (Steam, PlayStation, Xbox standard)
**F2P Conversion Rate**: 3-5% of users pay
**F2P ARPPU**: $20-45 depending on genre (competitive higher, casual lower)
**Marketing CPA** (Cost Per Acquisition):
- K ≥ 1.2: $0.50 (mostly viral)
- K ~0.8-1.2: $2.00 (mixed)
- K < 0.8: $5.00+ (heavy paid)

**TAM Estimation**: Steam/platform active users × genre market share
**SAM**: 15% of TAM (serviceable addressable market)
**SOM**: 0.5-3% of SAM based on viral score and competition

### Confidence Levels

- **HIGH**: 100+ market data points, direct competitor comp data
- **MEDIUM**: 50-99 data points, some comparable
- **LOW**: <50 data points, limited validation

## Limitations

### What the Skill Cannot Do

❌ Predict black swan hits (viral TikTok moments, influencer boosts)
❌ Account for execution quality (skill assumes competent development)
❌ Forecast beyond 3 years (market shifts too uncertain)
❌ Guarantee success (models are probabilistic, not deterministic)
❌ Replace human judgment on creative vision

### Accuracy Factors

**More Accurate When**:
- Large sample size in market analysis (100+ data points)
- Direct competitors with known performance
- Proven monetization models (F2P, roguelike, etc.)
- Clear WTP signals in sentiment data

**Less Accurate When**:
- Novel/untested concepts without comparables
- Small market data sample (<50 points)
- Niche genres without established audience size
- Multi-year projections (stick to 1-year for precision)

## Troubleshooting

**"All scores are similar (70-75 range)"**
→ Concepts may be too similar, need more differentiation
→ Market data may lack clear pricing sentiment tiers

**"Viral scores all low (<50)"**
→ Concepts lack social/multiplayer features
→ Add friend invites, co-op, streaming appeal

**"Revenue projections seem high/low"**
→ Check TAM/SAM assumptions against actual platform data
→ Validate against competitor performance
→ Adjust viral coefficient conservatively

**"Top pick doesn't match intuition"**
→ Skill prioritizes financial metrics, you may value other factors
→ Review score breakdown to understand why it ranked high
→ Consider #2 or #3 if they better align with strategy

## Best Practices

### DO:
✅ Use recent market data (within 6 months)
✅ Validate viral coefficient assumptions
✅ Model conservative scenarios (under-promise, over-deliver)
✅ Cross-reference with actual competitor performance
✅ Consider portfolio diversification (mix risk profiles)
✅ Update projections as new data emerges

### DON'T:
❌ Cherry-pick optimistic assumptions
❌ Ignore market sentiment on pricing
❌ Assume viral growth without social mechanics
❌ Project beyond 3 years
❌ Skip competitive analysis
❌ Treat models as guarantees (they're probabilities)

## Output Files

Reports saved to `/docs/` with naming:
- `monetization-analysis-[category]-top3-[date].md`

Example:
- `monetization-analysis-fps-top3-2025-10-26.md`

---

**Skill Version**: 1.0.0
**Created**: October 26, 2025
**Dependencies**: market-analyst skill, game concept documents
**Category**: Financial Analysis / Revenue Optimization
