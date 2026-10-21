ZEFRI: ПОСЛЕДНИЙ СТРАННИК — проект для сборки APK (Capacitor 6)

ВАРИАНТ A. Без установки программ (через GitHub, бесплатно)
1. Зарегистрируйтесь на github.com и создайте новый репозиторий (Public или Private).
2. Загрузите в него всё содержимое этой папки (кнопка «Add file → Upload files»).
   Важно: папка .github должна загрузиться вместе с файлом build-apk.yml внутри.
3. Откройте вкладку Actions → «Build APK» → «Run workflow».
4. Через 5–10 минут откройте завершённый запуск и внизу в разделе Artifacts скачайте «Zefri-APK» (внутри app-debug.apk).
5. Перенесите APK на телефон и установите (Android попросит разрешить установку из неизвестных источников).

ВАРИАНТ B. Android Studio на компьютере
1. Установите Node.js 20, JDK 17 и Android Studio.
2. В этой папке выполните: npm install, затем npx cap add android, затем npx cap sync android.
3. Откройте папку android в Android Studio и выберите Build → Build APK(s).

ЗАМЕТКИ
- Это debug-APK: он ставится на телефон напрямую, но не подходит для Google Play.
  Для магазинов нужен подписанный релиз: Build → Generate Signed Bundle / APK.
- Название приложения меняется в capacitor.config.json (appName), идентификатор там же (appId).
- Иконка по умолчанию — стандартная Capacitor. Свою можно заменить в android/app/src/main/res/mipmap-*.
- Игра хранит прогресс (золото, таланты, рекорд) внутри приложения, при удалении приложения он пропадёт.
- Обновление игры: замените www/index.html новой версией и соберите APK заново.
