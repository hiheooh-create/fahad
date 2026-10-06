# NayaDaur — Article Website

Yeh ek clean static article website hai. Aap articles browser ke `editor.html` page se likh sakte hain.

## Publish karne ka tareeqa

1. `index.html`, `article.html`, `editor.html`, `styles.css`, `app.js`, aur `articles.js` ko ek folder mein rakhein.
2. `editor.html` kholen aur article save karein.
3. **Export articles.js** par click karein.
4. Download hui `articles.js` ko purani file se replace karein.
5. Puri folder ko Netlify, GitHub Pages, Vercel, ya apni hosting par upload karein.

## Adsterra code

Site ke `index.html` aur `article.html` mein ad limits ka variable add hai: `window.AD_LIMITS = { popunderPerMinute: 1, socialBarPerPage: 1, nativeBannerPerPage: 1, smartlinkPerPage: 1 }`. Aapka supplied Adsterra popunder code sitewide localStorage window 60 seconds ke saath dynamically load hota hai, is liye ek visitor ko ek minute mein maximum ek load attempt diya jata hai.

Abhi site mein policy-safe placeholder display-ad slots bhi hain. Adsterra se approved code milne ke baad us code ko sirf relevant `.ad-placeholder` blocks mein add karein. Ads ko navigation, buttons, ya misleading elements ke bilkul paas na rakhein. Apne ads par click na karein aur users ko click karne ke liye encourage na karein.

Note: yeh client-side frequency cap hai; Adsterra ka apna server-side control hamesha final authority hota hai.

## Important limitation

Yeh static version articles ko browser mein draft ke taur par save karta hai. Agar aap chahte hain ke aap online dashboard se article add karein aur woh foran sab visitors ko dikhe, to backend/CMS (jaise WordPress, Decap CMS, ya Supabase) connect karna hoga.
