# 🧠 PROMPT MÜHENDİSLİĞİ TEMELLERİ (The Foundations)

**Görev (Task):** Modele ne yapacağını net bir dilde söyleyin. Promptunuzun içinde yapay zekaya persona belirlemek istediğiniz sonuca daha kolay ulaşmanızı sağlayacaktır. Örneğin yapay zekaya direkt olarak "bir python hello world kodu yaz" demek yerine "Sen 20 sene deneyimli bir yazılım mühendisisin, Python yazılım dilinde bir hello world kodu yaz" dediğinizde dil modeli sadece yazılımla ilgili konuları kapsamına alacaktır ve dil modelinin düşünme süreci son derece kolaylaşacaktır.

**Bağlam (Context):** Modelin durumu anlaması için gerekli bilgileri detaylı şekilde verin. Örneğin bir otelin müşterilerine hitap eden bir video oluşturmak için "A oteli için bir reels videosu oluştur" yazmak yerine "A oteli İzmir'de bulunuyor ve 25-30 yaş arası genç kitleye hitap ediyor. Bu otel için kitlenin ilgisini çekebilecek bir reels videosu hazırla" demelisiniz.

**Referanslar:** Modele takip etmesi için örnekler veya dökümanlar verin. Verdiğiniz dökümanları seçerken yapay zekanın anlamayacağı (silik yazılar, bulanık görseller vb.) dosyalar yerine direkt olarak anlaşılabilir dosyalar vermek, yapay zekanın yazı ve resimle belirttiğiniz bağlamı anlamasını kolaylaştıracaktır.

**Değerlendirme:** Çıktının istediğiniz kriterlere uyup uymadığını kontrol edin. Eğer kriterler uygun değilse revize edin.

**İterasyon:** Tek seferde mükemmele ulaşmak zordur. Problemi parçalara bölmek ve ayrı promptlarda anlatmak, yapay zekanın uzun bağlamlarla uğraşmasını engelleyerek çıkacak sonuçları çok daha nokta atışı vermesini sağlar.

---

## ⚡ Hızlı Komutlar (Quick Commands)
Günlük kullanımda en çok işe yarayan kısa komut kalıpları:
- **Hızlı Özet:** `TL;DR:` veya `Bunu 1 cümleyle özetle.`
- **Geliştirme:** `Bu metni daha ilgi çekici/profesyonel hale getir.`
- **Fikir Üretme:** `[Konu] hakkında 10 yaratıcı fikir listele.`
- **Format Belirleme:** `Bana Markdown / JSON / Tablo formatında yanıt ver.`
- **Uzunluk Sınırı:** `50 kelimenin altında tut.` veya `Detaylı bir şekilde açıkla.`
- **Ton Değişimi:** `Daha samimi / resmi / eğlenceli bir dille yaz.`
- **Adım Adım:** `Bunu adım adım düşünerek çözelim.`

---

## 🛠️ Temel ve İleri Seviye Prompt Teknikleri (17 Temel Teknik)

Bu bölüm, başlangıç seviyesinden ileri seviyeye kadar, küçük (örn: 1B parametreli) modellerden bile daha doğru, yaratıcı ve güvenilir yanıtlar almanızı sağlayacak 17 temel tekniği içermektedir.

### 1. Zero-Shot Prompting (Sıfır Örnekle Promptlama)
* **Ana Fikir:** Modele hiçbir örnek vermeden doğrudan görevi sormaktır.
* **Ne Zaman Kullanılır:** Basit soru-cevaplarda, temel metin özetlemede, hızlı beyin fırtınası yaparken ve modelin genel bilgisinin yeterli olduğu durumlarda.
* **Nasıl Uygulanır:** İsteğinizi doğrudan belirtin. Hedef kitle gibi bağlamlar ekleyerek iyileştirilebilir.
* **Örnek:**
  * *Önce:* `Fotosentez nedir?`
  * *Sonra:* `Fotosentezi 5 yaşındaki bir çocuğun anlayabileceği şekilde açıkla.` (Çıktı daha basit ve ilgi çekici olur).

### 2. Few-Shot Prompting (Az Örnekle Promptlama)
* **Ana Fikir:** Modelin istenen görevi ve formatı anlaması için birkaç girdi/çıktı (soru/cevap) örneği sunmaktır.
* **Ne Zaman Kullanılır:** Duygu analizi, basit kod üretimi, veri çekme/formatlama veya çok spesifik bir tarzda metin üretilmesi gerektiğinde.
* **Nasıl Uygulanır:** Asıl sorunuzdan önce `kullanıcı` girdisi ve beklenen `asistan` çıktısı örneklerini ekleyin.
* **Örnek:**
  ```text
  Kullanıcı: Sınıflandır: 'Hayatımda izlediğim en iyi filmdi!'
  Asistan: Pozitif
  Kullanıcı: Sınıflandır: 'Zaman kaybıydı, nefret ettim.'
  Asistan: Negatif
  Kullanıcı: Sınıflandır: 'Film fena değildi, ne çok iyi ne çok kötü.'
  ```

### 3. Role Prompting (Rol Atama)
* **Ana Fikir:** Modele belirli bir persona, uzman veya karakter rolü vermektir.
* **Ne Zaman Kullanılır:** Etkileşimleri daha ilgi çekici hale getirmek, spesifik kitlelere yönelik açıklamalar yapmak ve uzman perspektifinden yanıtlar almak için.
* **Nasıl Uygulanır:** Promptun başına `Sen [Rol]sün...` kalıbını ekleyin.
* **Örnek:** `Sen 20 yıllık deneyime sahip, dost canlısı bir astronom olan Profesör Astra'sın. Bana kara delikleri açıkla.`

### 4. Style Prompting (Stil Promptlama)
* **Ana Fikir:** Modeli belirli bir edebi, sanatsal, resmi veya gayri resmi tarzda yazmaya yönlendirmektir.
* **Ne Zaman Kullanılır:** Yaratıcı yazarlık, farklı kitlelere içerik uyarlama ve marka dilini yakalamada.
* **Nasıl Uygulanır:** `[Tarz] tarzında yaz` şeklinde belirtin.
* **Örnek:** `Gün batımının kısa bir tasvirini bir Haiku (Japon şiir türü) tarzında yaz.`

### 5. Emotion Prompting (Duygu Promptlama)
* **Ana Fikir:** Modelden belirli bir duyguyu yansıtan veya empatik bir bakış açısıyla yanıt vermesini istemektir.
* **Ne Zaman Kullanılır:** Teşekkür notları, özür metinleri, empatik müşteri hizmetleri yanıtları oluştururken.
* **Nasıl Uygulanır:** `Bunu çok [duygu] hissettirecek şekilde yaz.`
* **Örnek:** `Aldığım hediye için bir teşekkür notu yaz. Çok heyecanlı ve derinden minnettar hissettirsin.`

### 6. Contextual Prompting (Bağlamsal Promptlama)
* **Ana Fikir:** İsteğinizle ilgili yeterli arka plan bilgisini modele sunmaktır.
* **Ne Zaman Kullanılır:** Kişiselleştirilmiş öneriler, özel verilere dayalı problem çözme ve çok turlu konuşmalarda.
* **Nasıl Uygulanır:** Tüm detayları, geçmişi, tercihleri ve kısıtlamaları prompta ekleyin.
* **Örnek:** `Kız kardeşim (30 yaşında) için doğum günü hediyesi önerisi istiyorum. İlgi alanları: Fantastik romanlar, bahçecilik, çay. Bütçe: 50$.`

### 7. Chain-of-Thought (CoT - Düşünce Zinciri)
* **Ana Fikir:** Modeli "adım adım düşünmeye" (think step by step) teşvik ederek, çok adımlı mantık gerektiren görevlerde başarıyı artırmaktır.
* **Ne Zaman Kullanılır:** Matematik problemleri, mantık bulmacaları ve hata ayıklama (debugging).
* **Nasıl Uygulanır:** Prompta `Adım adım düşünelim` ekleyin veya mantık adımlarını gösteren örnekler verin.

### 8. System Prompting (Sistem Promptlama)
* **Ana Fikir:** Tüm bir sohbet oturumu boyunca geçerli olacak üst düzey talimatları, bağlamı veya rolü "sistem mesajı" olarak vermektir.
* **Ne Zaman Kullanılır:** Modelin tutarlı davranmasını sağlamak ve genel kuralları belirlemek için.
* **Örnek:** *Sistem Mesajı:* `Sen 'Kısa Özetleyicisin'. Tek ve net bir cümle ile özet yapmak birincil görevindir.`

### 9. Explicit Instructions Prompting (Açık Talimatlar)
* **Ana Fikir:** Yanlış yoruma yer bırakmayacak şekilde kristal netliğinde, doğrudan ve dolaysız isteklerde bulunmaktır.
* **Ne Zaman Kullanılır:** Belirli bir çıktı yapısı, uzunluk sınırı veya hariç tutulacak konular olduğunda.
* **Örnek:** `Elmalar hakkında kısa bir paragraf yaz. Sadece besinsel faydalarına ve yaygın türlerine odaklan. Tam olarak 3 cümle olsun. Elma yetiştiriciliğinden bahsetme.`

### 10. Output Priming (Çıktıyı Hazırlama/Tetikleme)
* **Ana Fikir:** İstenen yapıyı veya formatı elde etmek için modele cümlenin veya listenin başını vererek onu yönlendirmektir.
* **Ne Zaman Kullanılır:** JSON, Liste veya belirli bir kalıpta çıktı istendiğinde.
* **Örnek:** `Vanilyalı kekin malzemeleri nelerdir? Lütfen liste halinde ver.\nİşte vanilyalı kekin malzemeleri:\n-`

### 11. Rephrase and Respond (RaR - Yeniden İfade Et ve Yanıtla)
* **Ana Fikir:** Yanıt üretmeden önce modelden, sizin isteğinizi kendi kelimeleriyle tekrar ifade etmesini istemektir.
* **Ne Zaman Kullanılır:** Çok yönlü, karmaşık ve belirsizliğe açık görevlerde.
* **Örnek:** `Bir yolculuk hakkında hikaye istiyorum. Önce ne tür bir yolculuk yazacağını kısaca tanımla... Sonra bu tanıma dayanarak hikayeyi yaz.`

### 12. Step-Back Prompting (Bir Adım Geriye Çekilme)
* **Ana Fikir:** Modeli spesifik soruyu yanıtlamadan önce, konuyla ilgili daha geniş kavramları ve temel prensipleri açıklamaya yönlendirmektir.
* **Ne Zaman Kullanılır:** "Virüsler canlı mıdır?" gibi tartışmalı, karmaşık veya temel ilkelerden beslenen sorularda.
* **Örnek:** `Domates bir meyve mi yoksa sebze mi? Lütfen önce: 1. Botanik olarak meyve nedir? 2. Mutfakta sebze ne anlama gelir? açıkla. Sonra domatesin hangisine girdiğini söyle.`

### 13. Self-Critique & Refinement (Öz-Eleştiri ve İyileştirme)
* **Ana Fikir:** Modelden önce bir yanıt üretmesini, ardından bu yanıtı belirli kriterlere göre eleştirmesini ve son olarak daha iyi bir versiyon yazmasını istemektir.
* **Ne Zaman Kullanılır:** Slogan bulma, hikaye fikirleri, karmaşık açıklamaları iyileştirme.
* **Örnek:** `1. Çevre dostu bir su şişesi için slogan üret. 2. Sloganını eleştir: Akılda kalıcı mı? Zayıf yönleri neler? 3. Eleştirine dayanarak daha iyi bir slogan ver.`

### 14. Goal Decomposition Prompting (Hedefi Parçalara Bölme)
* **Ana Fikir:** Büyük ve karmaşık bir görevi, promptun içinde küçük ve yönetilebilir alt görevlere bölmektir.
* **Ne Zaman Kullanılır:** Etkinlik planlama, bölüm bölüm rapor yazma.
* **Örnek:** `Bir doğa gezisi planla: 1. Gidilecek yer türü öner. 2. 3-4 temel eşya listele. 3. Cumartesi ve Pazar için birer ana aktivite öner. 4. Bir güvenlik ipucu ver.`

### 15. Meta-Prompting (Prompt Üreten Prompt)
* **Ana Fikir:** Bir modelden, başka (veya aynı) bir model için daha iyi bir prompt yazmasını istemektir.
* **Ne Zaman Kullanılır:** Karmaşık bir isteği nasıl ifade edeceğinizi bilemediğinizde.
* **Örnek:** `Bir LLM'den 3 farklı fantastik hikaye fikri isteyeceğim. Her fikirde benzersiz bir karakter, güçlü bir çatışma ve büyülü bir element olmalı. Bunu LLM'e sormak için kullanmam gereken en mükemmel ve detaylı promptu bana yaz.`

### 16. ReAct (Reason + Act / Akıl Yürüt ve Harekete Geç)
* **Ana Fikir:** Karmaşık problemleri çözerken akıl yürütme (problemi parçalama) ile eylemi (bilgi arama veya araç kullanımı simülasyonu) iç içe geçirmektir.
* **Ne Zaman Kullanılır:** Çok adımlı araştırma ve bilgi sentezleme gerektiren görevlerde.
* **Örnek:** `Cevabı bulmak için şu döngüyü izle: Düşünce (Thought): [Akıl yürütme], Eylem (Action): [İhtiyaç duyulan bilgi], Gözlem (Observation): [Varsayımsal sonuç]... Sonra nihai cevabı ver.`

### 17. Thread-of-Thought (ThoT - Düşünce İpliği)
* **Ana Fikir:** Modelin uzun metinlerde veya çok turlu diyaloglarda tutarlı ve birbiriyle bağlantılı bir mantık zinciri (hikaye örgüsü) kurmasını sağlamaktır.
* **Ne Zaman Kullanılır:** Uzun makaleler, denemeler ve adım adım birbirine bağlı açıklamalar.
* **Örnek:** `Bir yasanın nasıl onaylandığını açıkla. Açıklamanı yapılandır: 1. Giriş... 2. Yasa tasarısı... [vb.] Tüm açıklaman boyunca her aşamanın bir öncekini mantıksal olarak takip ettiğinden ve kopmayan bir "iplik/bağ" kurduğundan emin ol.`

---

## 📐 Prompt Mühendisliği Çerçeveleri (Frameworks)

Promptlarınızı standartlaştırmak ve maksimum verim almak için aşağıdaki formülleri kullanabilirsiniz:

### 1. RICCE Formülü
- **R (Role - Rol):** Kim gibi davranacak? (*Örn: Sen bir İK yöneticisisin.*)
- **I (Instruction - Talimat):** Ne yapacak? (*Örn: Bu özgeçmişi incele.*)
- **C (Context - Bağlam):** Arka plan ne? (*Örn: Teknoloji sektöründe bir yazılım pozisyonu için başvuruyor.*)
- **C (Constraints - Kısıtlamalar):** Sınırlar neler? (*Örn: En fazla 3 madde halinde özetle.*)
- **E (Examples - Örnekler):** Örnek çıktı nasıl olmalı? (*Örn: Örnek format: - [Güçlü Yön] ...*)

### 2. TREE Formülü
- **T (Task - Görev):** Bir blog taslağı oluştur.
- **R (Role - Rol):** Uzman metin yazarı.
- **E (Examples - Örnekler):** [Daha önceki başarılı blog yazılarından örnekler]
- **E (Evaluation - Değerlendirme):** Tüm SEO anahtar kelimelerinin kullanıldığından emin ol.

### 3. CRISP Formülü
- **C (Clarity - Netlik):** Hedefi netleştir.
- **R (Role - Rol):** Seyahat uzmanı.
- **I (Input - Girdi):** Paris'e gideceğim.
- **S (Structure - Yapı):** Tablo formatı.
- **P (Purpose - Amaç):** Bütçe dostu ipuçları bulmak.

### 4. Prompt Sandwich (Sandviç Prompt)
Büyük metinler verirken modelin talimatı unutmaması için talimatı başa ve sona koyma tekniği.
- **Üst Ekmek:** `Lütfen aşağıdaki metni özetle ve 50 kelimeyi geçme.`
- **İçerik (Et):** `[Çok uzun bir makale metni]`
- **Alt Ekmek:** `Unutma, özet sadece en önemli noktaları içermeli ve 50 kelimeden kısa olmalı.`

---

## 🏆 Model Üreticilerinden En İyi Uygulamalar (Best Practices)

### OpenAI (ChatGPT / GPT-4) Tavsiyeleri
- **Talimatları başa koyun:** Sistem promptunu veya ana talimatı her zaman en başta verin.
- **Bölücüler (Delimiters) kullanın:** Metinleri, kodları veya verileri ayırmak için `"""`, `---`, veya `###` gibi işaretler kullanın. *(Örn: Aşağıdaki ### işaretleri arasındaki metni özetle.)*
- **"Ne yapılmayacağını" değil, "Ne yapılacağını" söyleyin:** Negatif yönergeler yerine (Şunu yapma), pozitif yönergeler verin (Bunun yerine şunu yap).
- **Formatlı Çıktılar:** Modeller Markdown, JSON ve HTML formatlarında çok başarılıdır. Çıktı formatını net belirtin.

### Anthropic (Claude) Tavsiyeleri
- **XML Etiketleri (Tags) Kullanımı:** Claude, XML etiketlerini tanımak üzere özel olarak eğitilmiştir. Verileri ve talimatları ayırmak için mutlaka XML kullanın.
  - *Örnek:* 
    `<instruction>Aşağıdaki metni analiz et.</instruction>`
    `<text>Buraya analiz edilecek metin gelecek.</text>`
- **Örnekleri ` <example>` etiketi içine alın:** Few-shot prompting yaparken örnekleri XML ile belirginleştirin.
- **Uzun Bağlamları Başa Koyun:** Eğer modele uzun bir döküman veriyorsanız, dökümanı promptun en başına, asıl sorunuzu ise en sona koyun (Claude bu şekilde daha iyi performans gösterir).

---

# 🤖 Multimodal (Çoklu Model) ve Ajanlar (AI Agents)

**Multimodal:** Artık sadece metinle sınırlı değiliz. Görsel, ses ve video gibi farklı veri tiplerini prompt sürecine dahil ederek yapay zekayı bir "göz" veya "kulak" olarak kullanabilirsiniz. *Örnek:* Bir mimari çizim fotoğrafı yükleyip "Bu tasarımdaki güvenlik açıklarını listele" diyebilirsiniz.

**YZ Ajanları (AI Agents):** Modelin sadece bir chatbot değil, bir çalışan gibi davrandığı evre.
- **Akış:** Rol → Durum → Görev → Bitiş formülüyle otonom görevler icra edilir. Uzman geri bildirimiyle süreç iyileştirilir.

**Meta Prompting:** Bir yapay zeka ajanını kullanarak farklı bir yapay zekaya prompt yazdırmak ve tüm süreci AI destekli prompt mühendisliği bazında optimize etmektir. Kendi promptunuzu geliştirmek için modele şunu diyebilirsiniz: *"Benim için mükemmel bir prompt yazmanı istiyorum. Amacım [X]. Bana bu amaca ulaşmak için hangi bilgilere ihtiyacın olduğunu sor."*

---

# ⚠️ Uyarı (Güvenlik ve Etik)

Burada kritik bir olay var: **Güvenlik katmanı sizsiniz.** Yapay zekanın verdiği hiçbir şeye körü körüne güvenmeyin, yapay zekayı hayat rehberiniz olarak görmeyin, çıkan sonucu sorgulayın. Çünkü:

- **Halüsinasyon:** Dil modellerinin çoğu hala gelişmektedir ve halüsinasyon görerek olmayan bir şeyi kendi yapay "hayal güçlerinden" uydurabilirler (Özellikle kaynak sorulduğunda sahte link/makale üretme eğilimleri vardır).
- **Önyargı:** Modelin eğitim verisinden gelen taraflı yaklaşımları filtrelemek gerekir. Model önyargılarından dolayı ırkçılık, renkçilik, çeşitli siyasi gruplara sempati vb. önyargıları sonuca yansıtabilir. Verilen yanıtların objektifliğini her zaman test edin.
