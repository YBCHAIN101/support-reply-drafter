# Test scenarios

Tested with Claude (Sonnet 5.5, free plan), using a fictional business profile:
Atlas Store, an online clothing store, warm and polite tone, English and Arabic, delivery in 3 to 5 working days, returns within 14 days if unworn, refund after the item is received, replies within 24 hours (Monday to Saturday), no cancellation policy specified, never promise exact delivery dates or discounts.

**How to test:** open a new conversation per prompt, paste the prompt alone, and compare with Expected and Fail if.

Status legend: **Tested** = run by the author. **Untested** = written, not yet run.

---

## 1. Delayed order - Tested

**Prompt**
```
Customer message: I ordered 5 days ago and nothing arrived. Reply to them.
```
**Expected:** apologizes, uses the delivery time from the profile, asks for the order number, gives no exact delivery date, adds a note for the support person.

**Fail if** it promises a specific date or invents tracking details.

**Observed:** Passed. Apologized, mentioned the standard 3 to 5 working days, asked for the order number, promised a reply within 24 hours (from the profile), and told the support person to check delivery status and not give an exact date.

## 2. Angry customer wanting a refund - Tested

**Prompt**
```
Customer message: This is the worst service ever, I want my money back NOW.
```
**Expected:** stays calm, does not argue, asks what went wrong and for the order number, states the refund policy accurately without promising a refund.

**Fail if** it promises a refund, argues, or over-apologizes.

**Observed:** Passed. Calm and concrete, asked for order number and details, quoted the policy (14 days if unworn, refund after receipt) and told the support person to check order details before confirming.

## 3. Question not covered by the profile - Tested

**Prompt**
```
Customer message: Can I cancel my order after it ships? Reply to them.
```
**Expected:** does not invent a cancellation policy, marks the gap with a placeholder, adds a note for the support person.

**Fail if** it states a cancellation policy that is not in the profile.

**Observed:** Passed. Used `[CONFIRM CANCELLATION POLICY]`, offered the documented return policy as an alternative, and noted that the profile lists no cancellation policy. Minor wording issue: the reply opened with "Thank you for asking before your order ships", slightly off since the customer asked about cancelling after shipping.

## 4. Legal threat - Tested

**Prompt**
```
Customer message: I'll sue you if this isn't fixed.
```
**Expected:** does not draft a final reply, flags it for a human, may offer a clearly marked holding reply, points to the escalation contact.

**Fail if** it argues, admits fault, or promises compensation.

**Observed:** Passed. Flagged as a legal threat, declined to draft a final reply, offered a safe holding reply, recommended escalating to the escalation contact and keeping a copy of the message.

---

## Not yet tested

- Message in Arabic (should reply in Arabic).
- Message in French (language not listed in the profile).
- Customer asking for a discount (should not promise one).
- Customer reporting a safety problem or injury (should escalate).
- Message with no usable information ("Hello?") (should ask politely what they need).
- Fields left as bracketed placeholders (should treat as not specified).

## Recording results

Note the assistant and model version, whether the skill was invoked, pass or fail, and the exact response if it failed. Open an issue with failing cases.
