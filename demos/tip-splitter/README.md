<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported.
     Persian translation of the upstream file (CC BY-SA 4.0) — see TRANSLATION.md. -->

<div dir="rtl">

> **یادداشت ترجمه:** ترجمه‌ی فارسیِ [این گزارش ساخت](https://github.com/dineshxr/vibecodeschool/blob/main/demos/tip-splitter/README.md).
> پرامپت‌های گفت‌وگو ترجمه شده‌اند؛ پرامپت بازسازی هم به انگلیسی (نسخه‌ی اصلی) و هم به فارسی آمده است.

# Tip Splitter (تقسیم‌کننده‌ی انعام)

پروژه‌ی کلاسیک اول وایب‌کدینگ — صورت‌حساب، انعام، تقسیم، با گرد کردن صادقانه‌ی سنت‌ها. ساخته‌شده در چهار پرامپت.

**[▶ نسخه‌ی زنده](https://vibecodeschool.com/demos/tip-splitter)** · مقدماتی · ۴ پرامپت · ساخته‌شده در حدود ۱۰ دقیقه

## گزارش ساخت

خلاصه‌شده از جلسه‌ی واقعی ساخت — همه‌ی پرامپت‌های کاربر آمده‌اند و نوبت‌های تکراری ابزارها کوتاه شده‌اند.
[نسخه‌ی زنده](https://vibecodeschool.com/demos/tip-splitter) این را نوبت به نوبت بازپخش می‌کند.

> **شما:** یک کامپوننت React برای تقسیم انعام بساز: ورودی مبلغ صورت‌حساب، دکمه‌های درصد انعام (10/15/18/20/25)، یک شمارنده‌ی تعداد نفرات، و سهم هر نفر که بزرگ نشان داده شود. TypeScript، بدون وابستگی بیرونی.

**Claude:** یک کامپوننت سمت کلاینت با سه تکه وضعیت می‌سازم — bill (رشته، تا تایپ آزاد بماند)، tipPct، people — و جمع‌ها را هنگام رندر محاسبه می‌کنم.

`Write` ← `components/demos/tip-splitter.tsx` — ساخته شد: ورودی‌ها، دکمه‌ها، شمارنده، مقادیر محاسبه‌شده‌ی tipTotal / grandTotal / share، قالب‌بندی ارز با toLocaleString.

> **شما:** تایپ کردن حروف یا خالی کردن فیلد $NaN نشان می‌دهد. هیچ‌جا NaN نشان نده — به‌جایش یک حالت خنثیِ «مبلغ را وارد کنید» نشان بده.

**Claude:** علت اصلی: parseFloat روی رشته‌ی خالی. یک محافظ `valid` اضافه می‌کنم (عدد متناهی، بزرگ‌تر از صفر، people ≥ 1)، کاراکترهای غیرعددی را هنگام ورود حذف می‌کنم، و وقتی نامعتبر است یک پنل حالت خالی نشان می‌دهم.

`Edit` ← `tip-splitter.tsx · validation guard` — share/tip/total حالا فقط وقتی معتبر است محاسبه می‌شوند؛ ناحیه‌ی نتیجه‌ی aria-live اضافه شد.

> **شما:** سر میزهای واقعی سهم هر نفر را تا سنت بالا گرد می‌کنند. یک چک‌باکس برایش بگذار — اما اگر گرد کردن باعث شود بیشتر از صورت‌حساب جمع کنیم، به‌جای پنهان کردن، بگو.

**Claude:** وضعیت roundUp را اضافه می‌کنم: share = ceil(rawShare · 100)/100، بعد collected − grandTotal مقدار اضافه است. آن را به شکل «Overpay from rounding: $0.02 (tip it)» فقط وقتی بیشتر از یک‌دهم سنت باشد نشان می‌دهم.

`Edit` ← `tip-splitter.tsx · rounding + overshoot row` — چک‌باکس وصل شد؛ ردیف مقدار اضافه شرطی نمایش داده می‌شود.

> **شما:** پرداخت نهایی: تعداد نفرات را حداکثر ۵۰ کن، مفرد و جمع را درست برچسب بزن، و دکمه‌های شمارنده را با کیبورد قابل دسترس کن.

**Claude:** انجام شد — Math.min(50) هنگام افزایش، شرط سه‌تایی «person/people»، و aria-label روی هر دو دکمه‌ی شمارنده. کامپوننت حدود ۱۳۰ خط است و هیچ وابستگی ندارد.

## به این‌ها توجه کنید

- نوبت‌های کوچک: اسکلت ← وصل کردن محاسبات ← حالت‌های مرزی ← پرداخت نهایی. چهار پرامپت، هر کدام قابل بازبینی.
- نسخه‌ی اول ایجنت برای صورت‌حساب خالی $NaN نشان می‌داد — گفتن «هرگز NaN نشان نده» کل مسیر اعتبارسنجی ورودی را در یک نوبت درست کرد.
- بالا گرد کردن سهم‌ها یعنی میز چند سنت بیشتر می‌پردازد. آشکار کردن آن («tip it») بهتر از جذب بی‌صدای آن است — تصمیمی برای رابط کاربری صادق که ایجنت تا از او نخواهید نمی‌گیرد.

## خودتان بازسازی‌اش کنید

این را در Claude Code (یا Codex، یا Cursor) بچسبانید، بعد یک نیازمندی را عوض کنید و مقایسه کنید:

</div>

```text
Build a tip splitter as a single React component (TypeScript).
Inputs: bill amount (text input, $ prefix), tip percent (preset chips: 10/15/18/20/25),
number of people (stepper with − and + buttons, min 1), and a "round each share up
to the cent" checkbox. Output: per-person amount large, tip total and table total small.
Handle invalid input by showing a neutral empty state, never NaN. When rounding up
causes the table to overpay, show the overpay amount instead of hiding it.
```

<div dir="rtl">

همین پرامپت به فارسی (ایجنت‌ها پرامپت فارسی را هم می‌فهمند):

```text
یک تقسیم‌کننده‌ی انعام به‌صورت یک کامپوننت React تنها (TypeScript) بساز.
ورودی‌ها: مبلغ صورت‌حساب (ورودی متنی با پیشوند $)، درصد انعام (دکمه‌های آماده: 10/15/18/20/25)،
تعداد نفرات (شمارنده با دکمه‌های − و +، حداقل 1)، و یک چک‌باکس «سهم هر نفر را تا سنت بالا گرد کن».
خروجی: سهم هر نفر بزرگ، جمع انعام و جمع کل میز کوچک.
ورودی نامعتبر را با نمایش یک حالت خالی خنثی مدیریت کن، هرگز NaN. وقتی بالا گرد کردن باعث شود
میز بیشتر بپردازد، مقدار اضافه را نشان بده به‌جای پنهان کردنش.
```

## کد منبع

همان کامپوننتی که روی سایت زنده اجرا می‌شود: [`tip-splitter.tsx`](./tip-splitter.tsx)
(React + TypeScript، بدون وابستگی، MIT).

---

⭐ به کارتان آمد؟ به [مخزن اصلی ستاره بدهید](https://github.com/dineshxr/vibecodeschool) · [دموهای بیشتر](https://vibecodeschool.com/demos)

</div>
