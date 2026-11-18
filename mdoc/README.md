# mdoc card templates

SVG card designs for mdoc credentials, served by GitHub Pages from
`https://inji.github.io/inji-config/mdoc/`.

Which docType uses which file is configured per environment in inji-config's
`inji-default.properties`, and reaches Inji Wallet through Mimoto's `allProperties`:

```properties
mosip.inji.mdocTemplateBaseUrl=https://inji.github.io/inji-config/mdoc/
mosip.inji.mdocTemplates={"org.iso.18013.5.1.mDL":"org.iso.18013.5.1.mDL.svg", ...}
```

| File | Used for |
|---|---|
| `org.iso.18013.5.1.mDL.svg` | Driving licence |
| `org.iso.23220.photoID.1.svg` | Identity card; also used for `org.iso.23220.photoid.1` and the EU PID (`eu.europa.ec.eudi.pid.1`) |
| `eu.europa.ec.eudi.hiid.1.svg` | Health insurance card |
| `org.iso.7367.1.mVRC.svg` | Vehicle registration |

Each file is named after the docType it was designed for.

Templates read credential data through placeholders: `{{/claims/<namespace>/<element>}}`,
`{{/portraits/<namespace>}}`, `{{/signatures/<namespace>}}` (the holder's signature image), and `{{/qrCodeImage}}` in an `<image id="qrCodeImage">` slot.
The wallet fills claim names that issuers spell differently (for example `family_name` and
`family_name_unicode`); an element an issuer does not send renders as `-`.

Rules for templates, so the wallet can render them safely:

- one file per docType, named `<docType>.svg`, each under 512 KiB;
- no scripts, `foreignObject`, `style`, event handlers or DOCTYPE;
- no external references: images only as placeholders or embedded PNG/JPEG data.

GitHub Pages caches files for 10 minutes, so a change can take that long to reach wallets.
Use new file names for changes that need different claims. A breaking change to the
placeholder format needs a new folder, so wallets already installed keep these files.
