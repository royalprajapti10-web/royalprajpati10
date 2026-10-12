संस्था श्री सक्षम — अपडेटेड फाइलें

इस अपडेट में:
1. Account टैब: Login email, Supabase User ID, login status, User ID copy और Logout.
2. संस्था का नाम बदलने का फॉर्म.
3. Logo crop: image चुनने के बाद zoom, horizontal और vertical crop adjust करके Apply Logo.
4. Service worker cache v4, ताकि पुरानी app file अटकने की समस्या कम हो.
5. बाकी cashbook, report, backup और Excel import features बनाए रखे हैं.

GitHub Pages पर अपडेट करने के चरण:
1. पहले मौजूदा app का JSON backup डाउनलोड करें (Home > Backup & data > Download backup).
2. ZIP extract करें और सभी updated files upload करें, लेकिन config.js को बिना जांचे overwrite न करें.
3. अपने GitHub repository के मौजूदा config.js में जो Supabase URL और public anon key पहले से सही हैं, उन्हें जस का तस रखें.
4. Supabase Dashboard > SQL Editor में supabase_setup.sql चलाएँ, अगर पहले नहीं चलाया है.
5. GitHub Pages URL Chrome में खोलें और internet के साथ refresh करें. फिर installed app बंद करके दोबारा खोलें.

महत्वपूर्ण सुरक्षा सीमा:
- इस update में Account tab, rename और adjustable logo crop शामिल हैं.
- चार अलग लोगों को अलग-अलग permission देना (owner/admin, viewer आदि) अभी पूरा secure team-sharing feature नहीं है. सिर्फ local role dropdown सुरक्षा नहीं देता. इसे चालू करने के लिए database membership tables/RLS और app में per-institution sharing integration अलग से लागू करना होगा.
- किसी को अपना Supabase service_role key कभी न दें. config.js में केवल project URL और public anon/publishable key ही हो.
- User ID कोई password नहीं है; password अलग और निजी रखें.
- अपना मौजूदा config.js बचाकर रखें. इस ZIP में config.js template placeholders के साथ है.
