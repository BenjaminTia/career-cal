# career-cal — Career, competition and extracurricular calendar

Hackathons, competitions, networking events, campus talks and workshops, internship and job
applications, scholarship/bursary applications, professional-body membership and progress CHECK
banners, served as an Apple Calendar subscription.

Coursework, classes, exams and school administration live in the separate **uni-cal** feed:
https://benjamintia.github.io/uni-cal/uni.ics

Canonical feed:

```
https://benjamintia.github.io/career-cal/career.ics
```

## Subscribe (Apple Calendar)
Settings > Calendar > Accounts > Add Account > Other > Add Subscribed Calendar, then paste the
canonical URL above. Use a second subscription for uni-cal; the two feeds never overlap.

## What belongs here
- Hackathons and research sprints (Apart AI Collusion Sprint, HKMU Hackathon, MLH, Imperial)
- Competitions and their registration/preparation markers (Huawei ICT, Techathon+, IEEEXtreme,
  PMIHK, ICBC FinTech, English Olympiad, Pokémon TCG)
- Networking events, mixers, talks, expos and seminars, including university-organised ones
  (HKSTP Career Talk, PCIM Asia, HKLF, GYEF, Eason Chan x HKMU talk, wellness talks)
- Campus extracurricular activities (workshops, yoga, museum visits, volunteering, sports courses)
- Internship, job and programme applications, openings and interviews (HKPC, SFC, HKSTP, NATON,
  Career Advisory, Student Helper recruitment)
- Scholarship, bursary and award applications (Dream Builder, WPDA, OSS, Hsin Chong, SPSS,
  For Our Future, HSBC, Student Life Enrichment Subsidy)
- Professional-body membership (IEEE) and civic appointments (MSSY)
- Career/competition progress CHECK banners

Not here: classes, coursework assessments, exams, enrolment/fees, campus IT or facilities notices
— those belong to `uni-cal`.

## Files
- `career.ics` — canonical subscription URL (use this one).
- `career2.ics` — byte-identical mirror, used to bypass a stale client cache.

## Updating
Edit `career.ics`, copy it over `career2.ics`, then stage exactly those files by name:

```
cp career.ics career2.ics
git -c core.autocrlf=false add career.ics career2.ics README.md
git commit -m "..." && git push origin main
```

Never use `git add -A`, never commit backup snapshots here, and never write a home address, phone
number, student ID or other private identifier into a SUMMARY or DESCRIPTION: this repo is public.
Feeds must stay pure CRLF, folded at <=75 octets, one VTIMEZONE per TZID, and must parse cleanly in
both `icalendar` and `vobject` before pushing. Verify the live Pages bytes (HTTP 200,
`text/calendar`) after the rebuild.

## Provenance
Created 24 Oct 2026 by splitting the combined `university-cal` feed: 163 original VEVENTs were
partitioned 74 (uni-cal) / 89 (career-cal) with every original UID, DTSTART/DTEND, DESCRIPTION and
VALARM preserved unchanged.
