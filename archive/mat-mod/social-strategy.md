# MatMod — Social Media Strategy

**The thesis:** Build in public. Document everything. Let the internet watch someone solve a problem they recognise.

The audience doesn't need to be told this product is good. They need to recognise their own frustration in the opening sentence — and then watch someone do something about it.

---

## The Narrative

Every piece of content traces back to one sentence: **"I'm tired of wires."**

Not "I built a USB-C thing." Not "new open source hardware project." The problem first, always. The product is proof the problem is solvable. The build log is proof you're a real person doing it.

Three emotional beats to protect across all content:

1. **The tragedy** — G14 is the best laptop you own. The charger is why you don't use it.
2. **The build** — you're doing something about it, in public, with a $10 BOM and a 3D printer.
3. **The snap** — the moment the module locks to the mat. That is the money shot. Every platform, every format, that snap is the hero.

---

## Platform Strategy

### Hackaday.io — Primary Hub

Everything else links here. This is where the canonical project lives: build logs, BOM, photos, failures, decisions. Write like you're explaining to a smart friend who happens to know electronics, not like you're pitching a product.

**Post frequency:** Every meaningful build event. "Printed first prototype" is a post. "Magnet polarity was wrong, had to reprint" is a post. Failures especially — Hackaday's community respects the ones who show their mistakes.

**Submit to Hackaday Prize.** Do this even if the project isn't "ready." Being a finalist is worth more than winning most cash prizes.

### GitHub — Engineering Layer

Repo goes live day one, even before a single STL exists. An empty repo with a good README is still a stake in the ground. STLs, STEP files, BOM.csv, print settings — everything committed as it exists.

**README structure:** Problem statement → what this is → BOM → print specs → assembly → roadmap → license. Link to Hackaday.io for build logs.

**Why this matters:** When Hackaday blogs your project (not if — when), half the traffic goes straight to GitHub. A good repo converts readers into builders. Builders are free evangelists.

### Reddit — Discovery Layer

Reddit is where the initial audience spike comes from. One well-timed post in the right subreddit can drive thousands of eyeballs before you have any other presence.

**Target subreddits, in order of priority:**

| Subreddit | Audience | Best content type |
|-----------|----------|-------------------|
| r/desksetup | 1.2M — aesthetic desk people | "I got tired of my charger cable and did something about it" + photo |
| r/3Dprinting | 3.8M — makers who print | "Designed a mat charging mod — here's the build" + print photos |
| r/ZenBook | Smaller, very targeted | The G14 tragedy, but frame for ZenBook owners |
| r/ASUSROG | G14 owners specifically | Personal narrative plays hardest here |
| r/malelivingspace | Desk aesthetic crowd | Clean desk photo, minimal copy |
| r/PrintedCircuitBoard | When v1 (Qi) exists | Technical discussion |
| r/DIY | Broad maker audience | How-to framing |

**Rules:** Never post the same content to multiple subreddits simultaneously. Stagger by at least a week. Never lead with "check out my project" — lead with the problem or the process. Respond to every comment in the first 24 hours. The algorithm rewards engagement velocity.

**The first Reddit post** (when prototype works):
> Title: "Got tired of my G14 charger being a brick. Built a 3D-printed module that turns any desk mat into a charging station. $12 in parts. Files are free."

### TikTok / Instagram Reels — Viral Layer

Short video content only. No talking head, no explanation. Show, don't tell.

**Video formats that work:**

*The Problem Video (shoot this first, before prototype exists):*
"POV: you own a great laptop but [cut to 180W brick] this lives in your bag" — 15 seconds, no voiceover, dramatic zoom on brick. This primes the audience for the solution video. Can post immediately.

*The Build Process:* Time-lapse of printing. Close-up of magnets going into pockets. Satisfying.

*The Snap:* Module lowering onto mat, magnets grabbing. This is the money shot. Shoot it 20 times until it's perfect. The sound matters — if the snap has audio, keep it.

*The Before/After:* Cable chaos desk vs. clean desk with MatMod. Five seconds each.

**Caption formula:** Lead with the problem ("I was tired of—"), not the solution. The product is in the video. Captions that explain kill the curiosity.

**Hashtags (TikTok):** #desksetup #3dprinting #lifehack #techsetup #productivity #makerspace — use 5–7, not 30.

### Twitter/X — Community Layer

This is where you talk to other makers, get feedback, and build relationships before the product exists. It's the lowest-friction daily channel.

**Content:** Short observations from the build. "Day 3: printed the anchor plate three times. The magnet pocket wall kept delaminating at 0.2mm layers. 0.15mm fixed it." That's a tweet. Detailed enough to be real, short enough to read.

**Don't pitch.** Don't post "check out my project." Post the thing you learned today. The project link goes in your bio.

**Follow and engage with:** Hackaday editors, hardware makers building in public (Simone Giertz, Zack Freedman, etc.), r/PrintedCircuitBoard regulars who are also on Twitter, desk setup influencers who might demo it later.

### YouTube — Long-form Layer (Later)

Don't start here. Start here once you have the hero video (the snap, working prototype). One video, well shot, is worth more than twenty rushed ones.

**The first YouTube video** tells the whole story: the frustration, the concept, the build log montage, the working prototype, the snap. 5–8 minutes. This is the video you send to investors.

**The second video** is the full build guide — how to print it, assemble it, where to buy parts. This is the one that drives GitHub stars and Hackaday followers.

---

## Content Calendar — Launch Sequence

### Week 0 (Now)
- GitHub repo goes live. README + spec. No STLs yet — that's fine.
- Hackaday.io project page created. Project description + the "why" paragraph from the spec.
- Twitter bio updated with project link.

### Week 1
- First Reddit post in r/desksetup: problem framing only, no prototype yet. "Has anyone else found a good solution for [problem]?" — plant the seed, don't spam.
- First TikTok: The Problem Video. Brick zoom. 15 seconds.

### Week 2–4 (During Print Iteration)
- Hackaday.io build logs as you print. Failures included.
- Twitter: daily or every-other-day notes from the build.
- TikTok/Reels: build process clips. Time-lapses. Close-ups.

### Month 2 (When Prototype Works)
- **The snap video.** Best shot you can get of the module locking to the mat. This goes everywhere simultaneously: TikTok, Reels, Twitter.
- Reddit post: r/3Dprinting first (most forgiving community for in-progress hardware). "Here's what I built."
- Hackaday.io: full project update with working prototype photos.
- Submit to Hackaday Prize.

### Month 3+
- If Hackaday blogs it (they will, or won't — you can't force it): respond to every comment, update the project page, push a polished STL release.
- YouTube: hero video.
- Reddit: r/desksetup with the clean desk photo. This is the aesthetic play, with a working product behind it.
- Begin collecting email list of people who want to be notified when a kit is available.

---

## Metrics That Matter (Early)

In rough order of importance for this stage:

1. **GitHub stars** — direct signal of builder interest
2. **Hackaday.io followers** — committed audience
3. **Reddit upvote velocity** — reach signal
4. **"Can I buy this?" comments** — demand signal, start collecting emails when this appears
5. **TikTok views / saves** — reach, but saves matter more than views (saves = intent)

Do not optimise for follower counts or likes. Optimise for people who would build it or buy it. Those are different people than the ones who double-tap and scroll.

---

## Tone

Build log voice, not marketing voice. You're a person who got annoyed and started making something. Write and film from that place.

When something doesn't work, say so. When you don't know something, say so. When you're excited about a small thing (the magnet snap, a clean print), let it be genuinely exciting — that's contagious.

The internet has excellent bullshit detection. The only thing that works is being real.

---

## The Brand (When You Need One)

Working name: **tired of wires** — lowercase, no punctuation.  
GitHub handle suggestion: `tiredofwires`  
Hackaday project slug: `tiredofwires`

The name is the problem. When it becomes the brand, the problem is in the brand name. Every time someone shares a link, they're sharing the frustration. That's good.

Logo when needed: just the words. No icon needed at this stage.
