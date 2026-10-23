# Super Mobile Shop – GitHub-এ আপলোডের জন্য প্রস্তুত

**এই ফোল্ডারের সব ফাইল** (কোনো ফোল্ডার বানাতে হবে না) GitHub রিপোজিটরিতে আপলোড করুন।
Netlify নিজে থেকে `public` ফোল্ডার ও সার্ভার-ফাংশনের ফোল্ডার বানিয়ে নেবে (`build.sh` সেটা করে)।

## ফাইলগুলো
| ফাইল | কাজ |
|---|---|
| index.html, app.js, style.css | ওয়েবসাইট |
| api.mjs | সার্ভার-কোড (লগইন, সংরক্ষণ, ছবি আপলোড) |
| netlify.toml | Netlify সেটিংস ও নিরাপত্তা হেডার |
| build.sh | `public` ফোল্ডার নিজে বানায় |
| package.json | প্রয়োজনীয় প্যাকেজের তালিকা |

## আপলোডের পর Netlify-তে
1. Netlify → রিপোজিটরি জুড়ুন (Build command ও Publish directory ফাঁকা বা যা-ই থাক, `netlify.toml` সেটা ঠিক করে নেবে)।
2. **Site configuration → Environment variables**-এ `ADMIN_PASSWORD` ও `SESSION_SECRET` বসান (Scopes-এ `Functions` টিক)। মান বানাতে আলাদা `generate-secrets.html` ফাইলটি ব্রাউজারে খুলুন।
3. **Deploys → Trigger deploy**।
4. `আপনার-সাইট/api/health` খুলে দুটোই `true` দেখুন।
5. সাইটে উপরে বাঁয়ে দোকানের নামে ৫ বার দ্রুত ট্যাপ করে লগইন করুন।

## সমস্যা হলে
Deploy log-এ "ঠিক আছে: public ফোল্ডার ও ফাংশন তৈরি হয়েছে" লেখা দেখা উচিত। "ত্রুটি: … পাওয়া যায়নি" এলে বোঝা যাবে কোন ফাইল আপলোড হয়নি।
