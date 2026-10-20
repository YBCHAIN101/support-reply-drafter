# support-reply-drafter

**A customizable skill that drafts clear, kind, on-brand replies to customer messages, and never invents policies or promises.**

[English](#english) | [العربية](#العربية)

---

## English

### What is it?

A skill for Claude (a `SKILL.md` file). You fill in a short **business profile** (tone, policies, hours, escalation contact), and the assistant drafts replies for a support person to review and send.

It is designed to:
- Use only facts from the profile and the customer's message.
- Mark missing information with a placeholder instead of guessing.
- Stay calm with angry customers, without arguing or over-apologizing.
- **Escalate to a human** for legal threats, safety issues, fraud, harassment, and anything the profile does not cover and could be costly.

It is a drafting aid, not a replacement for a support person. Always review replies before sending.

### How to customize

Open `SKILL.md` and replace each bracketed field in **Business profile**. Fields left in brackets are treated as "not specified". Examples:

- Tone of voice: warm and polite
- Refund policy: returns accepted within 14 days if unworn
- Things we never say: exact delivery dates, discounts

### Installation (Claude)

1. In Claude go to **Customize -> Skills -> Add -> Create a skill**.
2. Put `support-reply-drafter` in **Skill name** and the `description` line from the top of `SKILL.md` in **Description** (without the quotation marks).
3. Paste everything below the closing `---` into the instructions box, after filling in the business profile.
4. Make sure the toggle is on. Menu names may vary by plan and app version.

### Test results

See [`examples/test-scenarios.md`](examples/test-scenarios.md). Tested with Claude (Sonnet 5.5, free plan) using a fictional store.

### Limitations

- Claude decides when to use a skill, so behavior is not guaranteed in every conversation.
- The skill cannot verify orders, stock, or delivery status. A person must check facts before sending.
- Not legal, medical, or financial advice.

### License

MIT

---

## العربية

### ما هذه المهارة؟

مهارة لـ Claude (ملف `SKILL.md`) تصيغ مسودات ردود على رسائل العملاء، ليراجعها موظف الدعم ويرسلها. تملأ **ملف النشاط** (الأسلوب والسياسات والمواعيد وجهة التصعيد)، فتكتب المهارة ردودًا باسم نشاطك.

صُممت لتحقق ما يلي:
- تعتمد على ما في الملف ورسالة العميل فقط.
- تضع علامة مكان المعلومة الناقصة بدل أن تخمّن.
- تبقى هادئة مع العميل الغاضب دون جدال أو اعتذار مبالغ فيه.
- **تحيل إلى إنسان** في التهديدات القانونية والمواقف الحساسة والاحتيال والتحرش، وكل ما لا يغطيه الملف وقد يكلّف النشاط.

هي أداة مساعدة وليست بديلًا عن موظف الدعم، وراجع كل رد قبل إرساله.

### التخصيص

افتح `SKILL.md` واستبدل الحقول بين الأقواس في قسم **Business profile**. الحقول التي تبقى بين أقواس تُعامل كأنها «غير محددة».

### التثبيت (في Claude)

1. اذهب إلى **Customize ثم Skills ثم Add ثم Create a skill**.
2. ضع `support-reply-drafter` في خانة الاسم، وسطر `description` من أعلى الملف في خانة الوصف (دون علامتي الاقتباس).
3. الصق كل ما بعد `---` الثانية في خانة التعليمات بعد ملء ملف النشاط.
4. تأكد أن مفتاح التفعيل مضاء.

### الاختبارات

راجع [`examples/test-scenarios.md`](examples/test-scenarios.md)، وقد اختُبرت مع Claude على متجر وهمي.

### حدود المهارة

- Claude هو من يقرر متى يستخدمها، فلا ضمان لكل محادثة.
- لا تستطيع التحقق من الطلبات أو المخزون أو حالة الشحن، وعلى موظف التأكد من الحقائق قبل الإرسال.
- ليست استشارة قانونية أو طبية أو مالية.
