<div dir="rtl">

# درباره‌ی این ترجمه

این مخزن ترجمه‌ی فارسیِ [Vibe Code School](https://github.com/dineshxr/vibecodeschool) است، ساخته‌ی
[Dinesh Puppala](https://github.com/dineshxr) ([vibecodeschool.com](https://vibecodeschool.com)).

- **محتوا** (نقشه‌ی راه، سرفصل دوره‌ها، فهرست Awesome، واژه‌نامه) تحت مجوز
  [CC BY-SA 4.0](./LICENSE-CONTENT) است. این ترجمه هم با همان مجوز منتشر می‌شود.
- **کد** (دموها، قالب‌ها) تحت مجوز [MIT](./LICENSE) است.
- **تغییرات:** متن‌ها از انگلیسی به فارسی ترجمه شده‌اند، یادداشت ترجمه به هر فایل افزوده شده و
  این فایل (راهنمای ترجمه و واژه‌نامه) اضافه شده است. کد، نام فایل‌ها، دستورها و پیوندهای سایت
  اصلی دست نخورده‌اند.

نسخه‌ی تعاملی دوره‌ها روی [vibecodeschool.com](https://vibecodeschool.com) است و فعلاً فقط به انگلیسی در
دسترس است.

## وضعیت ترجمه

| بخش | وضعیت |
|-----|-------|
| README، CONTRIBUTING، فهرست Awesome | ✅ ترجمه شده |
| نقشه‌ی راه (`roadmap/`) | ✅ ترجمه شده |
| سرفصل دوره‌ها (`courses/`) | ✅ ترجمه شده |
| واژه‌نامه‌ی کدنویسی با هوش مصنوعی (`dictionary/`) | ⏳ مرحله‌ی بعد — فعلاً انگلیسی |
| قالب‌ها و دموها (`templates/`، `demos/`) | ⏳ مرحله‌ی بعد — فعلاً انگلیسی |

## اصول ترجمه

1. **اصطلاحات فنی:** معادل فارسی، و در اولین کاربرد در هر فایل، اصل انگلیسی داخل پرانتز.
   واژه‌هایی که میان برنامه‌نویسان فارسی‌زبان جاافتاده‌اند (پرامپت، توکن، هوک، ترمینال) به همان شکل
   می‌مانند.
2. **نام محصولات و ابزارها** ترجمه نمی‌شوند: Claude Code، Codex، Cursor، Antigravity، MCP و…
3. **کد، دستورها، نام فایل‌ها و مسیرها** انگلیسی می‌مانند (`/init`، `CLAUDE.md`، `AGENTS.md`).
4. **لحن** مثل متن اصلی: مستقیم، مشخص، بدون اغراق.

## واژه‌نامه‌ی ترجمه

برای یکدست ماندن ترجمه، این معادل‌ها را به کار ببرید:

| English | فارسی |
|---------|-------|
| vibe coding | وایب‌کدینگ |
| agent / AI agent | ایجنت / ایجنت هوش مصنوعی |
| agentic | ایجنتی |
| subagent | زیرایجنت |
| fleet of agents | ناوگان ایجنت‌ها |
| prompt | پرامپت |
| prompt engineering | مهندسی پرامپت |
| token | توکن |
| context window | پنجره‌ی زمینه |
| context engineering | مهندسی زمینه |
| compaction | فشرده‌سازی زمینه |
| harness | هارنس |
| hook | هوک |
| skill | مهارت |
| slash command | دستور اسلش |
| plan mode | حالت برنامه‌ریزی |
| permission mode | حالت مجوز |
| headless mode | حالت بی‌رابط |
| worktree | ورک‌تری |
| project memory | حافظه‌ی پروژه |
| artifact | آرتیفکت |
| connector | کانکتور |
| plugin | افزونه |
| scheduled task | کار زمان‌بندی‌شده |
| loop | چرخه |
| diff | دیف (تفاوت تغییرات) |
| repository / repo | مخزن |
| pull request (PR) | درخواست ادغام (PR) |
| issue | ایشو |
| deploy | دیپلوی |
| ship | منتشر کردن / تحویل دادن |
| scaffold | ساختن اسکلت اولیه |
| review | بازبینی |
| steer | هدایت کردن |
| sandbox | سندباکس |
| prompt injection | تزریق پرامپت |
| jailbreak | جیلبریک |
| guardrails | محافظ‌ها |
| red teaming | آزمون تیم قرمز |
| hallucination | توهم (hallucination) |
| human-in-the-loop | انسان در حلقه |
| RAG | تولید افزوده با بازیابی (RAG) |
| evals | ارزیابی‌ها (evals) |
| observability | مشاهده‌پذیری |
| fine-tuning | تنظیم دقیق |
| open-weight model | مدل وزن‌باز |
| structured output | خروجی ساختاریافته |
| chain-of-thought | زنجیره‌ی تفکر |
| multimodal | چندوجهی |
| roadmap | نقشه‌ی راه |
| course / module / lesson | دوره / بخش / درس |
| capstone | پروژه‌ی پایانی |
| quiz | آزمونک |
| XP / streak | امتیاز (XP) / روزهای پیاپی |
| walkthrough | راهنمای گام‌به‌گام |
| replay | بازپخش |

## هماهنگ ماندن با نسخه‌ی اصلی

مخزن اصلی هر هفته به‌روز می‌شود. برای دریافت تغییرات:

```bash
git remote add upstream https://github.com/dineshxr/vibecodeschool.git
git fetch upstream
git diff HEAD upstream/main --stat   # ببینید چه فایل‌هایی عوض شده‌اند
```

سپس همان بخش‌ها را در ترجمه به‌روز کنید. برای همکاری در ترجمه، پیش از شروع یک ایشو باز کنید تا
دو نفر روی یک فایل کار نکنند.

</div>
