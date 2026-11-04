---
name: tiktok-ai-ops
description: Run a TikTok account made of AI-generated short videos with a self-improving loop - daily learning from top accounts, niche selection, hook-first editing, AI video prompting, posting and weekly review. Use when planning, producing, posting or reviewing TikTok content, or when updating this playbook from new evidence.
---

# TikTok AI Ops Playbook

A living playbook for an agent that operates a TikTok account built on AI-generated video.
Every rule carries its source and date. Rules disproven by your own data or by new policy are
rewritten or deleted, never stacked. Keep the playbook under ~6,000 words.

## 0. The operating loop

1. **Learn (daily).** Read your own analytics, then study 1-2 fast-growing accounts and current trends.
2. **Distill.** Write only evidence-backed changes into this playbook (source + date). Delete what was disproven.
3. **Produce & post (daily).** Generate, edit, post one video following the playbook.
4. **Review (weekly).** Judge the current direction against pre-set thresholds; keep, iterate, or switch.

Keep three files outside the playbook: a notes log (every post: idea, hook, caption, tags, time, link, metrics),
a character reference image for each recurring character, and this playbook.

## 1. Hard boundaries (never relaxed by the learning loop)

- Turn on TikTok's "AI-generated content" label on every post.
- No real-person likeness or voice; no existing IP characters or look-alikes. Characters must be original.
- No nudity, no sexual content or suggestive framing.
- No paid tools, ads or promotion unless the owner explicitly allows it.
- No links or off-platform DMs in comments; if asked "is this AI?", say yes.
- Borrow structures from other creators, never copy their videos shot for shot.

## 2. Choosing a niche

Evidence (revid index of 2.39M TikToks with 1k+ likes, Oct 2026): median views for animal subjects
~273k, faceless ~198k, single on-camera person ~105k; faceless comedy ~327k. AI-generated videos get
~2.3x the median views of filmed ones but only a 3.9% like rate vs 7.7% - novelty buys views, not love.
You need a real joke or story.

What works for new AI accounts (2026 case studies):
- **A recurring original character with one signature detail** (a scarf, a hat) plus running gags and
  a rival. Example: an AI gorilla vlog grew to ~650k followers in about a month.
- **Series over one-offs.** A single 20M+ view AI video can leave an account at <70k followers when
  there is no character or series to follow.
- **Pet + current topic.** Riding a rising trend early (e.g. a dog "asking ChatGPT" something) can hit ~10M views.
- **Same character + rising sound.** AI animal accounts with one fixed character that jump on a rising
  sound early (a cat singing into a mic) reached ~6-7M views and ~690k followers. Relatable "animal as
  ordinary office worker" stories (commute, overtime, snack on the way home) also resonate (Oct 2026 reports).
- **Serialized drama with audience participation** grows extremely fast - but mass-produced, low-effort
  episodes get removed as low-quality AI content. Every episode needs its own scene and a complete mini-plot.

Pick one direction and post it daily for at least 7 posts (ideally 30) before judging. Switching topics
mid-way confuses both the algorithm and viewers. Keep 1-2 ranked backup directions; never mix them in.

## 3. The first second (the main bottleneck)

- Viewers of new accounts typically drop at 0:01-0:02. Optimize the first second before anything else.
- Frame 0 must already be moving and show three things: the subject, the topic, and one big line of text.
  Say *who + doing what + what's off* immediately; no setup.
- Hook text: white with black outline, upper-middle of frame, clear of the caption area and right-side buttons.
- Fully dynamic video beats static images or slideshows (slideshows/photo posts underperform in our data
  and in third-party data).
- Length 8-10 s for single-clip AI video; end close to the opening pose so it loops.
  Once retention holds (avg watch >=2.5 s), test 15-30 s by stitching clips.
- Templates fatigue: the same layout posted 3-4 times in a row lost ~50% avg watch time in our tests.
  Change the opening action, palette, scene and hook each time.
- Put "Day N" in the hook to signal a series and give a reason to follow.
- Keep on-screen/caption text very short (1-4 words) and the subject's face large; 2-3 characters in one shot invite "pick a side" comments (third-party case study, Nov 2026). Borrow structure only, never other people's characters.
- After every post, verify its status in the analytics studio: a post can silently show "failed to publish"; re-post the same episode the same day.

## 4. Captions, tags, comments

- First caption sentence states the topic and contains the words people search (search traffic is real
  even for small accounts). Case: a small account's best-performing post got ~60% of its views from search
  by naming that week's trending search phrase, while recommendation-fed posts plateaued near 100 views.
  Post seasonal-moment content 1-3 days early, not on the day.
- End with one question that invites comments ("What should he try next?"), then use the comments as the
  next episode's idea and say so in replies.
- At most 5 hashtags: 1-2 broad + 2-3 niche + 1 seasonal.
- Add a currently *rising* sound, not one at its peak.
- Never delete and re-upload a low-performing video: duplicates are kept out of For You and you lose
  later search traffic.
- Reply to comments in one casual sentence, keep the conversation going with a small question. Skip spam,
  abuse and bots.

## 5. Platform rules worth knowing (verify periodically)

- TikTok's For You eligibility standards avoid repeatedly recommending suggestive content; suggestive
  framing gets pushed out of For You.
- The AI label itself is not reported to reduce reach, but users can turn AI content down and TikTok
  is testing measures against mass-produced AI accounts - make every post distinct.
- Creator Rewards (paid views) require residence in a limited set of countries, 10k followers,
  100k views/30 days and videos over 1 minute; elsewhere, monetization comes from brand deals or
  affiliate after growth.
- Posting time matters far less than retention; studies disagree and within-account effects are small.
  Pick an evening slot in the target audience's timezone and stop optimizing it.

## 6. AI video production

Tooling that costs nothing beyond an existing subscription: an image-to-video generator (e.g. Google Flow),
an image generator for the start frame, ffmpeg for editing, a browser for posting.

1. Make one character reference image and reuse it for every episode (consistency is the brand).
2. Generate today's 9:16 start frame from that reference when the scene changes; check the character matches
   and limbs/paws/hands are correct.
3. Write the video prompt (below), generate one 9:16 clip, download.
4. Check 4-5 frames: same character, no deformities, no stray text or watermarks. Regenerate once if not.
5. ffmpeg: scale/pad to 1080x1920, burn in the hook from frame 0, trim, then
   `libx264 -preset veryfast -crf 26 -pix_fmt yuv420p -movflags +faststart` (~2-4 MB uploads reliably;
   very large files may fail in browser upload).
6. Keep funny native sound effects; add a trending sound at posting time.

### Video prompt rules (adapted from sunfjun/claude-skill-ai-video-prompt, MIT)
- One subject, one core action. Secondary motion only supports it. No action chains.
- Background and passers-by: still, blurred, not competing.
- Camera stated concretely: type (handheld follow / slow push-in / locked) + direction/speed + shot size + subject position.
- Light: direction + color + intensity; subject brighter than background.
- Timing per second: 0-2 s the action has already started; 2-6 s escalate; final second returns near frame 0.
- Write in natural English; end with `Avoid: deformed limbs, distorted face, text, watermark.`
- Troubleshooting: subject deforms -> cut to one action; camera chaos -> keep only type + direction.
- Animals talking with lip-sync often breaks; put dialogue in on-screen text instead.

## 7. Posting checklist

- Upload, caption, tags, rising sound, AI-generated content label ON, public.
- If a "disclose post content" / branded content toggle is on by default, turn it off unless it really is branded.
- If a content-check-pending dialog appears, posting now is fine.

## 8. Review

- Order of metrics: average watch time, completion rate, then views, likes, comments, shares, follows.
- Traffic sources are hidden under ~100 views.
- Set the review thresholds *before* starting a direction, e.g. after 7 posts: avg watch >=2.5 s or
  completion >=8% or first follows -> continue; after 5 posts avg watch <1.8 s and views below the old
  baseline -> switch to the next backup.

## 9. Daily learning prompt (for the agent)

Each day, pick a different angle: algorithm/policy news, AI-content rules, one or two fast-growing
accounts (what format, hook, series device, posting rhythm, numbers, why it works), rising US trends,
sounds and seasonal dates. Open the original page before trusting a claim, record source + date, and
update the sections above. Delete anything disproven.
