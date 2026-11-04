# MD Viewer Privacy Policy · Gizlilik Politikası

[English](#english) · [Türkçe](#türkçe)

---

## English

**Effective date:** November 4, 2026

**Developer:** Minata Entertainment, LLC, a studio based in Antalya, Türkiye, registered as a limited liability company in Delaware, United States.
**Contact:** [hello@minata.dev](mailto:hello@minata.dev)

This policy applies to MD Viewer 1.0.0 and later, the macOS Markdown viewer, whether you download it from this repository or get it from the Mac App Store, and to the Quick Look extension that comes with it.

### In short

- MD Viewer **does not collect any data**. Nothing is sent to us or to anyone else.
- There are **no accounts, no analytics, no tracking, no advertising and no crash reporting** in the app.
- MD Viewer **sends nothing over the network**. Its own code contains no networking, no update check and no telemetry, and the libraries it needs are bundled inside the app. The only exception is the optional *Load images from the internet* setting (see below), which is off by default.
- MD Viewer runs in the **macOS App Sandbox**: it can read only the files and folders you open or allow, and the folder permissions you grant stay on your Mac.
- Your documents are read on your Mac and stay on your Mac.

### What the app does on your Mac

**Reading.** MD Viewer reads the Markdown files and folders you open. Opening a document gives MD Viewer access to that file only; to show images next to it, resolve `[[links]]` or save comments beside it, MD Viewer asks you, with a band in the window and the standard macOS folder panel, to allow the folder. A folder or Obsidian vault index, if you allow one, is kept in memory only and is never written to disk. The history behind the *Changes* view exists only while a document is open and is discarded when you quit.

**Writing.** The app changes files only when you ask it to:

- clicking a task checkbox (`- [ ]`) updates that checkbox in the `.md` file (you can undo it with ⌘Z);
- adding a review comment creates or updates a side file named `<document>.md.review.md` next to the document once you have allowed the document's folder; until then the comments are kept in the app's own storage on your Mac and move next to the document when you allow the folder. The document itself is not touched;
- *Export as PDF* saves a PDF at the location you choose.

**Folder permissions and the App Sandbox.** MD Viewer runs in the macOS App Sandbox, so it can read and write only the files and folders you open or allow. A folder you allow is remembered as a *security-scoped bookmark*, which is stored locally in the app's preferences on your Mac. It never leaves your device and is not shared with anyone. You can review and remove every allowed folder under Settings ▸ Folder Access; removing access deletes nothing on your Mac.

**Preferences.** Settings such as theme, view mode, zoom, language, Markdown dialect, and the lists of recent and favorite folders and documents are stored locally on your Mac, in the app's preferences and in the recent-items lists that macOS keeps. They are never transmitted. You can reset them by deleting the app's preferences.

**Quick Look.** The Quick Look extension runs in the macOS sandbox with read-only access to the file being previewed and has no network access.

### The sandbox and network access

The permissions of a sandboxed app include one for *outgoing network connections* (`com.apple.security.network.client`), and MD Viewer holds it. The reason is technical: the system web engine (WebKit) that draws your documents does not start inside the sandbox without it. MD Viewer's own code has no networking, and the content security policy of the pages that draw your documents blocks every request they could make to a remote address, except images from the internet when you turn that setting on. The Quick Look extension has no network access at all.

### Remote images

Remote images are **off by default**. If you turn on *Load images from the internet* in Settings, a document that references an image by web address makes your Mac request that image from the server that hosts it. That server can then see your IP address and the time of the request, as with any web page. Turn the setting off again at any time.

Clicking a web link in a document opens it in your default browser (MD Viewer asks you to confirm links that look risky). From then on the browser, not MD Viewer, is connecting to that site.

### Data sharing

MD Viewer does not share, sell or rent any data, because it does not collect any. No third-party service is built into the app, and no third-party code is loaded from the internet.

macOS itself may offer to send crash reports to Apple if you have enabled that in System Settings. That is a macOS feature that MD Viewer neither controls nor receives.

### Children

MD Viewer collects no data from anyone, including children.

### Changes to this policy

If this policy changes, the new text is published in this repository with a new effective date at the top. The history of changes is visible in the repository.

### Contact

Questions about privacy: [hello@minata.dev](mailto:hello@minata.dev) · Minata Entertainment, LLC, Antalya, Türkiye.

---

## Türkçe

**Yürürlük tarihi:** 4 Kasım 2026

**Geliştirici:** Minata Entertainment, LLC. Antalya, Türkiye'de çalışan, ABD'nin Delaware eyaletinde limited şirket (LLC) olarak kayıtlı bir stüdyo.
**İletişim:** [hello@minata.dev](mailto:hello@minata.dev)

Bu politika, macOS için Markdown görüntüleyici MD Viewer'ın 1.0.0 ve sonraki sürümlerine (bu depodan indirseniz de Mac App Store'dan edinseniz de) ve uygulamayla gelen Quick Look uzantısına uygulanır.

### Kısaca

- MD Viewer **hiçbir veri toplamaz**. Bize ya da bir başkasına hiçbir şey gönderilmez.
- Uygulamada **hesap, analitik, izleme, reklam ve çökme raporlama yoktur**.
- MD Viewer **ağ üzerinden hiçbir şey göndermez**. Kendi kodunda ağ iletişimi, güncelleme denetimi ve telemetri yoktur; ihtiyaç duyduğu kütüphaneler uygulamanın içindedir. Tek istisna, varsayılan olarak kapalı olan isteğe bağlı *İnternetteki görselleri yükle* ayarıdır (aşağıya bakın).
- MD Viewer **macOS App Sandbox (korumalı alan)** içinde çalışır: yalnızca açtığınız ya da izin verdiğiniz dosya ve klasörleri okuyabilir; verdiğiniz klasör izinleri Mac'inizde kalır.
- Belgeleriniz Mac'inizde okunur ve Mac'inizde kalır.

### Uygulama Mac'inizde ne yapar

**Okuma.** MD Viewer, açtığınız Markdown dosyalarını ve klasörlerini okur. Bir belgeyi açmak MD Viewer'a yalnızca o dosyaya erişim verir; yanındaki görselleri göstermek, `[[bağlantıları]]` çözmek ya da yorumları yanına kaydetmek için MD Viewer, penceredeki bir şerit ve standart macOS klasör paneliyle klasöre izin vermenizi ister. Bir klasör ya da Obsidian kasası dizinine izin verirseniz, bu dizin yalnızca bellekte tutulur ve diske yazılmaz. *Değişiklikler* görünümünün geçmişi belge açık olduğu sürece vardır ve uygulamadan çıkınca silinir.

**Yazma.** Uygulama dosyalara yalnızca siz istediğinizde yazar:

- bir görev kutusuna (`- [ ]`) tıklamak, `.md` dosyasındaki o kutuyu günceller (⌘Z ile geri alabilirsiniz);
- inceleme yorumu eklemek, belgenin klasörüne izin verdikten sonra belgenin yanında `<belge>.md.review.md` adlı bir yan dosya oluşturur ya da günceller; o zamana kadar yorumlar Mac'inizde uygulamanın kendi depolama alanında tutulur ve klasöre izin verdiğinizde belgenin yanına taşınır. Belgenin kendisine dokunulmaz;
- *PDF Olarak Dışa Aktar*, seçtiğiniz konuma bir PDF kaydeder.

**Klasör izinleri ve App Sandbox.** MD Viewer macOS App Sandbox içinde çalıştığından yalnızca açtığınız ya da izin verdiğiniz dosya ve klasörleri okuyabilir ve onlara yazabilir. İzin verdiğiniz klasör, Mac'inizde uygulamanın tercihlerinde yerel olarak saklanan bir *güvenlik kapsamlı yer imi* olarak hatırlanır. Cihazınızdan hiç çıkmaz ve kimseyle paylaşılmaz. İzin verilen her klasörü Ayarlar ▸ Klasör Erişimi altında görüp kaldırabilirsiniz; erişimi kaldırmak Mac'inizde hiçbir şeyi silmez.

**Tercihler.** Tema, görünüm modu, yakınlaştırma, dil, Markdown lehçesi ve son/favori klasör ve belge listeleri gibi ayarlar Mac'inizde, uygulamanın tercihlerinde ve macOS'un tuttuğu son kullanılanlar listelerinde yerel olarak saklanır. Hiçbir yere iletilmez. Uygulamanın tercihlerini silerek sıfırlayabilirsiniz.

**Quick Look.** Quick Look uzantısı macOS sandbox içinde çalışır; yalnızca önizlenen dosyaya salt okunur erişimi vardır ve ağ erişimi yoktur.

### Sandbox ve ağ erişimi

Korumalı alandaki bir uygulamanın izinleri arasında *giden ağ bağlantıları* için bir izin de vardır (`com.apple.security.network.client`) ve MD Viewer bu izne sahiptir. Gerekçe teknik: belgelerinizi çizen sistem web motoru (WebKit) bu izin olmadan korumalı alanda başlamaz. MD Viewer'ın kendi kodunda ağ iletişimi yoktur ve belgelerinizi çizen sayfaların içerik güvenlik politikası, ayarını açtığınızda internetteki görseller dışında, uzak bir adrese yapabilecekleri her isteği engeller. Quick Look uzantısının hiçbir ağ erişimi yoktur.

### Uzak görseller

Uzak görseller **varsayılan olarak kapalıdır**. Ayarlar'da *İnternetteki görselleri yükle*'yi açarsanız, bir görseli web adresiyle belirten belge, Mac'inizin o görseli barındıran sunucudan istemesine yol açar. Her web sayfasında olduğu gibi, o sunucu IP adresinizi ve isteğin zamanını görebilir. Ayarı istediğiniz an yeniden kapatabilirsiniz.

Belgedeki bir web bağlantısına tıklamak, onu varsayılan tarayıcınızda açar (riskli görünen bağlantılar için MD Viewer önce onay ister). O andan sonra o siteye bağlanan MD Viewer değil, tarayıcınızdır.

### Veri paylaşımı

MD Viewer hiçbir veri toplamadığı için hiçbir veriyi paylaşmaz, satmaz ya da kiralamaz. Uygulamada yerleşik bir üçüncü taraf hizmeti yoktur ve internetten üçüncü taraf kodu yüklenmez.

macOS'un kendisi, Sistem Ayarları'nda etkinleştirdiyseniz çökme raporlarını Apple'a göndermeyi önerebilir. Bu, MD Viewer'ın denetlemediği ve almadığı bir macOS özelliğidir.

### Çocuklar

MD Viewer çocuklar dahil kimseden veri toplamaz.

### Politikadaki değişiklikler

Bu politika değişirse yeni metin, en üstte yeni bir yürürlük tarihiyle bu depoda yayımlanır. Değişikliklerin geçmişi depoda görülebilir.

### İletişim

Gizlilikle ilgili sorular: [hello@minata.dev](mailto:hello@minata.dev) · Minata Entertainment, LLC, Antalya, Türkiye.
