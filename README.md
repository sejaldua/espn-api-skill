# espn-api

An [Agent Skill](https://agentskills.io) for querying ESPN's public APIs across 17 sports and 139 leagues. Gives AI coding agents deep knowledge of every ESPN API endpoint, response schema, sport/league slug, and common pitfall so they can help you fetch sports data correctly on the first try.

## Install

```bash
npx skills add sejaldua/espn-api
```

## What It Does

When you ask your AI agent to fetch sports data from ESPN, this skill provides:

- **Complete endpoint catalog** across 6 ESPN API domains (Site, Core v2/v3, Web v3, CDN, Now)
- **All 139 league slugs** mapped to their sport categories
- **JSON response schemas** with annotated examples for every major endpoint
- **Common gotchas** (the standings path trap, CDN's `xhr=1` requirement, `$ref` link patterns, date formats, pagination defaults, and more)
- **Ready-to-use code patterns** in Python, TypeScript, curl, and bash
- **Helper scripts** you can run directly from the terminal

## Supported Sports

Basketball, Football, Baseball, Hockey, Soccer, Golf, Racing, Tennis, MMA, Lacrosse, Rugby, Cricket, Volleyball, Water Polo, Field Hockey, Australian Football, Rugby League

## Coverage

| Category | What You Get |
|----------|-------------|
| Scores & Schedules | Live scoreboards, date-filtered results, game summaries |
| Teams & Rosters | Team lists, rosters, depth charts, injuries, transactions |
| Player Stats | Season stats, game logs, splits, career data, leaderboards |
| Standings & Rankings | League standings, conference rankings, power index |
| Betting & Odds | Spreads, moneylines, over/unders, win probabilities, futures |
| Play-by-Play | Full play data, game situations, drives (football) |
| News | Real-time news feed filtered by sport, league, or team |
| Fantasy | Fantasy league data, rosters, matchups, draft details |
| CDN Game Packages | Richest single-request game data (boxscore + plays + win prob + odds) |

## Helper Scripts

Included scripts for quick terminal access (zero dependencies for bash, stdlib-only for Python):

```bash
# Bash
./scripts/espn_fetch.sh scoreboard basketball nba
./scripts/espn_fetch.sh standings football nfl
./scripts/espn_fetch.sh athlete-stats basketball nba 3136776

# Python
python scripts/espn_fetch.py scoreboard basketball nba --date 20250315
python scripts/espn_fetch.py search "Stephen Curry" --sport basketball
```

## Skill Structure

```
espn-api/
├── SKILL.md                         # Main skill instructions
├── references/
│   ├── endpoints.md                 # Full endpoint catalog (6 API domains)
│   ├── league-slugs.md              # All 139 league slugs by sport
│   ├── response-schemas.md          # Annotated JSON response examples
│   └── gotchas.md                   # 16 common pitfalls and how to avoid them
├── scripts/
│   ├── espn_fetch.py                # Python CLI helper (stdlib only)
│   └── espn_fetch.sh                # Bash/curl CLI helper
└── README.md
```

## Credits

API documentation sourced from [pseudo-r/Public-ESPN-API](https://github.com/pseudo-r/Public-ESPN-API), an excellent community effort to document ESPN's undocumented public APIs.

## Disclaimer

This skill documents ESPN's **undocumented** public APIs. These endpoints are not officially supported and may change without notice. No authentication is required for most endpoints. Use responsibly, implement caching, and respect ESPN's terms of service.

## License

MIT
