# Anime Physics Studio 3D

لعبة ويب (WebGL2) في ملف HTML واحد — شخصية أنمي البالغة بفيزياء حقيقية (Verlet للشعر، نوابض للتنورة، squash & stretch، ارتداد، قفز، موجة).

## التشغيل الفوري (بدون تجميع)

افتح الرابط مباشرة في المتصفح:

**https://fouadbakdi2000-source.github.io/anime-physics-3d/**

أو حمّل الملف `www/index.html` وافتحه محليًا.

## التحكم

| الإجراء | الطريقة |
|---|---|
| تدوير الكاميرا | اسحب |
| تقريب / تبعيد | عجلة الفأرة أو القرص (pinch) |
| دفعة فيزيائية | انقر (tap) |
| قفز | Space أو زر «قفز» |
| موجة | W أو زر «موجة» |
| تصفير | R أو زر «تصفير» |

## الفيزياء

- **Verlet integration** — 8 عقدة للشعر، 3 مراحل تثبيت الأطوال، تصادم مع الجسم
- **نوابض (spring-damper)** — التنورة بـ 22 لوحًا، stiff = 26 × bounce، damp = 3.4
- **squash & stretch** — عند القفز والهبوط مع ارتداد
- **رياح وإيقاع تنفّس** — sine waves على الشعر والتنورة

## البناء (APK)

- **GitHub Pages** → التشغيل الفوري من المتصفح
- **GitHub Actions** → `.github/workflows/build-apk.yml` يبني APK عبر Cordova + توقيع debug، ويرفعه كـ Artifact + Release

## البنية

```
anime-physics-3d/
├─ www/index.html          # اللعبة (WebGL2، 28KB)
├─ config.xml              # إعدادات Cordova
└─ .github/workflows/      # بناء APK التلقائي
```