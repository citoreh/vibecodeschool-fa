<!-- GENERATED FILE — do not edit by hand.
     Source: lib/courses.ts in the Vibe Code School site (scripts/export-oss.mts).
     Content PRs are welcome: edits get applied to the site source and re-exported.
     Persian translation of the upstream file (CC BY-SA 4.0) — see TRANSLATION.md. -->

<div dir="rtl">

> **یادداشت ترجمه:** ترجمه‌ی فارسیِ [این گزارش ساخت](https://github.com/dineshxr/vibecodeschool/blob/main/demos/claude-md-generator/README.md).
> پرامپت‌های گفت‌وگو ترجمه شده‌اند؛ پرامپت بازسازی هم به انگلیسی (نسخه‌ی اصلی) و هم به فارسی آمده است.

# CLAUDE.md Generator (سازنده‌ی CLAUDE.md)

به شش سؤال جواب دهید، یک CLAUDE.md آماده‌ی کامیت برای مخزنتان بگیرید. پرطرفدارترین آرتیفکت دوره‌ی ۰۱، در قالب یک ابزار.

**[▶ نسخه‌ی زنده](https://vibecodeschool.com/demos/claude-md-generator)** · ابزار کاربردی · ۳ پرامپت · ساخته‌شده در حدود ۱۵ دقیقه

## گزارش ساخت

خلاصه‌شده از جلسه‌ی واقعی ساخت — همه‌ی پرامپت‌های کاربر آمده‌اند و نوبت‌های تکراری ابزارها کوتاه شده‌اند.
[نسخه‌ی زنده](https://vibecodeschool.com/demos/claude-md-generator) این را نوبت به نوبت بازپخش می‌کند.

> **شما:** یک سازنده‌ی CLAUDE.md بساز: فرم در سمت چپ (نام، توضیح، پشته‌ی فناوری، مدیر بسته، اسکریپت‌های dev/test، چک‌باکس‌های قواعد خانه، textarea دام‌ها)، خروجی مارک‌داون زنده در سمت راست با یک دکمه‌ی کپی.

**Claude:** شش قاعده‌ی خانه را به‌صورت داده تعریف می‌کنم (id، برچسب، متن قالب)، برای هر فیلد وضعیت فرم، و مارک‌داون را درون یک useMemo می‌سازم تا پنل سمت راست با هر کلید دوباره تولید شود.

`Write` ← `components/demos/claude-md-generator.tsx` — ساخته شد: ثابت RULES، فیلدهای فرم، قالب useMemo با بخش‌های Stack / Commands / House rules / Working agreement، و CopyButton روی خروجی.

> **شما:** بخش دستورها `npm dev` چاپ می‌کند — این غلط است، npm به `npm run dev` نیاز دارد. pnpm، yarn و bun بدون run مشکلی ندارند.

**Claude:** درست است — `run ` را فقط وقتی مدیر بسته npm است اضافه می‌کنم: ${pm} ${pm === "npm" ? "run " : ""}${script}. روی هر دو خط dev و test اعمال شد.

`Edit` ← `claude-md-generator.tsx · npm run fix` — خطوط دستورها حالا به مدیر بسته وابسته‌اند.

> **شما:** دام‌ها: از textarea هر خط یک بولت، خطوط خالی رد شوند، و وقتی هیچ دامی نیست کل بخش حذف شود. برای توضیح هم همین‌طور.

**Claude:** بر اساس خط جدید جدا می‌کنم، فاصله‌ها را حذف می‌کنم، مقادیر خالی را فیلتر می‌کنم، به بولت تبدیل می‌کنم — و عنوان بخش فقط وقتی فهرست خالی نیست رندر می‌شود. توضیح هم همین رفتار شرطی را می‌گیرد. فایل تولیدشده حالا هیچ بخش خالی‌ای ندارد.

## به این‌ها توجه کنید

- قالب + فرم بهتر از صفحه‌ی سفید است: این سازنده همان ساختار CLAUDE.md را پیاده می‌کند که در دوره‌ی ۰۱ آموزش داده می‌شود (پشته‌ی فناوری ← دستورها ← قواعد خانه ← دام‌ها ← توافق کاری).
- یک ظرافت واقعی که ایجنت فقط وقتی به او گفته شد گرفت: `npm` به `npm run dev` نیاز دارد در حالی که pnpm/yarn/bun `pnpm dev` را می‌پذیرند — منطق قالب، نه ظاهر، جایی است که توجه در بازبینی بازده دارد.
- خروجی زنده با useMemo یعنی سند همیشه همگام است — هیچ دکمه‌ی «تولید کن»ی نیست که فراموش شود.

## خودتان بازسازی‌اش کنید

این را در Claude Code (یا Codex، یا Cursor) بچسبانید، بعد یک نیازمندی را عوض کنید و مقایسه کنید:

</div>

```text
Build a "CLAUDE.md generator" React component (TypeScript). Left side: a form —
project name, one-line description, stack, package manager (pnpm/npm/yarn/bun),
dev and test script names, six house-rule checkboxes (small diffs, tests first,
no drive-by refactors, conventional commits, ask before migrations, match style),
and a multiline "project gotchas" field. Right side: the generated CLAUDE.md,
regenerating live via useMemo, with a copy button. npm needs "run" before script
names; the others don't — get that right.
```

<div dir="rtl">

همین پرامپت به فارسی:

```text
یک کامپوننت React با نام «سازنده‌ی CLAUDE.md» (TypeScript) بساز. سمت چپ: یک فرم —
نام پروژه، توضیح یک‌خطی، پشته‌ی فناوری، مدیر بسته (pnpm/npm/yarn/bun)،
نام اسکریپت‌های dev و test، شش چک‌باکس قواعد خانه (دیف‌های کوچک، اول تست،
بدون بازآرایی سرِ راه، conventional commits، پیش از مهاجرت بپرس، هماهنگی با سبک موجود)،
و یک فیلد چندخطی «دام‌های پروژه». سمت راست: CLAUDE.md تولیدشده که با useMemo
به‌صورت زنده دوباره تولید می‌شود، با یک دکمه‌ی کپی. npm پیش از نام اسکریپت‌ها به «run»
نیاز دارد؛ بقیه نه — این را درست انجام بده.
```

## کد منبع

همان کامپوننتی که روی سایت زنده اجرا می‌شود: [`claude-md-generator.tsx`](./claude-md-generator.tsx)
(React + TypeScript، بدون وابستگی، MIT).

---

⭐ به کارتان آمد؟ به [مخزن اصلی ستاره بدهید](https://github.com/dineshxr/vibecodeschool) · [دموهای بیشتر](https://vibecodeschool.com/demos)

</div>
