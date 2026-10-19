<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported.
     Persian translation of the upstream file (CC BY-SA 4.0) — see TRANSLATION.md. -->

<div dir="rtl">

> **یادداشت ترجمه:** ترجمه‌ی فارسیِ [این گزارش ساخت](https://github.com/dineshxr/vibecodeschool/blob/main/demos/focus-timer/README.md).
> پرامپت‌های گفت‌وگو ترجمه شده‌اند؛ پرامپت بازسازی هم به انگلیسی (نسخه‌ی اصلی) و هم به فارسی آمده است.

# Focus Timer (تایمر تمرکز)

یک تایمر پومودوروی ۲۵/۵ با جابه‌جایی خودکار مرحله‌ها و نوار پیشرفت — و یک باگ interval در React که ایجنت باید درست رفعش می‌کرد.

**[▶ نسخه‌ی زنده](https://vibecodeschool.com/demos/focus-timer)** · مقدماتی · ۴ پرامپت · ساخته‌شده در حدود ۱۲ دقیقه

## گزارش ساخت

خلاصه‌شده از جلسه‌ی واقعی ساخت — همه‌ی پرامپت‌های کاربر آمده‌اند و نوبت‌های تکراری ابزارها کوتاه شده‌اند.
[نسخه‌ی زنده](https://vibecodeschool.com/demos/focus-timer) این را نوبت به نوبت بازپخش می‌کند.

> **شما:** یک کامپوننت تایمر پومودورو بساز: ۲۵ دقیقه تمرکز، ۵ دقیقه استراحت، جابه‌جایی خودکار، نمایش MM:SS، شروع/مکث/بازنشانی، شمارنده‌ی جلسه‌ها. TypeScript React، بدون وابستگی.

**Claude:** وضعیت‌های phase/left/running/sessions را با یک setInterval درون یک effect که به `running` وابسته است راه می‌اندازم؛ هر ثانیه یک واحد کم می‌شود و وقتی ساعت به صفر برسد مرحله عوض می‌شود.

`Write` ← `components/demos/focus-timer.tsx` — ساخته شد: effect مربوط به interval همراه با پاک‌سازی، MM:SS با padStart، عوض شدن مرحله در صفر.

> **شما:** باگ: در حالت توسعه، گاهی مرحله‌ی استراحت کلاً جا می‌افتد و جلسه‌ها دوتا دوتا شمرده می‌شوند. مستقیم از تمرکز به تمرکز می‌پرد.

**Claude:** این نشانه‌ی StrictMode است: عوض شدن مرحله درون updaterِ setLeft انجام می‌شود، و React در حالت توسعه updaterها را دو بار صدا می‌زند دقیقاً برای آشکار کردن همین ناخالصی. راه‌حل: updater فقط شمارش معکوس می‌کند (خالص)؛ یک effect جداگانه left === 0 را زیر نظر دارد و عوض کردن مرحله و افزایش جلسه را یک بار انجام می‌دهد.

`Edit` ← `focus-timer.tsx · pure updater + zero-watcher effect` — updater مقدار max(s−1, 0) را برمی‌گرداند؛ effect جدید جابه‌جایی‌های تمرکز←استراحت←تمرکز را مدیریت می‌کند.

> **شما:** یک نوار پیشرفت باریک اضافه کن که در طول مرحله پر شود، و کاری کن دکمه بسته به وضعیت Start / Pause / Resume بنویسد.

**Claude:** پیشرفت از (total − left) / total به دست می‌آید — بدون وضعیت تازه. برچسب دکمه: در حال اجرا ← Pause؛ left === total ← Start؛ در غیر این صورت Resume.

`Edit` ← `focus-timer.tsx · progress bar + button labels` — role=progressbar با مقدارهای aria؛ ویژگی data-phase برای استایل‌دهی.

> **شما:** مرور دسترس‌پذیری: ساعتِ در حال تیک‌تاک نباید صفحه‌خوان‌ها را بمباران کند، اما تغییر مرحله باید اعلام شود.

**Claude:** روی ساعت aria-live="off" گذاشتم (هر ثانیه عوض می‌شود) و برچسب مرحله را در جریان عادی صفحه نگه داشتم — به‌ندرت عوض می‌شود و هنگام فوکوس طبیعی خوانده می‌شود. انجام شد: حدود ۱۰۰ خط، پاک‌سازی بررسی شد، بدون انحراف زمانی.

## به این‌ها توجه کنید

- نسخه‌ی اول مرحله‌ها را *درون* updaterِ setLeft عوض می‌کرد — React در StrictMode updaterها را دو بار صدا می‌زند، پس استراحت‌ها جا می‌افتادند. راه‌حل: updaterها خالص می‌مانند؛ عوض کردن مرحله به effect خودش منتقل شد که صفر را زیر نظر دارد.
- «خطا یا رفتار را عیناً بچسبانید» درباره‌ی باگ‌هایی که *می‌بینید* هم صدق می‌کند: توصیف نشانه‌ی دقیق («مرحله‌ی استراحت گاهی جا می‌افتد») باعث شد ایجنت فوراً دو بار صدا زده شدن در StrictMode را تشخیص دهد.
- به دست آوردن نوار پیشرفت از (total − left) / total یعنی هیچ وضعیت اضافه‌ای که باید همگام نگه داشته شود وجود ندارد.

## خودتان بازسازی‌اش کنید

این را در Claude Code (یا Codex، یا Cursor) بچسبانید، بعد یک نیازمندی را عوض کنید و مقایسه کنید:

</div>

```text
Build a pomodoro focus timer as a single React component (TypeScript).
25-minute focus / 5-minute break phases that switch automatically. Show MM:SS big,
a thin progress bar, Start/Pause/Resume and Reset buttons, and a completed-sessions
counter. The setInterval must be cleaned up correctly (no drift, no double ticks in
StrictMode), and state updater functions must stay pure — no side effects inside them.
```

<div dir="rtl">

همین پرامپت به فارسی:

```text
یک تایمر تمرکز پومودورو به‌صورت یک کامپوننت React تنها (TypeScript) بساز.
مرحله‌های ۲۵ دقیقه تمرکز / ۵ دقیقه استراحت که خودکار جابه‌جا می‌شوند. MM:SS را بزرگ نشان بده،
یک نوار پیشرفت باریک، دکمه‌های Start/Pause/Resume و Reset، و شمارنده‌ی جلسه‌های تمام‌شده.
setInterval باید درست پاک‌سازی شود (بدون انحراف زمانی، بدون تیک دوتایی در StrictMode)،
و توابع updater وضعیت باید خالص بمانند — بدون هیچ اثر جانبی درونشان.
```

## کد منبع

همان کامپوننتی که روی سایت زنده اجرا می‌شود: [`focus-timer.tsx`](./focus-timer.tsx)
(React + TypeScript، بدون وابستگی، MIT).

---

⭐ به کارتان آمد؟ به [مخزن اصلی ستاره بدهید](https://github.com/dineshxr/vibecodeschool) · [دموهای بیشتر](https://vibecodeschool.com/demos)

</div>
