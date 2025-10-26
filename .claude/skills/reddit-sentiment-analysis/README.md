# Reddit Sentiment Analysis Skill

## Quick Start

This skill enables comprehensive sentiment analysis of Reddit discussions about products, games, brands, or any topic.

## Installation

Ensure the Reddit MCP server is configured in your `.mcp.json`:

```json
{
  "mcpServers": {
    "reddit": {
      "command": "uvx",
      "args": ["mcp-server-reddit"]
    }
  }
}
```

## Basic Usage

### Analyze a Game
```
"Analyze Reddit sentiment about [Game Name]"
```

The skill will:
1. Identify relevant gaming subreddits
2. Collect hot and top posts
3. Analyze posts and comments for sentiment
4. Extract what people like, dislike, and wish for
5. Generate a structured summary report

### Analyze a Product/Brand
```
"What's the sentiment on Reddit about [Product/Brand]?"
```

The skill works for any product category:
- Technology products (phones, laptops, gadgets)
- Services (streaming, SaaS, apps)
- Companies and brands
- Consumer goods

## Output

The skill generates a comprehensive markdown report including:

- **Overall Sentiment Score**: Percentage breakdown (positive/negative/neutral)
- **What People LIKE**: Top 5-7 positive aspects with quotes and frequency
- **What People DISLIKE**: Top 5-7 negative aspects with severity ratings
- **What People WISH FOR**: Top 5-7 feature requests with urgency
- **Key Insights**: Actionable findings and recommendations
- **Competitor Mentions**: Context about competitive products

## Files

- `SKILL.md` - Complete skill documentation with workflow and protocol
- `examples.md` - 5+ detailed usage examples with real scenarios
- `README.md` - This quick reference guide

## Features

✅ Multi-subreddit analysis for balanced perspective
✅ Parallel data collection for speed
✅ Deep comment analysis (not just post titles)
✅ Evidence-based insights with direct quotes
✅ Quantified metrics (percentages, frequencies)
✅ Aspect extraction (specific features discussed)
✅ Temporal tracking (sentiment over time)
✅ Competitive benchmarking
✅ Structured, actionable output

## Configuration Options

### Quick Analysis (~5 minutes)
- 1-2 subreddits
- 10-20 posts
- 10-15 comments per post

### Comprehensive Analysis (~15 minutes)
- 3-5 subreddits
- 40-60 posts
- 20-30 comments per post

### Competitive Analysis (~20 minutes)
- 5-10 subreddits
- 60-100 posts
- 15-20 comments per post

## Best Practices

✅ **DO**: Analyze multiple subreddits for balanced view
✅ **DO**: Include both hot and top posts
✅ **DO**: Read comments (richest sentiment source)
✅ **DO**: Provide direct quotes as evidence
✅ **DO**: Batch all API calls in parallel

❌ **DON'T**: Only check one subreddit (bias risk)
❌ **DON'T**: Ignore comments
❌ **DON'T**: Make claims without evidence
❌ **DON'T**: Mix multiple products in one analysis

## Example Output Structure

```markdown
# Sentiment Analysis: [Product Name]

## Overall Sentiment Score
- Positive: 72%
- Negative: 18%
- Neutral: 10%

## What People LIKE
1. **Feature X** (mentioned 89 times, 94% positive)
   - "Quote showing positive sentiment"
   - Common themes: fast, reliable, easy to use

2. **Feature Y** (mentioned 67 times, 89% positive)
   ...

## What People DISLIKE
1. **Issue X** (mentioned 43 times, 87% negative)
   - "Quote showing negative sentiment"
   - Severity: HIGH

2. **Issue Y** (mentioned 31 times, 72% negative)
   ...

## What People WISH FOR
1. **Request X** (mentioned 52 times)
   - "Quote showing desire/wish"
   - Urgency: HIGH

2. **Request Y** (mentioned 38 times)
   ...

## Key Insights
- [Actionable insight 1]
- [Actionable insight 2]
```

## Integration

This skill works well with:
- Product roadmap planning (prioritize based on user wishes)
- Competitive analysis (benchmark against competitors)
- Market research (validate assumptions)
- Feature development (data-driven decisions)

## Troubleshooting

**Not enough posts found?**
→ Expand to more subreddits or increase time range

**Sentiment too one-sided?**
→ Check for subreddit bias (fan subs vs general subs)

**Missing key aspects?**
→ Increase comment depth and limit

**Taking too long?**
→ Reduce post count, focus on top posts only

## Use Cases

🎮 **Gaming**: Understand player preferences and pain points
📱 **Tech Products**: Track feature reception and issues
🏢 **Brands**: Monitor brand perception and reputation
🛍️ **Consumer Products**: Gather product feedback
📊 **Market Research**: Validate product-market fit
🔍 **Competitive Intel**: Benchmark against competitors

## Next Steps

1. Read `SKILL.md` for complete workflow documentation
2. Review `examples.md` for detailed usage scenarios
3. Try a basic analysis on a familiar product/game
4. Customize subreddit selection for your use case
5. Adjust analysis depth based on time/detail needs

---

**Created by**: agent-skill-creator
**Version**: 1.0.0
**Last Updated**: January 26, 2025
