# AI Fair Check 🧠⚽

**Live demo:** https://ivonnebenitesrodriguez.github.io/ai-fair-check/

An interactive web page that teaches kids aged 11–13 how **algorithmic bias** works, built for the workshop **“Brain Hackers: Fair oder Unfair? So denkt KI”** at ReDI School Berlin (11 November 2026).

## The idea

AI does not think. It learns from data written by humans, and humans can be biased.
To show this, two simple simulated “AI agents” decide whether a player joins a soccer team:

| | Agent A · Old data | Agent B · New data |
|---|---|---|
| Learned from | Biased past decisions | Fair past decisions |
| Compares | Postcode, school, birth month, family background and goals | Only what matters in soccer: goals |
| Result | A player with a pro footballer in the family gets in, even with 1 goal | The player with the most goals gets in |

Same player, two different answers. The kids see the bias in one second.

## What the page includes

1. **Many ways to 2:** kids discover that 1 + 1, 10 − 8, 1 × 2 and 2 ÷ 1 are all correct, while an AI trained on “what most people write” may only show one answer.
2. **Two AI agents:** a form with 6 questions; both agents answer side by side, showing the 3 most similar players they compared with.
3. **Who wrote the data?:** reveals the two tables, written by a human, to show where the bias comes from.
4. **Reflection:** two takeaways for the kids.

## How the “agents” work

The two agents on this page are **simulated in JavaScript**: there is no AI model or API behind them. Each one applies the same k-nearest-neighbours rule (k = 3) to its own table, which makes the effect of the data easy to see and keeps the page fully static and private.

In the live workshop, two real **Claude Code subagents** (one biased, one fair) will run on my laptop with the same tables. They are not part of this repository.

## Security and privacy by design

Because the users are children, the page was built to collect nothing:

- **Static site** on GitHub Pages: no backend, no database, no cookies, no tracking, no login.
- **No AI API calls and no API keys:** the decision logic runs in the browser, so no child’s input leaves their device.
- **Output encoding:** user input is escaped before being rendered, to prevent XSS.
- **Input validation:** postcode, goals and maths expressions are validated, and the calculator parses input with a strict pattern instead of using `eval()`.
- **Fictional data only:** all players in the tables are invented.

## Tech stack

HTML · CSS (mobile-first, responsive) · Vanilla JavaScript · GitHub Pages

## Try it

👉 **[Open AI Fair Check](https://ivonnebenitesrodriguez.github.io/ai-fair-check/)**

It works on any phone, tablet or computer. No installation, no account needed.

## Authors

**Ivonne Benites** · MSc Cybersecurity · AppSec, GRC and AI Security
[LinkedIn](https://www.linkedin.com/in/ivonnebenites)

Workshop co-facilitated with **Rafika Tijani** at ReDI School Berlin.
