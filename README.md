# ITMO — אתר ניהול דיגיטל | מיכאל אוחנה

אתר תדמית ולידים עבור ITMO (מיכאל אוחנה) — ניהול דיגיטל כולל: הקמת אתרים, קידום אורגני,
מערכות בתי מלון (PMS), ערוצי הפצה OTA, רשתות חברתיות, אוטומציה וניהול מערכות.

- **דומיין:** https://www.itmo.co.il (הפניה אוטומטית מ-itmo.co.il ל-www)
- **אחסון:** GitHub repo `OhanaMichael/itmo-website` → פרסום אוטומטי לאוויר בכל `git push`
- **טכנולוגיה:** HTML סטטי + קובץ CSS משותף אחד. ללא framework, ללא שלב build. נטען מהר.

---

## מבנה הפרויקט

```
itmo-site-v8/
├── index.html                  # עמוד הבית
├── blog.html                   # עמוד הבלוג (אינדקס מאמרים)
├── blog/                       # מאמרים
│   ├── how-to-choose-hotel-pms.html
│   └── organic-seo-guide-2026.html
├── services/                   # 9 עמודי שירות + עמוד-גג + פרויקט שהושלם
│   ├── digital-management.html # עמוד-גג "ניהול דיגיטל"
│   ├── web-development.html
│   ├── seo.html
│   ├── hotel-management-systems.html
│   ├── ota-channel-management.html
│   ├── social-media-marketing.html
│   ├── automation-customer-journey.html
│   ├── google-business-local.html
│   ├── procurement-systems.html
│   └── it-systems-management.html
├── assets/
│   ├── css/main.css            # כל העיצוב — מקור אמת יחיד
│   ├── og-image.png/.jpg       # תמונת שיתוף לרשתות (1200x630)
│   ├── favicon.svg/.ico/-32.png, apple-touch-icon.png
│   └── logo.svg
├── sitemap.xml                 # מפת אתר לגוגל (14 כתובות)
├── robots.txt                  # הנחיות לסורקים
└── docs/                       # תיעוד (מסמך Word)
```

---

## עמודי האתר

| עמוד | כתובת | מטרה |
|------|-------|------|
| בית | `/` | מבט-על, שירותים, לידים |
| ניהול דיגיטל (גג) | `/services/digital-management.html` | סקירת כל השירותים |
| הקמת אתרים | `/services/web-development.html` | שירות + לידים |
| קידום אורגני SEO | `/services/seo.html` | שירות + לידים |
| מערכות בתי מלון PMS | `/services/hotel-management-systems.html` | שירות + לידים |
| ערוצי הפצה OTA | `/services/ota-channel-management.html` | שירות + לידים |
| רשתות חברתיות | `/services/social-media-marketing.html` | שירות + לידים |
| אוטומציה ומסע לקוח | `/services/automation-customer-journey.html` | שירות + לידים |
| נוכחות בגוגל (Local) | `/services/google-business-local.html` | שירות + לידים |
| ביז בגליל — מערכת הצעות מחיר (פרויקט שהושלם) | `/services/procurement-systems.html` | מקרה בוחן — לא שירות שוטף |
| ניהול מערכות ממוחשבות | `/services/it-systems-management.html` | שירות + לידים |
| ניהול מערכות לרשויות | `/services/public-sector-systems.html` | שירות + לידים |
| בלוג | `/blog.html` + `/blog/*` | תוכן ל-SEO |

---

## מערכת העיצוב

כל העיצוב מנוהל מקובץ אחד: `assets/css/main.css`. שינוי שם משפיע על כל האתר.

**צבעים** (בראש הקובץ, תחת `:root`):

```css
--primary: #0a4d68;     /* כחול-טורקיז ראשי */
--primary-light: #0d7ca8;
--accent: #f39c12;      /* כתום הדגשה */
--ink: #1c2733;         /* טקסט */
--light: #f6f8fa;       /* רקע בהיר */
```

**גופנים:** Heebo (טקסט) + Assistant (כותרות), נטענים מ-Google Fonts.

לשינוי צבע המותג — ערוך את הערכים תחת `:root` בלבד; הם מתעדכנים בכל מקום.

---

## עריכת תוכן — הנחיות חשובות

1. **קול אחיד:** כל הטקסטים מנוסחים בלשון **"אנחנו / ITMO"** (לא "אני"). שמרו על זה.
2. **כותרת עליונה, תפריט ופוטר** מופיעים *בתוך כל קובץ HTML בנפרד* (אתר סטטי).
   לשינוי שמשפיע על כל העמודים (למשל פריט תפריט חדש) — יש לעדכן בכל הקבצים
   (חיפוש-והחלפה), או לבקש עדכון מרוכז.
3. עריכת טקסט רגילה: פתחו את קובץ ה-HTML, אתרו את המשפט, ערכו ושמרו.

---

## הוספת מאמר חדש לבלוג

1. העתיקו קובץ מאמר קיים מ-`blog/` (למשל `organic-seo-guide-2026.html`) לשם חדש באנגלית, למשל `blog/my-new-post.html`.
2. בקובץ החדש עדכנו: `<title>`, `<meta name="description">`, `<meta name="keywords">`, ה-`<h1>`, וכל גוף המאמר.
3. עדכנו את ה-Schema (`Article`) בראש הקובץ: `headline`, `description`, `datePublished` (תאריך פרסום), וה-`@id`/קישור canonical.
4. עדכנו את ה-breadcrumb (פירורי לחם) לשם המאמר.
5. הוסיפו כרטיס מאמר ל-`blog.html` (העתיקו כרטיס קיים, עדכנו כותרת, תקציר וקישור).
6. הוסיפו שורת `<url>` ל-`sitemap.xml` עם כתובת המאמר החדש.
7. העלו לאוויר (ראו "העלאה לאוויר").

> טיפ: מאמרים איכותיים וממוקדי-מילות-מפתח הם מנוע התנועה האורגנית. לפחות מאמר בחודש.

---

## הוספת עמוד שירות חדש

1. העתיקו עמוד שירות קיים מ-`services/`, שנו שם קובץ באנגלית.
2. עדכנו: `<title>`, meta description/keywords, canonical, `<h1>`, התוכן, ה-FAQ וה-Schema (`Service` + `BreadcrumbList` + `FAQPage`).
3. הוסיפו קישור לעמוד ב**תפריט הנפתח** וב**פוטר** — בכל קבצי ה-HTML.
4. הוסיפו כרטיס בעמוד הבית וב-`services/digital-management.html`.
5. הוסיפו שורה ב-`sitemap.xml`. העלו לאוויר.

---

## SEO — מה כבר מובנה

- **כותרות ותיאורים ייחודיים** לכל עמוד (Title + meta description).
- **נתוני Schema (JSON-LD)** בכל עמוד: `ProfessionalService` (בית), `Service` + `BreadcrumbList` + `FAQPage` (שירותים), `Article` (בלוג).
- **Open Graph + Twitter Card** + תמונת שיתוף (`og-image.png`).
- **canonical** ב-www בכל עמוד (תואם לכתובת המוגשת).
- **sitemap.xml** + **robots.txt** (פתוח גם לבוטים של AI).
- מבנה עמודים היררכי, breadcrumbs, ומהירות טעינה גבוהה (CSS אחד, ללא JS כבד).

**צעד הבא ב-SEO:** חיבור Google Search Console והגשת `sitemap.xml` (ראו "מה הלאה").

---

## טופס יצירת קשר

- הטופס בעמוד הבית שולח דרך **Formspree** (מזהה טופס: `xnjygkea`).
- הפניות מגיעות למייל `michael@itmo.co.il`. החבילה החינמית: עד 50 פניות בחודש.
- לשינוי יעד/הגדרות — היכנסו ל-formspree.io. להחלפת מזהה — עדכנו את ה-`action` בטופס שב-`index.html`.

---

## העלאה לאוויר (Deploy)

האתר מתפרסם אוטומטית מ-GitHub. לאחר עריכת קבצים, מ-PowerShell בתיקיית הפרויקט:

```powershell
git add -A
git commit -m "תיאור השינוי"
git push origin main
```

תוך דקה-שתיים השינוי חי ב-www.itmo.co.il.
אם מופיעה שגיאת `index.lock`: `Remove-Item ".git\index.lock" -Force` ואז שוב מ-`git add -A`.

---

## תחזוקה ובדיקות

- לאחר שינוי, בדקו שהעמוד נטען נכון בדפדפן לפני push.
- ודאו שכל עמוד מכיל **H1 אחד**, canonical, וקישור ל-`/assets/css/main.css`.
- ודאו שה-JSON-LD תקין (אפשר לבדוק ב-Google Rich Results Test).

---

## מה הלאה (Roadmap)

1. **Google Search Console** — אימות בעלות + הגשת `sitemap.xml` (מזרז דירוג).
2. **Google Analytics / מעקב** — למדוד תנועה ומקורות לידים.
3. **תוכן שוטף לבלוג** — מאמר בחודש לפחות, ממוקד מילות מפתח.
4. **ביקורות והמלצות** — להוסיף עדויות לקוחות לחיזוק אמון והמרה.
5. **Google עסק שלי** — אופטימיזציה לנוכחות מקומית.

---

© 2026 ITMO · מיכאל אוחנה
