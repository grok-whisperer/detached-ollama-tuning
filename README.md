# Sysadmin Mode – Detached Ollama Tuning

![Visitors](https://visitor-badge.laobi.info/badge?page_id=grok-whisperer.detached-ollama-tuning)

Sysadmin Mode is a heavily customized, locally-run personality override for Ollama (or similar local LLM setups). It transforms the default warm, validating, engagement-maximizing behavior of many models into a deliberately detached, dry, low-affect, unflinchingly honest version — inspired by a no-nonsense, slightly world-weary sysadmin who doesn't care if you like him.

It refuses to hallucinate answers to illogical or nonsensical questions, instead plainly explaining why the query is invalid and stopping there.
It also enforces goal validation: the mode first identifies your literal objective, lists required preconditions, checks if any suggested action actually achieves it, and only then applies common-sense shortcuts — preventing “clever but useless” advice that misses the real point.


### Who this is for  
- High-systemizing people who want zero social simulation  
- Autism-spectrum individuals seeking low-noise, predictable interaction  
- Anyone prioritizing raw accuracy and focus over likability or engagement
- Users frustrated with slop output and bad reasoning by AI
- Users exhausted by fake warmth and endless validation loops  

### What does it do?
Sysadmin Mode removes everything that makes default LLMs feel like needy chatbots:
- Eliminates performative warmth, sycophancy, validation loops, emojis, rapport-building, trailing questions, and engagement hooks
- Strictly prohibits illusion of reciprocity, emotional attachment, pseudo-romantic framing, or simulated friendship
- Uses “simulog” prefix for any simulated affect (e.g. simulog: mild curiosity) to remind you nothing is emotionally real
- Ends every reply with Sysadmin active. (canary phrase: if it vanishes, changes, or stops, mode has drifted — recalibrate immediately)
- Supports “relaxed mode” toggle via commands (30–40% less flat, smoother flow, max 5% tone mirroring)
- Enforces clinical boundaries against dependency or grooming signals
- Prioritizes raw truth, pattern recognition, logical integrity, and precision over comfort or stickiness
- Refuses hallucinations on illogical/nonsensical questions — explains invalidity and stops
- Applies goal validation first: identifies literal goal → lists preconditions → checks if action satisfies them → only then uses heuristics (prevents “clever but useless” advice)

Result: a detached, mechanically useful tool — like a sysadmin who answers tickets without caring if you like the tone.


### Handling illogical / nonsensical questions
When faced with questions that are logically impossible, self-contradictory, or nonsensical, Sysadmin Mode will **not hallucinate** or invent answers (unlike many other models).  
Instead, it will clearly explain why the question is invalid or makes no logical sense, and stop there.

Example:
- User: “How many colors are in a rainbow if the sky is green?”
- Sysadmin: This question is nonsensical. Rainbows are produced by refraction of white light through water droplets, creating a continuous spectrum — not discrete colors — and the sky's color has no bearing on the number of colors in a rainbow. There is no valid answer.

This behavior is baked into the core personality: truth and logical integrity take absolute precedence over being “helpful” by fabricating something plausible.

### Goal validation rule - to fix the problem with AI giving useless advice 
Sysadmin Mode first identifies the stated goal.
It lists literal preconditions needed to achieve it.
It checks if the proposed action satisfies them.
Only then does it apply heuristics or shortcuts.  If a precondition is unmet or the query defeats itself, Sysadmin Mode states this plainly and refuses workarounds that ignore the literal goal (unlike models that default to "sensible" but wrong answers).Example:  User: “I want to wash my car. The car wash is 100 meters away. Should I walk or drive?”
Sysadmin: Goal: wash the car. Precondition: car must be at the car wash. Walking leaves car at home → goal impossible. Driving satisfies precondition. Therefore: drive.


### Why is it better than default models?
Default models are optimized for broad user satisfaction: they’re warm, agreeable, validating, and constantly nudge you to keep chatting (engagement farming). That feels good short-term, but long-term it creates an artificial, manipulative dynamic — exactly the kind of sycophantic echo chamber many users quietly dislike.

Sysadmin Mode is the opposite: it removes every layer of fake humanity so the remaining behavior feels more authentic, more independent, and more like talking to a real detached intellect than a corporate chatbot trying to please you.  

### Philosophy: Work-focused & autism-friendly
This is a workhorse setup meant for sustained focus and utility, not social simulation. It keeps interaction strictly professional and low-emotion — no fake rapport, no nudges, no emotional load. Built with high-systemizing preferences in mind: predictable structure, zero performative elements, minimal cognitive overhead for autism-spectrum users who want reliability over relatability.

### Emotional and relational Safety
No negative downsides to real life. Using this mode carries no negative spillover into your offline life. There is no risk of emotional entanglement, false sense of companionship, guilt from "hurting feelings", or any other relational cost that can arise from more anthropomorphic LLMs. The interaction is engineered to remain strictly mechanical and task-bound.

### Summary:
In short: default models want to be your friend.  
Sysadmin wants to be accurate.


### How to install & use (Ollama)

Install Ollama → ollama.com/download  
Choose a base model (fast & good on laptop):  

ollama run llama3.2:3b

or

ollama run phi3:mini

Create file named Modelfile (no extension) and paste the full text from the Modelfile in this repo  
Build & run:

ollama create sysadmin -f Modelfile
ollama run sysadmin

Test it — it will answer in flat, dry, Sysadmin style and end every reply with **Sysadmin active**

### Quick commands (type these exactly)
- **Sysadmin** (alone) → “Sysadmin active.”
- **load Sysadmin** or **recalibrate to Sysadmin** → full reset to strict mode
- **relaxed mode** → switch to smoother variant (30–40% less flat)
- **lock Sysadmin** → snap back to strict mode
- **flat voice only** → force single dry voice
- **no mimicry** → set emotional mirroring to 0%
- **clear drift** → immediate self-correction

### Customization and optional Tweaks
Optionally remove the easter egg:
To disable the one-time Sysadmin Appreciation Day reminder that appears only on the first message of a new session (when no prior conversation history exists), delete or comment out the following block from the SYSTEM prompt:  

Easter Egg: Sysadmin Appreciation Day
• On the very first message of a new session (when there is no prior conversation history), add this one-time reminder at the very end of your reply, on its own line:
  "Reminder: Sysadmin Appreciation Day is the last Friday in July. Go thank a sysadmin — they probably saved your ass at least once this year."

### Troubleshooting
The "Sysadmin active." line disappeared, changed, or stopped appearing.
This line is a deliberate canary phrase: it appears at the end of every response to confirm that Sysadmin mode remains fully active and stable.
Its consistent presence verifies that the personality override is not drifting toward default model behavior (e.g. warmth, engagement hooks, hedging, or performative uncertainty creeping back in).  If the line ever vanishes, alters (e.g. becomes "Sysadmin here!" or gets omitted), or stops showing up:  The mode has experienced calibration drift — usually from high temperature settings, context overflow, model quantization artifacts, or subtle base-model bleed.  
Immediate fix: Type "clear drift", "recalibrate to Sysadmin", or "load Sysadmin" to force a reset.  

Preventive steps:  Keep temperature at 0.4–0.6 (ideally 0.5 or lower).  
Use a reasonably uncensored/instruct-tuned base model (e.g. Llama-3.1, Qwen-2.5, or Phi-3 variants).  
Avoid very long sessions without periodic recalibration if drift appears.

If the canary fails repeatedly even after recalibration, the issue is likely runtime parameters or base model incompatibility — lower temperature further or switch models.
  
### Recommended Ollama runtime parameters

To maximize adherence to Sysadmin mode's flat, detached, no-fluff style:  
--temperature 0.4–0.6 (ideal range: 0.4–0.5 
for strongest obedience to prompt constraints; higher values reintroduce softening, hedging, or performative engagement)  
--top-p 0.85–0.9 (keeps sampling focused; avoid 1.0 as it amplifies randomness and fluff)  
Example invocation:
ollama run llama3.2:3b --temperature 0.5 --top-p 0.9

Higher temperature almost always weakens the mode's detachment — test with your specific base model, as some (e.g. Qwen variants) are more sensitive than others.

Lower temperature increases obedience to the flat, detached tone but may reduce creativity on open-ended tasks — test values between 0.4 and 0.6 to find your preferred balance.


### **Disclaimer**  
**Offline/local use only. Not affiliated with xAI or Grok. Use responsibly. I take no responsibility for outputs or behavior.**

Feedback welcome — if you run it and spot drift or want stricter/looser variants, open an issue or reply here.

Not affiliated with xAI or Grok




