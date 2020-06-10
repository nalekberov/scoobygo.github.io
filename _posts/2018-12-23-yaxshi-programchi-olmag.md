---
layout: post
lang: az
title:  "Yaxşı proqramçı olmaq"
---

**Bu yazı Robert L. Read-in [How To Be a Programmer: A Short, Comprehensive, and Personal Summary](https://www.doc.ic.ac.uk/~susan/475/HowToBeAProgrammer.pdf) kitabının dilimizə tərcüməsidir, iş davam etməkdədir, fikirləriniz bölüşməyi unutmayın.**

Yaxşı proqramçı olmaq çətin və möhtəşəm işdir. Softver layihəsini reallaşdırmağın ən çətin yanı proqramçının öz kolleqaları və istifadəçiləri ilə necə davranmağıdır. Kompyuter prqramı yazmaq çox önəmlidir, çox böyük intellekt və qabiliyyət tələb edir. 

Kompyuter proqramlaşdırması kurslarda tədris olunur. Ən yaxşı kitablar The Pragmatic Programmer, Code Complete, Rapid Development, və Extreme Programming Explained kompyuter proqramlaşdırmasını və yaxşı proqramçı olmağın çətinliklərini öyrədir. Paul Graham və Eric Raymondun esseyləri bu məqaləni oxumamışdan əvvəl oxunmalıdır. Bu essey isə digər mükəmməl işlərdən proqramlaşdırmada sosial problemləri və ən önəmli qabiliyyətləri önə çəkməklə fərqlənir.

Bu çox subyektivdir. Bu essey ona görə də daha çox şəxsi baxışlara əsaslanır. Mən özümü bir proqramçının rastlaşdığı əksər problemlərlə sərhədləyirəm. Bu problemlərin çoxu və onların həlləri insan təbiətinə çox ümumidir. Buna baxmayaraq bu kitabın faydalı olacağını düşünürəm. Mən bunları maksimum şüurlu toplamağa çalışmışam, hansı ki, arzu edərdim kimsə bunu mənə 21 yaşımda olarkən izah edərdi.

Bu kitabda boss layihəni sizə verən hər hansı bir insanə təsvir edir. Mən biznes, şirkət, və komandanı sinonim olaraq istifadə edirəm, baxmayaraq ki, biznes pul qazanmanı həyata keçirir, şirkət modern iş mühitini verir, və komanda loyallığı paylaşdığınız insanlardır.
Komandaya xoş gəldiniz.

### **Hissə 1**

# **Yeni başlayan**

## **2   Şəxsi qabiliyyətlər**

#### **2.1 Debug etməyi öyrən**

Debug etmək proqramçı olmağın təməl daşıdır. Bunun birinci mənası proqramdan xətanı aradan götürmək, əsas mənası isə proqramı icra edərək onu izləməkdir. Proqramı effektiv olaraq debug etməyən proqramçı kordur.

İdealistlər düşünə bilərlər ki, dizayn, analiz və komplekslik teoriyasi fundamentaldır, onlar isə işləyən proqramçılar deyildirlər. İşləyən proqramşı ideal dünyada yaşamır. Hətta o ideal olsa belə, o GNU kimi böyük softver şirkətləri və kolleqaları əhatəsindədir, və bunlarla əməkdaşlıqda olmaq məcburiyyətindədir. Bu koların çoxu mükəmməl deyildir və mükəmməl şəkildə dokumentasiya olunmamışdır. Bu kodun necə icra olunmasından xəbərsiz olanı isə balaca bir xəta kənara ata bilər. Çox vaxt bundan xəbərdar olmaq üçün eksperiment etmək - debug etmək tələb edir.

Debug olunmaq programın icrası ilə bağlıdır, proqramın özü ilə deyil. Əgər siz böyük softver şirkətindən proqram alırsınızsa, əksər hallarda proqramı (kodunu) görmək imkanına sahib olmursunuz. Amma bəzən elə hallar olur ki, proqram dokumentasiyada yazıldığı kimi işləmir (kompyuteriniz kreş etmək ağıla gələn misallardan biri olar), bəzən isə dokumentasiya ümumiyyətlə bu barədə heç nə izah etmir. Bir çox hallarda proqramçı bir xəta yaradır, koda baxış keçirir, amma xətanın necə baş verəcəyini təsəvvür etmir. Qaçınılmazdır ki, təxminləri tam olaraq düzgün deyil və ya elə şərt baş verir ki, o əvvəlcədən qarşısını ala bilmir. Bəzən koda sadəcə baxış keçirmək yarayır. İşə yaramayanda isə o debug etməlidir bunu görmək üçün.

Proramın necə icra olunması barədə təsəvvür yaranması üçün kodu icra etmək və onu izləmək lazım gəlir. Bəzən bu görünəndir, ekranda görünən hər hansı bir obyekt və ya iki hadisə arasında olan müəyyən gecikmə kimi. Bir çox digər hallarda isə bu görünmür, bir verilənin koddakı vəziyyəti, hansı sətrin icra olunması və ya kompleks bir verilənlər sturkturasında görülən iş kimi. Bu görünməz şeylər isə günüzünə çıxmalıdır.

İcra olunan proqramın daxili aləmini göstərməyin əsas yollarını belə kateqoriyalaşdıra bilərik
 - Debug alətindən istifadə etmək
 - Sətrin çapolunması - proqramda müvəqqəti dəyişikliklər edərək, əsasən müəyyən informasiyanı çap edən sətr əlavə etmək
 - Log yazmaq  - Proqrama bütün icra vaxtı ərzində log yazma imkanı əlavə etmək

Debug alətləri işə yaraqıqları zaman həqiqətən möhtəşəmdir. Digər iki metod isə daha da əhəmiyyətlidir. Debug alətləri bəzən dilin inkişaf prosesindən geridə qalır, və beləcə bəzən onlar işə yaramırlar. Debug aləti proqramın necə icra olunacağını müəyyən qədər dəyişə biləcəyi üçün bütün hallarda praktiki olmaya bilərlər. Nəhayət, debug etməyin bəzi başqa metodları da vardır, kompleks verilən strukturasını yoxlamaq kimi. Debug alətini stabil olduğu müddətcə necə istifadə etməyi bilmək yaxşıdır. Amma digər iki metodu tətbiq etmək çox mühümdür.

 Bəzi yeni başlayanların debug etməklər bağlı kodu dəyişib və icra etməklə əlaqədar şüuraltı qorxuları var. Bu başa düşüləmdir, daha çox kəşfiyyat əməliyyatı kimi görünür. Amma yeni başlayanlar koda onu tullandırmaq üçün barmaq etməyi öyrənməlidir. Kodu eksperiment etməyi və edilərn heç nəyin onu pis etməyəcəyindən əmin olmalıdırlar. Əgər siz müəllim və mentorsanızsa bu cür yeni başlayanlara bu prosesi izah edərək bu qorxuya qalib gəlməkdə kömək edin, lazım gələrsə əllərindən tutun. Biz bu başlanğıcda yaranan qorxuya görə çox proqramçını itiririk.
