# Auto Payment SMS Relay — প্রথম Setup

এই Android app-এর কাজ শুধু incoming bKash/Nagad SMS ধরার relay হিসেবে কাজ করা।
Website/PHP এখনো লাগবে না; প্রথমে app install করে SMS permission এবং parser test করুন।

## 1) Android Studio
Android Studio-তে এই project folder open করুন।

## 2) ফোন
USB debugging চালু করে ফোন connect করুন এবং Run চাপুন।
অথবা Android Studio থেকে APK build করে নিজের ফোনে install করুন।

## 3) Permission
App খুলে SMS permission = Allow দিন।
Android-এর SMS permission sensitive/restricted; নিজের test device-এ permission না পেলে Android-এর বর্তমান permission rules অনুযায়ী manual/installer restriction থাকতে পারে।

## 4) Settings
- Website API URL: পরে আপনার PHP endpoint
- API Secret Key: পরে আপনার নিজের random secret
- Receiving number: যে bKash/Nagad account-এ টাকা আসবে
- Device ID: যেমন BKASH-NAGAD-01
- Method: BOTH

এখন website না থাকায় URL/key blank রাখলেও হবে।

## 5) Parser test
`TEST SAMPLE SMS PARSER` চাপুন। bKash sample হলে OK দেখাবে।

## 6) Real SMS test
আপনার receiving phone-এ আসা real bKash/Nagad SMS-এর sender address এবং format app-এর parser অনুযায়ী match করলে relay backend-এ পাঠাবে।

### bKash expected sender
bKash

### Nagad expected sender
NAGAD

শুধু text দেখে payment approve করা হবে না। Website side-এ আবার sender, amount, sender number, receiver account, unique TrxID এবং pending payment মিলিয়ে তারপর credit করতে হবে।

## Security
- bKash/Nagad PIN/OTP কখনো app-এ দেবেন না।
- API key শুধু নিজের website-এর custom secret; এটি bKash/Nagad API credential নয়।
- HTTPS endpoint ব্যবহার করুন।
- Duplicate TrxID server-side database unique constraint দিয়ে block করতে হবে।
- SMS sender label একা cryptographic proof নয়; server-side validation আবশ্যক।

## Next step
App install/test হয়ে গেলে website-এর ZIP + SQL দিয়ে PHP listener + database bridge তৈরি করা যাবে।