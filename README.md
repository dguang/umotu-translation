# Umotu App Translations

Community translations for the [Umotu](https://umotu.org) mobile wallet app.

We use AI for initial translations, but rely on **native speakers** to make strings natural and accurate. Your contributions help make Umotu accessible to users worldwide.

## Supported Languages

| Code | Language | Native Name |
|------|----------|-------------|
| en | English | English |
| es | Spanish | Español |
| pt | Portuguese | Português |
| fr | French | Français |
| de | German | Deutsch |
| ar | Arabic | العربية |
| hi | Hindi | हिन्दी |
| bn | Bengali | বাংলা |
| id | Indonesian | Bahasa Indonesia |
| sw | Swahili | Kiswahili |
| zh | Chinese | 中文 |
| jp | Japanese | 日本語 |
| kr | Korean | 한국어 |
| ru | Russian | Русский |
| vn | Vietnamese | Tiếng Việt |
| tr | Turkish | Türkçe |
| th | Thai | ไทย |
| fa | Persian | فارسی |
| ms | Malay | Bahasa Melayu |
| my | Burmese | မြန်မာ |
| km | Khmer | ភាសាខ្មែរ |
| ne | Nepali | नेपाली |
| cz | Czech | Čeština |
| po | Polish | Polski |
| ro | Romanian | Română |
| uz | Uzbek | Oʻzbekcha |
| ur | Urdu | اردو |
| tl | Filipino | Tagalog |
| it | Italian | Italiano |
| uk | Ukrainian | Українська |
| ha | Hausa | Hausa |
| am | Amharic | አማርኛ |

## File Structure

```
locales/
├── en/
│   └── common.json    # Source of truth (English)
├── es/
│   └── common.json    # Spanish translations
├── zh/
│   └── common.json    # Chinese translations
└── .../
```

Each language has its own folder with a `common.json` file containing all translations.

## How to Contribute

### Improving Existing Translations

1. **Fork this repository**
2. **Find your language folder** (e.g., `locales/es/` for Spanish)
3. **Edit `common.json`** - Fix any awkward, incorrect, or unnatural translations
4. **Submit a Pull Request** with a clear description of what you changed

### Adding a New Language

1. **Fork this repository**
2. **Copy the English folder**: `cp -r locales/en locales/XX` (replace XX with language code)
3. **Translate all strings** in `locales/XX/common.json`
4. **Submit a Pull Request** - Include the language name and code in your PR description
5. We'll add the language to the app in the next release

## Translation Guidelines

### Rules

- **Keep JSON keys identical** - Only translate the values, never the keys
- **Preserve placeholders** - Keep `{{variable}}` exactly as-is (e.g., `{{amount}}`, `{{date}}`, `{{count}}`)
- **Use sentence case** - Capitalize only the first word and proper nouns
- **Avoid slang/jargon** - Use clear, professional language
- **Match the tone** - Keep translations friendly but professional, matching the English style

### Example

```json
{
  "send": {
    "amount": "Amount",
    "sendingTo": "Sending to {{count}} recipient",
    "confirmTitle": "Confirm Transaction"
  }
}
```

For Spanish:
```json
{
  "send": {
    "amount": "Cantidad",
    "sendingTo": "Enviando a {{count}} destinatario",
    "confirmTitle": "Confirmar Transacción"
  }
}
```

### Pluralization

Some strings have plural forms using `_plural` suffix:

```json
{
  "sendingTo": "Sending to {{count}} recipient",
  "sendingTo_plural": "Sending to {{count}} recipients"
}
```

Translate both forms appropriately for your language.

### RTL Languages (Arabic, Persian, Urdu, Hebrew)

- Translations work the same way
- The app automatically handles right-to-left layout
- Test that UI elements display correctly if possible

## Preferred Terminology

Please use these specific terms consistently:

| English Term | Description |
|--------------|-------------|
| Recovery phrase | NOT "seed words" or "mnemonic" |
| Private key | The cryptographic key |
| Data Availability (DA) | The DA layer check |
| Sentinel | Network validator role |
| Emission Controller | The token emission system |
| Launch Allocation | Initial token distribution |

## Testing Your Translations

1. Switch language in the app: **Settings → Language**
2. Check for:
   - Text truncation (strings too long)
   - Layout issues
   - Placeholder rendering (`{{count}}` should show numbers)
   - Natural reading flow

## Questions?

- Open an [Issue](https://github.com/dguang/umotu-translation/issues) for questions
- Join our community channels for discussion

Thank you for helping make Umotu accessible to everyone!
