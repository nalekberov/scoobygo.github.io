---
layout: post
lang: az
title:  "25 ildən sonra PHP"
---

Bu postu yazmağımda ilham mənbəyim Jetbrainsin dərc etdiyi [bu](https://www.jetbrains.com/lp/php-25/) post oldu. PHP ilə aşağı yuxarı 5 il təcrübəm olduğu üçün istədim fikirlərimi yazım.

PHP əsasən amatörləri cəlb etdi
Təxmini 6 il əvvəl idi, bankda işləyirdim, vəzifəm bank sisteminə modullar yazmaq idi, çox köhnə bir sistem idi, özünün spesifik dili var idi.
İş olduqca rutin və sıxıcı gəlməyə başlamışdı, əvvəlcədən də veb developer olaraq təcrübəm olduğu üçün işdən ayrılmağı qərara almışdım, və bu 
dəyişikliyi olduğu qədərə rahat etmək üçün ən asan öyrənilə biləcək dil axtarırdım, və bir az axtarışdan sonra PHPnin bu kriteriyalara cavab
verən ən ideal dil olduğunu gördüm. Və təcrübəmdə gördüm ki, aşağı yuxarı PHP ilə yazanların bir çoxu ya asan öyrənilə bildiyi üçün, ya da
daha rahat dil axtarışı nəticəsində seçmişdi. Səbəblər fikrimcə çoxdur. Əlbəttə PHP dünyasındadı işini çox yaxşı bilən peşəkarlar mövcuddur,
onlar fantastik işlər görməyə davam edirlər, amma məsələ aktuallığını saxlayır, və PHP dünyası əsasən amatörlərdən ibarətdir. Dilin dizaynı
ilə bunun arasında korrelyasiya var? Məncə hə, amma bunu bu cür şərh edərdim: PHP pis dizayn olunub deyə o dildə yazanlar amatörləşmir, 
amatör olanlar, və bu cür də qalmaq istəyən əsasən PHP kimi dillərdən yapışırlar. Yaxşı bəs startaplar niyə bu dili seçir soruşa bilərsən,
səbəb birinci və əsası PHP ilə layihə başlatmaq sadəcə bir neçə saat alır, PHP inkişafetdiricilər isə statistikaya əsasən daha az maaş
alanlardır. Yenə PHP'də yazmaq birini mütlər olaraq qeyri-peşəkar etmir. Peşəkar bütün vəziyyətlərdə peşəkarlığını saxlayır, verilən alət
nə olursa olsun.

## PHP fundamental problemlərini saxlamağa davam elədi
Məsələ burasındadır ki, Rasmus Lerdorf PHP 1994 ildə yaratdığı zaman fikrində peşəkar proqramlaşdırma dili yaratmaq deyil idi, o onu öz 
saytında yerləşdirdiyi rezumesinə gələn ziyarətləri izləmək üçün yazmışdı. Ona görə də adını Personal Home Page (PHP)Tools adı vermişdir.
Funsionallığı demək olar ki, şablon yaratmaq ilə limitli idi. Düzdür verilənlər bazası ilə işləmək imkanı da verirdi. Amma yenə də dil
demək olmazdı. 1995-ci ilə Rasmus dilin qaynaq kodunu vebdə açıq şəkilə yerləşdirir. Bu digər inkişafetdiricilərə həm koda baxmağa, həm
də onu istifadə etməyə imkan yaratdı və PHP-nin inkişafına yeni yol açdı. Getdikcə bəzi verilənlər bazalarına üstündə dəstək gətirdi. PHP 5
ilə dilə artıq obyekt yönümkü proqramlaşdırma özəllikləri əlavə olunmağa başlandı. Amma PHP hər zaman özündə "çatışmazlığı" saxladı.
İnternetdə bir çox blog postları var, [buna](https://eev.ee/blog/2012/04/09/php-a-fractal-of-bad-design/), və ya [buna](http://phpsadness.com)
baxa bilərsən. Amma mən özüm şəxsən hiss elədiklərimi qeyd edəcəm. 

## PHP "gözlənilməz"liklərini saxladı.

Məsələn array_map və array_filter funksialarında callback funksiyası hansında birinci gəlir, hansında ikinci gəlir bunu hələ də bilmirəm, 
ya IDE istifadə etməliyəm, ya da ki, tez-tez dokumentasiyaya baxmalıyam, peşəkar dizayn olunmuş istənilən alət bu kimi çaşdırmaları özü 
ilə gətirmir, dokumentasiyaya baxmaq saniyələrimi alar, məsələ itirilən zamanda deyil, məsələ fokusun dağılmasıdır, və bu kimi çaşdırmalar çoxdur.
PHP ekosistemi hələ də standartlar gətirməkdə çətinlik çəkir, onlar ya peşəkar olmur, ya da ekosistem daxilində bəzi oyunçular qəbul edir, bəziləri
isə qəbul etmir. Və bu şəkildə özündə fraqmentasiyalar yaradır, əlbəttə fərqli fikir və yanaşmalar yaxşıdır, amma standartların olması və bu
standartlara sadiq qalmaq bir texnologiyanın gələcəyinin necə olacağını bəlli edir və ona yön verir. Misal üçün Python-un PEP-lərinə bax, məncə
Python çox sağlam community yığmasında və sürətli inkişafında ən çox təsir edən faktorlardan birindən biri bu idi. Çünki (xüsusilə) bir şirkət
bir texnologiya seçərkən istəyərək və istəməyərək onunla bir kontrakta girir, o dilin gələcək planı, indiki vəziyyəti, ekosistemi dilin öz
imkanlarında qat-qat daha çox təsiredici faktorlardır. PHP-FIG də isə təəsüf mən bunu görə bilmirəm, birincisi qurumun nüfuzu olduqca zəifdir,
ikinci məsələ sağlamolmayan bir dinamika var, Symfony lider Fabian Potencier bu qurumdan çıxacağını elan elədi, bəzi digər layihələr də bunu
izlədi. Fabianın fikrincə bu qurum özləri istədiyi tərzdə freymvork yaratmaq üçün standarlar icad edirdi. Bunlar mübahisəli mövzulardır, amma
fakt faktılığında qalır ki, bu cür fikir ayrılığı dilin ətrafındakı texnologiyaları seçim zamanı bir çox sual yaranır.


## PHP'nin illər uzunu mükəmməl özəlliklər olaraq təqdim etdikləri
PHP dünyada populyarlığına və istifadəsinə görə ilk yerlərdə olan dillərdən biridir. Facebook, Tumblr, Dailiymotion kimi məşhur saytlar
PHP'də yazılıb, düzdür onların indiki kod bazalarının neçə faizinin hal-hazırda PHP'dən ibarətdir, bu əsas suallardan biridir, amma
fakt faktlığını saxlayır. Məhz o şirkətlərin yaranmasında rolu olan texnologiyadır. İş belə olduğu zaman əlbəttə dil inkişaf etməli idi,
inkişaf etdi də, PHP [gradual](https://en.wikipedia.org/wiki/Gradual_typing) tipləri gətirdi, və skalyar tipləri artıq funksiyalarda artıq
elan etmək olurdu, bu da yazılan kodu productiona qoyulmamışdan əvvəl tiplə bağlı yarana biləcək potensial xətaları tapmaqda kömək edirdi.
PHP indi daha tip imkanları gətirmək istəyir, məsələn Union tiplər, amma hələ də generic tiplrə dildə mövcud deyil, nəzərə alsaq ki, PHP
maksimum Javaya bənzəməyə çalışır, bu çatışmazlıq çox biruzə verir özünü, düzdür psalm kimi alətlər, kodu şərh bloklarında annotasiya edərək
statik analiz etməklə köməklik edir, amma şərh blokunda annotasiya bərbaddır. Yəqin edirəm bir neçə il sonra PHP annotasiya imkanı gətirərək
böyük anonslar edəcək, və böyük rezonanslara səbəb olacaq. Əlbəttə maraqlıdır, Java-ya bənzəyən, compileolunmayan bir dildə layihə yazmaq
xüsusilə agile metodologiyası ilə işlədiyiniz zaman compile prosesi olmadığı üçün çox rahat iterasiyalar etmək imkanı verir ki, bu da məhsulunuza
davamlı olaraq yeni özzəlikləri maksimum yeyinliklə əlavə etməyə imkan varir. Amma sual budur ki, seçdiyiniz alət sizi taktiki gedişlərdə
qazandırır, amma strateji qələbəyə aparırmı?

Fikrini bölüşməm istəyirsən? scoobygo [at] protonmail.com'a yaz, sən nə düşünürsən eşitmək maraqlıdır. :)
