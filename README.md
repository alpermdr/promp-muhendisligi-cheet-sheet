1. 5 Temel Kavram (The Foundations)
    Görev (Task): Modele ne yapacağını net bir dilde söyleyin.Promptunuzun içinde yapay zekaya persona belirlemek istediğiniz sonuca daha kolay ulaşmanızı sağlayacaktır,örneğin yapay zekaya direkt olarak "bir python hello world kodu"
    demek yerine "sen 20 sene deneyimli bir yazılım mühendisisin python yazılım dilinde bir hello world kodu yaz" dediğinizde dil modeli sadece yazılımla ilgili konuları kapsamına alacaktır ve dil modelinin düşünme süreci son derece kolaylaşacaktır.

    Bağlam (Context): Modelin durumu anlaması için gerekli bilgileri detaylı şekilde verin örneğin bir otelin müşterilerine hitap eden bir video oluşturmak için "A oteli için bir reels videosu oluştur" yazmak yerine "A oteli izmirde bulunuyor
    ve 25-30 yaş arası genç kitleye hitap ediyor bu otel için kitlenin ilgisiniçekebilecek bir reels videosu hazırla"

    Referanslar: Modele takip etmesi için örnekler veya dökümanlar verin.Verdiğiniz dökümanları seçerken yapay zekanın anlamayacağı (silik yazılar,bulanık görseller vb.) dosyalar yerine direkt olarak anlaşılabilir dosyalar vermek yapay zekanın yazı
    ve resimle belirttiğiniz bağlamı anlamasını kolaylaştıracaktır
    
    Değerlendirme: Çıktının istediğiniz kriterlere uyup uymadığını kontrol edin.Eğer kriterler uygun değilse revize edin
    
    İterasyon: Tek seferde mükemmele ulaşmak zordur.Problemi parçalara bölmek ve ayrı promptlarda anlatmak yapay zekanın uzun bağlamlarla uğraşmasını engelleyerek çıkacak sonuçları çok daha nokta atışı vermesini sağlar

2. Multimodal (Çoklu Model)

Artık sadece metinle sınırlı değiliz. Görsel, ses ve video gibi farklı veri tiplerini prompt sürecine dahil ederek yapay zekayı bir "göz" veya "kulak" olarak kullanma aşamasıdır.
3. Uyarı (Güvenlik ve etik)

Burada kritik bir olay var : Güvenlik katmanı sizsiniz yapay zekanın verdiği hiçbirşeye körü körüne güvenmeyin yapay zekayı hayat rehberiniz olarak görmeyin çıkan sonucu sorglayın çünkü:

    Halüsinasyon: Dil modellerinin çoğu hala gelişmektedir ve halüsinasyon görerek olmayan birşeyi kendi yapay "hayal güçlerinden" uydurabilirler.

    Önyargı: Modelin eğitim verisinden gelen taraflı yaklaşımları filtrelemek gerekir.Model önyargılarından dolayı ırkçılık,renkçilik,çeşitli siyasi gruplara sempati vb. önyargıları sonuca yansıtabilir.

4. İleri Teknikler (Advanced Prompting)

Akıl yürütme süreçlerini optimize ettiğimiz yer burası:

    Prompt Zincirleme: Büyük bir görevi küçük prompt parçalarına bölerek tek prompta doldurmaktır.

    Düşünce Zinciri (CoT): Modele "adım adım düşün" diyerek mantıksal hataları azaltarak sıralı şekilde görevleri yapmasını sağlamaktır.

    Düşünce Ağacı (ToT): Farklı çözüm yollarını dallandırıp en iyisini seçmek ve sırasıyla yapay zekaya yaptırmaktır.

5. YZ Ajanları (AI Agents)

Modelin sadece bir chatbot değil, bir çalışan gibi davrandığı evre.
*Akış:Rol → Durum → Görev → Bitiş formülüyle otonom görevler icra edilir. Uzman geri bildirimiyle süreç iyileştirilir.


6. Meta Prompting

Meta prompting bir yapay zeka ajanını kullanarak farklı bir yapay zekaya
prompt yazdırmak ve tüm süreci ai destekli prompt mühendisliği bazında optimize etmektir.
