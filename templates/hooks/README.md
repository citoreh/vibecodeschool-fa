<div dir="rtl">

> **یادداشت ترجمه:** ترجمه‌ی فارسیِ [این README](https://github.com/dineshxr/vibecodeschool/blob/main/templates/hooks/README.md).
> بلوک‌های JSON دست نخورده‌اند و می‌توانید مستقیم کپی‌شان کنید.

# دستورالعمل‌های هوک

هوک‌ها در نقطه‌های مشخصی از چرخه‌ی عمر یک جلسه‌ی Claude Code دستورهای شل اجرا می‌کنند — محافظ‌هایی
قطعی که به این بستگی ندارند که مدل قاعده‌های شما را به یاد داشته باشد. آن‌ها را در `.claude/settings.json`
پیکربندی کنید. مستندات: [code.claude.com/docs → hooks](https://code.claude.com/docs/en/hooks-guide).

سه دستورالعمل که نیاز بیشتر تیم‌ها را پوشش می‌دهند:

## ۱. قالب‌بندی خودکار هر فایلی که ایجنت ویرایش می‌کند

`PostToolUse` روی Edit/Write — ایجنت هرگز کد قالب‌بندی‌نشده تحویل نمی‌دهد، و شما هرگز نویز قالب‌بندی را در
دیف‌ها نمی‌بینید:

</div>

```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Edit|Write",
        "hooks": [
          {
            "type": "command",
            "command": "jq -r '.tool_input.file_path' | { read f; [[ \"$f\" == *.ts || \"$f\" == *.tsx ]] && npx prettier --write \"$f\" > /dev/null 2>&1; true; }"
          }
        ]
      }
    ]
  }
}
```

<div dir="rtl">

## ۲. محافظت از فایل‌هایی که ایجنت هرگز نباید به آن‌ها دست بزند

یک `PreToolUse` که ویرایش مسیرهای محافظت‌شده را مسدود می‌کند (کد خروج 2 = مسدود، و stderr به‌عنوان
بازخورد به ایجنت نشان داده می‌شود):

</div>

```json
{
  "hooks": {
    "PreToolUse": [
      {
        "matcher": "Edit|Write",
        "hooks": [
          {
            "type": "command",
            "command": "jq -r '.tool_input.file_path' | { read f; case \"$f\" in *generated*|*.lock|*/migrations/*) echo \"BLOCKED: $f is protected — edit the source/codegen instead\" >&2; exit 2;; esac; }"
          }
        ]
      }
    ]
  }
}
```

<div dir="rtl">

## ۳. نمایش نتیجه‌ی تست‌ها پس از هر تغییر منطقی

یک `PostToolUse` که تست‌های سریع بسته‌ی مربوط را اجرا می‌کند و شکست‌ها را مستقیم به چرخه برمی‌گرداند
(ایجنت stderr را می‌بیند و بدون این‌که از او خواسته شود رفعش می‌کند):

</div>

```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Edit",
        "hooks": [
          {
            "type": "command",
            "command": "jq -r '.tool_input.file_path' | { read f; [[ \"$f\" == src/* ]] && pnpm vitest related \"$f\" --run --reporter=dot 2>&1 | tail -5; true; }"
          }
        ]
      }
    ]
  }
}
```

<div dir="rtl">

**قاعده‌های سرانگشتی:** هوک‌ها باید سریع باشند (روی هر فراخوانی ابزار منطبق به‌صورت هم‌زمان اجرا می‌شوند)،
با صدای بلند شکست بخورند (`exit 2` همراه با stderr از رد شدن بی‌صدا بهتر است)، و فقط چیزهایی را اجبار کنند
که در CI هم اجبار می‌کنید. [درس هوک‌ها](https://vibecodeschool.com/courses/claude-code-vibe-coding)
در دوره‌ی ۰۱ کل چرخه‌ی عمر را پوشش می‌دهد.

</div>
