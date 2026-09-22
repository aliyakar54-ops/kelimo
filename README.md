# KELIMO — Online Multiplayer + Sesli Sohbet

Bu paket iki parçalıdır:
- `web/`: Node.js + Socket.IO oyun/sinyal sunucusu ve web istemcisi.
- Capacitor yapılandırması: Android APK/AAB üretmek için.

## Bilgisayarda test
1. Node.js 20+ kur.
2. Proje klasöründe terminal aç.
3. `npm install`
4. `npm start`
5. Tarayıcıdan `http://localhost:3000` aç.

Aynı Wi‑Fi'daki telefondan test etmek için bilgisayarın yerel IP'siyle bağlanabilirsin. Mikrofon için güvenli bağlantı (HTTPS) gerekir; localhost özel istisnadır.

## Gerçek internet oyunu
Sunucuyu HTTPS destekleyen bir Node.js servisine yayınla. Örnek sağlayıcılar: Render, Railway, Fly.io veya kendi VPS'in. `web/server.js` bu sunucuda çalıştırılır. `health` adresi `/health`.

## Android
Android Studio + Android SDK + JDK 21 kurulu bilgisayarda:
1. `npm install`
2. `npx cap add android`
3. `npx cap sync android`
4. `npx cap open android`
5. Android Studio'da Build > Generate Signed App Bundle / APK.

Not: APK içine Node.js sunucusu gömülmez. APK, internetteki Kelimo sunucusuna bağlanır. Üretim için istemcide Socket.IO sunucu adresini gerçek HTTPS/WSS adresine sabitlemek gerekir.
