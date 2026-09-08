# Internationalization and Localization

Internationalization (i18n) is building a product so it can support multiple languages and regions. Localization (l10n) is adapting it for a specific market. Both require planning from the start.

---

## 1. Key Terms

| Term | Meaning |
|------|---------|
| **i18n** | Preparing the product for any language or region. |
| **l10n** | Adapting the product for a specific locale. |
| **Locale** | A language and region pair (e.g., `en-US`, `de-DE`). |
| **RTL** | Right-to-left languages like Arabic and Hebrew. |
| **Transliteration** | Converting text from one script to another. |

---

## 2. Internationalization Principles

### Separate content from code

- Keep strings in resource files, not inline.
- Use keys for UI strings, not hard-coded text.
- Avoid concatenating strings; use placeholders and pluralization rules.

### Use Unicode and UTF-8

- Support all scripts: Latin, Cyrillic, CJK, Arabic, emoji.
- Use UTF-8 encoding everywhere.

### Design for text expansion

- German and Finnish can be 30% longer than English.
- Japanese and Chinese can be more compact.
- Allow labels to wrap or truncate gracefully.

### Support plurals and grammar

Different languages have different plural rules. Use a library that supports:

- One / few / many / other.
- Gender and case agreement where needed.

### Dates, numbers, currencies

- Format based on locale.
- Use CLDR or a localization library.
- Do not assume MM/DD/YYYY or comma/decimal separators.

---

## 3. Localization Beyond Translation

### Cultural adaptation

- Tone and formality vary by culture.
- Imagery and examples should be relevant.
- Color and symbolism may have different meanings.
- Payment, shipping, and tax norms differ.
- Legal and privacy requirements vary by region.

### RTL design

- Flip layouts for right-to-left languages.
- Mirror icons and navigation where appropriate.
- Keep some elements (e.g., playback controls, numbers) in their original direction.
- Test with native RTL speakers.

### Local formats

- Names: first/last order, multiple names, patronymics.
- Addresses: postal code, state, province, region vary.
- Phone numbers: formatting and validation.
- Currency and taxes.
- Units of measurement.

---

## 4. Technical Best Practices

### Use a localization library

- Use libraries like i18next, FormatJS, or ICU for formatting.
- Centralize locale data.
- Lazy-load translations to reduce bundle size.

### Pseudo-localization

Test layouts with longer, accented, or mirrored placeholder text before translation begins. This exposes layout and truncation issues early.

### Locale detection

- Detect from browser or system.
- Allow users to override.
- Save the preference.
- Use the locale in URL or domain if SEO matters.

### Testing

- Test every supported locale.
- Test with native speakers, not just translators.
- Test RTL layouts, date formats, and number formats.
- Check for untranslated strings and layout breaks.

---

## 5. Common Mistakes

- Hard-coding strings in code.
- Assuming text length and layout fit all languages.
- Concatenating strings with variables.
- Ignoring plural rules.
- Forgetting RTL.
- Using machine translation without review.
- Not testing in real locales.
- Not updating translations when the product changes.
- Translating without cultural context.

---

## 6. Checklist

- [ ] Strings are externalized from code.
- [ ] Pluralization and grammar rules are handled.
- [ ] Text expansion is designed for.
- [ ] Dates, numbers, and currencies are locale-formatted.
- [ ] RTL layouts are supported and tested.
- [ ] Locale detection and user override work.
- [ ] Images and examples are culturally appropriate.
- [ ] Pseudo-localization is used during development.
- [ ] Native speakers review translations.
- [ ] All supported locales are tested.
