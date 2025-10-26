# Market Analyst Skill

## Quick Start

This skill analyzes multiple Reddit sentiment reports to identify market trends, gaps, and opportunities.

## What It Does

**Input**: 2+ sentiment analysis reports (from reddit-sentiment-analysis skill)

**Output**: Comprehensive market analysis with:
- ✅ Universal success factors (what always works)
- ❌ Universal pain points (what always fails)
- 🎯 Market gaps & opportunities (unmet demand)
- 💡 Novelty innovations (unique successes to replicate)
- 🔮 Predicted hits (likely successful products)
- 📊 Strategic recommendations (actionable insights)

## Basic Usage

### Analyze Existing Reports

```
"Analyze the gaming sentiment reports in /docs and identify market opportunities"
```

The skill will:
1. Load all `reddit-sentiment-*.md` files from `/docs/`
2. Extract structured data (likes, dislikes, wishes)
3. Find patterns across all products
4. Identify gaps and opportunities
5. Generate comprehensive market analysis report

### With Stream-Chain Pipeline

```
Use stream-chain to:
1. Run reddit sentiment analysis on [5 products]
2. Feed results to market-analyst skill
3. Generate market opportunity report
```

## Output Structure

The skill generates a detailed report including:

### 1. Universal Success Factors
What drives satisfaction across ALL products analyzed:
- Features/aspects present in 50%+ products
- High positive sentiment (85%+)
- Representative quotes and evidence

**Example**:
```
✅ Responsive Controls (5/5 products, 92% positive)
   - Players consistently praise tight, responsive gameplay
   - Critical for player satisfaction
   - Must-have feature for this category
```

### 2. Universal Pain Points
What consistently frustrates users across products:
- Issues appearing in 60%+ products
- High severity ratings
- Root causes and prevention strategies

**Example**:
```
❌ Aggressive Monetization (4/5 products, 94% negative, HIGH severity)
   - $70 base price + battle passes + cosmetic MTX
   - Players feel nickel-and-dimed
   - Avoid: Layer multiple monetization systems
```

### 3. Market Gaps (Prioritized)
Unmet demand with opportunity scores:
- Feature gaps (wished for, nobody delivers)
- Segment gaps (underserved audiences)
- Price gaps (wrong pricing tiers)
- Business model gaps (better service models)

**Example**:
```
🎯 2-3 Year Game Lifecycles - Priority: 92/100
   - Demand: Mentioned in 4/5 products, HIGH urgency
   - Gap: All games have 1-year support cycles
   - Opportunity: Game with committed 3-year roadmap
   - Market size: $500M+ (estimated TAM)
```

### 4. Novelty Successes
Unique innovations that could be replicated:
- What makes them unique
- Why they work
- Transferability to other products
- Replicability assessment

**Example**:
```
💡 Omnimovement System (Call of Duty BO6)
   - Unique: Sprint/slide/dive in any direction
   - Why it works: Increases skill ceiling, feels fluid
   - Transferable: Yes, to any movement-based game
   - Replicability: MEDIUM (requires animation system overhaul)
```

### 5. Predicted Hits
Products/concepts likely to succeed based on data:
- Hit probability score
- Alignment with success factors
- Gap-filling potential
- Risk assessment

**Example**:
```
🔮 Tactical Extraction Shooter at $25 - Hit Probability: 87%
   ✅ Aligns with success factors: 91/100
   ✅ Avoids pain points: 88/100
   ✅ Fills gaps: 94/100
   ✅ Has novelty: 65/100
   ✅ Price/value: 95/100
```

### 6. Strategic Recommendations
Actionable product development guidance:
- Must-have features
- Critical pitfalls to avoid
- Market opportunity priorities
- Innovation suggestions
- Positioning strategies

## Use Cases

### Product Development
- Prioritize features based on universal success factors
- Avoid common pitfalls that consistently fail
- Validate product-market fit before building

### Market Entry
- Identify underserved segments
- Find gaps in competitive landscape
- Position against established players

### Investment Analysis
- Evaluate product concepts for hit potential
- Assess market opportunity size
- Validate business model assumptions

### Competitive Strategy
- Understand what drives competitor success/failure
- Find differentiation opportunities
- Identify blue ocean spaces

### Trend Forecasting
- Spot emerging patterns early
- Identify dying trends to avoid
- Predict market evolution

## Requirements

### Minimum Input
- **2+ sentiment analysis reports** in `/docs/`
- Reports from **same product category** (e.g., all FPS games)
- Reports from **similar time period** (within 3 months)

### Optimal Input
- **3-5 sentiment reports** for robust patterns
- Mix of **successful and struggling** products
- **Recent data** (within 1 month)
- **Similar market segments** (direct competitors)

## Example Workflow

### Gaming Market Analysis

**Step 1**: Generate sentiment reports
```
- Analyze Battlefield 6
- Analyze Counter-Strike 2
- Analyze Call of Duty: Black Ops 6
- Analyze ARC Raiders
- Analyze Escape From Duckov
```

**Step 2**: Run market analysis
```
"Analyze the 5 gaming sentiment reports and identify market opportunities"
```

**Step 3**: Review output
```
/docs/market-analysis-fps-games-2025-10-26.md
```

**Key Findings**:
- Success: Responsive gunplay, value pricing, innovation
- Failures: $70 pricing + MTX, annual releases, small maps
- Gaps: Affordable tactical shooters with 3-year support
- Predicted hit: $25 extraction shooter with committed roadmap

### SaaS Product Analysis

**Step 1**: Analyze productivity tools
```
- Analyze Notion
- Analyze Obsidian
- Analyze Roam Research
- Analyze Evernote
```

**Step 2**: Run market analysis
**Step 3**: Get strategic insights for new product

## Integration

### Works With

**Primary Data Source**:
- `reddit-sentiment-analysis` skill

**Pipeline Integration**:
- `stream-chain` skill (sentiment → market analysis)

**Follow-up Analysis**:
- `competitive-analysis` skill (deep dive competitors)
- `product-roadmap` skill (prioritize features)
- `trend-analysis` skill (temporal patterns)

### Typical Pipeline

```bash
# 1. Gather sentiment data
reddit-sentiment-analysis → [5 products analyzed]

# 2. Synthesize market insights
market-analyst → [comprehensive report]

# 3. Deep dive opportunities
competitive-analysis → [specific competitor analysis]

# 4. Build product roadmap
product-roadmap → [prioritized feature plan]
```

## Output Files

Reports saved to `/docs/` with naming:
- `market-analysis-[category]-[date].md`

Example:
- `market-analysis-fps-games-2025-10-26.md`
- `market-analysis-productivity-tools-2025-10-26.md`
- `market-analysis-streaming-services-2025-10-26.md`

## Tips for Best Results

### 1. Consistent Category
✅ Analyze products in the same category
❌ Don't mix FPS games with puzzle games

### 2. Balanced Sample
✅ Include successful AND struggling products
❌ Don't only analyze hits (creates survivorship bias)

### 3. Recent Data
✅ Use sentiment reports from similar time period
❌ Don't mix 2023 data with 2025 data

### 4. Sufficient Volume
✅ Minimum 3 products for reliable patterns
❌ 2 products = too small for cross-analysis

### 5. Context Awareness
✅ Consider market maturity, demographics, platforms
❌ Don't ignore context that affects sentiment

## Troubleshooting

**"No clear patterns found"**
→ Products may be too different (check category consistency)
→ Sample size too small (add more products)

**"Gaps seem obvious/already addressed"**
→ Market may be well-served (look for niche segments)
→ Reports may be outdated (use recent data)

**"Predicted hits seem unrealistic"**
→ Check data quality of input reports
→ Validate assumptions with market research
→ Consider feasibility constraints

**"Recommendations too generic"**
→ Add more products for specificity
→ Focus on narrower category segment
→ Include more recent data

## Advanced Features

### Temporal Analysis
Compare sentiment across time periods:
```
- Q1 2025 sentiment reports
- Q4 2024 sentiment reports
→ Identify trend evolution
```

### Demographic Segmentation
Analyze different user segments:
```
- Casual player sentiment
- Hardcore player sentiment
→ Identify segment-specific opportunities
```

### Cross-Category Insights
Find transferable innovations:
```
- Analyze RPGs
- Analyze FPS games
→ Identify mechanics that could cross over
```

## Success Metrics

Good market analysis reports will:
- ✅ Identify 3-5 clear universal success factors
- ✅ Highlight 3-5 consistent pain points
- ✅ Reveal 2-4 high-priority market gaps
- ✅ Showcase 2-3 novelty innovations
- ✅ Predict 2-3 likely hit concepts
- ✅ Provide 5-10 actionable recommendations

## Next Steps After Analysis

1. **Validate findings** with additional market research
2. **Prioritize opportunities** based on your capabilities
3. **Prototype solutions** for highest-priority gaps
4. **Test assumptions** with user interviews/surveys
5. **Iterate strategy** based on new data

---

**Skill Version**: 1.0.0
**Created**: October 26, 2025
**Dependencies**: reddit-sentiment-analysis skill
**Category**: Market Intelligence / Strategic Analysis
