# 🛡️ Junkman SMS Filtresi (iOS)

[![Platform: iOS](https://img.shields.io/badge/Platform-iOS-blue.svg)](https://apps.apple.com/tr/app/junkman-smart-sms-blocker/id1591815272)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)

Türkiye'deki agresif bahis, casino, iddaa ve istenmeyen SMS'leri engellemek için optimize edilmiş **Regex (Düzenli İfade)** kuralları. Bu filtre seti, önemli mesajları (Banka, Kargo, Devlet Kurumları) kaçırmadan maksimum koruma sağlamayı hedefler.

---

## ✨ Özellikler

* **🎯 Yüksek Başarı Oranı:** "b.e.t", "c a s i n o", "k a z a n ç" gibi boşluklu, noktalı veya özel karakterli yazımları yakalar.
* **✅ Akıllı Güvenli Liste (Whitelist):** Bankalar, Kargo firmaları, Operatörler, E-Devlet ve Oyun platformları otomatik olarak korunur.
* **🇹🇷 Türkçe Dil Uyumu:** Türkçe karakter duyarlılığı (ı/i, ş/s, ğ/g) sayesinde yerel spam kalıplarına tam uyum sağlar.
* **🔗 Link Engelleyici:** `.xyz`, `.bet`, `.link` gibi şüpheli ve zararlı uzantıları hedef alan özel kurallar içerir.

---

## 🚀 Kurulum & Kullanım

Junkman uygulamasında filtrelerin doğru çalışması için aşağıdaki adımları sırasıyla takip edin.

### 📱 Adım Adım Kurulum

1. iPhone’unuzda **Junkman** uygulamasını açın.  
2. **Kural Listeleriniz** sekmesine gidin.  
3. ✅ İzin Verilen Kurallar

İzin verilen kuralını eklemek için:

* **İzin verilen** sekmesine girin.  
* Sağ üstteki **+** ikonuna basın.  
* Bu repoda bulunan regexleri **sırasıyla ekleyin.**
  
>**Kural ayarları:**
>- **Şuna uygula:** Gönderici  
>- **Düzenli ifade (Regex):** Açık  
4. 🚫 İstenmeyen Kurallar

Spam ve bahis içeriklerini engelleyen kuralı eklemek için:

* **İstenmeyen** sekmesine girin.  
* **+** ikonuna basın.  
* Repodaki ilgili regexleri ekleyin.
  
>**Kural ayarları:**
>- **Şuna uygula:** Gönderici veya Mesaj  
>- **Düzenli ifade (Regex):** Açık  

---

## 1. ✅ İzin Verilenler (Whitelist)

> [!IMPORTANT]
> **ÖNEMLİ:** Bu kuralları eklerken **Kural Listeleri** kısmını **"İzin Verilen"** olarak seçmelisiniz. Bu sayede bahis filtresindeki yasaklı kelimeler (örn: bonus, yatırım) banka mesajlarında geçse bile engellenmez.

### 🏦 Bankalar ve Dijital Cüzdanlar
*Kapsam: Tüm kamu ve özel bankalar, Papara, Tosla, Paycell vb.*
```regex
(?i)(ziraat|vak[ıi]f|halk\s?ban|[ıi]ş\s?ban|[ıi]s\s?ban|garanti|akban|yap[ıi]\s?kredi|qnb|finans\s?ban|deniz\s?ban|teb\s?ban|cepte\s?teb|kuveyt|albaraka|t[uü]rk\s?iye\s?finans|hsbc|ing\s?ban|odea|fiba|enpara|papara|tosla|paycell|nays|pep|fastpay|paribu|btcturk|moka|iyzi)
```
### 📦 Kargo Firmaları
Kapsam: Aras, Yurtiçi, MNG, PTT, Hepsijet, Trendyol Express, Amazon vb.
```regex
(?i)(aras|mng|ptt|dhl|ups|fedex|tnt|yurt\s?[ıi][çc][ıi]|s[uü]rat|hepsi\s?jet|sendeo|kolay\s?gelsin|kargomsende|scotty|horoz|trendyol|amazon|jetizz|inter\s?global)
```
### 📶 Operatörler ve İnternet Sağlayıcıları
Kapsam: Turkcell, Vodafone, Türk Telekom, TurkNet, Superonline vb.
```regex
(?i)(turk\s?cell|vodafone|t[uü]rk\s?telekom|avea|ttnet|super\s?online|bim\s?cell|ptt\s?cell|tekno\s?sa|net\s?gsm|t[uü]rk\s?net|milleni|kablo\s?net|t[uü]rk\s?sat|d\s?smart|digiturk|tivibu)
```
### 🏛️ Kritik Kurumlar & Servisler
Kapsam: E-Devlet, MHRS (182), ÖSYM, EGM, Belediyeler (BSB, BB, BLD, BL vb. dinamik uzantılar dahil), Valilikler; HGS, OGS, THY, TCDD, Obilet, Enuygun, Martı gibi ulaşım firmaları; TREDAŞ, TESKİ, İGDAŞ, Enerjisa, Aksa, İSKİ, BEDAŞ gibi tüm elektrik, su ve doğalgaz dağıtım şirketleri.
```regex
(?i)(e[\W_]*devlet|turkiye\.?gov|mhrs|182|btk|gib|uyap|afad|kades|egm|hgs|ogs|osym|belediye|bel\.?tr|b[uü]y[uü]k\s?seh[iı]r|\w+\s?(?:bsb|bb|bld|bl)|ibb(?:\s?ik)?|s[uü]leymanpa[sş]a|valilik|tcdd|yht|thy|t[uü]rk\s?hava|pegasus|sun\s?express|a\s?jet|obilet|enuygun|turna|mart[ıi]|binbin|hop|treda[sş]|teski|gazda[sş]|iski|igda[sş]|beda[sş]|ayeda[sş]|seda[sş]|ueda[sş]|gediz|toroslar|enerjisa|aksa|enerya|palgaz|limak|ck\s?enerji|izsu|aski|buski|koski|saski|meski|gaski|zorlu\s?enerji)
```
### 🎮 Oyun Platformları & E-Pin Siteleri
Kapsam: Steam (Valve), Epic Games, Blizzard (Battle.net), EA Games (Origin), Riot Games, Ubisoft, Wargaming; PlayStation, Xbox, Nintendo; İtemsatış, Gamesatış, ByNoGame, Oyunfor gibi popüler E-Pin ve bakiye siteleri.
```regex
(?i)(steam|valve|epic\s?games|blizzard|battle\.?net|ea\s?games|origin|ubisoft|uplay|riot\s?games|wargaming|rockstar|twitch|discord|playstation|sony|xbox|microsoft|nintendo|item\s?sat[ıi][şs]|game\s?sat[ıi][şs]|bynogame|oyunfor|kabasakal|klasgame|foxngame|razer|steelseries)
```


## 2. ⛔ İstenmeyen (Blacklist)
> [!WARNING]
> Kural Listeleri: İstenmeyen olarak seçilmelidir.

### 🎰 Agresif Bahis ve Spam Filtresi
Kapsam: Bet, Casino, Slot, Bonus, Freespin ve varyasyonları; Aviator, Bonanza, Sweet, Dede gibi popüler slot oyunları; Papara, PayFix, Mefete, Kripto, Forex gibi e-cüzdan ve finans terimleri; İcra, uzlaşma, gümrük, kargo teslim gibi oltalama (phishing) sözcükleri; Metin2, PvP server gibi oyun reklamları; Takipçi ve beğeni satışları; t.me, bit.ly, cutt.ly gibi zararlı kısa link servisleri ve .xyz, .bet, .vip, .click gibi spam alan adları.

```regex
(?i)(b[\W_]*e[\W_]*t|c[\W_]*a[\W_]*s[\W_]*i[\W_]*n[\W_]*o|s[\W_]*l[\W_]*o[\W_]*t|p[\W_]*o[\W_]*k[\W_]*e[\W_]*r|r[\W_]*u[\W_]*l[\W_]*e[\W_]*t|b[\W_]*o[\W_]*n[\W_]*u[\W_]*s|f[\W_]*r[\W_]*e[\W_]*e[\W_]*s[\W_]*p[\W_]*i[\W_]*n|d[\W_]*e[\W_]*n[\W_]*e[\W_]*m[\W_]*e|[çc][\W_]*e[\W_]*v[\W_]*r[\W_]*i[\W_]*m|k[\W_]*a[\W_]*y[\W_]*[ıi][\W_]*p|y[\W_]*a[\W_]*t[\W_]*[ıi][\W_]*r[\W_]*[ıi][\W_]*m|j[\W_]*a[\W_]*c[\W_]*k[\W_]*p[\W_]*o[\W_]*t|a[\W_]*v[\W_]*i[\W_]*a[\W_]*t[\W_]*o[\W_]*r|b[\W_]*o[\W_]*n[\W_]*a[\W_]*n[\W_]*z[\W_]*a|o[\W_]*l[\W_]*y[\W_]*m[\W_]*p[\W_]*u[\W_]*s|z[\W_]*e[\W_]*p[\W_]*l[\W_]*i[\W_]*n|s[\W_]*w[\W_]*e[\W_]*e[\W_]*t|g[\W_]*a[\W_]*t[\W_]*e[\W_]*s|d[\W_]*e[\W_]*d[\W_]*e|s[\W_]*h[\W_]*o[\W_]*o[\W_]*t|g[\W_]*[üu][\W_]*n[\W_]*c[\W_]*e[\W_]*l|g[\W_]*i[\W_]*r[\W_]*i[\W_]*[şs]|y[\W_]*e[\W_]*n[\W_]*i.*a[\W_]*d[\W_]*r[\W_]*e[\W_]*s|l[\W_]*i[\W_]*n[\W_]*k|t[\W_]*[ıi][\W_]*k[\W_]*l[\W_]*a|k[\W_]*a[\W_]*z[\W_]*a[\W_]*n|x[\W_]*k[\W_]*a[\W_]*t[\W_]*[ıi]|o[\W_]*r[\W_]*a[\W_]*n|k[\W_]*u[\W_]*p[\W_]*o[\W_]*n|ş[\W_]*a[\W_]*n[\W_]*s|[çc][\W_]*e[\W_]*k[\W_]*i[\W_]*m|b[\W_]*a[\W_]*h[\W_]*i[\W_]*s|d[\W_]*i[\W_]*s[\W_]*c[\W_]*o[\W_]*u[\W_]*n[\W_]*t|p[\W_]*a[\W_]*p[\W_]*a[\W_]*r[\W_]*a|p[\W_]*a[\W_]*y[\W_]*f[\W_]*i[\W_]*x|m[\W_]*e[\W_]*f[\W_]*e[\W_]*t[\W_]*e|p[\W_]*r[\W_]*o[\W_]*m[\W_]*o[\W_]*s[\W_]*y[\W_]*o[\W_]*n|[çc][\W_]*e[\W_]*v[\W_]*r[\W_]*i[\W_]*m[\W_]*s[\W_]*i[\W_]*z|v[\W_]*i[\W_]*p|i[\W_]*c[\W_]*r[\W_]*a|u[\W_]*z[\W_]*l[\W_]*a[\W_]*[şs][\W_]*m[\W_]*a|d[\W_]*o[\W_]*s[\W_]*y[\W_]*a[\W_]*n[\W_]*[ıi][\W_]*z|k[\W_]*r[\W_]*i[\W_]*p[\W_]*t[\W_]*o|f[\W_]*o[\W_]*r[\W_]*e[\W_]*x|s[\W_]*i[\W_]*n[\W_]*y[\W_]*a[\W_]*l|[üu]yel[iı]k\s?bonusu?|mga\s?l[iı]sans|rtp\s?[0-9.,]+|metin\s?2|mt2|pvp\s?server|wslik|emek\s?server|boss\s?arenas[ıi]|(1|55)-(99|105|107|120|127|200)|kct\s?oyun|lonca|old\s?school|server|yap[ıi]s[ıi]yla|yerini\s?al|takip[cç][iı]|be[gğ]eni|izlenme|g[üu]mr[üu]k|kargo\s?teslim|cutt\.ly|t2m\.io|t\.me|bit\.ly|kisa\.link|bityl\.co|is\.gd|tinyurl\.com|rb\.gy|tiny\.cc|tr\.link|ay\.link|shorte\.st|[0-9.,]+\s?(tl|try|₺)|%[0-9.,]+|\.(xyz|bet|link|top|site|club|live|pro|biz|cloud|cam|fun|online|info|mobi|me|cc|vip|io|app|click))
```

## ℹ️ Önemli Notlar
> [!TIP]
> Kuralların doğru çalışması için Regexlerin eksiksiz kopyalandığından ve Junkman ayarlarında "Düzenli İfade (Regex)" seçeneğinin aktif olduğundan emin olun.

## 🤝 Katkıda Bulunma
Yeni bir spam kalıbı mı fark ettiniz? Lütfen bir Issue açarak bildirin veya Pull Request göndererek listeyi güncel tutmamıza yardımcı olun.

## 📜 Lisans
Bu proje **MIT Lisansı** ile lisanslanmıştır. Detaylar için `LICENSE` dosyasına göz atabilirsiniz.

## ⚖️ Sorumluluk Reddi (Disclaimer)
> [!CAUTION]
> **Resmi Bağlantı:** Bu depo (repository) Junkman uygulamasının resmi bir parçası, ürünü veya iştiraki değildir. Bu çalışma, iOS kullanıcılarının deneyimini iyileştirmek amacıyla bağımsız olarak geliştirilmiş yardımcı bir kural setidir.
>
> **Kullanım Sorumluluğu:** Paylaşılan Regex kuralları "olduğu gibi" sunulmaktadır. Kuralların kullanımı sonucunda (nadiren de olsa) önemli bir mesajın hatalı bir şekilde "İstenmeyen" olarak işaretlenmesi veya bir spam mesajının filtreden kaçması durumunda sorumluluk kullanıcıya aittir. 
>
> **Öneri:** Özellikle banka, hukuki işlem ve kargo gibi kritik mesajların takibi için uygulamanın "İstenmeyen" klasörünü periyodik olarak kontrol etmeniz önerilir.

