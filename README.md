# GitHunter

GitHunter is a GitHub profile analysis tool that builds AI-powered developer reports. Given a GitHub username (and an optional job description), GitHunter fetches public profile data via the GitHub REST and GraphQL APIs, runs an AI analysis through Google Gemini, and delivers the results as a downloadable PDF and/or a Google Slides presentation — with outputs persisted in Supabase and cached in Redis for fast repeat lookups.

---

## Features

| Feature | Details |
|---|---|
| **GitHub Data Aggregation** | Fetches user profile, all public repos, pinned repos (GraphQL), per-repo commits & PRs, language distribution, stars, watchers, forks, and total repository size |
| **Smart Repo Ranking** | Pinned repos surface first (candidate-curated showcase), then sorted by stars → forks → recent activity |
| **AI Analysis (Gemini)** | Google Gemini generates narrative insights tailored to the chosen view mode |
| **Recruiter & Developer Modes** | `recruiter` view surfaces portfolio highlights and job-fit scoring; `developer` view digs into technical depth and contribution patterns |
| **Job Description Matching** | Optionally pass a job description to score and tailor the analysis against specific requirements |
| **PDF Export** | Full-page PDF report generated with PDFKit |
| **Google Slides Export** | Populates a Drive-hosted Slides template and shares the result |
| **Async Job Queue** | Analysis jobs are processed via a Bull + Redis queue, decoupling request intake from heavy computation |
| **Redis Caching** | Reports and job status are cached (default TTL: 1 hour) to serve repeat requests instantly |
| **Supabase Persistence** | Reports are stored in Supabase for durable retrieval across restarts |

---

![Alt text](https://media.discordapp.net/attachments/1469067417593581639/1470085068314640444/image.png?ex=6a7fe2a9&is=6a7e9129&hm=2c7a65f7e791543b0770c97f25f7d92457fcd4ed7eb84786a9cd2a4d2dc6fff6&=&format=webp&quality=lossless&width=1518&height=819)

![Alt text](https://media.discordapp.net/attachments/1469067417593581639/1470085109855162460/image.png?ex=6a7fe2b3&is=6a7e9133&hm=5cfcdac50f74f8a9d267639c10fc63421bcabfe19592671a4073ef577c9958fc&=&format=webp&quality=lossless&width=1526&height=819)
