# FX Analyses — Dual AI GitHub Pages Build

এটি আপনার আগের ZIP-এর upgraded static frontend build।

## নতুন সিস্টেম
- App/website নাম: **FX Analyses**
- OpenAI + Gemini দুই AI একই market snapshot বিশ্লেষণ করে।
- দুই AI একই direction (UP/DOWN) দিলে final signal দেখায়; ভিন্ন হলে **WAIT**।
- Analysis panel-এ trend, EMA/SMA, RSI, MACD, support/resistance, volatility, candle body/wick, Doji/Hammer/Engulfing, breakout/pullback, HH/LL, multi-timeframe context ইত্যাদি check-list।
- 4–5 সেকেন্ডের মধ্যে UI analysis animation ও final result।
- বাংলা browser voice output।
- সম্ভাব্য profit এবং loss **estimate** দেখায়; guarantee নয়।
- Login ছাড়া SIGNAL ACTIVE চাপলে login popup।
- নিচে floating Login/Logout button।
- Admin key: **1028**।
- Admin generated keys: 10m, 15m, 20m, 1h, 2h, 3h, 5h, 12h, 24h, 1 month।
- Generated key expiry হলে auto logout।
- Admin generated key delete এবং logout control।
- PWA manifest/service worker included।
- আপনার দেওয়া logo URL ব্যবহার করার চেষ্টা করা হয়েছে; URLটি সরাসরি image file না হলে `icon.svg` fallback থাকবে।

## OpenAI + Gemini keys
`app-config.js` খুলে:
```js
OPENAI_API_KEY:"...",
GEMINI_API_KEY:"..."
```
দুটো বসান।

**Security:** GitHub Pages-এর JavaScript-এ API key রাখলে key visitor-এর browser-এ দেখা যায়। Public/real-money deployment-এর জন্য backend/serverless proxy ব্যবহার করুন।

## Quotex current candle
এই ZIP-এর chart এখন local candle simulation/analysis UI ব্যবহার করে। Quotex-এর private OTC live candle browser থেকে সরাসরি/নির্ভরযোগ্যভাবে পড়ার জন্য অনুমোদিত live-data feed/backend দরকার। তাই কোনো fake feed-কে Quotex live data হিসেবে দেখানো হয়নি। আপনার কাছে lawful data provider/API থাকলে `app.js`-এর data adapter অংশে সেটি যুক্ত করা যাবে।

## Device count limitation
শুধু GitHub Pages + localStorage দিয়ে সত্যিকারের cross-device live device count, remote logout, shared admin key database নিরাপদভাবে করা যায় না। এই build local browser storage-এ key/session management করে। Production version-এ Supabase/Firebase বা নিজস্ব backend লাগবে, তখন admin থেকে অন্য ফোনের session সত্যিকারে logout এবং live device count করা সম্ভব।

## GitHub Pages
ZIP extract করে সব file repository root-এ upload করুন। GitHub → Settings → Pages → Deploy from branch → `main` → root নির্বাচন করুন।
