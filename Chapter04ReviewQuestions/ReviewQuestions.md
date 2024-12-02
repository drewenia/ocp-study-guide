# Review Questions

1- What is output by the following code? (Choose all that apply.)

1 - Aşağıdaki kodun çıktısı nedir? (Geçerli olan her şeyi seçin.)

```
1: public class Fish {
2: public static void main(String[] args) {
3:      int numFish = 4;
4:      String fishType = "tuna";
5:      String anotherFish = numFish + 1;
6:      System.out.println(anotherFish + " " + fishType);
7:      System.out.println(numFish + " " + 1);
8: } }
```

```
A. 4 1
B. 5
C. 5 tuna
D. 5tuna
E. 51tuna
F. Code compile edilmez.
```

**Cevap :** F. 5. satır compile edilmez. Bu soru, veri tiplerine dikkat edip etmediğinizi kontrol ediyor. numFish bir
int değeridir ve 1 de bir int değeridir. Bu nedenle, sayısal toplama işlemi kullanılır ve 5 elde edilir. Sorun, bir int
değerini String değişkeninde saklayamamamızdır. 5. satır String anotherFish = numFish + 1 + ""; şeklinde olsaydı,
cevaplar A ve C seçenekleri olurdu. 5. satırda tanımlanan değişken "5" string'i olurdu ve her iki output statement'ı da
concatenation kullanırdı.

2 - Which of these array declarations are not legal? (Choose all that apply.)

2- Bu array declaration'larından hangisi yasal değildir? (Geçerli olanların tümünü seçin.)

```
A. int[][] scores = new int[5][];
B. Object[][][] cubbies = new Object[3][0][5];
C. String beans[] = new beans[6];
D. java.util.Date[] dates[] = new java.util.Date[2][];
E. int[][] types = new int[];
F. int[][] java = new int[][];
```

**Cevap :** C, E, F seçenekleri doğrudur. C seçeneği, değişken adını bir tür gibi kullandığı için açıkça geçersizdir. E
ve F seçenekleri herhangi bir boyut belirtmez. Çok boyutlu bir array'in sonraki boyutları için boyutu bırakmak legal
olsa da, ilki gereklidir. A seçeneği legal bir 2B array bildirir. B seçeneği legal bir 3B array bildirir. D seçeneği
legal bir 2B array bildirir. Sınavda daha önce öğrenmediğiniz sınıfları görmenin normal olduğunu unutmayın. Bunlar
hakkında bir şey bilmeniz beklenmez.

3 - Note that March 13, 2022 is the weekend when we spring forward, and November 6, 2022 is when we fall back for
daylight saving time. Which of the following can fill in the blank without the code throwing an exception? (Choose all
that apply.)

3 - 13 Mart 2022'nin, saatlerin ileri alındığı hafta sonu olduğunu ve 6 Kasım 2022'nin, saatlerin geri alındığı zaman
olduğunu unutmayın. Aşağıdakilerden hangisi, kodun bir exception atmamasını sağlayarak boşluğu doldurabilir? (Tüm
geçerli seçenekleri işaretleyin.)

```
var zone = ZoneId.of("US/Eastern");
var date = _____________________________;
var time = LocalTime.of(2, 15);
var z = ZonedDateTime.of(date, time, zone);
```

```
A. LocalDate.of(2022, 3, 13)
B. LocalDate.of(2022, 3, 40)
C. LocalDate.of(2022, 11, 6)
D. LocalDate.of(2022, 11, 7)
E. LocalDate.of(2023, 2, 29)
F. LocalDate.of(2022, MonthEnum.MARCH, 13);
```

**Cevap :** A, C, D. B seçeneği, Mart ayında 40. gün olmadığı için bir exception atar. E seçeneği de 2023'ün artık yıl
olmadığı ve Şubat ayının 29 günü bulunmadığı için bir exception atar. F seçeneği, enum'un MonthEnum yerine Month olarak
adlandırılması gerektiği için compile edilmez. D seçeneği, sadece normal bir tarih olduğu için ve gün ışığından
yararlanma süresiyle hiçbir ilgisi olmadığı için doğrudur. A ve C seçenekleri, Java'nın gün ışığından yararlanma
süresine göre ayarlama yapabildiği için doğrudur.

A seçeneği çıktı olarak;

```
2022-03-13T03:15-04:00[US/Eastern]
```

C seçeneği çıktı olarak;

```
2022-11-06T02:15-05:00[US/Eastern]
```

D seçeneği çıktı olarak;

```
2022-11-07T02:15-05:00[US/Eastern]
```

4 - Which of the following are output by this code? (Choose all that apply.)

4 - Aşağıdakilerden hangisi bu kodun çıktısıdır? (Geçerli olan tümünü seçin.)

```
3: var s = "Hello";
4: var t = new String(s);
5: if ("Hello".equals(s)) System.out.println("one");
6: if (t == s) System.out.println("two");
7: if (t.intern() == s) System.out.println("three");
8: if ("Hello" == s) System.out.println("four");
9: if ("Hello".intern() == t) System.out.println("five");
```

```
A. one
B. two
C. three
D. four
E. five
F. Code compile edilmez
G. Yukarıdakinlerden hiçbiri
```

**Cevap :** A, C, D. Kod sorunsuz compile ediliyor. 3. satır, String pool'unda ki String'e işaret ediyor. 4. satır,
String constructor'ını açıkça çağırıyor ve bu nedenle s'den farklı bir object halini alıyor. 5. satır, object eşitliğini
kontrol ediyor, bu doğru olduğu için 1 yazdırıyor. 6. satır, object referansı eşitliğini kullanıyor, farklı object'ler
olduğu için bu doğru değil. 7. satır, intern() methodunu çağırıyor, bu da String pool'undan değeri döndürdüğü için 's'
ile aynı referanstır. 8. satır da referansları karşılaştırıyor ancak her iki referans da String pool'unda ki object'i
işaret ettiği için true. Son olarak, 9. satır bir hiledir. "Hello" String'i zaten String pool'un da, bu nedenle intern()
çağrısı bir şey değiştirmez. t referansı halen farklı bir object, bu nedenle sonuç hala false.

5 - What is the result of the following code?

5 - Aşağıdaki kodun sonucu nedir?

```
7: var sb = new StringBuilder();
8: sb.append("aaa").insert(1, "bb").insert(4, "ccc");
9: System.out.println(sb);
```

```
A. abbaaccc
B. abbaccca
C. bbaaaccc
D. bbaaccca
E. Boş satır
F. Code compile edilmez
```

**Cevap :**B. Bu örnek, method chaining'i kullanır. append() çağrısından sonra, 'sb' "aaa" içerir. Bu sonuç, ilk
insert() çağrısına geçirilir ve burada 1. index'e eklenir. Bu noktada, 'sb' "abbaa" içerir. Bu sonuç, son insert()
çağrısına geçirilir ve burada 4. index'e eklenir, "abbaccca" sonucunu verir.

6 - How many of these lines contain a compiler error? (Choose all that apply.)

6 - Bu satırlardan kaç tanesi compiler hatası içeriyor? (Geçerli olanların tümünü seçin.)

```
23: double one = Math.pow(1, 2);
24: int two = Math.round(1.0);
25: float three = Math.random();
26: var doubles = new double[] {one, two, three};
```

```
A. 0
B. 1
C. 2
D. 3
E. 4
```

**Cevap :** C. Matematiksel işlemlerde return type'larına dikkat edin. Hilelerden biri 24. satırdadır. round() methodu,
bir float ile çağrıldığında bir int döndürür. Ancak, bunu bir double ile çağırıyoruz, bu nedenle bir long döndürür.
Diğer hile 25. satırdadır. random() methodu bir double döndürür. İki satırda bir compiler hatası olduğu için, C
seçeneği doğrudur.

```
double one = Math.pow(1, 2);

int two = Math.round(3.54f);
long returnTypeLong = Math.round(1.0);

double random = Math.random();

var doubles = new double[]{one, two, returnTypeLong, random};
```

7 - Which of these statements is true of the two values? (Choose all that apply.)

7 - Bu iki değer için aşağıdaki statement'lardan hangisi true? (Geçerli olanları seçin.)

```
2022–08–28T05:00 GMT-04:00 
2022–08–28T09:00 GMT-06:00 
```

```
A. İlk date/time daha erkendir.
B. İkinci date/time daha erkendir.
C. İki date/times aynıdır
D. Date/Times iki saat arayla.
E. Date/Times altı saat arayla.
F. Date/Times on saat arayla.
```

A, E. Zaman dilimleriyle uğraşırken, ilk olarak zaman dilimini çıkararak GMT'ye dönüştürmek en iyisidir. Negatif bir
sayı çıkarmak, eklemekle aynıdır. İlk date/time 9:00 GMT, ikincisi 15:00 GMT'dir. Bu nedenle, ilki altı saat daha
erkendir.

8 - Which of the following return 5 when run independently? (Choose all that apply.)

8 - Aşağıdakilerden hangisi bağımsız olarak çalıştırıldığında 5 döndürür? (Geçerli olan tümünü seçin.)

```
var string = "12345";
var builder = new StringBuilder("12345");
```

```
A. builder.charAt(4)
B. builder.replace(2, 4, "6").charAt(3)
C. builder.replace(2, 5, "6").charAt(2)
D. string.charAt(5)
E. string.length
F. string.replace("123", "1").charAt(2)
G. Yukarıdakinlerden hiçbiri
```

**Cevap :** A, B, F. Index'lerin sıfırdan başladığını unutmayın, yani 4. index 5'e karşılık gelir ve A seçeneği
doğrudur. B seçeneği için, replace() methodu değiştirmeye 2. index'ten başlar ve 4. index'den önce biter. Bu, iki
karakterin değiştirildiği ve charAt(3)'ün 1265'in ara değerinde çağrıldığı anlamına gelir. 3. index'de ki karakter
5'tir, bu da B seçeneğini doğru yapar. C seçeneği benzerdir ve ara değer 126 olur ve 6 döndürür. D seçeneği, 5. index'de
karakter olmadığı için bir exception ile sonuçlanır. E seçeneği yanlıştır. length() methodunun parantezleri eksik olduğu
için compile edilmez. Son olarak, F seçeneğinin replace'i 145 ara değerini verir. 2. index'de ki karakter 5'tir, bu
nedenle F seçeneği doğrudur.

9 - Which of the following are true about arrays? (Choose all that apply.)

9 - Array'ler hakkında aşağıdakilerden hangisi true? (Geçerli olanların tümünü seçin.)

```
A. İlk eleman 0 index'idir.
B. İlk eleman 1 index'idir.
C. Array'ler sabit boyuttadır.
D. Array'ler immutable'dır
E. Aynı primitive değerleri içeren iki farklı array'de equals() çağrısı her zaman true değerini döndürür.
F. Aynı primitive değerleri içeren iki farklı array'de equals() çağrısı her zaman false döndürür.
G. Aynı primitive değerleri içeren iki farklı array'de equals() çağrısı true veya false dönebilir.
```

**Cevap :** A, C, F. Array'ler sıfır tabanlıdır, bu da A seçeneğini doğru ve B seçeneğini yanlış yapar. Boyutlarını
değiştiremezler, bu da C seçeneğidir. Değerler değiştirilebilir, bu da D seçeneğini yanlış yapar. Bir array equals()
methodunu override etmez, bu nedenle object eşitliğini kullanır. İki farklı object eşit olmadığı için, F seçeneği
doğrudur ve E ve G seçenekleri yanlıştır.

10 - How many of these lines contain a compiler error? (Choose all that apply.)

10 - Bu satırlardan kaç tanesi compiler hatası içeriyor? (Geçerli olanların tümünü seçin.)

```
23: int one = Math.min(5, 3);
24: long two = Math.round(5.5);
25: double three = Math.floor(6.6);
26: var doubles = new double[] {one, two, three};
```

```
A. 0
B. 1
C. 2
D. 3
E. 4
```

**Cevap :** A. Bu satırların tümü compile edilir. min() ve floor() methodları, sırasıyla int ve double olarak geçirilen
aynı türü döndürür. round() methodu, bir double ile çağrıldığında bir long döndürür. Kod compile edildiği için A
seçeneği doğrudur.

```
int one = Math.min(5, 3);

long two = Math.round(5.5);
int roundIntReturnType = Math.round(3.14f);

double three = Math.floor(6.6);

var doubles = new double[] {one, two, three};
```

11 - What is the output of the following code?

11 - Aşağıdaki kodun çıktısı nedir?

```
var date = LocalDate.of(2022, 4, 3);
date.plusDays(2);
date.plusHours(3);
System.out.println(date.getYear() + " " + date.getMonth()
+ " " + date.getDayOfMonth());
```

```
A. 2022 MARCH 4
B. 2022 MARCH 6
C. 2022 APRIL 3
D. 2022 APRIL 5
E. Code compile edilmez
F. Runtime Exception fırlatılır
```

**Cevap :** E. Bir LocalDate'in time öğesi yoktur. Bu nedenle, saat eklemek için bir method yoktur, bu da E seçeneğini
doğru cevap yapar.

12 - What is output by the following code? (Choose all that apply.)

12 - Aşağıdaki kodun çıktısı nedir? (Geçerli olan her şeyi seçin.)

```
var numbers = "012345678".indent(1);
numbers = numbers.stripLeading();
System.out.println(numbers.substring(1, 3)); 
System.out.println(numbers.substring(7, 7));
System.out.print(numbers.substring(7));
```

```
A. 12
B. 123
C. 7
D. 78
E. Boş satır
F. Code compile edilmez
G. Exception fırlatılır
```

**Cevap :** A, D, E. İlk olarak, indent() çağrısının başa boşluk eklediğini ve stripLeading() çağrısının bunu hemen
çıkardığını unutmayın. Bu nedenle, bu methodlar birbirini iptal eder ve hiçbir etkisi yoktur. substring() methodunun iki
formu vardır. İlki başlamak için bir index ve hemen öncesinde durmak için bir index alır. İkincisi sadece başlamak
için bir index alır ve String'in sonuna kadar gider. Index'lerin sıfır tabanlı olduğunu unutmayın. İlk çağrı 1.
index'den başlar ve 3. index'in öncesinde durması gerektiği için 2. index'de biter. Bu bize A seçeneğini verir. İkinci
çağrı 7. index'den başlar ve aynı yerde biter, boş bir String ile sonuçlanır, bu da E seçeneğidir. Bu boş bir satır
yazdırır. Son çağrı 7. index'den başlar ve String'in sonuna kadar gider, D seçeneği ile biter.

13 - What is the result of the following code?

13 - Aşağıdaki kodun sonucu nedir?

```
public class Lion {
    public void roar(String roar1, StringBuilder roar2) {
        roar1.concat("!!!");
        roar2.append("!!!");
    }
    public static void main(String[] args) {
        var roar1 = "roar";
        var roar2 = new StringBuilder("roar");
        new Lion().roar(roar1, roar2);
        System.out.println(roar1 + " " + roar2);
} }
```

```
A. roar roar
B. roar roar!!!
C. roar!!! roar
D. roar!!! roar!!!
E. Exception fırlatılır
F. Code compile edilmez
```

**Cevap :** B. Bir String immutable'dır. concat() çağrısı yeni bir String döndürür ancak orijinalini değiştirmez. Bir
StringBuilder mutable'dır. append() çağrısı, mevcut karakter dizisine karakterler ekler ve aynı nesneye bir referans
döndürür. Bu nedenle, B seçeneği doğrudur.

14 - Given the following, which can correctly fill in the blank? (Choose all that apply.)

14 - Aşağıdakiler göz önüne alındığında, hangisi boşluğu doğru şekilde doldurabilir? (Geçerli olan her şeyi seçin.)

```
var date = LocalDate.now();
var time = LocalTime.now();
var dateTime = LocalDateTime.now();
var zoneId = ZoneId.systemDefault();
var zonedDateTime = ZonedDateTime.of(dateTime, zoneId);
Instant instant = _______________________;
```

```
A. Instant.now()
B. new Instant()
C. date.toInstant()
D. dateTime.toInstant()
E. time.toInstant()
F. zonedDateTime.toInstant()
```

**Cevap :** A, F. A seçeneği, current instant'ı doğru şekilde oluşturur. F seçeneği de uygun bir dönüşümdür. B seçeneği
yanlıştır çünkü Instant, diğer birçok date/time sınıfı gibi, genel bir constructor'a sahip değildir ve methodlar
aracılığıyla instantiated yapılır. C, D ve E seçenekleri yanlıştır çünkü kaynak nesne zaman içinde bir noktayı temsil
etmez. Zaman dilimi olmadan, Java hangi moment'i Instant için kullanacağını bilemez.

15 - What is the output of the following? (Choose all that apply.)

15 - Aşağıdakilerin çıktısı nedir? (Geçerli olan her şeyi seçin.)

```
var arr = new String[] { "PIG", "pig", "123"};
Arrays.sort(arr);
System.out.println(Arrays.toString(arr));
System.out.println(Arrays.binarySearch(arr, "Pippa"));
```

```
A. [pig, PIG, 123]
B. [PIG, pig, 123]
C. [123, PIG, pig]
D. [123, pig, PIG]
E. -3
F. -2
G. Bu örnekte binarySearch() işlevinin sonuçları undefined'dır.
```

**Cevap :** C, E. Sayılar harflerden önce ve büyük harfler küçük harflerden önce sıralanır. Bu, C seçeneğini cevaplardan
biri yapar. binarySearch() methodu, bir değerin ekleneceği yeri, yani Pippa array'i inceler. Doğru konum C seçeneğinde
ki 'PIG' in bir yanıdır. PIG index 1 de olduğu için Pippa 2. indexde yer alır, java bunu negates eder ve -2 haline
çevirir. Son olarak -1 ekleyeceğimiz için -2 -1 E seçeneğini doğru hale getirir

16 - What is included in the output of the following code? (Choose all that apply.)

16 - Aşağıdaki kodun çıktısında neler yer almaktadır? (Geçerli olan her şeyi seçin.)

```
var base = "ewe\nsheep\\t";
int length = base.length(); 
int indent = base.indent(2).length(); 
int translate = base.translateEscapes().length();

var formatted = "%s %s %s".formatted(length, indent, translate);
System.out.format(formatted);
```

```
A. 10
B. 11
C. 12
D. 13
E. 14
F. 15
G. 16
```

**Cevap :** A, B, G. İki escape karakteri olduğu için base'de 11 karakter vardır. \n yeni bir satırı temsil eden bir
karakter olarak ve \ bir ters eğik çizgiyi temsil eden bir karakter olarak sayılır. Bu, B seçeneğini cevaplardan biri
yapar. indent() methodu, base'in her iki satırının başına iki karakter ekler. Bu bize dört ek karakter verir. Ancak,
method ayrıca eksikse sonuna bir yeni satır ekleyerek normalize eder. Ek karakter, mevcut 11 karaktere beş karakter
eklediğimiz anlamına gelir, bu da G seçeneğidir. Son olarak, translateEscapes() methodu, herhangi bir text escape
karakterini gerçek kaçış karakterlerine çevirir, \\t'yi \t'ye dönüştürür. Bu, bir karakterden kurtulur ve base 10
karakter kalır, bu da A seçeneğiyle eşleşir.

17 - Which of these statements are true? (Choose all that apply.)

17 - Bu statement'lardan hangileri true? (Geçerli olan tümünü seçin.)

```
var letters = new StringBuilder("abcdefg");
```

```
A. letters.substring(1, 2) tek karakterli bir String döndürür.
B. letters.substring(2, 2) tek karakterli bir String döndürür.
C. letters.substring(6, 5) tek karakterli bir String döndürür.
D. letters.substring(6, 6) tek karakterli bir String döndürür.
E. letters.substring(1, 2) exception fırlatır
F. letters.substring(2, 2) exception fırlatır
G. letters.substring(6, 5) exception fırlatır
H. letters.substring(6, 6) exception fırlatır
```

**Cevap :** A, G. substring() methodu başlangıç index'ini içerir ancak bitiş index'ini içermez. 1 ve 2 ile
çağrıldığında, tek karakterli bir String döndürür, bu da A seçeneğini doğru ve E seçeneğini yanlış yapar. substring()'ı
her ikisi için de 2 ile çağırmak legal olarak mümkündür. Boş bir String döndürür, bu da B ve F seçeneklerini yanlış
yapar. Java, index'lerin ters sırada belirlenmesine izin vermez. G seçeneği doğrudur çünkü bir
StringIndexOutOfBoundsException atar. Son olarak, H seçeneği yanlıştır çünkü boş bir String döndürür.

18 - What is the result of the following code? (Choose all that apply.)

18 - Aşağıdaki kodun sonucu nedir? (Geçerli olan her şeyi seçin.)

```
13: String s1 = """
14:         purr""";
15: String s2 = "";
16:
17: s1.toUpperCase();
18: s1.trim();
19: s1.substring(1, 3);
20: s1 += "two";
21:
22: s2 += 2;
23: s2 += 'c';
24: s2 += false;
25:
26: if ( s2 == "2cfalse") System.out.println("==");
27: if ( s2.equals("2cfalse")) System.out.println("equals");
28: System.out.println(s1.length());
```

```
A. 2
B. 4
C. 7
D. 10
E. ==
F. equals
G. exception fırlatılır
H. Code compile edilmez
```

**Cevap :** C, F. Bu soru, birden fazla parçadan oluştuğu için biraz zorlayıcı. İlk olarak, 13. ve 14. satırlardaki
metin bloğunun, normal bir String'e eşdeğer olduğunu bilmeniz gerekir. Sonunda satır sonu olmadığı için bu, dört
karakterdir. Ardından, String nesnelerinin immutable olduğunu bilmeniz gerekir, yani 17-19 satırlarının sonuçları
göz ardı edilir. Son olarak, 20. satırda bir şeyler olur. Üç yeni karakteri s1'e ekliyoruz ve şimdi 7 karakter
uzunluğunda bir String'imiz var, bu da C seçeneğini doğru kılıyor. Daha sonra, s2 += 2, s2 = s2 + 2 olarak genişler. Bir
String, herhangi bir diğer türle concatenate edildiğinde bir String verir. 22, 23 ve 24 satırları, s2'ye ekleme yapar
ve "2cfalse" sonucunu verir. 27. satırdaki if statement'i, iki String object'inin değerlerini object equality
kullanılarak aynı olduğu için true döner. 26. satırdaki if statement'ı, iki String object'i bellekte aynı olmadığı için
false döner. Biri doğrudan string pool'undan gelir, diğeri ise String işlemleri kullanılarak oluşturulur.

19 - Which of the following fill in the blank to print a positive integer? (Choose all that apply.)

19 - Aşağıdakilerden hangisi pozitif bir tamsayı yazdırmak için boşluğu doldurur? (Geçerli olanların tümünü seçin.)

```
String[] s1 = { "Camel", "Peacock", "Llama"};
String[] s2 = { "Camel", "Llama", "Peacock"};
String[] s3 = { "Camel"};
String[] s4 = { "Camel", null};
System.out.println(Arrays._________________);
```

```
A. compare(s1, s2)
B. mismatch(s1, s2)
C. compare(s3, s4)
D. mismatch (s3, s4)
E. compare(s4, s4)
F. mismatch (s4, s4)
```

**Cevap :** A, B, D. compare() methodu, array'ler farklı olduğunda ve ilki daha büyük olduğunda pozitif bir tamsayı
döndürür. Bu durum, A seçeneği için geçerlidir. İki Object array'ini, comparable element'ler içinde, lexicographically
olarak karşılaştırır. Karşılaştırma, arraylerde ki her karakterin Unicode değerine dayanır. s1 array'inde ki 1 index'de
ki 'Peacock' için 'P' karakterinin Unicode değeri 'U+0050', s2 array'inde ki 1. index'de ki 'Llama' için ilk karakter
olan 'L' nin Unicode değeri 'U+004C' dir. Dolayısıyla P>L dir. Unicode değerlerinin "A "dan "Z "ye ve "a "dan "z "ye
sırayla artan tam sayılar olduğunu görmüş olacaksınız, bu nedenle aynı durumdaki karakterler için daha büyük, eşit veya
daha küçük belirlemek kolaydır. Sadece küçük harf karakterlerinin büyük harf karakterlerinden daha büyük Unicode
değerlerine sahip olduğunu unutmayın. Yani "P" == "P" ama "P" < "p" olur.B seçeneğinde ki mismatch() methodu, array'ler
1 veya daha büyük bir pozisyon index'inde farklı olduğunda pozitif bir tamsayı döndürür. C seçeneği s3 array'i s4'den
küçük olduğu için -1 döndürür. D seçeneğinde ki mismatch methodu 0. index'ler eşit olduğu ve s4'ün 1. index'inde null
olduğu için 1 değerini döndürür, farklı olan 1 tane eleman vardır. E ve F seçenekleri ikisi birden aynı array'i compare
ettiklerinden dolayı 0 döndürürler

20 - Note that March 13, 2022 is the weekend that clocks spring ahead for daylight saving time. What is the output of
the following? (Choose all that apply.)

20 - 13 Mart 2022'nin yaz saati uygulaması için saatlerin ileri alındığı hafta sonu olduğunu unutmayın. Aşağıdakilerin
çıktısı nedir? (Geçerli olan her şeyi seçin.)

```
var date = LocalDate.of(2022, Month.MARCH, 13);
var time = LocalTime.of(1, 30);
var zone = ZoneId.of("US/Eastern");
var dateTime1 = ZonedDateTime.of(date, time, zone);
var dateTime2 = dateTime1.plus(1, ChronoUnit.HOURS);

long diff = ChronoUnit.HOURS.between(dateTime1, dateTime2);
int hour = dateTime2.getHour();
boolean offset = dateTime1.getOffset() == dateTime2.getOffset();

System.out.println("diff = " + diff);
System.out.println("hour = " + hour);
System.out.println("offset = " + offset);
```

```
A. diff = 1
B. diff = 2
C. hour = 2
D. hour = 3
E. offset = true
F. Code compile edilmez
G. Runtime Exception fırlatır
```

**Cevap :** A, D. dateTime1 object'i, initialize edildiği anda 1:30 saatine sahiptir. dateTime2 object'i bir saat
sonradır. Ancak, ileriye atlama sırasında 2:30 yoktur, saat 3:30'a ayarlanır. A seçeneği doğrudur çünkü bir saat
sonradır. D seçeneği de doğrudur çünkü yeni saatin saati 3'tür. E seçeneği doğru değildir çünkü gün ışığından yararlanma
süresi nedeniyle saat dilimi offseti değiştirilmiştir.

21 - Which of the following can fill in the blank to print avaJ? (Choose all that apply.)

21 - Aşağıdakilerden hangisi avaJ yazdırmak için boşluğu doldurabilir? (Geçerli olan tümünü seçin.)

```
3: var puzzle = new StringBuilder("Java");
4: puzzle._____________ ;
5: System.out.println(puzzle);
```

```
A. reverse()
B. append("vaJ$").substring(0, 4)
C. append("vaJ$").delete(0, 3).deleteCharAt(puzzle.length() - 1)
D. append("vaJ$").delete(0, 3).deleteCharAt(puzzle.length())
E. Yukarıdakinlerden hiçbiri
```

**Cevap :** A, C. Bir StringBuilder'daki karakterleri tersine çevirmenin en kolay yolu reverse() methodudur; bu nedenle,
A seçeneği doğrudur. B seçeneğinde, substring() bir String döndürür ve bu String hiçbir yerde saklanmaz. C seçeneği,
yöntem zincirleme kullanır. İlk olarak, "JavavaJ$" değerini oluşturur. Ardından, ilk üç karakteri kaldırır ve "avaJ$"
olur. Son olarak, son karakteri kaldırır ve "avaJ" olur. D seçeneği, son indeksten sonraki karakteri silemeyeceğiniz
için bir exception fırlatır. Unutmayın ki deleteCharAt(), sıfıra dayalı indeksler kullanır ve length(), indeks yerine
karakter sayısını sayar.

22 - What is the output of the following code?

22 - Aşağıdaki kodun çıktısı nedir?

```
var date = LocalDate.of(2022, Month.APRIL, 30);

date.plusDays(2);
date.plusYears(3);

System.out.println(date.getYear() + " " + date.getMonth() + " " + date.getDayOfMonth());
```

```
A. 2022 APRIL 30
B. 2022 MAY 2
C. 2025 APRIL 2
D. 2025 APRIL 30
E. 2025 MAY 2
F. Code compile edilmez
G. Runtime Exception fırlatır
```

**Cevap :** A. Date, 2022 yılının 30 Nisan'ı olarak başlar. Date'ler immutable'dır ve plus methodlarının dönüş
değerleri göz ardı edildiğinden, sonuç değişmeden kalır. Bu nedenle, A seçeneği doğrudur.