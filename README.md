# TradeHub Journal

אתר סטטי ל-GitHub Pages לניהול חדשות כלכליות, עסקאות Intraday, עסקאות Swing והשקעות לטווח ארוך.

## מבנה קבצים

```text
index.html
assets/css/style.css
assets/js/app.js
data/news-sources.json
data/intraday-trades.json
data/swing-trades.json
data/longterm-investments.json
.nojekyll
```

## איך להעלות ל-GitHub Pages

1. העלה את כל הקבצים לתיקיית השורש של ה-Repository.
2. ודא שהקובץ הראשי נקרא `index.html`.
3. ב-GitHub פתח: Settings → Pages.
4. בחר Branch: `main`, Folder: `/root`.
5. לחץ Save.

## שמירת נתונים

האתר סטטי ולכן הדפדפן לא יכול לעדכן את קבצי ה-JSON בתוך ה-Repository בעצמו.

מה כן קיים:

- טעינה התחלתית מקבצי JSON בתיקיית `data`.
- שמירה מקומית בדפדפן באמצעות `localStorage`.
- כפתור ייצוא JSON לכל קטגוריה.
- כפתור ייבוא JSON לכל קטגוריה.
- כפתור ייצוא מלא לכל המערכת.

אם תרצה בעתיד שמירה אמיתית לתוך GitHub, צריך להוסיף GitHub Action / Backend / API מאובטח. לא מומלץ לשים Token של GitHub בתוך קובץ JS ציבורי.

## חדשות כלכליות

הקובץ `data/news-sources.json` מכיל מקורות RSS. בגלל מגבלות CORS, חלק מהאתרים עלולים לחסום טעינה ישירה בדפדפן. במקרה כזה יוצג קישור לפתיחה ידנית.

אפשר להוסיף או להסיר מקורות לפי המבנה הבא:

```json
{
  "name": "Source Name",
  "category": "Markets",
  "home": "https://example.com/",
  "rss": "https://example.com/rss.xml"
}
```

## תמונות גרף

בכל רשומה אפשר:

- להעלות תמונת גרף מהמחשב.
- או להדביק קישור לתמונה.
- בטבלה יופיע אייקון תמונה, ולחיצה עליו פותחת חלונית תצוגה.

שים לב: תמונות שמועלות מהמחשב נשמרות כ-Base64 בתוך הדפדפן ובקובץ הייצוא. אם מעלים הרבה תמונות כבדות, קובץ ה-JSON יגדל.
