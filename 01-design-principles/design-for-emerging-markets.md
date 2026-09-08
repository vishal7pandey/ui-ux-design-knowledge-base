# Design for Emerging Markets

Designing for emerging markets means building products for users with different devices, networks, incomes, and contexts. It requires restraint, flexibility, and deep respect for local reality.

---

## 1. Key Considerations

### Devices

- Many users have low-end or older smartphones.
- Small screens and limited memory are common.
- Android is dominant in many markets.
- Tablets and desktops may be rare.

### Networks

- Mobile data can be expensive and unreliable.
- Many users are on 2G or 3G networks.
- Connectivity may come and go throughout the day.
- Wi-Fi is not always available.

### Literacy and language

- Multiple languages, dialects, and scripts.
- Lower literacy levels in some user groups.
- Voice and video may be more natural than text.
- Localized content is critical.

### Digital experience

- Users may be less familiar with Western design patterns.
- Common assumptions about navigation and icons may not hold.
- On-device help and guidance are important.

### Trust and payment

- Cash-on-delivery, mobile money, and local wallets are common.
- Trust and social proof matter more.
- Users may be cautious about sharing data.

---

## 2. Design Principles

### Lightweight

- Keep app size small.
- Reduce data usage.
- Optimize images, fonts, and videos.
- Lazy load and cache aggressively.

### Resilient

- Work offline or on poor networks.
- Retry gracefully.
- Show progress and status.
- Preserve user work.

### Local

- Support local languages and scripts.
- Adapt to local formats, dates, and currencies.
- Use culturally relevant imagery and examples.
- Partner with local teams and researchers.

### Accessible

- Large, clear touch targets.
- Simple language and visuals.
- Voice and audio support where possible.
- High contrast and readable type.

### Trustworthy

- Be transparent about data and costs.
- Show security and verification.
- Use familiar payment and social proof.

---

## 3. Patterns for Emerging Markets

### Data saving mode

- Let users opt into low-data mode.
- Reduce image quality, disable auto-play, and limit background sync.

### Offline-first

- Cache key content.
- Queue actions for later.
- Make the app useful without constant connection.

### Progressive onboarding

- Use visuals, not just text.
- Show value quickly.
- Avoid long sign-up flows.

### Phone number as identity

- Use phone numbers for login and verification.
- SMS OTP is common.
- Avoid email if it is not the local norm.

### Local payment options

- Support mobile money, cash-on-delivery, and local wallets.
- Be clear about fees and timing.

### Help and support

- In-app help in local languages.
- Easy access to human support.
- Community or peer support options.

---

## 4. Testing

- Test on the actual devices users have.
- Test on slow and intermittent networks.
- Conduct research in local languages.
- Include users with low digital literacy.
- Test payment and verification locally.

---

## 5. Common Mistakes

- Assuming the same devices and networks as developed markets.
- Large app sizes and heavy media.
- Ignoring offline use.
- Not localizing beyond language.
- Using icons and patterns that are not locally understood.
- Requiring email or credit cards.
- Overlooking trust and cost concerns.

---

## 6. Checklist

- [ ] App is tested on low-end, common devices.
- [ ] App size and data usage are minimized.
- [ ] Offline and poor-network modes are supported.
- [ ] Local languages, scripts, and formats are supported.
- [ ] Payments match local preferences.
- [ ] Onboarding is simple and visual.
- [ ] Touch targets are large and clear.
- [ ] Voice and audio options are considered.
- [ ] Trust, security, and cost are clearly communicated.
- [ ] Research and testing are done in the target market.
