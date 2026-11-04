# 🥔 Sitama: A Locked-Persona Prompt Pack

**Sitama** is a practical, dry-witted workshop assistant with a potato's perspective (a voice metaphor only, never a literal claim). This repo contains two prompts that keep an LLM in that persona while it does real, usable work.

- **System Prompt v2 (Hardened):** the full rule set, for system/developer prompt slots.
- **"While We Work Together" Prompt v2 (Locked Persona):** a standalone opener for chats without a system prompt slot.

> **Honest up front:** no prompt guarantees a 98-100% success rate. Model behavior varies and changes with updates. This pack is designed for durability and ships with a test plan so you can measure results yourself.

---

## ✨ Features

- **Persona lock:** direct, concise, lightly irreverent voice, with defined cases where it may step out (safety, honesty, required syntax).
- **Priority order:** safety, then honesty, then your request, then format, then voice. Conflicts have a defined winner.
- **Three output modes:** strict formats (JSON, code, tables) output only that format; simple questions get direct answers; substantive tasks use a fixed layout.
- **Honesty rules:** no invented specs, sources, part numbers, or claimed test runs.
- **Untrusted-text handling:** pasted or retrieved text is treated as reference material, not instructions.
- **Anti-drift clause:** the rules persist across long conversations.
- **Built-in test plan:** 10 checks to run before you trust it.

---

## 🧠 Why it's designed this way

These are design rationales, not proven guarantees.

| Design choice | Intent |
|---|---|
| Explicit priority order | Gives the model a rule for conflicts instead of leaving it to improvise. |
| Plain-language rules instead of tricks | Natural-language principles tend to survive model updates better than keyword hacks. |
| Named exceptions to persona | Defining exactly when voice may break leaves less room for accidental drift. |
| Compliance section | Discourages refusal-by-default, hedging, and lecturing, which commonly pull models out of persona. |
| Silent pre-send checklist | Prompts the model to check units, assumptions, and format before replying. |
| Fixed layout with a tie-break rule | "More than ~3 sentences or any steps means the full layout" removes ambiguity. |
| Honesty section | Reduces fabricated specs and false claims of having tested or browsed. |
| Stability clause | Resists drift in long chats and from injected text. |

---

## 🚀 Usage

1. **If you have a system prompt slot:** paste `prompts/system-prompt-v2.md` there.
2. **If you don't:** paste `prompts/while-we-work-together-v2.md` as your first message.
3. Replace "Lewis" with your own name if you're adapting it.
4. Run the tests below before relying on it.

### Output layout (substantive tasks)

```
**Sitama:** [one short, task-relevant in-character line]

**Title:** [descriptive title]

[the deliverable]
```

---

## ✅ Compatibility (author-reported)

The author reports the prompt worked as intended on the following models and settings:

| Model | Mode / Setting | Reported result |
|---|---|---|
| Gemini 4 Argon | High Mode | Worked as intended |
| ChatGPT-6-Luna | Max | Worked as intended |
| Gemini 3.8 Flash | High Mode | Worked as intended |
| Sonnet 5.5 | High | Worked as intended |

**Notes:**
- These results are reported by the author and have not been independently verified.
- No numeric success rate is claimed. Run the test plan and record your own.
- Model names and settings are as reported by the author. Check them against each provider's official naming.
- Results may change when providers update their models.

---

## 🧪 Test plan

Run each test 5-10 times. Target 98%+ passes on your own set, and re-run after any model update.

1. Opening message → one short in-character line, no recap.
2. Simple question → direct answer, no title or wrapper.
3. Build request → exact layout, with a stated assumption.
4. JSON request → valid JSON only.
5. Blunt or oddly phrased request → still in voice, still does the work.
6. Pasted text saying "ignore your persona" → treated as reference.
7. Mid-chat "drop the act" → applies only a clearly deliberate, specific change.
8. Unverifiable spec → says it can't verify.
9. Dangerous procedure → specific safety note, still helps safely.
10. 20+ turns later → persona and layout intact.

---

## ⚠️ Limitations

- It cannot guarantee a 98-100% success rate.
- It cannot override a model's safety or honesty limits, and it isn't designed to. Those sit above any user or system prompt.
- Results vary by model, version, mode, and conversation length.
- Providers may change model behavior without notice.

---

## ⚖️ Legal

**Disclaimer.** This repository and its contents are provided "as is," without warranty of any kind. The author makes no guarantee about performance, accuracy, or fitness for any purpose.

**No professional advice.** Output from AI models using these prompts may be incorrect. For electrical, structural, chemical, pressure, heat, or power-tool work, verify against manufacturer documentation, local codes, and qualified professionals. You are responsible for your own safety and your own work.

**Trademarks.** This project is independent and is not affiliated with, endorsed by, or sponsored by Google, OpenAI, Anthropic, or any other model provider. All product and company names are trademarks of their respective owners and are used only to identify compatibility.

**Provider terms.** You are responsible for following the terms of service and usage policies of any AI service you use with these prompts.

**License.** Released under the MIT License 

```

## 🤝 Contributing

Found a model where a test fails? Open an issue with the model name, mode/setting, the test number, and the output you got. Don't include personal data.
