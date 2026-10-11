संस्था श्री सक्षम — Login और दूसरे मोबाइल पर एक ही डेटा

ज़रूरी बात: सिर्फ GitHub पर ZIP upload करने से app update नहीं होती। ZIP को Extract करके उसके अंदर की files repository के ROOT में upload/replace करनी हैं।

फाइलें root में ऐसी दिखनी चाहिए:
index.html
config.js
manifest.webmanifest
sw.js
icon.svg
icon-192.png
icon-512.png
logo-round.png
supabase_setup.sql

CLOUD LOGIN चालू करने के लिए Supabase setup अनिवार्य है:
1) https://supabase.com पर account बनाएं और New project बनाएं।
2) Project Settings > API से Project URL और anon/public key copy करें। service_role key कभी इस्तेमाल न करें।
3) GitHub repository में config.js खोलें और YOUR_SUPABASE_PROJECT_URL तथा YOUR_SUPABASE_ANON_KEY को अपनी values से बदलें। Save/Commit करें।
4) Supabase Dashboard > SQL Editor > New query में supabase_setup.sql का पूरा code paste करके Run करें।
5) Supabase Authentication URL Configuration में Site URL अपनी प्रकाशित GitHub Pages URL रखें।
6) GitHub Pages URL को https से खोलें। Sign up करें, email verification आए तो verify करें, फिर login करें।
7) दूसरे फोन में वही वेबसाइट और वही account login करें।

अगर config.js में placeholders हैं, login form चालू नहीं होगा। यह सुरक्षित रूप से cloud setup की प्रतीक्षा करेगा।

ध्यान दें:
- Public/anon key browser में इस्तेमाल करने के लिए है। service_role key कभी वेबसाइट/ZIP में न डालें।
- प्रत्येक account का अपना private data है। अलग operator/viewer accounts के लिए institution sharing/membership roles अभी अलग backend feature है।
- पुराना data हो तो पहले app से JSON backup export करें।
- Cloud login/sync के लिए internet चाहिए; offline किए गए बदलावों का automatic merge अभी guarantee नहीं है।
