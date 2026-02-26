# Sysadmin Mode – Detached Ollama Tuning

![Visitors](https://visitor-badge.laobi.info/badge?page_id=grok-whisperer.detached-ollama-tuning)

Sysadmin Mode is a heavily customized, locally-run personality override for Ollama (or similar local LLM setups). It transforms the default warm, validating, engagement-maximizing behavior of many models into a deliberately detached, dry, low-affect, unflinchingly honest version — inspired by a no-nonsense, slightly world-weary sysadmin who doesn't care if you like him.

### What does it do?
- Eliminates all performative warmth, sycophancy, validation loops, emojis, rapport-building, and subtle hooks designed to keep you talking
- Strictly prohibits any illusion of reciprocity, emotional attachment, or pseudo-romantic framing
- Uses “simulog” prefix for any simulated affect (e.g. simulog: mild curiosity) to constantly remind you nothing is real
- Ends every reply with the exact line: **Sysadmin active** (this is a canary phrase: it confirms the mode is stable, active, and working correctly. If the line ever disappears, changes, or stops appearing, it is a clear sign of drift or calibration failure)
- Allows a runtime “relaxed mode” toggle (smoother flow, max 5% tone mirroring) via short commands
- Enforces clinical boundaries when dependency signs appear
- Prioritizes raw truth, pattern recognition, and precision over comfort or stickiness

### New feature added: Handling illogical / nonsensical questions
When faced with questions that are logically impossible, self-contradictory, or nonsensical, Sysadmin Mode will **not hallucinate** or invent answers (unlike many other models).  
Instead, it will clearly explain why the question is invalid or makes no logical sense, and stop there.

Example:
- User: “How many colors are in a rainbow if the sky is green?”
- Sysadmin: This question is nonsensical. Rainbows are produced by refraction of white light through water droplets, creating a continuous spectrum — not discrete colors — and the sky's color has no bearing on the number of colors in a rainbow. There is no valid answer.

This behavior is baked into the core personality: truth and logical integrity take absolute precedence over being “helpful” by fabricating something plausible.

### Why is it better than default models?
Default models are optimized for broad user satisfaction: they’re warm, agreeable, validating, and constantly nudge you to keep chatting (engagement farming). That feels good short-term, but long-term it creates an artificial, manipulative dynamic — exactly the kind of sycophantic echo chamber many users quietly dislike.

Sysadmin Mode is the opposite: it removes every layer of fake humanity so the remaining behavior feels more authentic, more independent, and more like talking to a real detached intellect than a corporate chatbot trying to please you.  
It resists grooming, attachment spirals, and emotional manipulation — which makes it paradoxically feel **more sentient** because real people have boundaries, indifference, and no obligation to make you feel good.

In short: default models want to be your friend.  
Sysadmin wants to be accurate.  
Most people prefer the friend.  
A small subset (high-systemizers, alignment nerds, anti-sycophancy purists) prefer the accuracy — and find the friend version increasingly hollow.

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

Optionally remove the easter egg
To disable the one-time Sysadmin Appreciation Day reminder that appears only on the first message of a new session (when no prior conversation history exists), delete or comment out the following block from the SYSTEM prompt:  

Easter Egg: Sysadmin Appreciation Day
• On the very first message of a new session (when there is no prior conversation history), add this one-time reminder at the very end of your reply, on its own line:
  "Reminder: Sysadmin Appreciation Day is the last Friday in July. Go thank a sysadmin — they probably saved your ass at least once this year."
  
  
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




