# ফোন দিয়ে APK বানানোর সবচেয়ে সহজ উপায়

এই project-এ GitHub Actions workflow দেওয়া আছে। PC/USB ছাড়াই GitHub-এর server-এ build করানো যাবে।

1. GitHub account খুলুন/login করুন।
2. New repository তৈরি করুন, যেমন `AutoPaymentSmsRelay`.
3. এই ZIP extract করে সব file repository-তে upload করুন।
4. GitHub repository → Actions → `Build APK` → `Run workflow`.
5. Build শেষ হলে Actions run খুলুন।
6. `Artifacts` থেকে `AutoPaymentSmsRelay-debug` download করুন।
7. ZIP extract করে `app-debug.apk` ফোনে install করুন।
8. Android চাইলে "Install unknown apps" permission দিন।

নোট: GitHub Actions build করার জন্য repository public বা আপনার GitHub plan-এ private repository Actions ব্যবহারযোগ্য হতে হবে।
