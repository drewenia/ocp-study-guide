# Review Questions

1 - Which of the following data types can be used in a switch expression? (Choose all that apply.)

1 - Aşağıdaki veri türlerinden hangisi bir switch expression'ın da kullanılabilir? (Geçerli olan tümünü seçin.)

```
A. enum
B. int
C. Byte
D. long
E. String
F. char
G. var
H. double
```

**Cevap :**  A, B, C, E, F, G. Bir switch expression'ı yalnızca int, byte, short ve char gibi primitive veri türlerini
ve bunlarla ilişkili Integer, Byte, Short ve Character wrapper sınıflarını destekler. Bu, B, C ve F seçeneklerini doğru
kılar ve D ile H seçeneklerini devre dışı bırakır. Ayrıca enum ve String veri türlerini de destekler, bu da A ve E
seçeneklerini doğru yapar. Son olarak, switch, türü desteklenen bir switch veri türüne çözümlenebiliyorsa var
keyword'unu de destekler, bu da G seçeneğini doğru kılar.

2 - What is the output of the following code snippet? (Choose all that apply.)

2 - Aşağıdaki kod parçacığının çıktısı nedir? (Geçerli olan her şeyi seçin.)

```
3: int temperature = 4;
4: long humidity = -temperature + temperature * 3;
5: if (temperature>=4)
6: if (humidity < 6) System.out.println("Too Low");
7: else System.out.println("Just Right");
8: else System.out.println("Too High");
```

```
A. Too Low
B. Just Right
C. Too High
D. Runtime'da NullPointerException fırlatılır
E. Satır 7 den ötürü code compile edilmez
F. Satır 8 den ötürü code compile edilmez
```

**Cevap :** B. Kod derlenir ve sorunsuz şekilde çalışır Bu nedenle D, E ve F seçenekleri yanlıştır. Satır 7 ve 8'deki
ardışık iki else statement'i biraz garip görünebilir, ancak bunlar sırasıyla satır 5 ve 6'daki ayrı if statement'larıyla
ilişkilidir. Satır 4'teki humidity değeri -4 + 12'ye eşittir, yani sonuç 8'dir. Satır 5'teki ilk if statement'i true
olarak değerlendirilir, bu nedenle satır 6 çalıştırılır ve false olarak değerlendirilir. Bu durum satır 7'deki else
ifadesinin çalışmasına neden olur ve "Just Right" yazdırılır. Bu nedenle B seçeneği doğru cevaptır.

3 - Which of the following data types are permitted on the right side of a for-each expression? (Choose all that apply.)

3 - Bir for-each expression'ının sağ tarafında aşağıdaki veri türlerinden hangisine izin verilir? (Geçerli olan tümünü
seçin.)

```
A. Double[][]
B. Object
C. Map
D. List
E. String
F. char[]
G. Exception
H. Set
```

**Cevap :** A, D, F, H. A for-each döngüsü, array'leri destekler, bu nedenle A ve F seçenekleri doğrudur. Double[][]
için, for-each döngüsünün her elemanı bir Double[] olacaktır. Bir for-each döngüsü ayrıca java.lang.Iterable'ı implement
eden sınıfları da destekler. Bu, birçok Collections Framework sınıfını içerir, ancak bunların hepsi java.lang.Iterable'ı
implement etmez. Bu nedenle, C seçeneği yanlıştır ve D ile H seçenekleri doğrudur. B, E ve G seçenekleri yanlıştır,
çünkü java.lang.Iterable'ı implement etmezler. Bir String, sıralı karakterlerden oluşan bir liste olsa da, sınıf,
for-each döngüsü için gerekli interface'i implement etmez.

4 - What is the output of calling printReptile(6)?

4 - printReptile(6) çağrısının çıktısı nedir?

```
void printReptile(int category) {
    var type = switch(category) {
        case 1,2 -> "Snake";
        case 3,4 -> "Lizard";
        case 5,6 -> "Turtle";
        case 7,8 -> "Alligator";
    };
    System.out.print(type);
}
```

```
A. Snake
B. Lizard
C. Turtle
D. Alligator
E. TurtleAlligator
F. Yukarıdakinlerden hiçbiri
```

F. Kod compile edilemez çünkü switch expression, tüm olası durum değerlerinin ele alınmasını gerektirir, bu da F
seçeneğini doğru yapar. Geçerli bir default statement'i eklenirse, kod compile edilir ve runtime'da Turtle yazdırılır.
Geleneksel switch statement'larının aksine, switch expression'ları tam olarak bir branch'i çalıştırır ve case
statement'ları arasında break komutları kullanılmaz.

5 - What is the output of the following code snippet?

5 - Aşağıdaki kod parçacığının çıktısı nedir?

```
List<Integer> myFavoriteNumbers = new ArrayList<>();
myFavoriteNumbers.add(10);
myFavoriteNumbers.add(14);

for (var a : myFavoriteNumbers) {
    System.out.print(a + ", ");
    break;
}

for (int b : myFavoriteNumbers) {
    continue;
    System.out.print(b + ", ");
}

for (Object c : myFavoriteNumbers)
    System.out.print(c + ", ");
```

```
A. Sorunsuz bir şekilde compile ediliyor ve çalışıyor ancak herhangi bir çıktı üretmiyor.
B. 10, 14,
C. 10, 10, 14,
D. 10, 10, 14, 10, 14,
E. Tam olarak bir satır kod derlenmiyor.
F. Tam olarak iki satır kod derlenmiyor.
G. Üç veya daha fazla satır kod derlenmez.
H. Kod infinite bir loop içeriyor ve sonlanmıyor.
```

**Cevap :** E. İkinci for-each döngüsü, bir continue statement'i ve ardından bir print() statement'i içerir. Çünkü
continue statement'i koşullu değildir ve her zaman for-each döngüsünün body'sinin bir parçası olarak dahil edilir,
print() statement'i ulaşılabilir değildir. Bu nedenle, print() statement'i compile edilemez. Bu, tek compiler hatası
olduğu için E seçeneği doğrudur. Diğer kod satırları herhangi bir sorun olmadan compile edilir.

6 - Which statements about decision structures are true? (Choose all that apply.)

6 - Karar yapıları hakkında hangi statement'lar true? (Geçerli olan tümünü seçin.)

```
A. Bir for-each döngüsü herhangi bir Collections Framework nesnesi üzerinde yürütülebilir.

B. Bir while döngüsünün gövdesinin en az bir kez çalıştırılacağı garanti edilir.

C. Bir for döngüsünün conditional expression'ı (koşullu ifadesi), döngü body'sinin ilk execution'ından önce
değerlendirilir.

D. Bir String alan ve sonucu bir değişkene atayan bir switch expression'ı, default bir branch gerektirir.

E. Bir do/while döngüsünün body'sinin en az bir kez çalıştırılacağı garanti edilir.

F. Bir if statement'i birden fazla karşılık gelen else statement'ına sahip olabilir.
```

**Cevap :** C, D, E. Bir for-each döngüsü, java.lang.Iterable'ı implement eden herhangi bir Collections objesinde
çalıştırılabilir, örneğin List veya Set, ancak Map gibi bazı Collections sınıflarında çalışmaz, bu yüzden A seçeneği
yanlıştır. Bir do/while döngüsünün gövdesi bir veya daha fazla kez çalıştırılırken, while döngüsünün gövdesi sıfır veya
daha fazla kez çalıştırılır, bu da E seçeneğini doğru, B seçeneğini ise yanlış yapar. For döngülerinin koşullu ifadesi,
döngü çalıştırılmadan önce değerlendirilir, bu da for döngüsünün sıfır veya daha fazla kez çalıştırılabileceği anlamına
gelir, bu yüzden C seçeneği doğrudur. Bir String alan switch expression'ı, sonucu bir değişkene atıyorsa bir default
branch'i gerektirir, bu da D seçeneğini doğru yapar. Son olarak, her if statement'ının en fazla bir eşleşen else
statement'ı vardır, bu yüzden F seçeneği yanlıştır.

7 - Assuming weather is a well-formed nonempty array, which code snippet, when inserted independently into the blank in
the following code, prints all of the elements of weather? (Choose all that apply.)

7 - Hava durumunun iyi biçimlendirilmiş boş olmayan bir array olduğunu varsayarsak, aşağıdaki kodda boşluğa bağımsız
olarak eklendiğinde hangi kod parçacığı hava durumunun tüm öğelerini yazdırır? (Geçerli olan tümünü seçin.)

```
private void print(int[] weather) {
    for(_____________) {
        System.out.println(weather[i]);
    }
}
```

```
A. int i=weather.length; i>0; i--
B. int i=0; i<=weather.length-1; ++i
C. var w : weather
D. int i=weather.length-1; i>=0; i--
E. int i=0, int j=3; i<weather.length; ++i
F. int i=0; ++i<10 && i<weather.length;
G. Yukarıdakinlerden hiçbiri
```

**Cevap :** B, D. A seçeneği yanlıştır çünkü ilk iteration'da, boş olmayan array'in weather[weather.length] öğesine
erişmeye çalışır, bu da bir ArrayIndexOutOfBoundsException hatasına yol açar. B seçeneği doğrudur ve elemanları sırayla
yazdıracaktır. C seçeneği compile edilemez çünkü i, weather[i] içinde tanımlanmamıştır. Bunun çalışabilmesi için,
for-each döngüsünün body'si de güncellenmelidir. D seçeneği de doğrudur ve array'in elemanlarını ters sırayla
yazdırmanın yaygın bir yoludur. E seçeneği compile edilemez ve bu nedenle yanlıştır. Bir for döngüsünde birden fazla öğe
declaration'ı yapılabilir, ancak veri türü sadece bir kez belirtilmelidir, örneğin for(int i=0, j=3; ...) şeklinde. Son
olarak, F seçeneği yanlıştır çünkü array'in ilk elemanı atlanır. Koşul ifadesi döngü ilk kez çalıştırılmadan önce
kontrol edildiğinden, döngü gövdesında kullanılan ilk i değeri 1 olacaktır.

8 - What is the output of calling printType(11)?

8 - printType(11) çağrısının çıktısı nedir?

```
31: void printType(Object o) {
32:     if(o instanceof Integer bat) {
33:         System.out.print("int");
34:     } else if(o instanceof Integer bat && bat < 10) {
35:         System.out.print("small int");
36:     } else if(o instanceof Long bat || bat <= 20) {
37:         System.out.print("long");
38:     } default {
39:         System.out.print("unknown");
40:     }
41: }
```

```
A. int
B. small int
C. long
D. unknown
E. Hiç bir şey print edilmez
F. Tam olarak bir satır kod derlenmiyor.
G. Tam olarak iki satır kod derlenmiyor.
H. Yukarıdakinlerden hiçbiri
```

**Cevap :** G. İlk iki pattern matching statement'i sorunsuz bir şekilde derlenir. bat değişkeninin, artık scope'da
olmadığından emin olunarak yeniden kullanılmasına izin verilir. Ancak 36. satır derlenemez. Flow scoping nedeniyle, 'o'
bir Long değilse, 'bat' bat <= 20 expression'ının da scope'da değildir. 38. satır da compile edilmez çünkü default bir
if/else statement'ının parçası olarak kullanılamaz. Bu iki nedenle, G seçeneği doğrudur.

9 - Which statements, when inserted independently into the following blank, will cause the code to print 2 at runtime? (
Choose all that apply.)

9 - Hangi statement'lar, aşağıdaki boşluğa bağımsız olarak eklendiğinde, kodun runtime'da 2 yazdırmasına neden olur? (
Geçerli olan tümünü seçin.)

```
int count = 0;
BUNNY: for(int row = 1; row <=3; row++)
    RABBIT: for(int col = 0; col <3 ; col++) {
        if((col + row) % 2 == 0)
            __________________;
        count++;
    }
System.out.println(count);
```

```
A. break BUNNY
B. break RABBIT
C. continue BUNNY
D. continue RABBIT
E. break
F. continue
G. Kod bir compiler hatası içerdiğinden yukarıdakilerin hiçbiri.
```

**Cevap :** B, C, E. Kod, nested bir loop ve col + row toplamı çift bir sayı olduğunda çalıştırılan bir koşullu ifade
içeriyor; aksi takdirde, count artırılıyor. E ve F seçenekleri, sırasıyla B ve D seçeneklerine eşdeğer olup,
unlabeled statement'lar most inner loop'a (en iç döngüye) uygulanır. Döngüleri incelediğimizde, koşulun ilk kez true
olduğu durum, inner loop'un ikinci iterasyonunda, row 1 ve col 1 olduğunda gerçekleşir. A seçeneği yanlıştır çünkü bu,
döngünün hemen çıkmasına ve count'un yalnızca 1 olarak ayarlanmasına yol açar. B, C ve E seçenekleri aynı yolu takip
eder. İlk olarak, count ilk inner loop'da 1'e artırılır, ardından inner loop'dan çıkılır. Outer loop'un bir sonraki
iterasyonunda, row 2 ve col 0 olduğunda, inner loop'dan hemen çıkılır. Outer loop'un üçüncü iterasyonunda, row 3 ve col
0 olduğunda, count 2'ye artırılır. Inner loop'un bir sonraki iterasyonunda toplam çift olduğu için çıkılır ve program
tamamlanır, bu nedenle B, C ve E seçeneklerinin her biri doğrudur. D ve F seçenekleri yanlıştır çünkü inner ve outer
loop'ların birden fazla kez çalışmasına yol açar ve count değeri 5 olduğunda tamamlanır. Tüm iterasyonları izlemeye
gerek yoktur; sadece count değeri 2'yi geçtiğinde durun.

10 - Given the following method, how many lines contain compilation errors? (Choose all that apply.)

10 - Aşağıdaki method göz önüne alındığında, kaç satır compiler hatası içerir? (Geçerli olanların tümünü seçin.)

```
10: private DayOfWeek getWeekDay(int day, final int thursday) {
11:     int otherDay = day;
12:     int Sunday = 0;
13:     switch(otherDay) {
14:         default:
15:         case 1: continue;
16:         case thursday: return DayOfWeek.THURSDAY;
17:         case 2,10: break;
18:         case Sunday: return DayOfWeek.SUNDAY;
19:         case DayOfWeek.MONDAY: return DayOfWeek.MONDAY;
20:     }
21:     return DayOfWeek.FRIDAY;
22: }
```

```
A. Yok, kod sorunsuz bir şekilde compile ediliyor.
B. 1
C. 2
D. 3
E. 4
F. 5
G. 6
H. Kod compile edilir ancak runtime'da hata verebilir.
```

**Cevap :** E. Bu kod birçok compiler hatası içeriyor, bu da A ve H seçeneklerini yanlış kılar. 15. satır compile
edilmez, çünkü continue bu şekilde bir switch statement'i içinde kullanılamaz. 16. satır bir compile time constant'i
değildir, çünkü herhangi bir int değeri parametre olarak geçirilebilir. final olarak işaretlemek bunu değiştirmez, bu
yüzden compile edilemez. 18. satır compile edilemez çünkü Sunday final olarak işaretlenmemiştir. Etkin olarak final
olmak yeterli değildir. Son olarak, 19. satır compile edilemez çünkü DayOfWeek.MONDAY bir int değeri değildir. switch
statement'ları enum değerlerini desteklese de, her case statement'i, switch değişkeni olan otherDay ile aynı veri türüne
sahip olmalıdır, bu da int'tir. Diğer satırlar compile edilebilir. Tam olarak dört satır compile edilmediği için, E
seçeneği doğru cevaptır.

11 - What is the output of calling printLocation(Animal.MAMMAL)?

11 - printLocation(Animal.MAMMAL) çağrısının çıktısı nedir?

```
10: class Zoo {
11:     enum Animal {BIRD, FISH, MAMMAL}
12:     void printLocation(Animal a) {
13:         long type = switch(a) {
14:             case BIRD -> 1;
15:             case FISH -> 2;
16:             case MAMMAL -> 3;
17:             default -> 4;
18:         };
19:     System.out.print(type);
20: } }
```

```
A. 3
B. 4
C. 34
D. Satır 13 den dolayı code compile edilmez
E. Satır 17 den dolayı code compile edilmez
F. Yukarıdakinlerden hiçbiri
```

**Cevap :** A. Kod compile edilir ve sorunsuz bir şekilde çalışır, runtime'da 3 yazdırır ve bu da A seçeneğini doğru
yapar. 17. satırdaki default statement'ı optional'dir çünkü tüm enum değerleri dikkate alınmıştır ve output
değiştirmeden kaldırılabilir.

12 - What is the result of the following code snippet?

12 - Aşağıdaki kod parçacığının sonucu nedir?

```
3: int sing = 8, squawk = 2, notes = 0;
4: while(sing > squawk) {
5:    sing--;
6:    squawk += 2;
7:    notes += sing + squawk; 
8: }
9: System.out.println(notes);
```

```
A. 11
B. 13
C. 23
D. 33
E. 50
F. Satır 7 den dolayı code compile edilmez
```

**Cevap :** C. İlk iterasyondan önce, sing = 8, squawk = 2 ve notes = 0 değerlerindedir. İlk döngünün iterasyonundan
sonra, sing 7'ye, squawk 4'e güncellenir ve notes, yeni sing + squawk değerlerinin toplamına eşitlenir: 7 + 4 = 11.
İkinci döngü iterasyonundan sonra, sing 6'ya, squawk 6'ya güncellenir ve notes, kendisi ile yeni sing + squawk
değerlerinin toplamına eşitlenir: 11 + 6 + 6 = 23. Döngünün üçüncü iterasyonunda, sing > squawk ifadesi false olur,
çünkü 6 > 6 ifadesi false'tur. Döngü sona erer ve sing'in en son değeri, yani 23, çıktı olarak verilir, bu yüzden doğru
cevap C seçeneğidir.

13 - What is the output of the following code snippet?

13 - Aşağıdaki kod parçacığının çıktısı nedir?

```
2: boolean keepGoing = true;
3: int result = 15, meters = 10;
4: do {
5:      meters--;
6:      if(meters==8) keepGoing = false;
7:      result -= 2;
8: } while keepGoing;
9: System.out.println(result);
```

```
A. 7
B. 9
C. 10
D. 11
E. 15
F. Satır 6 dan dolayı code compile edilmez
G. Farklı sebeplerden ötürü code compile edilmez
```

**Cevap :** G. Bu örnek karmaşık görünebilir, ancak kod compile edilemez. 8. satırda, boolean koşullu ifadesinin
etrafında gerekli parantezler eksiktir. Kod compile edilemediği için ve bu durum 6. satırdan kaynaklanmadığı için, doğru
cevap G seçeneğidir. Eğer 8. satırdaki hata parantezlerle düzeltilseydi, döngü iki kez çalıştırılırdı ve çıktı 11
olurdu.

14 - Which statements about the following code snippet are correct? (Choose all that apply.)

14 - Aşağıdaki kod parçacığı ile ilgili hangi statement'lar doğrudur? (Geçerli olan tümünü seçin.)

```
for(var penguin : new int[2])
    System.out.println(penguin);
var ostrich = new Character[3];
for(var emu : ostrich)
    System.out.println(emu);
List<Integer> parrots = new ArrayList<Integer>();
for(var macaw : parrots)
    System.out.println(macaw);
```

```
A. Penguen'in data type'ı Integer'dır.
B. Penguen'in data type'ı int'dir
C. emu'nun data type'ı undefined'dır
D. emu'nun data type'ı Character'dir
E. macaw'in data type'ı List'dir.
F. macaw'in data type'ı Integer'dır
G. Kod derlenmediği için yukarıdakilerin hiçbiri.
```

**Cevap :** B, D, F. Kod compile edilir, bu da G seçeneğini yanlış yapar. İlk for-each döngüsünde, döngünün sağ tarafı
int[] türündedir, bu nedenle her bir eleman olan penguin int türündedir, bu da B seçeneğini doğru yapar. İkinci for-each
döngüsünde, ostrich Character[] türündedir, bu nedenle emu Character türünde olur, bu da D seçeneğini doğru yapar. Son
for-each döngüsünde, parrots List<Integer> türündedir. List'te Integer jenerik türü kullanıldığından, macaw Integer
türünde olur, bu da F seçeneğini doğru yapar.

15 - What is the result of the following code snippet?

15 - Aşağıdaki kod parçacığının sonucu nedir?

```
final char a = 'A', e = 'E';
char grade = 'B';
switch (grade) {
    default:
    case a:
    case 'B': 'C': System.out.print("great ");
    case 'D': System.out.print("good "); break;
    case e:
    case 'F': System.out.print("not good ");
}
```

```
A. great
B. great good
C. good
D. not good
E. Bir veya daha fazla case statement'ının veri türü switch değişkeninin veri türüyle eşleşmediği için kod compile olmaz.
F. Yukarıdakinlerden hiçbiri
```

**Cevap :** F. Kod derlenmez, ancak E seçeneğinde belirtilen nedenden dolayı değil. İkinci case statement'ı geçersiz bir
syntax'a sahiptir. Her case statement'i case anahtar kelimesini içermelidir — diğer bir deyişle, bunları bir : ile
zincirleyemezsiniz. Bu nedenle, doğru cevap F seçeneğidir. Bu satır, case 'B', 'C' şeklinde düzeltilmiş veya 'C''den
önce case anahtar kelimesi eklenmiş olsaydı, kod geri kalan kısmıyla derlenir ve çalışma zamanında great good çıktısını
verirdi.

16 - Given the following array, which code snippets print the elements in reverse order from how they are declared? (
Choose all that apply.)

16 - Aşağıdaki array verildiğinde, hangi kod parçacıkları elemanları bildirildikleri sıranın tersine yazdırır? (Geçerli
olan tümünü seçin.)

```
char[] wolf = {'W', 'e', 'b', 'b', 'y'};
```

A.

```
int q = wolf.length;
for( ; ; ) {
    System.out.print(wolf[--q]);
    if(q==0) break;
}
```

B.

```
for(int m=wolf.length-1; m>=0; --m)
    System.out.print(wolf[m]);
```

C.

```
for(int z=0; z<wolf.length; z++)
    System.out.print(wolf[wolf.length-z]);
```

D.

```
int x = wolf.length-1;
for(int j=0; x>=0 && j==0; x--)
    System.out.print(wolf[x]);
```

E.

```
final int r = wolf.length;
for(int w = r-1; r>-1; w = r-1)
    System.out.print(wolf[w]);
```

F.

```
for(int i=wolf.length; i>0; --i)
    System.out.print(wolf[i]);
```

G. Yukarıdakinlerden hiçbiri

**Cevap :** A, B, D. wolf array'inde ki öğeleri ters sırayla yazdırmak için kodun wolf [wolf.length - 1] ile başlaması
ve wolf[0] ile bitmesi gerekir. A seçeneği bunu başarıyla yapar ve ilk doğru cevaptır. B seçeneği de doğrudur ve ters
bir döngünün yazılmasının en yaygın yollarından biridir. Bitiş koşulu genellikle m >= 0 veya m > -1 şeklinde yazılır ve
her ikisi de doğrudur. C ve F seçenekleri, runtime'da bir ArrayIndexOutOfBoundsException hatasına neden olur çünkü
her ikisi de ilk olarak wolf[wolf.length]'den okuma yapar; bu, wolf dizisinin 0 tabanlı dizinini aştığı için hataya yol
açar. C seçeneği, değer wolf[wolf.length - z - 1] olarak değiştirilirse başarılı olur. D seçeneği de doğrudur, çünkü j
gereksizdir ve bu örnekte göz ardı edilebilir. Son olarak, E seçeneği yanlıştır ve sonsuz bir döngü üretir, çünkü w, her
döngü iterasyonunda tekrar tekrar r - 1 (bu durumda 4) olarak ayarlanır. Güncelleme ifadesi ilk iterasyondan sonra
hiçbir etkiye sahip olmadığından, koşul asla sağlanmaz ve döngü sonlanmaz.

17 - What distinct numbers are printed when the following method is executed? (Choose all that apply.)

17 - Aşağıdaki method çalıştırıldığında hangi farklı sayılar yazdırılır? (Geçerli olanların tümünü seçin.)

```
private void countAttendees() {
    int participants = 4, animals = 2, performers = -1;
    while((participants = participants+1) < 10) {}
    do {} while (animals++ <= 1);
    for( ; performers<2; performers+=2) {}
    System.out.println(participants);
    System.out.println(animals);
    System.out.println(performers);
}
```

```
A. 6
B. 3
C. 4
D. 5
E. 10
F. 9
G. Bu code compile edilmez
H. Yukarıdakinlerden hiçbiri
```

**Cevap :** B, E. Kod sorunsuz bir şekilde compile edilir ve runtime'da iki farklı sayı yazdırır, bu nedenle G ve H
seçenekleri yanlıştır. İlk döngü toplamda beş kez çalışır ve döngü, participants değeri 10 olduğunda sona erer. Bu
nedenle, E seçeneği doğrudur. İkinci döngüde, animals başlangıçta 1'e eşit veya daha küçük değildir, ancak bir do/while
döngüsü olduğu için en az bir kez çalışır. Bu şekilde, animals değeri 3 olur ve döngü sona erer, bu da B seçeneğini
doğru yapar. Son olarak, son döngü toplamda iki kez çalışır; performers başlangıçta -1 değeriyle başlar, ilk döngü
sonunda 1'e gider ve ikinci döngüden sonra 3 değerine ulaşıp döngüyü sonlandırır. Bu da B seçeneğini bir kez daha doğru
yapar.

18 - Which statements about pattern matching and flow scoping are correct? (Choose all that apply.)

18 - Pattern matching and Flow scoping ile ilgili hangi statement'lar doğrudur? (Geçerli olan tümünü seçin.)

```
A. Bir if statement'ı ile pattern matching, instance operatörü kullanılarak implement edilir

B. Bir if statement'ı ile pattern matching, instanceon operatörü kullanılarak implement edilir

C. Bir if statement'ı ile pattern matching, instanceof operatörü kullanılarak implement edilir

D. Pattern variable, tanımlandığı if statement'dan sonra erişilemez.

E. Flow scoping, bir pattern variable'inin yalnızca compiler'in type'ını belirleyebildiği durumlarda erişilebilir olduğu
anlamına gelir.

F. Pattern matching, bir else statement'ı ile bir variable tanımlamak için kullanılabilir.
```

**Cevap :** C, E. Bir if statement'ı ile pattern matching, instanceof operatörü kullanılarak uygulanır; bu nedenle C
seçeneği doğrudur, A ve B seçenekleri ise yanlıştır. D seçeneği yanlıştır, bir pattern variable'ına tanımlandığı if
statement'ının dışında erişmek mümkün olduğundan D seçeneği yanlıştır. E seçeneği flow scoping ile ilgili doğru bir
ifadedir. F seçeneği yanlıştır. Pattern matching, else statement'larında değişken tanımlamayı desteklemez, çünkü else
statement'ları bir boolean ifade içermez.

19 - What is the output of the following code snippet?

19 - Aşağıdaki kod parçacığının çıktısı nedir?

```
2: double iguana = 0;
3: do {
4:      int snake = 1;
5:      System.out.print(snake++ + " ");
6:      iguana--;
7: } while (snake <= 5);
8: System.out.println(iguana);
```

```
A. 1 2 3 4 -4.0
B. 1 2 3 4 -5.0
C. 1 2 3 4 5 -4.0
D. 0 1 2 3 4 5 -5.0
E. Code compile edilmez
F. Kod compile ediliyor ancak runtime'da infinite bir loop oluşturuyor.
G. Yukarıdakinlerden hiçbiri
```

**Cevap :** E. snake değişkeni, do/while statement'ini body'sinde tanımlandığından, 7. satırda scope dışında kalır. Bu
nedenle, E seçeneği doğru cevaptır. Eğer snake 3. satırdan önce 1 değeriyle tanımlanmış olsaydı, çıktı 1 2 3 4 5 - 5.0
olurdu ve bu durumda G seçeneği doğru olurdu.

20 - Which statements, when inserted into the following blanks, allow the code to compile and run without entering an
infinite loop? (Choose all that apply.)

20 - Aşağıdaki boşluklara hangi statement'lar eklendiğinde kodun infinite loop'a girmeden compile edilmesini ve
çalışmasını sağlar? (Geçerli olan tümünü seçin.)

```
4: int height = 1;
5: L1: while(height++ <10) {
6:      long humidity = 12;
7:      L2: do {
8:          if(humidity-- % 12 == 0) _______________;
9:          int temperature = 30;
10:         L3: for( ; ; ) {
11:             temperature++;
12:             if(temperature>50) _______________;
13:         }
14:     } while (humidity > 4);
15: }
```

```
A. break L2 8.satırda; continue L2 12.satırda
B. continue 8. satıda; continue 12.satırda
C. break L3 8.satırda; break L1 12.satırda
D. continue L2 8.satırda; continue L3 12.satırda
E. continue L2 8.satırda; continue L2 12.satırda
F. Kod bir compiler hatası içerdiğinden yukarıdakilerin hiçbiri
```

**Cevap :** A, E. Bu kodu incelerken en önemli şey, innermost loop'un (en içteki döngünün) bir infinity loop olduğuna
dikkat etmektir. Bu nedenle, innermost loop'u tamamen atlayan veya bu loop'dan çıkan çözümleri arıyorsunuz.A seçeneği
doğrudur, çünkü 8. satırdaki break L2, ikinci iç döngüden çıkılmasını sağlar ve böylece innermost loop'u tamamen atlar.
B seçeneği yanlıştır, çünkü 8. satırdaki ilk continue, ikinci döngünün ilk iterasyonunda innermost loop'u atlar, ancak
ikinci iterasyonda atlamaz. Innermost loop'u çalıştırılır ve 12. satırdaki continue, runtime'da bir sonsuz döngüye
neden olur. C seçeneği yanlıştır, çünkü bir compiler hatası içerir. Label L3, kendi döngüsünün dışından görünür
değildir. D seçeneği yanlıştır, çünkü unlabeled break ve continue, en yakın döngüye uygulanır ve bu nedenle runtime'da
bir sonsuz döngüye neden olur. E seçeneği doğrudur, çünkü 8. satırdaki continue L2, innermost loop'u ikinci iç döngü
her çağrıldığında çalıştırır. Ancak 12. satırdaki continue L2, sonsuz döngüden çıkarak kontrolü ikinci döngüye geri
döndürür. İlk ve ikinci döngüler tamamlandığı için kod sorunsuz bir şekilde sonlanır.

21 - A minimum of how many lines need to be corrected before the following method will compile?

21 - Aşağıdaki methodun compile edilebilmesi için en az kaç satırın düzeltilmesi gerekir?

```
21: void findZookeeper(Long id) {
22:     System.out.print(switch(id) {
23:         case 10 -> {"Jane"}
24:         case 20 -> {yield "Lisa";};
25:         case 30 -> "Kelly";
26:         case 30 -> "Sarah";
27:         default -> "Unassigned";
28:     });
29: }
```

```
A. Zero
B. One
C. Two
D. Three
E. Four
F. Five
```

**Cevap :** E. 22. satır compile edilmez, çünkü Long bir switch statement'i veya expression'ı için uyumlu bir tür
değildir. 23. satır compile edilmez, çünkü "Jane" statement'ından sonra noktalı virgül (;) eksiktir ve bir yield
statement gereklidir. 24. satır derlenmez, çünkü satırın sonunda fazladan bir noktalı virgül bulunmaktadır. 25. ve 26.
satırlar compile edilmez, çünkü her iki satır da aynı case değerini kullanmaktadır. Kodun derlenebilmesi için bu
değerlerden en az birinin değiştirilmesi gerekir. Bu dört hatanın düzeltilmesi gerektiğinden, E seçeneği doğrudur.

22 - What is the output of the following code snippet? (Choose all that apply.)

22 - Aşağıdaki kod parçacığının çıktısı nedir? (Geçerli olan her şeyi seçin.)

```
2: var tailFeathers = 3;
3: final var one = 1;
4: switch (tailFeathers) {
5:      case one: System.out.print(3 + " ");
6:      default: case 3: System.out.print(5 + " ");
7: }
8: while (tailFeathers > 1) {
9: System.out.print(--tailFeathers + " "); }
```

```
A. 3
B. 5 1
C. 5 2
D. 3 5 1
E. 5 2 1
F. Kod, 3-5 satırları nedeniyle compile edilmeyecektir.
G. Kod, 6. satır nedeniyle compile edilmeyecektir.
```

**Cevap :** E. Kod sorunsuz bir şekilde derlenir, bu da F ve G seçeneklerini yanlış yapar. Unutmayın, 'var' hem switch
hem de while döngülerinde desteklenir, ancak compiler'in bu statement'larla uyumlu bir type belirlemesi gerekir. Ayrıca,
one değişkeni bir case ifadesinde kullanılabilir çünkü bu bir final local variable'dır ve bu nedenle compile time'da
constant'ıdır. tailFeathers değişkeninin değeri 3'tür ve bu, ikinci case statement'i ile eşleşir; dolayısıyla ilk çıktı
5'tir. while döngüsü iki kez çalıştırılır ve pre-decrement operatörü (--) tailFeathers değerini 3'ten önce 2'ye, sonra
ikinci döngüde 1'e düşürür. Bu nedenle, son çıktı 5 2 1 olur ve doğru cevap E seçeneğidir

23 - What is the output of the following code snippet?

23 - Aşağıdaki kod parçacığının çıktısı nedir?

```
15: int penguin = 50, turtle = 75;
16: boolean older = penguin >= turtle;
17: if (older = true) System.out.println("Success");
18: else System.out.println("Failure");
19: else if(penguin != 50) System.out.println("Other");
```

```
A. Success
B. Failure
C. Other
D. Kod, 17. satır nedeniyle compile edilmeyecektir.
E. Code compile edilir ancak runtime'da exception fırlatır
F. Yukarıdakinlerden hiçbiri
```

**Cevap :** F. 19. satır bir else statement'ı ile başlıyor, ancak onunla eşleşen bir önceki if statement'ı yok. Bu
nedenle, 19. satır compile edilmez ve doğru cevap F seçeneğidir. Eğer 19. satırdan else anahtar kelimesi kaldırılmış
olsaydı, kod parçacığı Success çıktısını verirdi.

24 - Which of the following are possible data types for friends that would allow the code to compile? (Choose all that
apply.)

24 - Aşağıdakilerden hangisi kodun compile edilmesini sağlayacak olası friends veri türleridir? (Geçerli olan tümünü
seçin.)

```
for(var friend in friends) {
    System.out.println(friend);
}
```

```
A. Set
B. Map
C. String
D. int[]
E. Collection
F. StringBuilder
G. Yukarıdakinlerden hiçbiri
```

**Cevap :** G. Statement, var olmayan bir 'in' keyword'u kullandığı için geçerli bir for-each döngüsü (veya geleneksel
bir for döngüsü) değildir. Bu nedenle kod compile edilmez ve doğru cevap G seçeneğidir. Eğer 'in' bir iki nokta üst
üste (:) ile değiştirilseydi, Set, int[] ve Collection doğru olurdu.

25 - What is the output of the following code snippet?

25 - Aşağıdaki kod parçacığının çıktısı nedir?

```
6: String instrument = "violin";
7: final String CELLO = "cello";
8: String viola = "viola";
9: int p = -1;
10: switch(instrument) {
11:     case "bass" : break;
12:     case CELLO : p++;
13:     default: p++;
14:     case "VIOLIN": p++;
15:     case "viola" : ++p; break;
16: }
17: System.out.print(p);
```

```
A. -1
B. 0
C. 1
D. 2
E. 3
F. Code compile edilmez
```

**Cevap :** D. Kod sorunsuz bir şekilde compile edilir, bu nedenle F seçeneği yanlıştır. 8. satırda oluşturulan viola
değişkeni hiçbir zaman kullanılmaz ve göz ardı edilebilir. Eğer bu değişken 15. satırdaki case değeri olarak
kullanılsaydı, final olarak işaretlenmediği için bir compiler hatasına neden olurdu. "violin" ve "VIOLIN" tam olarak
eşleşmediğinden, switch statement'ının default branch'i runtime da yürütülür. default Branch'i yürütüldükten sonra
'case "VIOLIN"' ve 'case "viola"' da yürütülür, bu yürütme yolu, p değişkenini toplamda üç kez artırır ve p'nin son
değerini 2 yapar; bu nedenle doğru cevap D seçeneğidir.

26 - What is the output of the following code snippet? (Choose all that apply.)

26 - Aşağıdaki kod parçacığının çıktısı nedir? (Geçerli olan her şeyi seçin.)

```
9: int w = 0, r = 1;
10: String name = "";
11: while(w < 2) {
12:     name += "A";
13:     do {
14:         name += "B";
15:         if(name.length()>0) name += "C";
16:         else break;
17:     } while (r <=1);
18:     r++; w++; }
19: System.out.println(name);
```

```
A. ABC
B. ABCABC
C. ABCABCABC
D. 15. satır bir compiler hatası içeriyor.
E. 18. satır bir compiler hatası içeriyor.
F. Kod compile ediliyor ancak runtime'da asla sonlandırılmıyor.
G. Kod compile ediliyor ancak runtime'da bir NullPointerException fırlatıyor
```

**Cevap :** F. Kod parçacığında herhangi bir compiler hatası bulunmadığından, D ve E seçenekleri yanlıştır. Ancak, bu
kod parçacığıyla ilgili bir sorun vardır. Karmaşık görünebilir, ancak burada önemli olan, r değişkeninin do/while
döngüsü dışında update edilmesidir. Bu, compile açısından izin verilir çünkü döngüden önce tanımlanmıştır, ancak bu
durum en içteki döngünün r <= 1 bitiş koşulunu hiçbir zaman kırmaması anlamına gelir. Runtime'da, en içteki döngüye ilk
kez girildiğinde sonsuz bir döngü oluşur; bu nedenle doğru cevap F seçeneğidir.

27 - What is printed by the following code snippet?

27 - Aşağıdaki kod parçacığı ne yazdırır?

```
23: byte amphibian = 1;
24: String name = "Frog";
25: String color = switch(amphibian) {
26:     case 1 -> { yield "Red"; }
27:     case 2 -> { if(name.equals("Frog")) yield "Green"; }
28:     case 3 -> { yield "Purple"; }
29:     default -> throw new RuntimeException();
30: };
31: System.out.print(color);
```

```
A. Red
B. Green
C. Purple
D. RedPurple
E. Runtime'da exception fırlatılır
F. Code compile edilmez.
```

**Cevap :** F. 27. satır compile edilmez çünkü case bloğu, name "Frog" ile eşit olmadığında bir değer döndürmez. Bu
nedenle, doğru cevap F seçeneğidir. Bir case bloğundaki her yol, switch expression'ının bir değer döndürmesi
bekleniyorsa bir değer döndürmelidir.

28 - What is the output of calling getFish("goldie")?

28 - getFish(“goldie”) çağrısının çıktısı nedir?

```
40: void getFish(Object fish) {
41:     if (!(fish instanceof String guppy))
42:         System.out.print("Eat!");
43:     else if (!(fish instanceof String guppy)) {
44:         throw new RuntimeException();
45:     }
46:     System.out.print("Swim!");
47: }
```

```
A. Eat!
B. Swim!
C. Eat! ardından bir exception
D. Eat!Swim!
E. Exception print edilir
F. Yukarıdakinlerden hiçbiri
```

**Cevap :** F. Akış kapsamına (flow scoping) göre, guppy, 41–42. satırlardan sonra türü String değilse scope'da olur. Bu
durumda, 43. satırda, 41. satırda tanımlanan local variable'in bir kopyası olan bir guppy değişkeni tanımlanır. Bu
nedenle kod compile edilmez ve doğru cevap F seçeneğidir. Eğer 43. satırda farklı bir değişken adı kullanılsaydı, kod
compile edilir ve belirtilen girişle çalışma zamanında Swim! çıktısını verirdi.

29 - What is the result of the following code?

29 - Aşağıdaki kodun sonucu nedir?

```
1: public class PrintIntegers {
2: public static void main(String[] args) {
3:      int y = -2;
4:      do System.out.print(++y + " ");
5:      while(y <= 5);
6: } }
```

```
A. -2 -1 0 1 2 3 4 5
B. -2 -1 0 1 2 3 4
C. -1 0 1 2 3 4 5 6
D. -1 0 1 2 3 4 5
E. Satır 5 den dolayı code compile edilmez
F. Code infinite bir loop içeriyor ve sonlanmıyor.
```

**Cevap :** C. Pre-increment operatörü kullanıldığı için görüntülenecek ilk değer -1 olacaktır; dolayısıyla A ve B
seçenekleri yanlıştır. Döngünün sondan bir önceki yinelemesinde, y 5'e artırılacak ve döngü 5 değerini yazdıracaktır.
Döngü devam edecektir çünkü 5 <= 5 ifadesi true'dur ve son yinelemede 6 yazdırılacaktır. Bu son yinelemenin sonunda,
6 <= 5 boolean expression'ı false olarak değerlendirilecek ve döngü sonlanacaktır. Döngü tarafından yazdırılan son değer
6 olduğundan, doğru cevap C seçeneğidir.