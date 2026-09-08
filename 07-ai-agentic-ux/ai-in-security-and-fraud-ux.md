# AI in Security and Fraud UX

AI helps detect and prevent fraud, but it can also block legitimate users. Security UX must protect users without creating friction or false positives.

---

## 1. Key Principles

### Security without friction

- Strong security should not make the product unusable.
- Step up authentication only when risk is high.

### Transparency

- Tell users why a login or transaction was blocked.
- Explain the risk without alarming.

### Control

- Give users a path to resolve false positives.
- Let them confirm or appeal decisions.

### Privacy

- Do not collect more data than needed.
- Be clear about what is monitored and why.

### Balance

- Catch fraud while keeping legitimate users happy.
- Monitor false positive rates.

---

## 2. Common Use Cases

- Login anomaly detection.
- Transaction fraud detection.
- Account takeover prevention.
- Bot detection.
- Identity verification.
- Payment authentication.
- Suspicious activity alerts.

---

## 3. UX Patterns

### Risk-based authentication

- Low risk: normal login.
- Medium risk: second factor.
- High risk: additional verification or lockout.

### Friction step-up

- Ask for extra verification only when needed.
- Explain why: “We noticed an unusual login.”

### Fraud alerts

- Notify the user of suspicious activity.
- Provide clear actions: approve, block, report.
- Use calm, not alarmist, language.

### Identity verification

- Guide the user through document or biometric checks.
- Show progress and what to expect.
- Protect the data.

### Account recovery

- Verify identity securely.
- Provide multiple recovery methods.
- Prevent social engineering.

### Review and appeal

- Let users dispute a security decision.
- Provide a clear timeline.
- Communicate the outcome.

---

## 4. Best Practices

- Use multiple signals, not just one.
- Keep the user informed at every step.
- Minimize false positives.
- Make escalation paths clear.
- Do not blame the user.
- Protect data used for security checks.
- Support accessible verification methods.
- Test with diverse users and devices.
- Monitor and adjust risk models.

---

## 5. Messaging

- “We noticed a new device. Please verify it’s you.”
- “This transaction looks unusual. Confirm or cancel.”
- “Your account was accessed from a new location. Was this you?”
- “We’re reviewing your request for security. We’ll update you soon.”

---

## 6. Common Mistakes

- False positives with no way to appeal.
- Too much friction for low-risk actions.
- Alarmist or vague messages.
- Blaming users for fraud.
- No explanation of why a transaction was blocked.
- Inaccessible verification methods.
- Collecting unnecessary data.
- Not monitoring false positive rates.

---

## 7. Checklist

- [ ] Security is proportional to risk.
- [ ] Users understand why they are being challenged.
- [ ] Verification methods are accessible.
- [ ] False positives can be appealed.
- [ ] Fraud alerts are clear and actionable.
- [ ] Account recovery is secure and usable.
- [ ] Data collection is minimized and transparent.
- [ ] Users are not blamed for security decisions.
- [ ] Risk models are monitored and adjusted.
- [ ] Security UX is tested with diverse users.
