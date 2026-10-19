<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported.
     Persian translation of the upstream file (CC BY-SA 4.0) — see TRANSLATION.md. -->

<div dir="rtl">

# ارائه‌دهنده‌ی مدل (model provider)

> سرویسی که واقعاً مدل را اجرا می‌کند: آزمایشگاهی مثل Anthropic یا OpenAI، ابری که آن را بازفروشی می‌کند، یا لپ‌تاپ خودتان از طریق Ollama.

*§۰۱ مدل · نام‌های دیگر: Provider، Inference provider · [نسخه‌ی تعاملی (انگلیسی)](https://vibecodeschool.com/ai-coding-dictionary/model-provider)*

ارائه‌دهنده‌ی مدل سرویسی است که [استنتاج](./inference.md) را برایتان اجرا می‌کند. معمولاً همان آزمایشگاهی است که [مدل](./model.md) را آموزش داده (Anthropic، OpenAI، گوگل)، گاهی ابری که آن را بازفروشی می‌کند (Amazon Bedrock، Google Vertex، Microsoft Azure)، و گاهی سخت‌افزار خودتان که یک مدل وزن‌باز را از طریق Ollama یا llama.cpp اجرا می‌کند. [هارنس](./harness.md) هر [درخواست به ارائه‌دهنده‌ی مدل](./model-provider-request.md) را برای ارائه‌دهنده می‌فرستد و توکن پس می‌گیرد.

این تمایز مهم است چون ارائه‌دهنده، نه هارنس، محدودیت‌هایی را تعیین می‌کند که به آن‌ها برمی‌خورید: قیمت هر [توکن](./token.md)، محدودیت نرخ، اندازه‌ی [پنجره‌ی زمینه](./context-window.md)، این‌که چه قابلیت‌هایی وجود دارد (کش پرامپت، تفکر گسترده، تخفیف پردازش دسته‌ای) و این‌که [کش پیشوند](./prefix-cache.md) چقدر زنده می‌ماند. وقتی یک ابزار روی دو حساب رفتار متفاوتی دارد، بررسی کنید آیا به ارائه‌دهنده‌ها یا رده‌های متفاوتی وصل‌اند.

بیشتر هارنس‌های کدنویسی اجازه‌ی عوض کردن ارائه‌دهنده را می‌دهند. Claude Code می‌تواند برای تیم‌هایی که از قبل پول یک ابر را می‌دهند، درخواست‌ها را به Bedrock یا Vertex بفرستد. Codex و Cursor را می‌توان به نقطه‌های پایانی دیگر یا کلیدهای خودتان وصل کرد. ارائه‌دهنده‌های محلی حریم خصوصی و نبودِ صورت‌حساب به‌ازای توکن را می‌دهند، به بهای مدل‌های ضعیف‌تر. اول بر اساس توانایی انتخاب کنید؛ ارائه‌دهنده‌ی ارزانی که نتواند کار را تمام کند، ارزان نیست.

## در ابزارها

- Claude Code: متغیرهای محیطی ارائه‌دهنده را بدون تغییر گردش‌کار به Amazon Bedrock یا Google Vertex AI عوض می‌کنند.
- Codex: `model_provider` در فایل پیکربندی، ابزار خط فرمان را به یک نقطه‌ی پایانی دیگرِ سازگار با OpenAI وصل می‌کند.
- Cursor: فهرست مدل‌ها چند ارائه‌دهنده را با هم دارد؛ در تنظیمات می‌توانید کلیدهای API خودتان را اضافه کنید.

## در گفت‌وگو

> «تیم امنیت ما اجازه‌ی فراخوانی مستقیم Anthropic را نمی‌دهد.»
>
> «پس Claude Code را از طریق Bedrock بفرست. همان مدل، ارائه‌دهنده‌ی دیگر، و درون حساب AWS خودتان می‌ماند.»

**مرتبط:** [سقف مصرف](./usage-limit.md) · [توکن‌های ورودی](./input-tokens.md) · [توکن‌های خروجی](./output-tokens.md)

## در مدرسه یادش بگیرید

- [دوره‌ی ۰۴ · پشته‌ی مدرن هوش مصنوعی](https://vibecodeschool.com/learn/aa-04-the-modern-ai-stack)
- [دوره‌ی ۰۴ · اجرای محلی مدل‌ها با Ollama](https://vibecodeschool.com/learn/aa-17-local-models-ollama)

---

بخشی از [واژه‌نامه‌ی کدنویسی با هوش مصنوعی](./README.md) از [Vibe Code School](https://vibecodeschool.com) ·
ترجمه‌ی فارسیِ [مدخل اصلی](https://github.com/dineshxr/vibecodeschool/blob/main/dictionary/model-provider.md) تحت CC BY-SA 4.0 · افزوده‌شده در 2026-09-12

</div>
