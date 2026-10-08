# NayaDaur — Article Website

Yeh ek clean static article website hai. Aap articles browser ke `editor.html` page se likh sakte hain.

## Publish karne ka tareeqa

1. `index.html`, `article.html`, `editor.html`, `styles.css`, `app.js`, aur `articles.js` ko ek folder mein rakhein.
2. `editor.html` kholen aur article save karein.
3. **Export articles.js** par click karein.
4. Download hui `articles.js` ko purani file se replace karein.
5. Puri folder ko Netlify, GitHub Pages, Vercel, ya apni hosting par upload karein.

## Adsterra code

Site ke `index.html` aur `article.html` mein ad limits ka variable add hai: `window.AD_LIMITS = { popunderPerMinute: 1, socialBarPerPage: 1, nativeBannerPerPage: 1, smartlinkPerPage: 1 }`. Aapka supplied Adsterra popunder, Social Bar, Native Banner aur Smartlink snippets add kiye gaye hain. Popunder sitewide localStorage window 60 seconds ke saath dynamically load hota hai, is liye ek visitor ko ek minute mein maximum ek load attempt diya jata hai.

Ad delivery provider approval, domain configuration aur browser settings par depend karti hai. Ads ko navigation, buttons, ya misleading elements ke bilkul paas na rakhein. Apne ads par click na karein aur users ko click karne ke liye encourage na karein.

Note: yeh client-side frequency cap hai; Adsterra ka apna server-side control hamesha final authority hota hai.

## Important limitation

Yeh static version articles ko browser mein draft ke taur par save karta hai. Agar aap chahte hain ke aap online dashboard se article add karein aur woh foran sab visitors ko dikhe, to backend/CMS (jaise WordPress, Decap CMS, ya Supabase) connect karna hoga.

## Current ad units

Updated codes are installed on `index.html` and `article.html`:

- Popunder: `https://benchform.org/1/a96549f2147eb3a151d49fdfa4326b71` — retains the existing sitewide client-side 60-second load-attempt cap.
- Social Bar: `https://biomanos.org/14/316447944293e2e5af796bc295f8d658` — one script per page.
- Native Banner: `https://biomanos.org/21/99ea61c422ef230f3656298af82cf35f` — one script and matching container per page.
- Smartlink: `https://apiguinee.org/4/9198abbfbbc9e9f41cc303a44aa2a6c8` — labelled sponsored link, opened only when clicked.

Old ad codes and the extra native placement were removed. The numeric AD_LIMITS values describe the intended limits; the native/social/smartlink counts are enforced by having one placement in each document, not by that configuration object. Third-party script behaviour and impressions are controlled by the provider.

There are now ten distinct units: the four above and the six display banners listed below. Each display banner appears once on the homepage and once on the article page. Live delivery has not been verified.

## Display banners

| Key | Width × Height |
| --- | --- |
| `293afc4154d565804240e91f8a47b09a` | 468 × 60 |
| `e72a035aef32a76f93b37fac75149b18` | 300 × 250 |
| `f858f45baa56734e2f58735c076018d7` | 160 × 300 |
| `d5afb054aa16ddf8b3e94510fc32f72d` | 160 × 600 |
| `9aef7a0b56ee0c3ce13a57aac0378a0f` | 320 × 50 |
| `201b4c3b307a80b843db93e5d2377ab5` | 728 × 90 |

Each banner keeps the provider-supplied options and a synchronous external script immediately after its options block. Do not add async/defer to these scripts: they share the provider’s global `atOptions`. Wide banners use a local horizontal scroll area on narrow screens; creatives are not resized or clipped. Advertisements are labelled and separated from navigation and action buttons.
