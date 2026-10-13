संस्था श्री सक्षम — अपडेटेड ऐप

मुख्य फीचर: Cashbook, जमा/खर्च, रिपोर्ट, Excel import/export, JSON backup/restore, संस्था का नाम बदलना, लोगो crop, Account tab, User ID, Logout, Account से password बदलना और Login पेज से Forgot Password।

पासवर्ड रीसेट चालू करने के लिए:
1. Supabase Dashboard → Authentication → URL Configuration खोलें।
2. Site URL में अपना GitHub Pages URL डालें।
3. Redirect URLs में ऐप का पूरा URL जोड़ें (repository path सहित)।
4. Authentication → Email में password recovery template जाँचें; reset link में {{ .ConfirmationURL }} होना चाहिए।
5. Forgot password पर login email डालें, ईमेल के Inbox/Spam में reset link खोलें, फिर नया password दो बार डालकर सेव करें।
6. Supabase का default email भेजने का सिस्टम सीमित है; नियमित उपयोग के लिए SMTP सेट करें।

GitHub पर ZIP की सभी फाइलें upload/replace करें, लेकिन अगर आपके config.js में असली Supabase URL और public anon/publishable key है तो उसे ZIP वाले placeholder से replace न करें। service_role/secret key कभी browser में न रखें।

ध्यान दें: अलग-अलग Login accounts का डेटा अपने-आप share नहीं होता। मौजूदा role dropdown secure team permissions नहीं है। डेटा बदलने से पहले backup रखें।

नए बदलाव (v6):
- Backup/Restore और Excel import controls अब Account tab में हैं।
- Reports में अवधि के अनुसार कुल जमा, कुल खर्च, शुद्ध अंतर, शुरुआती/अवधि-अंत बैलेंस और पूरी transaction list दिखती है।
- CSV export में summary + पूरी transaction list शामिल है।
- Excel export में Summary और Transactions नाम की दो sheets बनती हैं।
- PDF बटन प्रिंट-फ्रेंडली रिपोर्ट खोलता है; इसमें संस्था का नाम, लोगो, totals और सभी transactions आते हैं। प्रिंट dialog में Save as PDF चुनें।
- Service worker cache version बढ़ाया गया है ताकि नई UI अपडेट हो सके।
