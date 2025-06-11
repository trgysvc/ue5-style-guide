# [Gamemakin](https://gamemak.in) Unreal Engine Stil Rehberi() {

*A mostly reasonable approach to Unreal Engine 4*

Bu döküman büyük ölçüde  [Airbnb Javascript Style Guide](https://github.com/airbnb/javascript) 'dan esinlenilmiştir.

Çevirmenin notu;
"
Allar'ın popüler Unreal Engine stil rehberinin Türkçeleştirilmiş halini aşağıda bulabilirsiniz. 
Bu rehber, özellikle takım çalışmalarında ve büyük projelerde tutarlılığı, okunabilirliği ve verimliliği artırmak için kritik öneme sahiptir.

Unreal Engine (UE) ile proje geliştirmek, özellikle büyük ekiplerle çalışırken veya projeler karmaşıklaştığında belirli standartların oluşturulmasını gerektirir. 
Tutarlı bir yapı ve isimlendirme kuralı, projenin okunabilirliğini artırır, yeni ekip üyelerinin adaptasyonunu hızlandırır ve genel proje yönetimini kolaylaştırır. 
"

[![Analytics](https://ga-beacon.appspot.com/UA-80567399-1/repo?useReferrer)](#)

## Repo Bildirimi

Bu repo artık https://github.com/Allar/ue5-style-guide adresinde bulunmaktadır.  Bu  deponun  varsayılan dalı  `main`  olarak  yeniden  adlandırılmıştır.

## Bu şu anda UE4 içindir. UE5/v2 için v2 dalına bakın. 
## Linter ve Stil Rehberi Dokümantasyonu

Linter  ve  Stil  Rehberi  hakkında  daha  fazla  teknik  dokümanı  [ReadTheDocs](https://ue4-style-guide.readthedocs.io/en/latest/) adresinde bulabilirsiniz.

## Bu  Stil  Rehberini  Tartışın

Gamemakin  LLC'nin  http://discord.gamemak.in  adresinde  herkese  açık  bir  Discord  kanalı  ve  stil  rehberleri  ve  Linter eklentileri  hakkında  her  şeyi  tartışmak  isterseniz  bir  de  #linter  kanalı  bulunmaktadır.

## Bu Belgeye Bağlantı

Bu stil kılavuzunun her bölümü hem kolay referans hem de kolay bağlantı için numaralandırılmıştır. [http:// ue4.style](http://ue4.style) sonuna bir hashtag ve bölüm numarasını ekleyerek herhangi bir bölüme doğrudan bağlantı  
verebilirsiniz.
Örneğin, birisini bu stil kılavuzunun ilk ilkesine yönlendirmek istiyorsanız, `#0.1`  eklersiniz ve http://ue4.style#0.1 sonucunu elde edersiniz
 
## Çatallar ve Çeviriler

Bu depoya bir çekme isteği için uygun olmayan dikkate değer bir çatallanma veya çeviri  yaptıysanız, lütfen çatallanmayı veya çeviriyi buraya eklemek için bir çekme isteği gönderin.


* [Korece Çeviri](https://github.com/ymkim50/ue4-style-guide/blob/master/README_Kor.md) by ymkim50
* [Rusça Çeviri](https://github.com/CosmoMyzrailGorynych/ue4-style-guide-rus/blob/master/README.md) by CosmoMyzrailGorynych
* [Japonca Çeviri](https://github.com/akenatsu/ue4-style-guide/blob/master/README.jp.md) by akenatsu
* [Çince Çeviri](https://github.com/skylens-inc/ue4-style-guide/blob/master/README.md) by Beijing Skylens Tech.
* [Portekizce Çeviri](https://github.com/danlvr/ue5-style-guide/blob/main/README_PTBR.md) by danlvr.
* [Fransızca Çeviri](https://github.com/Arnaud58/ue5-style-guide/blob/main/README.md) by Arnaud58

## İçindekiler
- [Önemli Terminoloji](#important-terminology)
  - [Seviyeler/Haritalar](#terms-level-map)
  - [Tanımlayıcılar](#terms-identifiers)
  - [Durumlar](#terms-cases)
  - [Değişkenler / Özellikler](#terms-var-prop)
    - [Özellik](#terms-property)
    - [Değişken](#terms-variable)
- [0. İlkeler](#0)
  - [0.1 UE4 projenizin zaten bir stil kılavuzu varsa, onu takip etmelisiniz](#0.1)
  - [0.2 Herhangi bir Unreal Engine 4 projesindeki tüm yapı, varlıklar ve kod, kaç kişi katkıda bulunursa bulunsun, tek bir kişi tarafından oluşturulmuş gibi görünmelidir](#0.2)
  - [0.3 Arkadaşlar, arkadaşlarının kötü stile sahip olmasına izin vermez](#0.3)
  - [0.4 Stil kılavuzu olmayan bir ekip benim ekibim değildir](#0.4)
  - [0.5 Yasayı İhlal Etmeyin](#0.5)
- [00. Küresel Olarak Uygulanan Görüşler](#00)
  - [00.1 Yasak Karakterler](#00.1)
    - [Tanımlayıcılar](#identifiers)
- [1. Varlık Adlandırma Kuralları](#anc)
  - [1.1 Temel Varlık Adı - `Prefix_BaseAssetName_Variant_Suffix`](#base-asset-name)
    - [1.1 Örnekler](#1.1-examples)
  - [1.2 Varlık Adı Değiştiricileri](#asset-name-modifiers)
    - [1.2.1 En Yaygın](#anc-common)
    - [1.2.2 Animasyonlar](#anc-animations)
  - [1.2.3 Yapay Zeka (AI)](#anc-ai)
  - [1.2.4 Blueprints](#anc-bp)
  - [1.2.5 Malzemeler (Materials)](#anc-materials)
  - [1.2.6 Dokular (Textures)](#anc-textures)
    - [1.2.6.1 Doku Paketleme](#anc-textures-packing)
  - [1.2.7 Çeşitli](#anc-misc)
  - [1.2.8 Paper 2D](#anc-paper2d)
  - [1.2.9 Fizik](#anc-physics)
  - [1.2.10 Sesler](#anc-sounds)
  - [1.2.11 Kullanıcı Arayüzü (UI)](#anc-ui)
  - [1.2.12 Efektler](#anc-effects)
- [2. İçerik Dizini Yapısı](#structure)
  - [2e1 Örnek Proje İçerik Yapısı](#2e1)
  - [2.1 Klasör İsimleri](#structure-folder-names)
    - [2.1.1 Her Zaman PascalCase Kullan](#2.1.1)
    - [2.1.2 Asla Boşluk Kullanmayın](#2.1.2)
    - [2.1.3 Asla Unicode Karakterleri ve Diğer Sembolleri Kullanmayın](#2.1.3)
  - [2.2 Projeye Özel Varlıklar İçin En Üst Düzey Klasör Kullanın](#structure-top-level)
    - [2.2.1 Genel Varlık Yok (No Global Assets)](#2.2.1)
    - [2.2.2 Taşıma (Migration) ve Birleştirme (Merge) Çakışmalarını Azaltmak](#2.2.2)
      - [2.2.2e1 Ana Malzeme Örneği](#2.2.2e1)
    - [2.2.3 Risksiz Örnekler, Şablonlar ve Pazar Yeri İçeriği](#2.2.3)
    - [2.2.4 DLC, Alt Projeler ve Yamalar Kolayca Bakımlı](#2.2.4)
  - [2.3 Yerel Test İçin Geliştiriciler Klasörünü Kullanın](#structure-developers)
  - [2.4 Tüm Harita<sup>*</sup> Dosyaları Haritalar Adlı Bir Klasöre Aittir](#structure-maps)
  - [2.5 Kritik Planlar ve Diğer Varlıklar İçin `Core` Klasörünü Kullanın](#structure-core)
  - [2.6 `Assets` veya `AssetTypes` Adlı Klasörler Oluşturmayın](#structure-assettypes)
    - [2.6.1 `Assets` adlı bir klasör oluşturmak gereksizdir](#2.6.1)
    - [2.6.2 `Meshes`, `Textures` veya `Materials` adlı bir klasör oluşturmak gereksizdir](#2.6.2)
  - [2.7 Çok Büyük Varlık Kümeleri Kendi Klasör Düzenlerini Alır](#structure-large-sets)
  - [2.8 `Materyal kütüphanesi`](#structure-material-library)
  - [2.9 Boş Klasör Yok](#structure-no-empty-folders)
- [3. Blueprints](#bp)
  - [3.1 Derleme (Compiling)](#bp-compiling)
  - [3.2 Değişkenler (Variables)](#bp-vars)
    - [3.2.1 Adlandırma](#bp-var-naming)
      - [3.2.1.1 İsimler](#bp-var-naming-nouns)
      - [3.2.1.2 PascalCase](#bp-var-naming-case)
        - [3.2.1.2e Örnekler](#3.2.1.2e)
      - [3.2.1.3 Boolean `b` Öneki](#bp-var-bool-prefix)
      - [3.2.1.4 Boolean Adları](#bp-var-bool-names)
        - [3.2.1.4.1 Genel ve Bağımsız Eyalet Bilgileri](#3.2.1.4.1)
        - [3.2.1.4.2 Karmaşık Durumlar](#3.2.1.4.2)
      - [3.2.1.5 Dikkate Alınan Bağlam](#bp-vars-naming-context)
        - [3.2.1.5e Örnekler](#3.2.1.5e)
      - [3.2.1.6 Atomik Tür Adlarını Dahil Etmeyin](#bp-vars-naming-atomic)
      - [3.2.1.7 Atomik Olmayan Tür Adlarını Dahil Edin](#bp-vars-naming-complex)
      - [3.2.1.8 Diziler (Arrays)](#bp-vars-naming-arrays)
    - [3.2.2 Düzenlenebilir Değişkenler (Editable Variables)](#bp-vars-editable)
      - [3.2.2.1 Araç İpuçları](#bp-vars-editable-tooltips)
      - [3.2.2.2 Kaydırıcı ve Değer Aralıkları (Slider And Value Ranges)](#bp-vars-editable-ranges)
    - [3.2.3 Kategoriler](#bp-vars-categories)
    - [3.2.4 Değişken Erişim Düzeyi](#bp-vars-access)
      - [3.2.4.1 Özel Değişkenler](#bp-vars-access-private)
    - [3.2.5 Gelişmiş Görüntüleme](#bp-vars-advanced)
    - [3.2.6 Geçici Değişkenler](#bp-vars-transient)
    - [3.2.8 Yapılandırma Değişkenleri](#bp-vars-config)
  - [3.3 İşlevler, Olaylar ve Olay Göndericileri](#bp-functions)
    - [3.3.1 İşlev Adlandırma](#bp-funcs-naming)
    - [3.3.1.1 Tüm İşlevler Fiil Olmalıdır](#bp-funcs-naming-verbs)
    - [3.3.1.2 Özellik RepNotify İşlevleri Her Zaman `OnRep_Variable`](#bp-funcs-naming-onrep)
    - [3.3.1.3 Bool Döndüren Bilgi İşlevleri Soru Sormalıdır](#bp-funcs-naming-bool)
    - [3.3.1.4 Olay İşleyicileri ve Göndericiler `On` İle Başlamalıdır](#bp-funcs-naming-eventhandlers)
    - [3.3.1.5 Uzaktan Prosedür Çağrıları Hedef Önekine Sahip Olmalıdır](#bp-funcs-naming-rpcs)
    - [3.3.2 Tüm İşlevlerin Dönüş Düğümleri Olmalı](#bp-funcs-return)
    - [3.3.3 Hiçbir İşlevin 50'den Fazla Düğümü Olmamalıdır](#bp-graphs-funcs-node-limit)
    - [3.3.4 Tüm Genel Fonksiyonların Bir Açıklaması Olmalıdır](#bp-graphs-funcs-description)
    - [3.3.5 Tüm Özel Statik Eklenti `BlueprintCallable` İşlevleri Eklenti Adına Göre Kategorilendirilmelidir](#bp-graphs-funcs-plugin-category)
  - [3.4 Blueprint Grafikleri](#bp-graphs)
    - [3.4.1 Spagetti Yok](#bp-graphs-spaghetti)
    - [3.4.2 Düğümleri Değil Kabloları Hizala](#bp-graphs-align-wires)
    - [3.4.3 Beyaz Yürütme Satırları En Önceliklidir](#bp-graphs-exec-first-class)
    - [3.4.4 Grafikler Makul Şekilde Yorumlanmalıdır](#bp-graphs-block-comments)
    - [3.4.5 Grafikler Uygun Olduğunda Döküm Hatalarını Ele Almalıdır](#bp-graphs-cast-error-handling)
    - [3.4.6 Grafikler Sarkan / Gevşek / Ölü Düğümler Var mı](#bp-graphs-dangling-nodes)
- [4. Statik Ağlar (Static Meshes)](#4)
  - [4.1 Static Mesh UV leri](#s-uvs)
    - [4.1.1 Tüm Ağların UV'leri Olmalı](#s-uvs-no-missing)
    - [4.1.2 Tüm Ağların Işık Haritaları İçin Çakışan UV'leri Olmamalı](#s-uvs-no-overlapping)
  - [4.2 LOD'lar Doğru Şekilde Ayarlanmalı](#s-lods)
  - [4.3 Modüler Soketsiz Varlıklar Izgaraya Temiz Bir Şekilde Yapışmalıdır](#s-modular-snapping)
  - [4.4 Tüm Ağların Çakışması Olmalı](#s-collision)
  - [4.5 Tüm Ağların Doğru Şekilde Ölçeklenmesi Gerekiyor](#s-scaled)
- [5. Niagara](#Niagara)
  - [5.1 ASla Boşluk Kullanma](#ng-rules)
- [6. Levels / Maps](#levels)
  - [6.1 Hata veya Uyarı Yok](#levels-no-errors-or-warnings)
  - [6.2 Aydınlatma Kurulmalı](#levels-lighting-should-be-built)
  - [6.3 No Player Visible Z Fighting](#levels-no-visible-z-fighting)
  - [6.4 Pazar Yeri Belirli Kuralları](#levels-mp-rules)
    - [6.4.1 Genel Bakış Seviyesi (Overview Level)](#levels-mp-rules-overview)
    - [6.4.2 Demo Level](#levels-mp-rules-demo)
- [7. Dokular (Textures)](#textures)
  - [7.1 Boyutlar 2'nin Kuvvetleridir](#textures-dimensions)
  - [7.2 Doku Yoğunluğu Tekdüze Olmalıdır](#textures-density)
  - [7.3 Dokular 8192'den Büyük Olmamalıdır](#textures-max-size)
  - [7.4 Dokular Doğru Şekilde Gruplandırılmalıdır](#textures-group)

## Önemli Terminoloji

<a name="terms-level-map"></a>
##### Levels/Maps

'Harita' kelimesi genellikle ortalama bir kişinin 'seviye' olarak adlandırdığı şeye atıfta bulunur ve birbirinin yerine kullanılabilir. Bu terimin geçmişini [buradan](https://en.wikipedia.org/wiki/Level_(video_gaming)) inceleyin.

<a name="terms-identifiers"></a>
##### Tanımlayıcılar

`Tanımlayıcı`, bir "isim"e benzeyen veya bu işlevi gören herhangi bir şeydir. Örneğin, bir varlığın adı veya daha sonra bir malzemenin adı veya bir plan özelliği, bir değişken veya bir klasör adı veya bir veri tablosu satır adı vb...

<a name="terms-cases"></a>
##### Durumlar


`CaseWordsWhenNaming` için birkaç farklı yol vardır. İşte bazı yaygın büyük harf tipleri:

> ###### PascalCase
>
> Her kelimeyi büyük harfle yazın ve tüm boşlukları kaldırın, örn. `DesertEagle`, `StyleGuide`, `ASeriesOfWords`.
>
> ###### camelCase
>
> İlk harf her zaman küçük harftir ancak sonraki her kelime büyük harfle başlar, örn. `desertEagle`, `styleGuide`, `aSeriesOfWords`.
>
> ###### Snake_case
>
> Kelimeler keyfi olarak büyük veya küçük harfle başlayabilir ancak kelimeler alt çizgiyle ayrılır, örn. `desert_Eagle`, `Style_Guide`, `a_Series_of_Words`.

<a name="terms-var-prop"></a>
##### Değişkenler / Özellikler

Çoğu bağlamda 'değişken' ve 'özellik' kelimeleri birbirinin yerine kullanılabilir. Ancak ikisi de aynı bağlamda birlikte kullanılırsa:

<a name="terms-property"></a>
###### Özellik
Genellikle bir sınıfta tanımlanan bir değişkeni ifade eder. Örneğin, `BP_Barrel` değişkeni `bExploded` ise, `bExploded` `BP_Barrel`'ın bir özelliği olarak ifade edilebilir.

Bir sınıf bağlamında olduğunda, genellikle önceden tanımlanmış verilere erişimi ima etmek için kullanılır.

<a name="terms-variable"></a>
###### Değişken
Genellikle bir fonksiyon argümanı veya bir fonksiyon içindeki yerel bir değişken olarak tanımlanan bir değişkeni ifade eder.

Bir sınıf bağlamında olduğunda, genellikle tanımı ve ne içereceği hakkında tartışmayı iletmek için kullanılır.

<a name="0"></a>
## 0. İlkeler

Bu ilkeler [idomatic.js stil kılavuzundan](https://github.com/rwaldron/idiomatic.js/) uyarlanmıştır.

<a name="0.1"></a>
### 0.1 UE4 projenizde zaten bir stil kılavuzu varsa, onu takip etmelisiniz

Önceden var olan bir stil kılavuzu olan bir proje üzerinde veya bir ekiple çalışıyorsanız, buna saygı gösterilmelidir. Var olan bir stil kılavuzu ile bu kılavuz arasındaki herhangi bir tutarsızlık, var olana atfedilmelidir.

Stil kılavuzları canlı belgeler olmalıdır. Değişikliğin tüm kullanımlara fayda sağladığını düşünüyorsanız, mevcut bir stil kılavuzunda ve bu kılavuzda stil kılavuzu değişiklikleri önermelisiniz.

> #### "Stil konusunda tartışmaların bir anlamı yok. Bir stil kılavuzu olmalı ve onu takip etmelisiniz."
> [_Rebecca Murphey_](https://rmurphey.com)

<a name="0.2"></a>
### 0.2 Herhangi bir Unreal Engine 4 projesindeki tüm yapı, varlıklar ve kod, kaç kişi katkıda bulunursa bulunsun, tek bir kişi tarafından oluşturulmuş gibi görünmelidir

Bir projeden diğerine geçmek, stil ve yapının yeniden öğrenilmesine neden olmamalıdır. Bir stil kılavuzuna uymak, gereksiz tahminleri ve belirsizlikleri ortadan kaldırır.

Ayrıca, stil hakkında düşünmeye gerek olmadığından daha üretken bir oluşturma ve bakım sağlar. Sadece talimatları izleyin. Bu stil kılavuzu, en iyi uygulamalar düşünülerek yazılmıştır; bu da bu stil kılavuzunu izleyerek izlenmesi zor sorunları da en aza indireceğiniz anlamına gelir.

<a name="0.3"></a>
### 0.3 Arkadaşlar, arkadaşlarının kötü bir stile sahip olmasına izin vermez

Birinin bir stil kılavuzuna aykırı veya stil kılavuzu olmadan çalıştığını görürseniz, onu düzeltmeye çalışın.

Bir ekip içinde çalışırken veya [Unreal Slackers](http://join.unrealslackers.org/) gibi bir topluluk içinde tartışırken, insanlar tutarlı olduğunda yardım etmek ve yardım istemek çok daha kolaydır. Kimse birinin Blueprint spagettisini çözmeye veya isimleri anlayamadıkları varlıklarla uğraşmaya yardım etmekten hoşlanmaz.

Çalışmaları farklı ancak tutarlı ve mantıklı bir stil kılavuzuna uyan birine yardım ediyorsanız, buna uyum sağlayabilmelisiniz. Herhangi bir stil kılavuzuna uymuyorlarsa, lütfen onları buraya yönlendirin.
<a name="0.4"></a>

### 0.4 Stil kılavuzu olmayan bir ekip benim ekibim değildir

Bir Unreal Engine 4 ekibine katıldığınızda, ilk sorularınızdan biri "Bir stil kılavuzunuz var mı?" olmalıdır. Cevap hayırsa, bir ekip olarak çalışma yetenekleri konusunda şüpheci olmalısınız.

<a name="0.5"></a>
### 0.5 Yasayı İhlal Etmeyin

Gamemakin LLC bir avukat değildir, ancak lütfen bir projeye aşağıdakiler dahil ancak bunlarla sınırlı olmamak üzere yasa dışı eylemler ve davranışlar getirmeyin:

* Dağıtım hakkınız olmayan içerikleri dağıtmayın
* Başkalarının telif hakkı veya ticari marka materyallerini ihlal etmeyin
* İçerik çalmayın
* İçerik üzerindeki lisans kısıtlamalarına uyun, örneğin atıf gerektiğinde atıf yapın

<a name="00"></a>
## 00. Küresel Olarak Uygulanan Görüşler

@TODO: Bu bölümü 1 yapın ve bu belgeyi buna göre güncelleyin. Ya da belki de yapmayız?

<a name="00.1"></a>
### 00.1 Yasak Karakterler

<a name="identifiers-1"></a>
#### Tanımlayıcılar

Herhangi bir türdeki herhangi bir `Tanımlayıcı`da, kesinlikle zorunlu olmadıkça **asla** aşağıdakileri kullanmayın:

* Herhangi bir türdeki boşluk
* Ters eğik çizgiler `\`
* Semboller, örn. `#!@$%`
* Herhangi bir Unicode karakteri

Herhangi bir `Tanımlayıcı` mümkün olduğunda yalnızca aşağıdaki karakterlere sahip olmaya çalışmalıdır (RegEx `[A-Za-z0-9_]+`)

* ABCDEFGHIJKLMNOPQRSTUVWXYZ
* abcdefghijklmnopqrstuvwxyz
* 1234567890
* _ (tutumlu bir şekilde)

Bunun mantığı, bunun tüm tüm platformlarda tüm araçlarda veri ve kontrol etmediğiniz koddaki tanımlayıcılar için potansiyel olarak kötü karakter işleme nedeniyle kesintiyi önlemeye yardımcı olur.

<a name="anc"></a>
<a name="1"></a>
## 1. Varlık Adlandırma Kuralları

Adlandırma kuralları yasa olarak ele alınmalıdır. Bir adlandırma kuralına uyan bir proje, varlıklarının inanılmaz bir kolaylıkla yönetilmesini, aranmasını, ayrıştırılmasını ve sürdürülmesini sağlayabilir.

Çoğu şey, genellikle varlık türünün kısaltması ve ardından alt çizgi gelen öneklerle ön eklenmiştir.

<a name="base-asset-name"></a>
<a name="1.1"></a>
### 1.1 Temel Varlık Adı - `Prefix_BaseAssetName_Variant_Suffix`

Tüm varlıkların bir _Temel Varlık Adı_ olmalıdır. Temel Varlık Adı, ilgili varlıkların mantıksal bir gruplamasını temsil eder. Bu mantıksal grubun parçası olan herhangi bir varlık `Prefix_BaseAssetName_Variant_Suffix` standardını takip etmelidir.

`Prefix_BaseAssetName_Variant_Suffix` modelini akılda tutmak ve sağduyuyu kullanmak genellikle iyi varlık adlarını garantilemek için yeterlidir. Her bir öğeyle ilgili bazı ayrıntılı kurallar şunlardır.

`Prefix` ve `Suffix` varlık türüne göre aşağıdaki [Asset Name Modifier](#asset-name-modifiers) tabloları aracılığıyla belirlenmelidir.

`BaseAssetName` bu varlık grubunun bağlamıyla ilgili kısa ve kolayca tanınabilir bir adla belirlenmelidir. Örneğin, Bob adında bir karakteriniz varsa, Bob'un tüm varlıkları `Bob`'un `BaseAssetName`'ine sahip olacaktır.

Varlıkların benzersiz ve belirli varyasyonları için `Variant`, bir varlığın temel adının bir alt kümesi olan varlıkların mantıksal gruplandırmasını temsil eden kısa ve kolayca tanınabilir bir addır. Örneğin, Bob'un birden fazla görünümü varsa, bu görünümler yine de `Bob`'u `BaseAssetName` olarak kullanmalı ancak tanınabilir bir `Variant` içermelidir. 'Evil' görünümü `Bob_Evil` olarak ve 'Retro' görünümü `Bob_Retro` olarak anılır.

Varlıkların benzersiz ancak genel varyasyonları için `Variant`, `01` ile başlayan iki basamaklı bir sayıdır. Örneğin, tanımlanamayan kayalar üreten bir ortam sanatçınız varsa, bunlara `Rock_01`, `Rock_02`, `Rock_03` vb. adları verilir. Nadir istisnalar dışında, asla üç basamaklı bir varyant numarası talep etmemelisiniz. 100'den fazla varlığınız varsa, bunları farklı temel adlarla düzenlemeyi veya birden fazla varyant adı kullanmayı düşünmelisiniz.

Varlık varyantlarınızın nasıl yapıldığına bağlı olarak, varyant adlarını birbirine zincirleyebilirsiniz. Örneğin, bir Arch Viz projesi için döşeme varlıkları oluşturuyorsanız, `Flooring` temel adını, `Flooring_Marble_01`, `Flooring_Maple_01`, `Flooring_Tile_Squares_01` gibi zincirlenmiş varyantlarla kullanmalısınız.

<a name="1.1-examples"></a>
#### 1.1 Örnekler

##### 1.1e1 Bob

| Varlık Türü             | Varlık Adı                                                 |
| ----------------------- | ---------------------------------------------------------- |
| Skeletal Mesh           | SK_Bob                                                     |
| Material                | M_Bob                                                      |
| Texture (Diffuse/Albedo)| T_Bob_D                                                    |
| Texture (Normal)        | T_Bob_N                                                    |
| Texture (Evil Diffuse)  | T_Bob_Evil_D                                               |

##### 1.1e2 Rocks

| Varlık Türü             | Varlık Adı                                                 |
| ----------------------- | ---------------------------------------------------------- |
| Static Mesh (01)        | S_Rock_01                                                  |
| Static Mesh (02)        | S_Rock_02                                                  |
| Static Mesh (03)        | S_Rock_03                                                  |
| Material                | M_Rock                                                     |
| Material Instance (Snow)| MI_Rock_Snow                                               |

<a name="asset-name-modifiers"></a>
<a name="1.2"></a>
### 1.2 Varlık Adı Değiştiricileri

Bir varlığı adlandırırken, varlığın [Temel Varlık Adı] (#base-asset-name) ile kullanılacak önek ve soneki belirlemek için bu tabloları kullanın.

<a name="anc-common"></a>
<a name="1.2.1"></a>
#### 1.2.1 En Yaygın

| Varlık Türü             | Önek       | Sonek      | Notlar                           |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Level / Map             |            |            | [Maps adlı bir klasörde olmalıdır.](#2.4) |
| Level (Persistent)      |            | _P         |                                  |
| Level (Audio)           |            | _Audio     |                                  |
| Level (Lighting)        |            | _Lighting  |                                  |
| Level (Geometry)        |            | _Geo       |                                  |
| Level (Gameplay)        |            | _Gameplay  |                                  |
| Blueprint               | BP_        |            |                                  |
| Material                | M_         |            |                                  |
| Static Mesh             | S_         |            | Many use SM_. Biz S_ Kullanırız. |
| Skeletal Mesh           | SK_        |            |                                  |
| Texture                 | T_         | _?         | Bakın [Dokular](#anc-textures)   |
| Particle System         | PS_        |            |                                  |
| Widget Blueprint        | WBP_       |            |                                  |

<a name="anc-animations"></a>
<a name="1.2.2"></a>
#### 1.2.2 Animasyonlar

| Varlık Türü             | Önek       | Sonek      | Notlar                           |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Aim Offset              | AO_        |            |                                  |
| Aim Offset 1D           | AO_        |            |                                  |
| Animation Blueprint     | ABP_       |            |                                  |
| Animation Composite     | AC_        |            |                                  |
| Animation Montage       | AM_        |            |                                  |
| Animation Sequence      | A_         |            |                                  |
| Blend Space             | BS_        |            |                                  |
| Blend Space 1D          | BS_        |            |                                  |
| Level Sequence          | LS_        |            |                                  |
| Morph Target            | MT_        |            |                                  |
| Paper Flipbook          | PFB_       |            |                                  |
| Rig                     | Rig_       |            |                                  |
| Skeletal Mesh           | SK_        |            |                                  |
| Skeleton                | SKEL_      |            |                                  |

<a name="anc-ai"></a>
<a name="1.2.3"></a>
### 1.2.3 Yapay Zeka (AI) 

| Varlık Türü             | Önek       | Sonek      | Notlar                           |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| AI Controller           | AIC_       |            |                                  |
| Behavior Tree           | BT_        |            |                                  |
| Blackboard              | BB_        |            |                                  |
| Decorator               | BTDecorator_ |          |                                  |
| Service                 | BTService_ |            |                                  |
| Task                    | BTTask_    |            |                                  |
| Environment Query       | EQS_       |            |                                  |
| EnvQueryContext         | EQS_       | Context    |                                  |

<a name="anc-bp"></a>
<a name="1.2.4"></a>
### 1.2.4 Blueprints

| Varlık Türü             | Önek       | Sonek      | Notlar                           |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Blueprint               | BP_        |            |                                  |
| Blueprint Component     | BP_        | Component  | I.e. BP_InventoryComponent       |
| Blueprint Function Library | BPFL_   |            |                                  |
| Blueprint Interface     | BPI_       |            |                                  |
| Blueprint Macro Library | BPML_      |            | Do not use macro libraries if possible. |
| Enumeration             | E          |            | No underscore.                   |
| Structure               | F or S     |            | No underscore.                   |
| Tutorial Blueprint      | TBP_       |            |                                  |
| Widget Blueprint        | WBP_       |            |                                  |

<a name="anc-materials"></a>
<a name="1.2.5"></a>
### 1.2.5 Malzemeler

| Varlık Türü                   | Önek       | Sonek      | Notlar                           |
| ----------------------------- | ---------- | ---------- | -------------------------------- |
| Material                      | M_         |            |                                  |
| Material (Post Process)       | PP_        |            |                                  |
| Material Function             | MF_        |            |                                  |
| Material Instance             | MI_        |            |                                  |
| Material Parameter Collection | MPC_       |            |                                  |
| Subsurface Profile            | SP_        |            |                                  |
| Physical Materials            | PM_        |            |                                  |
| Decal                         | M_, MI_    | _Decal     |                                  |

<a name="anc-textures"></a>
<a name="1.2.6"></a>
### 1.2.6 Dokular

| Varlık Türü             | Önek       | Sonek      | Notlar                           |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Texture                 | T_         |            |                                  |
| Texture (Diffuse/Albedo/Base Color)| T_ | _D      |                                  |
| Texture (Normal)        | T_         | _N         |                                  |
| Texture (Roughness)     | T_         | _R         |                                  |
| Texture (Alpha/Opacity) | T_         | _A         |                                  |
| Texture (Ambient Occlusion) | T_     | _O         |                                  |
| Texture (Bump)          | T_         | _B         |                                  |
| Texture (Emissive)      | T_         | _E         |                                  |
| Texture (Mask)          | T_         | _M         |                                  |
| Texture (Specular)      | T_         | _S         |                                  |
| Texture (Metallic)      | T_         | _M         |                                  |
| Texture (Packed)        | T_         | _*         | See notes below about [packing](#anc-textures-packing). |
| Texture Cube            | TC_        |            |                                  |
| Media Texture           | MT_        |            |                                  |
| Render Target           | RT_        |            |                                  |
| Cube Render Target      | RTC_       |            |                                  |
| Texture Light Profile   | TLP        |            |                                  |

<a name="anc-textures-packing"></a>
<a name="1.2.6.1"></a>
#### 1.2.6.1 Doku Paketleme
Birden fazla doku verisi katmanını tek bir dokuya paketlemek yaygın bir uygulamadır. Bunun bir örneği, Emissive, Roughness, Ambient Occlusion'ı sırasıyla bir dokunun Kırmızı, Yeşil ve Mavi kanalları olarak paketlemektir. Son eki belirlemek için, yukarıdan verilen son ek harflerini bir araya getirin, örn. `_ERO`.

> Yaygın/Albedo'nuzun alfa kanalına bir Alfa/Opaklık katmanı eklemek genellikle kabul edilebilir ve bu yaygın bir uygulama olduğundan, `_D` son ekine `A` eklemek isteğe bağlıdır.

Bir dokuya 4 kanal veri (RGBA) paketlemek, Alfa/Opaklık maskesi hariç, Yaygın/Albedo'nun alfa kanalında alfa kanalı olan bir doku, alfa kanalı olmayan bir dokudan daha fazla ek yük getirdiğinden önerilmez.

<a name="anc-misc"></a>
<a name="1.2.7"></a>
### 1.2.7 Çeşitli

| Varlık Türü                | Önek       | Sonek      | Notlar                           |
| -------------------------- | ---------- | ---------- | -------------------------------- |
| Animated Vector Field      | VFA_       |            |                                  |
| Camera Anim                | CA_        |            |                                  |
| Color Curve                | Curve_     | _Color     |                                  |
| Curve Table                | Curve_     | _Table     |                                  |
| Data Asset                 | *_         |            | Prefix should be based on class. |
| Data Table                 | DT_        |            |                                  |
| Float Curve                | Curve_     | _Float     |                                  |
| Foliage Type               | FT_        |            |                                  |
| Force Feedback Effect      | FFE_       |            |                                  |
| Landscape Grass Type       | LG_        |            |                                  |
| Landscape Layer            | LL_        |            |                                  |
| Matinee Data               | Matinee_   |            |                                  |
| Media Player               | MP_        |            |                                  |
| File Media Source          | FMS_       |            |                                  |
| Object Library             | OL_        |            |                                  |
| Redirector                 |            |            | These should be fixed up ASAP.   |
| Sprite Sheet               | SS_        |            |                                  |
| Static Vector Field        | VF_        |            |                                  |
| Substance Graph Instance   | SGI_       |            |                                  |
| Substance Instance Factory | SIF_       |            |                                  |
| Touch Interface Setup      | TI_        |            |                                  |
| Vector Curve               | Curve_     | _Vector    |                                  |

<a name="anc-paper2d"></a>
<a name="1.2.8"></a>
### 1.2.8 Paper 2D

| Varlık Türü             | Önek       | Sonek      | Notlar                           |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Paper Flipbook          | PFB_       |            |                                  |
| Sprite                  | SPR_       |            |                                  |
| Sprite Atlas Group      | SPRG_      |            |                                  |
| Tile Map                | TM_        |            |                                  |
| Tile Set                | TS_        |            |                                  |

<a name="anc-physics"></a>
<a name="1.2.9"></a>
### 1.2.9 Fizik

| Varlık Türü             | Önek       | Sonek      | Notlar                           |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Physical Material       | PM_        |            |                                  |
| Physics Asset           | PHYS_      |            |                                  |
| Destructible Mesh       | DM_        |            |                                  |

<a name="anc-sounds"></a>
<a name="1.2.10"></a>
### 1.2.10 Ses

| Varlık Türü             | Önek       | Sonek      | Notlar                           |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Dialogue Voice          | DV_        |            |                                  |
| Dialogue Wave           | DW_        |            |                                  |
| Media Sound Wave        | MSW_       |            |                                  |
| Reverb Effect           | Reverb_    |            |                                  |
| Sound Attenuation       | ATT_       |            |                                  |
| Sound Class             |            |            | No prefix/suffix. Should be put in a folder called SoundClasses |
| Sound Concurrency       |            | _SC        | Should be named after a SoundClass |
| Sound Cue               | A_         | _Cue       |                                  |
| Sound Mix               | Mix_       |            |                                  |
| Sound Wave              | A_         |            |                                  |

<a name="anc-ui"></a>
<a name="1.2.11"></a>
### 1.2.11 Kullanıcı Arayüzü

| Varlık Türü             | Önek       | Sonek      | Notlar                           |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Font                    | Font_      |            |                                  |
| Slate Brush             | Brush_     |            |                                  |
| Slate Widget Style      | Style_     |            |                                  |
| Widget Blueprint        | WBP_       |            |                                  |

<a name="anc-effects"></a>
<a name="1.2.12"></a>
### 1.2.12 Efektler

| Varlık Türü             | Önek       | Sonek      | Notlar                           |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Particle System         | PS_        |            |                                  |
| Material (Post Process) | PP_        |            |                                  |

**[⬆ Back to Top](#table-of-contents)**

<a name="2"></a>
<a name="structure"></a>
## 2. İçerik Dizin Yapısı

Varlık adları kadar önemli olan bir projenin dizin yapısı stili de kanun olarak kabul edilmelidir. Varlık adlandırma kuralları ve içerik dizin yapısı el ele gider ve bunlardan birinin ihlali gereksiz kaosa neden olur.

Bir UE4 projesinin içeriğini düzenlemenin birden fazla yolu vardır. Bu stilde, varlık türlerini klasörlerle gruplayan başka bir yaygın yapı yerine, belirli bir türdeki varlıkları bulmak için varlıklarla çalışanlar için İçerik Tarayıcısının filtreleme ve arama yeteneklerine daha fazla dayanan bir yapı kullanacağız.

> Yukarıdaki [adlandırma kuralı] (#1.2) önekini kullanıyorsanız, `Mesheler', `Dokular' ve `Malzemeler' gibi benzer türdeki varlıkları içeren klasörler kullanmak gereksiz bir uygulamadır, çünkü varlık türleri zaten hem öneke göre sıralanmakta hem de içerik tarayıcısında filtrelenebilmektedir.

> <a name="2e1"><a>
### 2e1 Örnek Proje Klasör Yapısı 
<pre>
|-- Content
    |-- <a href="#2.2">GenericShooter</a>
        |-- Art
        |   |-- Industrial
        |   |   |-- Ambient
        |   |   |-- Machinery
        |   |   |-- Pipes
        |   |-- Nature
        |   |   |-- Ambient
        |   |   |-- Foliage
        |   |   |-- Rocks
        |   |   |-- Trees
        |   |-- Office
        |-- Characters
        |   |-- Bob
        |   |-- Common
        |   |   |-- <a href="#2.7">Animations</a>
        |   |   |-- Audio
        |   |-- Jack
        |   |-- Steve
        |   |-- <a href="#2.1.3">Zoe</a>
        |-- <a href="#2.5">Core</a>
        |   |-- Characters
        |   |-- Engine
        |   |-- <a href="#2.1.2">GameModes</a>
        |   |-- Interactables
        |   |-- Pickups
        |   |-- Weapons
        |-- Effects
        |   |-- Electrical
        |   |-- Fire
        |   |-- Weather
        |-- <a href="#2.4">Maps</a>
        |   |-- Campaign1
        |   |-- Campaign2
        |-- <a href="#2.8">MaterialLibrary</a>
        |   |-- Debug
        |   |-- Metal
        |   |-- Paint
        |   |-- Utility
        |   |-- Weathering
        |-- Placeables
        |   |-- Pickups
        |-- Weapons
            |-- Common
            |-- Pistols
            |   |-- DesertEagle
            |   |-- RocketPistol
            |-- Rifles
</pre>

Bu yapının nedenleri aşağıdaki alt bölümlerde listelenmiştir.

<a name="2.1"></a>
<a name="structure-folder-names"><a>
### 2.1 Klasör Adları

Bunlar içerik yapısındaki herhangi bir klasörü adlandırmak için genel kurallardır.

<a name="2.1.1"></a>
#### 2.1.1 Her Zaman PascalCase Kullanın[<sup>*</sup>](#terms-cases)

PascalCase, bir adı büyük harfle başlatmayı ve ardından boşluk kullanmak yerine, takip eden her sözcüğün de büyük harfle başlamasını ifade eder. Örneğin, `DesertEagle`, `RocketPistol` ve `ASeriesOfWords`.

Bkz. [Cases](#terms-cases).

<a name="2.1.2"></a>
#### 2.1.2 Asla Boşluk Kullanmayın

[2.1.1](#2.1.1)'i güçlendirerek, asla boşluk kullanmayın. Boşluklar çeşitli mühendislik araçlarının ve toplu işlemlerin başarısız olmasına neden olabilir. İdeal olarak, projenizin kökü de boşluk içermez ve `C:\Users\My Name\My Documents\Unreal Projects` yerine `D:\Project` gibi bir yerde bulunur.

<a name="2.1.3"></a>
#### 2.1.3 Asla Unicode Karakterleri ve Diğer Sembolleri Kullanmayın

Oyun karakterlerinizden birinin adı 'Zoë' ise, klasör adı `Zoe` olmalıdır. Unicode karakterleri, mühendislik aracı için [Spaces](#2.1.2)'den daha kötü olabilir ve UE4'ün bazı bölümleri de yollarda Unicode karakterlerini desteklemez.

Bununla ilgili olarak, projenizde [açıklanamayan sorunlar](https://answers.unrealengine.com/questions/101207/undefined.html) varsa ve bilgisayarınızın kullanıcı adı bir Unicode karakterine sahipse (yani adınız `Zoë` ise), `Belgelerim` klasörünüzde bulunan herhangi bir proje bu sorundan muzdarip olacaktır. Genellikle projenizi `D:\Project` gibi bir yere taşımak bu gizemli sorunları çözecektir.

`a-z`, `A-Z` ve `0-9` dışındaki `@`, `-`, `_`, `,`, `*` ve `#` gibi diğer karakterleri kullanmak da diğer platformlarda, kaynak denetiminde ve daha zayıf mühendislik araçlarında beklenmeyen ve izlenmesi zor sorunlara yol açabilir.

<a name="2.2"></a>
<a name="structure-top-level"><a>
### 2.2 Projeye Özgü Varlıklar İçin En Üst Düzey Klasör Kullanın

Bir projenin tüm varlıkları, projenin adını taşıyan bir klasörde bulunmalıdır. Örneğin, projenizin adı 'Generic Shooter' ise, _tüm_ içeriği `Content/GenericShooter` klasöründe bulunmalıdır.

> `Developers` klasörü, projenizin dayandığı varlıklar için değildir ve bu nedenle projeye özgü değildir. Bununla ilgili ayrıntılar için [Developer Folders](#2.3) bölümüne bakın.

Bu yaklaşımın birden fazla nedeni vardır.

<a name="2.2.1"></a>
#### 2.2.1 Global Varlık yok (No Global Assets)

Kod stili kılavuzlarında genellikle global ad alanını kirletmemeniz gerektiği yazılır ve bu da aynı ilkeyi izler. Varlıkların bir proje klasörünün dışında var olmasına izin verildiğinde, klasörde olmayan varlıklar varlıkları organize etmemek gibi kötü bir davranışı teşvik ettiğinden, katı bir yapı düzenini uygulamak genellikle çok daha zor hale gelir.

Her varlığın bir amacı olmalıdır, aksi takdirde bir projeye ait olmaz. Bir varlık deneysel bir testse ve proje tarafından kullanılmaması gerekiyorsa, [`Geliştirici`](#2.3) klasörüne konulmalıdır.

<a name="2.2.2"></a>
#### 2.2.2 Taşıma (Migration) ve Birleştirme (Merge) Çakışmalarını Azaltmak

Taşıma (Migration) ve Birleştirme (Merge) Çakışmalarını Azaltın

Birden fazla proje üzerinde çalışırken, bir ekibin her ikisi için de yararlı bir şey yapmışlarsa varlıkları bir projeden diğerine kopyalaması yaygındır. Bu gerçekleştiğinde, kopyalamayı gerçekleştirmenin en kolay yolu, yalnızca seçili varlığı değil, tüm bağımlılıklarını da kopyalayacağı için İçerik Tarayıcısının Göç işlevini kullanmaktır.

Bu bağımlılıklar başınızı kolayca derde sokabilir. İki projenin varlıklarının üst düzey bir klasörü yoksa ve benzer şekilde adlandırılmış veya daha önce taşınmış varlıklara sahiplerse, yeni bir taşıma işlemi yanlışlıkla mevcut varlıklardaki tüm değişiklikleri silebilir.

Bu ayrıca Epic'in Marketplace personelinin gönderilen varlıklar için aynı politikayı uygulamasının temel nedenidir.

Bir taşımadan sonra, varlıkların güvenli bir şekilde birleştirilmesi, içerik tarayıcısındaki 'Referansları Değiştir' aracı kullanılarak yapılabilir ve ayrıca bir projenin en üst düzey klasörüne ait olmayan varlıkların açıkça bir birleştirme beklediği de açıktır. Varlıklar birleştirildikten ve tamamen taşındıktan sonra, İçerik ağacınızda başka bir en üst düzey klasör olmamalıdır. Bu yöntem, gerçekleşen tüm taşımaları tamamen güvenli hale getirmek için %100 garantilidir.

<a name="2.2.2e1"></a>
##### 2.2.2e1 Ana Malzeme Örneği

Örneğin, bir projede başka bir projede kullanmak istediğiniz bir ana malzeme oluşturduğunuzu ve bu varlığı başka bir projeye taşıdığınızı varsayalım. Bu varlık en üst düzey klasörde değilse, `Content/MaterialLibrary/M_Master` gibi bir adı olabilir. Hedef projede halihazırda bir ana materyal yoksa, bu sorunsuz çalışmalıdır.

Bir veya her iki projede çalışma ilerledikçe, normal geliştirme süreci nedeniyle ilgili ana materyalleri belirli projelerine göre uyarlanmak üzere değişebilir.

Sorun, örneğin, bir proje için bir sanatçı güzel bir genel modüler statik ağlar seti oluşturduğunda ve birisi bu statik ağlar setini ikinci projeye dahil etmek istediğinde ortaya çıkar. Varlıkları oluşturan sanatçı, talimat verildiği gibi `Content/MaterialLibrary/M_Master`'a dayalı materyal örneklerini kullandıysa, bir geçiş gerçekleştirildiğinde daha önce geçiş yapılan `Content/MaterialLibrary/M_Master` varlığı için büyük bir çakışma olasılığı vardır.

Bu sorunun tahmin edilmesi ve hesaba katılması zor olabilir. Statik ağları taşıyan kişi, her iki projenin ana materyalinin geliştirilmesine aşina olan kişi olmayabilir ve söz konusu statik ağların ana materyale dayanan materyal örneklerine dayandığının farkında bile olmayabilir. Ancak Migrate aracının çalışması için tüm bağımlılık zincirine ihtiyaç vardır ve bu nedenle bu varlıkları diğer projeye kopyaladığında `Content/MaterialLibrary/M_Master` öğesini almak zorunda kalacak ve mevcut varlığın üzerine yazacaktır.

Bu noktada, her iki projenin ana materyalleri _herhangi bir şekilde_ uyumsuzsa, yalnızca varlıklar en üst düzey klasörde saklanmadığı için, bir projenin tüm materyal kütüphanesini ve daha önce taşınmış olabilecek diğer bağımlılıkları bozma riskiyle karşı karşıya kalırsınız. Statik ağların basit taşınması artık çok çirkin bir görev haline geliyor.

<a name="2.2.3"></a>
#### 2.2.3 Örnekler, Şablonlar ve Pazar Yeri İçeriği Risksizdir

[2.2.2](#2.2.2)'ye bir uzantı olarak, bir ekip üyesi pazar yerinden satın aldığı örnek içerik, şablon dosyaları veya varlıkları eklemeye karar verirse, projenizin en üst düzey klasörü benzersiz bir şekilde adlandırılmış olduğu sürece, bu yeni varlıkların projenize müdahale etmeyeceği garanti edilir.

Pazar yeri içeriğinin [en üst düzey klasör kuralına](#2.2) tam olarak uyacağına güvenemezsiniz. İçeriğinin çoğunluğu en üst düzey klasörde bulunan ancak muhtemelen değiştirilmiş Epic örnek içeriğine ve küresel `İçerik` klasörünü kirleten düzey dosyalarına sahip birçok varlık vardır.

[2.2](#2.2)'ye uyduğunuzda, yaşayabileceğiniz en kötü pazar yeri çatışması, iki pazar yeri varlığının da aynı Epic örnek içeriğine sahip olmasıdır. Tüm varlıklarınız, klasörünüze taşımış olabileceğiniz örnek içerikler de dahil olmak üzere projeye özgü bir klasördeyse, projeniz asla bozulmaz.

<a name="2.2.4"></a>
#### 2.2.4 DLC, Alt Projeler ve Yamalar Kolayca Bakım Yapılır

Projeniz DLC yayınlamayı planlıyorsa veya bununla ilişkili birden fazla alt proje varsa ve bunlar ya dışarı aktarılabilir ya da bir derlemede basitçe pişirilemezse, bu projelerle ilgili varlıkların kendi ayrı üst düzey içerik klasörü olmalıdır. Bu, DLC'yi ana proje içeriğinden ayırmayı çok daha kolay hale getirir. Alt projeler de minimum çabayla içeri ve dışarı aktarılabilir. Bir varlığın malzemesini değiştirmeniz veya bir yamada çok belirli bir varlık geçersiz kılma davranışı eklemeniz gerekiyorsa, bu değişiklikleri kolayca bir yama klasörüne koyabilir ve çekirdek projeyi bozma şansı olmadan güvenli bir şekilde çalışabilirsiniz.

<a name="2.3"></a>
<a name="structure-developers"></a>
### 2.3 Yerel Test İçin Geliştiriciler Klasörünü Kullanma

Bir projenin geliştirilmesi sırasında, ekip üyelerinin çekirdek projeyi riske atmadan özgürce deneyebilecekleri bir tür 'kum havuzu'na sahip olması çok yaygındır. Bu çalışma devam ediyor olabileceğinden, bu ekip üyeleri varlıklarını bir projenin kaynak kontrol sunucusuna koymak isteyebilirler. Tüm ekiplerin Geliştirici klasörlerini kullanması gerekmez, ancak bunları kullananlar genellikle kaynak kontrolüne gönderilen varlıklarla ilgili yaygın bir sorunla karşılaşırlar.

Bir ekip üyesinin yanlışlıkla kullanıma hazır olmayan varlıkları kullanması çok kolaydır ve bu varlıklar kaldırıldığında sorunlara neden olur. Örneğin, bir sanatçı modüler bir statik kafes seti üzerinde yineleme yapıyor ve hala boyutlandırma ve ızgara oturtma işlemlerini doğru yapmak için çalışıyor olabilir. Bir dünya oluşturucu bu varlıkları ana proje klasöründe görürse, inanılmaz bir değişikliğe ve/veya kaldırılmaya maruz kalabileceklerini bilmeden bunları bir seviyenin her yerinde kullanabilir. Bu da ekipteki herkesin çözmesi gereken büyük miktarda yeniden çalışmaya neden olur.

Bu modüler varlıklar bir Geliştirici klasörüne yerleştirilmiş olsaydı, dünya oluşturucusunun bunları kullanmak için hiçbir nedeni olmamalıydı ve tüm sorun asla yaşanmazdı. İçerik Tarayıcısı, Geliştirici klasörlerini gizleyecek belirli Görünüm Seçeneklerine sahiptir (varsayılan olarak gizlidirler) ve bu da Geliştirici varlıklarının normal kullanımda yanlışlıkla kullanılmasını imkansız hale getirir.

Varlıklar kullanıma hazır olduğunda, bir sanatçının varlıkları projeye özgü klasöre taşıması ve yönlendiricileri düzeltmesi yeterlidir. Bu, esasen varlıkları deneyselden üretime 'yükseltmektir'.

<a name="2.4"></a>
<a name="structure-maps"></a>
### 2.4 Tüm Harita[<sup>*</sup>](#terms-level-map) Dosyaları Haritalar Adlı Bir Klasöre Aittir

Harita dosyaları inanılmaz derecede özeldir ve her projenin kendi harita adlandırma sistemine sahip olması yaygındır, özellikle de alt seviyelerle veya akış seviyeleriyle çalışıyorlarsa. Belirli proje için hangi harita organizasyon sistemi yerinde olursa olsun, tüm seviyeler `/Content/Project/Maps` dizinine ait olmalıdır.

Birisine nerede olduğunu açıklamak zorunda kalmadan belirli bir haritayı açmasını söyleyebilmek büyük bir zaman tasarrufu ve genel bir 'yaşam kalitesi' iyileştirmesidir. Seviyelerin `Maps` dizininin alt klasörlerinde olması yaygındır, örneğin `Maps/Campaign1/` veya `Maps/Arenas`, ancak buradaki en önemli şey hepsinin `/Content/Project/Maps` dizininde bulunmasıdır.

Bu ayrıca mühendisler için yemek pişirme işini de basitleştirir. Bir yapı süreci için seviyeleri düzenlemek, onlar için keyfi klasörlerde kazmak zorunda kalırlarsa son derece sinir bozucu olabilir. Bir ekibin haritalarının hepsi tek bir yerdeyse, bir yapıda yanlışlıkla bir haritayı pişirmemek çok daha zordur. Ayrıca aydınlatma yapı betiklerini ve QA süreçlerini de basitleştirir.

<a name="2.5"></a>
<a name="structure-core"></a>
### 2.5 Kritik Planlar ve Diğer Varlıklar İçin Bir `Core` Klasörü Kullanın

Bir projenin işleyişi için kesinlikle temel olan varlıklar için `/Content/Project/Core` klasörünü kullanın. Örneğin, temel `GameMode`, `Character`, `PlayerController`, `GameState`, `PlayerState` ve ilgili Planlar burada yaşamalıdır.

Bu, diğer ekip üyeleri için çok net bir "bunlara dokunmayın" mesajı oluşturur. Mühendis olmayanların `Core` klasörüne girmek için çok az nedenleri olmalıdır. İyi bir kod yapısı stilini izleyerek, tasarımcılar oyun oynama ince ayarlarını işlevselliği ortaya çıkaran alt sınıflarda yapmalıdır. Dünya oluşturucuları, temel sınıfları potansiyel olarak kötüye kullanmak yerine belirlenmiş klasörlerde önceden hazırlanmış Planlar kullanmalıdır.

Örneğin, projeniz bir seviyeye yerleştirilebilen toplamalar gerektiriyorsa, bir toplama için temel davranışı tanımlayan `Core/Pickups` içinde temel bir Toplama sınıfı bulunmalıdır. Sağlık veya Cephane gibi belirli toplamalar `/Content/Project/Placeables/Pickups/` gibi bir klasörde bulunmalıdır. Oyun tasarımcıları bu klasörde toplamaları istedikleri gibi tanımlayabilir ve ince ayar yapabilirler, ancak `Core/Pickups` içine dokunmamalıdırlar çünkü bu, proje genelinde toplamaları istemeden bozabilir.


<a name="2.6"></a>
<a name="structure-assettypes"></a>
### 2.6 `Assets` veya `AssetTypes` Adlı Klasörler Oluşturmayın

<a name="2.6.1"></a>
#### 2.6.1 `Assets` adlı bir klasör oluşturmak gereksizdir

All assets are assets. "Tüm varlıklar varlıktır."

<a name="2.6.2"></a>
#### 2.6.2 `Meshes`, `Textures` veya `Materials` adlı klasörler oluşturmak iyi bir pratik değildir.

Tüm varlık adları varlık türleri düşünülerek adlandırılır. Bu klasörler yalnızca gereksiz bilgiler sunar ve bu klasörlerin kullanımı İçerik Tarayıcısının sağladığı sağlam ve kullanımı kolay filtreleme sistemiyle kolayca değiştirilebilir.

`Environment/Rocks/` içinde yalnızca statik ağları mı görüntülemek istiyorsunuz? Statik Ağ filtresini açmanız yeterlidir. Tüm varlıklar doğru şekilde adlandırılırsa, öneklerden bağımsız olarak alfabetik sıraya göre sıralanırlar. Hem statik ağları hem de iskelet ağlarını mı görüntülemek istiyorsunuz? Her iki filtreyi de açmanız yeterlidir. Bu, İçerik Tarayıcısı'nın ağaç görünümünde iki klasörü seçmek için `Control-Click` yapma ihtiyacını ortadan kaldırır.

> Bu ayrıca, çok az fayda karşılığında bir varlığın tam yol adını da genişletir. Statik bir ağ için `S_` öneki yalnızca iki karakterdir, oysa `Meshes/` yedi karakterdir.

Bunu yapmamak, birinin `Materials` klasörüne statik bir ağ veya doku koymasının kaçınılmazlığını da önler.

<a name="2.7"></a>
<a name="structure-large-sets"></a>
### 2.7 Geniş Varlık Setleri Kendi Klasör Yapısına Sahip Olmalıdır.

Bu, [2.6](#2.6) için bir sözde istisna olarak görülebilir.

Her bir varlığın benzersiz bir amaca sahip olduğu çok sayıda ilgili dosyaya sahip belirli varlık türleri vardır. En yaygın ikisi Animasyon ve Ses varlıklarıdır. Bu varlıklardan birbirine ait 15'ten fazlasına sahipseniz, birlikte olmalıdırlar.

For example, animations that are shared across multiple characters should lay in `Characters/Common/Animations` and may have sub-folders such as `Locomotion` or `Cinematic`.

> This does not apply to assets like textures and materials. It is common for a `Rocks` folder to have a large amount of textures if there are a large amount of rocks, however these textures are generally only related to a few specific rocks and should be named appropriately. Even if these textures are part of a [Material Library](#2.8).
> 
<a name="2.8"></a>
<a name="structure-material-library"></a>
### 2.8 `MaterialLibrary`

Projeniz ana malzemeler, katmanlı malzemeler veya varlıkların herhangi bir alt kümesine ait olmayan herhangi bir yeniden kullanılabilir malzeme veya doku kullanıyorsa, bu varlıklar `Content/Project/MaterialLibrary` içinde bulunmalıdır.

Bu şekilde tüm 'küresel' malzemelerin yaşayacak bir yeri olur ve kolayca bulunabilir.

> Bu ayrıca bir proje içinde 'sadece malzeme örneklerini kullan' politikasını uygulamayı inanılmaz derecede kolaylaştırır. Tüm sanatçılar ve varlıklar malzeme örneklerini kullanıyorsa, o zaman var olması gereken tek düzenli malzeme varlıkları bu klasörde olmalıdır. `MaterialLibrary` olmayan herhangi bir klasörde temel malzemeleri arayarak bunu kolayca doğrulayabilirsiniz.

`MaterialLibrary` yalnızca malzemelerden oluşmak zorunda değildir. Paylaşılan yardımcı program dokuları, materyal işlevleri ve bu nitelikteki diğer şeyler de amaçlanan amaçlarını belirten klasörler içinde burada saklanmalıdır. Örneğin, genel gürültü dokuları `MaterialLibrary/Utility` içinde bulunmalıdır.

Herhangi bir test veya hata ayıklama materyali `MaterialLibrary/Debug` içinde olmalıdır. Bu, hata ayıklama materyallerinin bir projeden gönderilmeden önce kolayca çıkarılmasını sağlar ve referans hataları gösterilirse üretim varlıklarının bunları kullanıp kullanmadığını inanılmaz derecede belirgin hale getirir.

<a name="2.9"></a>
<a name="structure-no-empty-folders"></a>
### 2.9 Boş Klasör Yok

Boş klasör olmamalı. İçerik tarayıcısını karıştırırlar.

İçerik tarayıcısında silemeyeceğiniz boş bir klasör olduğunu fark ederseniz, aşağıdakileri yapmalısınız:
1. Kaynak denetimini kullandığınızdan emin olun.
1. Projenizde hemen Fix Up Redirectors'ı çalıştırın. 1. Disk üzerindeki klasöre gidin ve içindeki varlıkları silin.
1. Düzenleyiciyi kapatın.
1. Kaynak denetim durumunuzun senkronize olduğundan emin olun (yani Perforce kullanıyorsanız, içerik dizininizde Reconcile Offline Work çalıştırın)
1. Düzenleyiciyi açın. Her şeyin hala beklendiği gibi çalıştığını doğrulayın. Çalışmıyorsa, geri alın, neyin yanlış gittiğini anlayın ve tekrar deneyin.
1. Klasörün artık gittiğinden emin olun.
1. Değişiklikleri kaynak denetimine gönderin.

**[⬆ Başa Dön](#table-of-contents)**


<a name="3"></a>
<a name="bp"></a>
## 3. Blueprints

Bu bölüm, Plan sınıflarına ve bunların iç işleyişlerine odaklanacaktır. Mümkün olduğunda, stil kuralları [Epic'in Kodlama Standardına](https://docs.unrealengine.com/latest/INT/Programming/Development/CodingStandard) uygundur.

Unutmayın: Blueprintler çok kötü hatalar taşır, dikkatli olun! (Cümle [KorkuVeren](http://github.com/KorkuVeren)

<a name="3.1"></a>
<a name="bp-compiling"></a>
### 3.1 Derleme

Tüm Blueprintler sıfır uyarı ve sıfır hata ile derlenmelidir. Blueprint uyarılarını ve hatalarını hemen düzeltmelisiniz çünkü bunlar çok korkutucu ve beklenmedik davranışlara hızla dönüşebilir.

Bozuk Blueprintler kaynak denetimine *göndermeyin*. Bunları kaynak denetimine kaydetmeniz gerekiyorsa, bunun yerine rafa kaldırın.

Bozuk Blueprintler, bozuk referanslar, beklenmeyen davranışlar, pişirme hataları ve sık sık gereksiz yeniden derleme gibi başka şekillerde ortaya çıkan sorunlara neden olabilir. Bozuk bir Blueprintin tüm oyununuzu bozma gücü vardır.

<a name="3.2"></a>
<a name="bp-vars"></a>
### 3.2 Değişkenler

`variable` ve `property` kelimeleri birbirinin yerine kullanılabilir.

<a name="3.2.1"></a>
<a name="bp-var-naming"></a>
#### 3.2.1 Adlandırma

<a name="3.2.1.1"></a>
<a name="bp-var-naming-nouns"></a>
##### 3.2.1.1 İsimler

Tüm non-boolean değişken isimleri, açık belirsiz olmayan ve tanımlayıcı isimler olmalıdır. 

<a name="3.2.1.2"></a>
<a name="bp-var-naming-case"></a>
##### 3.2.1.2 PascalCase

tüm non-boolean değişkenler [PascalCase](#terms-cases) biçiminde olmalıdır. 

<a name="3.2.1.2e"></a>
###### 3.2.1.2e Örnekler

* `Score`
* `Kills`
* `TargetPlayer`
* `Range`
* `CrosshairColor`
* `AbilityID`

<a name="3.2.1.3"></a>
<a name="bp-var-bool-prefix"></a>
##### 3.2.1.3 Boolean `b` Öneki

Tüm Boolean'lar PascalCase'de adlandırılmalı ancak küçük harfle `b` ile öneklenmelidir.

Örnek: `bDead` and `bEvil` kullan /  `Dead` and `Evil` KULLANMA.

UE4 Blueprint editörleri, değişkenin kullanıcı dostu görünümlerine `b` harfini eklememeleri gerektiğini bilir.

<a name="3.2.1.4"></a>
<a name="bp-var-bool-names"></a>
##### 3.2.1.4 Boolean İsimleri

<a name="3.2.1.4.1"></a>
###### 3.2.1.4.1 Genel ve Bağımsız Durum Bilgileri

Genel bilgileri temsil ediyorsa, tüm boolean'lar mümkün olduğunca açıklayıcı sıfatlar olarak adlandırılmalıdır. Değişkeni bir soru olarak ifade eden `Is` gibi sözcükler eklemeyin. Bu fonksiyonlar için ayrılmıştır.

Örnek: `bDead` ve `bHostile` kullanın `bIsDead` ve `bIsHostile` kullanmayın.

`bRunning` gibi fiiller kullanmamaya çalışın. Fiiller karmaşık durumlara yol açma eğilimindedir.

<a name="3.2.1.4.2"></a>
###### 3.2.1.4.2 Karmaşık Durumlar

Karmaşık ve/veya bağımlı durumları temsil etmek için boolean'lar kullanmayın. Bu, durum ekleme ve kaldırmayı karmaşık hale getirir ve artık kolayca okunamaz hale getirir. Bunun yerine bir numaralandırma kullanın.

Örnek: Bir silahı tanımlarken, bir silah hem yeniden yükleme hem de donatma yapamıyorsa `bReloading` ve `bEquipping` kullanmayın. `EWeaponState` adlı bir numaralandırma tanımlayın ve bunun yerine `WeaponState` adlı bu türde bir değişken kullanın. Bu, silahlara yeni durumlar eklemeyi çok daha kolay hale getirir.

Örnek: `bWalking` veya `bSprinting`'e de ihtiyacınız varsa `bRunning`'i **kullanmayın**. Bu, açıkça tanımlanmış durum adlarına sahip bir numaralandırma olarak tanımlanmalıdır.

<a name="3.2.1.5"></a>
<a name="bp-vars-naming-context"></a>
##### 3.2.1.5 Dikkate Alınan Bağlam

Tüm değişken adları, Blueprint'teki tüm değişken referanslarının her zaman bir bağlamı olacağı için bağlamlarıyla tekrarlı olmamalıdır.

<a name="3.2.1.5e"></a>
###### 3.2.1.5e Örnekler

`BP_PlayerCharacter` adlı bir Blueprint düşünün.

**KÖTÜ**

* `PlayerScore`
* `PlayerKills`
* `MyTargetPlayer`
* `MyCharacterName`
* `CharacterSkills`
* `ChosenCharacterSkin`

All of these variables are named redundantly. It is implied that the variable is representative of the `BP_PlayerCharacter` it belongs to because it is `BP_PlayerCharacter` that is defining these variables.

**İYİ**

* `Score`
* `Kills`
* `TargetPlayer`
* `Name`
* `Skills`
* `Skin`

<a name="3.2.1.6"></a>
<a name="bp-vars-naming-atomic"></a>
##### 3.2.1.6 Atomik Tür Adlarını Dahil Etmeyin

Atomik veya ilkel değişkenler, verileri en basit halleriyle temsil eden değişkenlerdir; örneğin boolean'lar, tam sayılar, kayan noktalı sayılar ve numaralandırmalar.

Dizeler ve vektörler, Blueprints ile çalışırken stil açısından atomik olarak kabul edilir, ancak teknik olarak atomik değildirler.

> Vektörler üç kayan noktadan oluşurken, vektörler genellikle bir bütün olarak işlenebilir, aynı şekilde rotatörler de.

> Metin değişkenlerini atomik olarak _düşünmeyin_, yerelleştirme işlevselliğini gizlice gizlerler. Karakter dizisinin atomik türü `Text` değil `String`'dir.

Atomik değişkenlerin adlarında tür adları olmamalıdır.

Örnek: `Score`, `Kills` ve `Description` kullanın `ScoreFloat`, `FloatKills`, `DescriptionString` kullanmayın.

Bu kuralın tek istisnası, bir değişkenin sayılacak bir şeyin 'bir sayısını' temsil etmesidir _ve_ değişken türü olmayan bir ad kullanıldığında okunması kolay değildir.

Örnek: Bir çit oluşturucunun X sayıda gönderi üretmesi gerekir. X'i `Posts` yerine `NumPosts` veya `PostsCount` içinde saklayın çünkü `Posts` potansiyel olarak `Post` adlı bir değişken türünün Dizisi olarak okunabilir.

<a name="3.2.1.7"></a>
<a name="bp-vars-naming-complex"></a>
##### 3.2.1.7 Atomik Olmayan Tür Adlarını Dahil Edin

Atomik olmayan veya karmaşık değişkenler, verileri atomik değişkenlerin bir koleksiyonu olarak temsil eden değişkenlerdir. `Text` ve `Name` gibi gizli davranışa sahip Yapılar, Sınıflar, Arayüzler ve ilkel öğeler bu kurala uygundur.

> Atomik değişken türündeki bir Dizi, değişkenlerin bir listesi olsa da, Diziler bir değişken türünün 'atomikliğini' değiştirmez.

Bu değişkenler, bağlamlarını dikkate alırken tür adlarını içermelidir.

Bir sınıf, karmaşık bir değişkenin bir örneğine sahipse, yani bir `BP_PlayerCharacter` bir `BP_Hat`'a sahipse, herhangi bir ad değişikliği yapılmadan değişken türü olarak saklanmalıdır.

Örnek: `Hat`, `Flag` ve `Ability` kullanın `MyHat`, `MyFlag` ve `PlayerAbility` kullanmayın.

Bir sınıf, karmaşık bir değişkenin temsil ettiği değere sahip değilse, değişken türüyle birlikte bir isim kullanmalısınız.

Örnek: Bir `BP_Turret`, bir `BP_PlayerCharacter`'ı hedefleme yeteneğine sahipse, hedefini `TargetPlayer` olarak saklamalıdır; çünkü `BP_Turret` bağlamında, sahip olmadığı başka bir karmaşık değişken türüne referans olduğu açık olmalıdır.


<a name="3.2.1.8"></a>
<a name="bp-vars-naming-arrays"></a>
##### 3.2.1.8 Diziler (Arrays)

Diziler yukarıdakiyle aynı adlandırma kurallarını izler, ancak çoğul bir isim olarak adlandırılmalıdır.

Örnek: `Targets`, `Hats` ve `EnemyPlayers` kullanın, `TargetList`, `HatArray`, `EnemyPlayerArray` kullanmayın.


<a name="3.2.2"></a>
<a name="bp-vars-editable"></a>
#### 3.2.2 Düzenlenebilir Değişkenler

Bir planın davranışını yapılandırmak için değerini değiştirmek güvenli olan tüm değişkenler `Düzenlenebilir` olarak işaretlenmelidir.

Tersine, değiştirilmesi güvenli olmayan veya tasarımcılara sunulmaması gereken tüm değişkenler düzenlenebilir olarak işaretlenmemelidir, ancak mühendislik nedenleriyle değişkenin `Spawn'da Açığa Çıkar` olarak işaretlenmesi gerekir.

Değişkenleri keyfi olarak `Düzenlenebilir` olarak işaretlemeyin.

<a name="3.2.2.1"></a>
<a name="bp-vars-editable-tooltips"></a>
##### 3.2.2.1 Tooltips

Düzenlenebilir olarak işaretlenenler de dahil olmak üzere tüm `Düzenlenebilir` değişkenler, `Oluşumda Açığa Çıkar` olarak işaretlenebilmeleri için, `Araç İpucu` alanlarında bu değerin değiştirilmesinin planın davranışını nasıl etkilediğini açıklayan bir açıklamaya sahip olmalıdır.

<a name="3.2.2.2"></a>
<a name="bp-vars-editable-ranges"></a>
##### 3.2.2.2 Kaydırıcı ve Değer Aralıkları (Slider And Value Ranges)

Bir değişkenin _ayarlanmaması_ gereken bir değer varsa, tüm `Düzenlenebilir` değişkenler kaydırıcı ve değer aralıklarını kullanmalıdır.

Örnek: Çit direkleri üreten bir planın `PostsCount` adlı düzenlenebilir bir değişkeni olabilir ve -1 değeri hiçbir anlam ifade etmez. Aralık alanlarını kullanarak en az 0 olarak işaretleyin.

Bir Yapı Komut Dosyasında düzenlenebilir bir değişken kullanılıyorsa, birisinin yanlışlıkla düzenleyiciyi çökertebilecek büyük bir değer atamasını önlemek için makul bir Kaydırıcı Aralığı tanımlanmalıdır.

Bir Değer Aralığı yalnızca bir değerin sınırları biliniyorsa tanımlanmalıdır. Bir Kaydırıcı Aralığı yanlışlıkla büyük sayıda girdiyi engellerken, tanımsız bir Değer Aralığı kullanıcının Kaydırıcı Aralığı dışında 'tehlikeli' olarak değerlendirilebilecek ancak yine de geçerli bir değer belirtmesine olanak tanır.

<a name="3.2.3"></a>
<a name="bp-vars-categories"></a>
#### 3.2.3 Kategoriler

Bir sınıfın yalnızca az sayıda değişkeni varsa, kategoriler gerekli değildir.

Bir sınıfın orta düzeyde değişkeni varsa (5-10), tüm `Düzenlenebilir` değişkenlere varsayılan olmayan bir kategori atanmalıdır. Yaygın bir kategori `Yapılandırma`dır.

Bir sınıfın çok sayıda değişkeni varsa, tüm `Düzenlenebilir` değişkenler temel kategori olarak `Yapılandırma` kategorisini kullanarak alt kategorilere ayrılmalıdır. Düzenlenemeyen değişkenler kullanımlarını açıklayan açıklayıcı kategorilere ayrılmalıdır.

> `|` boru karakterini kullanarak alt kategorileri tanımlayabilirsiniz, yani `Yapılandırma | Animasyonlar`.

Örnek: Bir silah sınıfı değişken kümesi şu şekilde düzenlenebilir:

    |-- Config
    |    |-- Animations
    |    |-- Effects
    |    |-- Audio
    |    |-- Recoil
    |    |-- Timings
    |-- Animations
    |-- State
    |-- Visuals

<a name="3.2.4"></a>
<a name="bp-vars-access"></a>
#### 3.2.4 Değişken Erişim Düzeyi

C++'da değişkenlerin bir erişim düzeyi kavramı vardır. Public, sınıfın dışındaki herhangi bir kodun değişkene erişebileceği anlamına gelir. Protected, yalnızca sınıfın ve herhangi bir alt sınıfın bu değişkene dahili olarak erişebileceği anlamına gelir. Private, yalnızca bu sınıfın ve hiçbir alt sınıfın bu değişkene erişemeyeceği anlamına gelir.

Şu anda şablonlarda tanımlanmış bir korumalı erişim kavramı yoktur.

`Düzenlenebilir` değişkenleri public değişkenler olarak ele alın. Düzenlenemeyen değişkenleri korumalı değişkenler olarak ele alın.

<a name="3.2.4.1"></a>
<a name="bp-vars-access-private"></a>
##### 3.2.4.1 Özel Değişkenler

Bir değişkene yalnızca tanımlandığı sınıf içinde erişilmesi gerektiği ve asla bir alt sınıfa erişilmemesi gerektiği bilinmiyorsa, değişkenleri özel olarak işaretlemeyin. Değişkenler `korumalı` olarak işaretlenebilene kadar, alt sınıf kullanımını kesinlikle kısıtlamak istediğinizde özel olarak ayırın.

<a name="3.2.5"></a>
<a name="bp-vars-advanced"></a>
#### 3.2.5 Gelişmiş Görüntüleme

Bir değişken düzenlenebilir ancak genellikle dokunulmamışsa, onu `Gelişmiş Görüntüleme` olarak işaretleyin. Bu, gelişmiş görüntüleme okuna tıklanmadığı sürece değişkeni gizli hale getirir.

`Gelişmiş Görüntüleme` seçeneğini bulmak için, değişken ayrıntıları listesinde gelişmiş görüntülenen değişken olarak listelenir.

<a name="3.2.6"></a>
<a name="bp-vars-transient"></a>
#### 3.2.6 Geçici Değişkenler

Geçici değişkenler, değerlerinin kaydedilmesi ve yüklenmesi gerekmeyen ve sıfır veya null başlangıç ​​değerine sahip değişkenlerdir. Bu, değeri çalışma zamanına kadar bilinmeyen diğer nesnelere ve aktörlere yapılan referanslar için yararlıdır. Bu, düzenleyicinin buna bir referans kaydetmesini önler ve plan sınıfının kaydedilmesini ve yüklenmesini hızlandırır.

Bu nedenle, tüm geçici değişkenler her zaman sıfır veya null olarak başlatılmalıdır. Aksi takdirde hata ayıklaması zor hatalarla sonuçlanacaktır.

<a name="3.2.7"></a>
<a name="bp-vars-config"></a>
#### 3.2.8 Yapılandırma Değişkenleri

`Yapılandırma Değişkeni` bayrağını kullanmayın. Bu, tasarımcıların plan davranışını kontrol etmesini zorlaştırır. Yapılandırma değişkenleri yalnızca C++'da nadiren değiştirilen değişkenler için kullanılmalıdır. Bunları `Gelişmiş Gelişmiş Görüntüleme` değişkenleri olarak düşünün.

<a name="3.3"></a>
<a name="bp-functions"></a>
### 3.3 İşlevler, Olaylar ve Olay Göndericileri

Bu bölüm, işlevleri, olayları ve olay göndericilerini nasıl yazmanız gerektiğini açıklar. Aksi belirtilmediği sürece işlevlere uygulanan her şey olaylara da uygulanır.

<a name="3.3.1"></a>
<a name="bp-funcs-naming"></a>
#### 3.3.1 İşlev Adlandırma

İşlevlerin, olayların ve olay dağıtıcılarının adlandırılması son derece önemlidir. Yalnızca isme dayanarak işlevler hakkında belirli varsayımlarda bulunulabilir. Örneğin:

* Saf bir işlev mi?
* Durum bilgilerini mi getiriyor?
* Bir işleyici mi?
* Bir RPC mi?
* Amacı nedir?

İşlevler uygun şekilde adlandırıldığında bu sorular ve daha fazlası yanıtlanabilir.

<a name="3.3.1.1"></a>
<a name="bp-funcs-naming-verbs"></a>
#### 3.3.1.1 Tüm İşlevler Fiil Olmalıdır

İster bilgi almak, ister verileri hesaplamak, isterse bir şeyin patlamasına neden olmak olsun, tüm işlevler ve olaylar bir tür eylem gerçekleştirir. Bu nedenle, tüm işlevler fiillerle başlamalıdır. Mümkün olduğunca şimdiki zamanda ifade edilmelidirler. Ayrıca ne yaptıklarına dair bir bağlamları olmalıdır.

`OnRep` işlevleri, olay işleyicileri ve olay dağıtıcıları bu kuralın bir istisnasıdır.

İyi örnekler:

* `Fire` - Bir Karakter / Silah sınıfındaysa iyi bir örnek, çünkü bağlamı vardır. Bir Varil / Çim / herhangi bir belirsiz sınıftaysa kötü.
* `Jump` - Bir Karakter sınıfındaysa iyi bir örnek, aksi takdirde bağlam gerekir. * `Explode`
* `ReceiveMessage`
* `SortPlayerArray`
* `GetArmOffset`
* `GetCoordinates`
* `UpdateTransforms`
* `EnableBigHeadMode`
* `IsEnemy` - ["Is" bir fiildir.](http://writingexplained.org/is-is-a-verb)

Kötü örnekler:

* `Dead` - Ölü mü? Deaden mi olacak?
* `Rock`
* `ProcessData` - Belirsiz, bu kelimeler hiçbir şey ifade etmiyor.
* `PlayerState` - İsimler belirsizdir.
* `Color` - Bağlamı olmayan fiil veya belirsiz isim.
  
<a name="3.3.1.2"></a>
<a name="bp-funcs-naming-onrep"></a>
#### 3.3.1.2 RepNotify İşlevleri Her Zaman `OnRep_Variable` Özelliği

Bildirim değişkenleriyle çoğaltılan tüm işlevler `OnRep_Variable` biçiminde olmalıdır. Bu, Blueprint düzenleyicisi tarafından zorunlu tutulur. Ancak bir C++ `OnRep` işlevi yazıyorsanız, onu Blueprints'e sunarken de bu kurala uymalıdır.

<a name="3.3.1.3"></a>
<a name="bp-funcs-naming-bool"></a>
#### 3.3.1.3 Bool Döndüren Bilgi İşlevleri Soru Sormalıdır

Herhangi bir nesnenin durumunu değiştirmeyen veya değiştirmeyen ve yalnızca bilgi, durum almak veya evet/hayır değeri hesaplamak için olan bir işlev yazarken, bir soru sormalıdır. Bu, [fiil kuralını](#bp-funcs-naming-verbs) de takip etmelidir.

Bu son derece önemlidir çünkü bir soru sorulmazsa, fonksiyonun bir eylem gerçekleştirdiği ve bu eylemin başarılı olup olmadığını döndürdüğü varsayılabilir.

İyi örnekler:

* `IsDead`
* `IsOnFire`
* `IsAlive`
* `IsSpeaking`
* `IsHavingAnExistentialCrisis`
* `IsVisible`
* `HasWeapon` - ["Has" bir fiildir.](http://grammar.yourdictionary.com/parts-of-speech/verbs/Helping-Verbs.html)
* `WasCharging` - ["Was" "be" fiilinin geçmiş zamanıdır.](http://grammar.yourdictionary.com/parts-of-speech/verbs/Helping-Verbs.html) 'Önceki kare' veya 'önceki durum'dan bahsederken "was" kullanın. * `CanReload` - ["Can" bir fiildir.](http://grammar.yourdictionary.com/parts-of-speech/verbs/Helping-Verbs.html)

Kötü örnekler:

* `Fire` - Ateşte mi? Ateş edecek mi? Ateş edecek mi?
* `OnFire` - Ateşleme için olay dağıtıcısıyla karıştırılabilir.
* `Dead` - Ölü mü? Ölüleştirecek mi?
* `Visibility` - Görünür mü? Görünürlüğü ayarla? Uçuş koşullarının bir açıklaması mı?
  
<a name="3.3.1.4"></a>
<a name="bp-funcs-naming-eventhandlers"></a>
#### 3.3.1.4 Olay İşleyicileri ve Göndericiler `On` İle Başlamalıdır

Bir olayı işleyen veya gönderen herhangi bir işlev `On` ile başlamalı ve [fiil kuralını](#bp-funcs-naming-verbs) izlemeye devam etmelidir. Ancak geçmiş zaman daha iyi okunuyorsa fiil sona taşınabilir.

`On` kelimesinin [birleşik kullanımları](http://dictionary.cambridge.org/us/grammar/british-grammar/about-words-clauses-and-sentences/collocation) fiil kuralını izlemekten muaftır.

`Handle` kullanımına izin verilmez. `Handle` yerine `On` kullanmak 'Gerçek Dışı'dır, diğer çerçeveler ise `On` yerine `Handle` kullanmayı tercih edebilir.

İyi örnekler:

* `OnDeath` - Oyunlarda yaygın yerleşim
* `OnPickup`
* `OnReceiveMessage`
* `OnMessageRecieved`
* `OnTargetChanged`
* `OnClick`
* `OnLeave`

Kötü örnekler:

* `OnData`
* `OnTarget`
* `HandleMessage`
* `HandleDeath`
  
<a name="3.3.1.5"></a>
<a name="bp-funcs-naming-rpcs"></a>
#### 3.3.1.5 Uzaktan Prosedür Çağrıları Hedefle Başlamalıdır

Herhangi bir RPC oluşturulduğunda, `Server`, `Client` veya `Multicast` ile başlanmalıdır. İstisna yok.

Ön ekten sonra, işlev adlandırmayla ilgili diğer tüm kuralları izleyin.

İyi örnekler:

* `ServerFireWeapon`
* `ClientNotifyDeath`
* `MulticastSpawnTracerEffect`

Kötü örnekler:

* `FireWeapon` - Bir tür RPC olduğunu göstermez.
* `ServerClientBroadcast` - Kafa karıştırıcı.
* `AllNotifyDeath` - `Multicast` kullanın, asla `All` kullanmayın.
* `ClientWeapon` - Fiil yok, belirsiz.
  

<a name="3.3.2"></a>
<a name="bp-funcs-return"></a>
#### 3.3.2 Tüm İşlevlerin Dönüş Düğümleri Olmalı

Tüm işlevlerin dönüş düğümleri olmalı, istisna yok.

Dönüş düğümleri, bir işlevin yürütülmesini tamamladığını açıkça belirtir. Mavi kopyaların `Sequence`, `ForLoopWithBreak` ve geriye doğru yeniden yönlendirme düğümleriyle doldurulabildiği bir dünyada, okunabilirlik, bakım ve daha kolay hata ayıklama için açık yürütme akışı önemlidir.

Mavi kopya derleyicisi yürütme akışını takip edebilir ve dönüş düğümleri kullanırsanız kodunuzun işlenmemiş bir dönüş veya kötü akışa sahip bir dalı varsa sizi uyarır.

Bir programcının bir Sequence düğümüne bir pin ekleyebileceği veya bir for döngüsü tamamlandıktan sonra mantık ekleyebileceği ancak döngü yinelemesinin erken dönebileceği durumlarda, bu genellikle kod akışında kazara bir hataya neden olabilir. Mavi kopya derleyicisinin uyarıları herkesi bu sorunlar hakkında hemen uyaracaktır.

<a name="3.3.3"></a>
<a name="bp-graphs-funcs-node-limit"></a>
#### 3.3.3 Hiçbir Fonksiyon 50'den Fazla Düğüme Sahip Olmamalıdır

Basitçe, hiçbir fonksiyon 50'den fazla düğüme sahip olmamalıdır. Bu kadar büyük herhangi bir fonksiyon, okunabilirlik ve bakım kolaylığı için daha küçük fonksiyonlara bölünmelidir.

Aşağıdaki düğümler, fonksiyon karmaşıklığını artırmadıkları düşünüldüğünden sayılmaz:

* Yorum
* Rota
* Dönüştürme
* Bir Değişken Alma
* Bir Yapıyı Kırma
* Fonksiyon Girişi
* Kendi
  
<a name="3.3.4"></a>
<a name="bp-graphs-funcs-description"></a>
#### 3.3.4 Tüm Genel Fonksiyonların Bir Açıklaması Olmalıdır

Bu kural, diğerlerinin sizin plan API'nizde daha kolay gezinebilmesi ve kullanabilmesi için daha çok genel veya pazar yeri planlarına uygulanır.

Basitçe, Public erişim belirtecine sahip herhangi bir işlevin açıklaması doldurulmalıdır.

<a name="3.3.5"></a>
<a name="bp-graphs-funcs-plugin-category"></a>
#### 3.3.5 Tüm Özel Statik Eklenti `BlueprintCallable` İşlevleri Eklenti Adına Göre Kategorilendirilmelidir

Projeniz `statik` `BlueprintCallable` işlevlerini tanımlayan bir eklenti içeriyorsa, bunların kategorisi eklentinin adına veya eklentinin adının bir alt kategorisine ayarlanmalıdır.

Örneğin, `Zed Kamera Arayüzü` veya `Zed Kamera Arayüzü | Görüntü Yakalama`.

<a name="3.4"></a>
<a name="bp-graphs"></a>
### 3.4 Blueprint Grafikleri

Bu bölüm tüm Blueprint grafiklerine uygulanan şeyleri kapsar.

<a name="3.4.1"></a>
<a name="bp-graphs-spaghetti"></a>
#### 3.4.1 Spagetti Yok "Spagetti Koddan Kaçının" 

"(Spagetti kod, kabloların birbirine girerek takibinin zorlaştığı karmaşık ve düzensiz grafikleri ifade eder.)"

Kabloların net başlangıçları ve sonları olmalıdır. Bir grafiği anlamak için asla zihinsel olarak kabloları çözmek zorunda kalmamalısınız. Aşağıdaki bölümlerin çoğu spagettiyi azaltmaya ayrılmıştır.

<a name="3.4.2"></a>
<a name="bp-graphs-align-wires"></a>
#### 3.4.2 Kabloları Hizalayın, Düğümleri Değil

Her zaman kabloları hizalayın, düğümleri değil. Bir düğümdeki boyutu ve pin konumunu her zaman kontrol edemezsiniz, ancak bir düğümün konumunu ve dolayısıyla kabloları her zaman kontrol edebilirsiniz. Düz kablolar net doğrusal akış sağlar. Kıvrımlı kablolar zekayı kötü bir şekilde yıpratır. BP düğümleri seçiliyken Bağlantıları Düzleştir komutunu kullanarak kabloları düzeltebilirsiniz. Kısayol: Q

İyi örnek: Düğümlerin tepeleri, mükemmel düz bir beyaz exec çizgisi oluşturmak için kademeli olarak düzenlenmiştir.
![Kablolarla Hizalanmış](https://github.com/Allar/ue5-style-guide/blob/main/images/bp-graphs-align-wires-good.png?raw=true "Kablolarla Hizalanmış")

Kötü Örnek: Düğümlerin tepeleri, kıvrımlı bir beyaz exec çizgisi oluşturarak hizalanmıştır.
![Kötü](https://github.com/Allar/ue5-style-guide/blob/main/images/bp-graphs-align-wires-bad.png?raw=true "Kıvrımlı")

Kabul Edilebilir Örnek: Hizalama araçlarını nasıl kullanırsanız kullanın, belirli düğümler işbirliği yapmayabilir. Bu durumda, düğümü daha yakına getirerek kıvrımı en aza indirmeye çalışın. ![Kabul Edilebilir](https://github.com/Allar/ue5-style-guide/blob/main/images/bp-graphs-align-wires-acceptable.png?raw=true "Kabul Edilebilir")

<a name="3.4.3"></a>
<a name="bp-graphs-exec-first-class"></a>
#### 3.4.3 Beyaz Yürütme Çizgileri En Önemli Önceliktir

Doğrusal bir beyaz yürütme çizgisini düzeltmek veya bir tür veri çizgisini düzeltmek arasında karar vermeniz gerekirse, her zaman beyaz yürütme çizgisini düzeltin.

<a name="3.4.4"></a>
<a name="bp-graphs-block-comments"></a>
#### 3.4.4 Grafikler Mantıklı Şekilde Yorumlanmalıdır

Düğüm blokları, daha üst düzey davranışlarını tanımlayan yorumlarla sarılmalıdır. Her bir düğümün kolayca okunabilir ve anlaşılabilir olması için her bir fonksiyon iyi adlandırılmış olsa da, bir amaca katkıda bulunan düğüm gruplarının amacı bir yorum bloğunda açıklanmalıdır. Bir fonksiyonun çok sayıda düğüm bloğu yoksa ve düğümlerin fonksiyonun hedefinde doğrudan bir amaca hizmet ettiği açıksa, fonksiyon adı ve açıklaması yeterli olacağından yorumlanmalarına gerek yoktur.

<a name="3.4.5"></a>
<a name="bp-graphs-cast-error-handling"></a>
#### 3.4.5 Grafikler, Gerektiğinde Tür Dönüştürme (Casting) Hatalarını Yönetmelidir

Bir fonksiyon veya olay bir dönüşümün her zaman başarılı olduğunu varsayarsa, dönüşüm başarısız olursa mantıkta uygun şekilde bir hata bildirmelidir. Bu, başkalarına 'çalışması gereken' bir şeyin neden çalışmadığını bildirir. Bir fonksiyon ayrıca, dönüştürülen referansın dönüştürülemeyebileceği biliniyorsa, başarısız bir dönüşümden sonra zarif bir kurtarma girişiminde bulunmalıdır.

Bu, her döküm düğümünün başarısızlığının ele alınması gerektiği anlamına gelmez. Birçok durumda, özellikle çarpışmalar gibi olaylarla ilgili olaylarda, yürütme akışının başarısız bir dökümde sessizce sonlanması beklenir.

<a name="3.4.6"></a>
<a name="bp-graphs-dangling-nodes"></a>
#### 3.4.6 Grafiklerde Sarkan / Gevşek / Ölü Düğüm Olmamalıdır

Tüm taslak grafiklerdeki tüm düğümlerin bir amacı olmalıdır. Hiçbir amacı olmayan veya yürütülmeyen sarkan taslak düğümlerini ortalıkta bırakmamalısınız.

**[⬆ Başa Dön](#table-of-contents)**


<a name="4"></a>
<a name="Static Meshes"></a>
<a name="s"></a>
## 4. Static Meshes

Bu bölüm Statik Ağ varlıklarına ve bunların iç yapılarına odaklanacaktır.

<a name="4.1"></a>
<a name="s-uvs"></a>
### 4.1 Static Mesh UVs

Eğer Linter kötü UV'ler raporluyor ve siz bunu takip edemiyorsanız, neden başarısız olduğuna dair kesin detaylar için projenizin `Saved/Logs` klasöründeki sonuç `.log` dosyasını açın. Gelecekte bu mesajları Lint raporuna dahil etmeyi umuyorum.

<a name="4.1.1"></a>
<a name="s-uvs-no-missing"></a>
#### 4.1.1 Tüm Ağların UV'leri Olmalı

Oldukça basit. Nasıl kullanılacaklarına bakılmaksızın tüm ağların eksik UV'leri olmamalıdır.

<a name="4.1.2"></a>
<a name="s-uvs-no-overlapping"></a>
#### 4.1.2 Tüm Ağların Işık Haritaları İçin Çakışan UV'leri Olmamalı

Oldukça basit. Nasıl kullanılacaklarına bakılmaksızın tüm ağların geçerli çakışmayan UV'leri olmalıdır.

<a name="4.2"></a>
<a name="s-lods"></a>
### 4.2 LOD'lar Doğru Şekilde Ayarlanmalıdır

Bu, proje bazında öznel bir kontroldür, ancak genel bir kural olarak, farklı mesafelerden görülebilen herhangi bir ağın uygun LOD'ları olmalıdır.

<a name="4.3"></a>
<a name="s-modular-snapping"></a>
### 4.3 Modüler Soketsiz Varlıklar Izgaraya Temiz Bir Şekilde Geçmelidir

Bu, varlık bazında öznel bir kontroldür, ancak herhangi bir modüler soketsiz varlık, projenin ızgara ayarlarına göre temiz bir şekilde birbirine geçmelidir.

2'nin kuvvetine göre bir ızgaraya mı yoksa 10 tabanlı bir ızgaraya mı geçileceği projeye bağlıdır. Ancak pazar yeri için modüler soketsiz varlıklar oluşturuyorsanız, Epic'in gereksinimi, ızgara 10 birim veya daha büyük olarak ayarlandığında bunların temiz bir şekilde geçmesidir.

<a name="4.4"></a>
<a name="s-collision"></a>
### 4.4 Tüm Ağlarda Çarpışma Olmalı

Bir varlığın bir seviyede çarpışma için kullanılıp kullanılmayacağına bakılmaksızın, tüm ağlarda uygun çarpışma tanımlanmalıdır. Bu, motora sınır hesaplamaları, tıkanıklık ve aydınlatma gibi konularda yardımcı olur. Çarpışma da varlığa uygun şekilde biçimlendirilmelidir.

<a name="4.5"></a>
<a name="s-scaled"></a>
### 4.5 Tüm Ağlar Doğru Şekilde Ölçeklendirilmelidir

Bu, proje bazında öznel bir kontroldür, ancak tüm varlıklar projelerine doğru şekilde ölçeklendirilmelidir. Seviye tasarımcıları veya plan yazarları, düzenleyicide onaylamaları için ağların ölçeğini ayarlamak zorunda kalmamalıdır. Motorda ağları ölçeklendirmek, bir ölçek düzeltmesi değil, bir ölçek geçersiz kılma olarak ele alınmalıdır.

**[⬆ Başa Dön](#table-of-contents)**


<a name="5"></a>
<a name="Niagara"></a>
<a name="ng"></a>
## 5. Niagara

Bu bölüm Niagara varlıklarına ve bunların iç yapılarına odaklanacaktır.

<a name="5.1"></a>
<a name="ng-rules"></a>
### 5.1 Hiçbir Zaman Boşluk Yok

[00.1 Yasak Tanımlayıcılar](#00) bölümünde belirtildiği gibi, tanımlayıcılarda boşluklar ve tüm beyaz boşluk karakterleri yasaktır. Bu, özellikle Niagara sistemleri için geçerlidir çünkü HLSL veya Niagara içinde komut dosyası yazmanın diğer yollarıyla çalışırken ve bir tanımlayıcıya başvurmaya çalışırken işleri önemli ölçüde zorlaştırır, hatta imkansız hale getirir.

(Orijinal Katkı [@dunenkoff](https://github.com/Allar/ue5-style-guide/issues/58))

**[⬆ Başa Dön](#table-of-contents)**


<a name="6"></a>
<a name="Levels"></a>
<a name="levels"></a>
## 6. Levels / Maps

"Seviyeler" ile "haritalar" arasındaki farkla ilgili [Terminoloji Notu'na](#terms-level-map) bakın.

Bu bölüm Seviye varlıklarına ve bunların iç işleyişlerine odaklanacaktır.

<a name="6.1"></a>
<a name="levels-no-errors-or-warnings"></a>
### 6.1 Hata veya Uyarı Yok

Tüm seviyeler sıfır hata veya uyarı ile yüklenmelidir. Bir seviye herhangi bir hata veya uyarı ile yüklenirse, ardışık sorunları önlemek için derhal düzeltilmelidir.

Konsol komutu "map check" kullanarak editördeki açık bir seviyede harita kontrolü çalıştırabilirsiniz.

Lütfen unutmayın: Linter bu konuda şu anda editörden daha katıdır ve editörün kendi kendine çözeceği yükleme hatalarını yakalar.

<a name="6.2"></a>
<a name="levels-lighting-should-be-built"></a>
### 6.2 Aydınlatma Yapılmalıdır

Geliştirme sırasında bazı seviyelerde zaman zaman aydınlatma yapılmaması normaldir. Ancak bir test/dahili/gönderi yapısı veya dağıtılacak herhangi bir yapı yaparken aydınlatma her zaman yapılmalıdır.

<a name="6.3"></a>
<a name="levels-no-visible-z-fighting"></a>
### 6.3 No Player Visible Z Fighting

"Z-Fighting" terimi, 3D grafiklerde iki yüzeyin aynı derinlikte olmasından kaynaklanan görsel bir hatadır. "Doğrudan çevirisi anlamsızdır."

"Oyuncunun Görebileceği Alanlarda Z-Fighting (Yüzey Titremesi) Olmamalıdır." 

Seviyeler, oyuncunun görebileceği tüm alanlarda [z-dövüşü](https://en.wikipedia.org/wiki/Z-fighting) içermemelidir.

<a name="6.4"></a>
<a name="levels-mp-rules"></a>
### 6.4 Pazar Yeri Belirli Kuralları

Bir proje UE Pazar Yerinde satılacaksa, bu kurallara uymalıdır.

<a name="6.4.1"></a>
<a name="levels-mp-rules-overview"></a>
#### 6.4.1 Genel Bakış Seviyesi

Projeniz görselleştirilmesi veya tanıtımı yapılması gereken varlıklar içeriyorsa, projenizde "Genel Bakış" adını içeren bir haritanız olmalıdır.

Bu genel bakış haritası, varlıkları görselleştiriyorsa, [Epic'in yönergelerine](http://help.epicgames.com/customer/en/portal/articles/2592186-marketplace-submission-guidelines-preparing-your-assets#Required%20Levels%20and%20Maps) göre ayarlanmalıdır.

Örneğin, `InteractionComponent_Overview`.

<a name="6.4.2"></a>
<a name="levels-mp-rules-demo"></a>
#### 6.4.2 Demo Level

Projeniz demosu yapılması gereken varlıklar içeriyorsa veya bir tür öğretici ile birlikte geliyorsa, projenizde “Demo” adını içeren bir haritanız olmalıdır. Bu seviye ayrıca, projenizin nasıl kullanılacağını gösteren bir biçimde içinde belgeler içermelidir. Bunun nasıl yapılacağına dair iyi örnekler için Epic'in İçerik Örnekleri projesine bakın.

Projeniz bir sanat paketi yerine bir oyun mekaniği veya başka bir sistem biçimiyse, bu "Genel Bakış" haritanızla aynı olabilir.

Örneğin, `InteractionComponent_Overview_Demo`, `ExplosionKit_Demo`.

**[⬆ Başa Dön](#table-of-contents)**


<a name="7"></a>
<a name="textures"></a>
## 7. Dokular

Bu bölüm Doku varlıklarına ve bunların iç yapılarına odaklanacaktır.

<a name="7.1"></a>
<a name="textures-dimensions"></a>
### 7.1 Doku Boyutları 2'nin Kuvvetleri Olmalıdır

UI dokuları hariç tüm dokuların boyutları 2'nin kuvvetlerinin katları olmalıdır. Dokuların kare olması gerekmez.

Örneğin, `128x512`, `1024x1024`, `2048x1024`, `1024x2048`, `1x512`.

<a name="7.2"></a>
<a name="textures-density"></a>
### 7.2 Doku Yoğunluğu Tekdüze Olmalıdır

Tüm dokular standart kullanım durumlarına uygun bir boyutta olmalıdır. Uygun doku yoğunluğu projeden projeye değişir, ancak o projedeki tüm dokuların tutarlı bir yoğunluğu olmalıdır.

Örneğin, bir projenin doku yoğunluğu 1 birim başına 8 piksel ise, 100x100 birim küpüne uygulanması amaçlanan bir doku 1024x1024 olmalıdır, çünkü bu, projenin doku yoğunluğuna uyan 2'nin en yakın kuvvetidir.

<a name="7.3"></a>
<a name="textures-max-size"></a>
### 7.3 Dokular 8192'den Büyük Olmamalıdır

Çok açık bir nedeniniz olmadığı sürece hiçbir doku 8192'yi aşan bir boyuta sahip olmamalıdır. Genellikle bu kadar büyük bir doku kullanmak sadece kaynak israfıdır.

<a name="7.4"></a>
<a name="textures-group"></a>
### 7.4 Dokular Doğru Şekilde Gruplandırılmalıdır

Her doku, LODing için kullanılan bir Doku Grubu özelliğine sahiptir ve bu, kullanımına göre doğru şekilde ayarlanmalıdır. Örneğin, tüm UI dokuları UI doku grubuna ait olmalıdır.

**[⬆ Başa Dön](#içerik tablosu)**

## Önemli Katkıda Bulunanlar

* [Michael Allar](http://allarsblog.com): [GitHub](https://github.com/Allar), [Twitter](https://twitter.com/michaelallar)
* [CosmoMyzrailGorynych](https://github.com/CosmoMyzrailGorynych)
* [billymcguffin](https://github.com/billymcguffin)
* [akenatsu](https://github.com/akenatsu)

## Lisans

Telif Hakkı (c) 2016 Gamemakin LLC

Bkz. [LİSANS](/LİSANS)

**[⬆ Başa Dön](#içerik tablosu)**

## Değişiklikler

Bu kılavuzu çatallandırmanızı ve kuralları ekibinizin stil kılavuzuna uyacak şekilde değiştirmenizi öneririz. Aşağıda, stil kılavuzunda yapılan bazı değişiklikleri listeleyebilirsiniz. Bu, birleştirme çakışmalarıyla uğraşmak zorunda kalmadan stil kılavuzunuzu periyodik olarak güncellemenizi sağlar.

# };
