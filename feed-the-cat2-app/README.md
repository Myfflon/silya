# Накорми кошку (Android)

## Как получить APK без Android Studio (через GitHub, бесплатно)
1. Зарегистрируйся на github.com и создай новый репозиторий (кнопка «New»).
2. Загрузи в него всё содержимое этой папки (Add file → Upload files). Папку `.github` тоже: она скрытая, на компьютере включи показ скрытых файлов.
3. Открой вкладку **Actions**, выбери **Build APK** и нажми **Run workflow**. Сборка идёт 4–6 минут.
4. Когда появится зелёная галочка, открой запуск и внизу в разделе **Artifacts** скачай `feed-the-cat-apk`. Внутри будет `app-debug.apk`.
5. Перекинь файл на телефон и открой его. Если телефон попросит, разреши установку из этого источника.

## Через Android Studio
```
npm install
npx cap add android
npx @capacitor/assets generate --android
npx cap sync android
npx cap open android
```
Дальше Build → Build APK(s). Чтобы закрепить вертикальную ориентацию, добавь `android:screenOrientation="portrait"` в `<activity>` в `AndroidManifest.xml`.

## Как установить как иконку без APK (PWA)
Выложи папку `www` на любой хостинг с https (GitHub Pages, Netlify), открой адрес в Chrome на телефоне и выбери «Установить приложение».

## Что где лежит
- `www/` сама игра (index.html, фото кота, манифест)
- `assets/icon.png` иконка приложения (кот)
- `.github/workflows/build-apk.yml` автосборка APK
