# Assesment Test

Aşağıdaki değerlendirme testini kullanarak Java’daki 1Z0-829 sınavına yönelik mevcut beceri seviyenizi ölçün. Bu test,
güçlü ve zayıf yönlerinizi vurgulamak için tasarlanmıştır, böylece hangi bölümleri birden fazla okumanız gerektiğini
anlayabilirsiniz. Değerlendirme testinde başarılı olsanız bile, gerçek sınavların oldukça zor olduğunu göz önünde
bulundurarak kitabı baştan sona okumanız önerilir.

1 - Aşağıdaki kod parçacığı çalıştırıldığında sonucu nedir?

```
41: final int score1 = 8, score2 = 3;
42: char myScore = 7;
43: var goal = switch (myScore) {
44:     default -> {if(10>score1) yield "unknown";}
45:     case score1 -> "great";
46:     case 2, 4, 6 -> "good";
47:     case score2, 0 -> {"bad";}
48:     };
49: System.out.println(goal);
```

* A. unknown
* B. great
* C. good
* D. bad
* E. unknowngreatgoodbad
* F. Kodun derlenmesi için tam olarak bir satırın değiştirilmesi gerekir.
* G. Kodun derlenmesi için tam olarak iki satırın değiştirilmesi gerekir.
* H. Yukarıdakilerin hiçbiri

**Cevap :** G. Soru derlenmiyor çünkü 44. ve 47. satırlar, her case'de bir değer döndürmüyor ve bu, bir switch
expression assign işleminde kullanıldığında gereklidir. 44. satırda, if ifadesi false olarak değerlendirildiğinde bir
yield statement'i eksik, 47. satırda ise tamamen bir yield statement'i eksik. İki satır da derlenmediği için doğru cevap
G seçeneğidir.

Tüm expression'lar gibi, switch expression'ları da tek bir değere göre değerlendirilir ve expression'lar da
kullanılabilir. Bu expression'lar, geçişi önlemek için break deyimlerine gerek bırakmayan "case L ->" etiketleri
içerebilir. Switch expression'ının değerini belirtmek için yield statement'i kullanabilirsiniz.

```
public enum Day {
    MONDAY,
    TUESDAY,
    WEDNESDAY,
    THURSDAY,
    FRIDAY,
    SATURDAY,
    SUNDAY
}
```

Günün adının uzunluğunu bir değişkende saklamak yerine "return" edilseydi daha iyi olurdu; bunu bir switch
expression'ı ile yapabilirsiniz. Ayrıca, hatayı önlemek için break expression'larına ihtiyacınız olmasaydı daha iyi
olurdu; yazmaları zahmetli ve unutmaları kolaydır. Bunu yeni bir tür büyük/küçük harf etiketi ile yapabilirsiniz.
Aşağıda, haftanın bir gününün harf sayısını yazdırmak için yeni tür büyük/küçük harf etiketini kullanan bir switch
expression'ı yer almaktadır:

```
public static void main(String[] args) {
    Day day = Day.WEDNESDAY;
    System.out.println(
            switch (day) {
                case MONDAY,FRIDAY,SUNDAY -> 6;
                case TUESDAY -> 7;
                case THURSDAY, SATURDAY -> 8;
                case WEDNESDAY -> 9;
                default -> throw new IllegalStateException("Invalid day : " +day);
            }
    );
}
```

Yeni tür "case" etiketi aşağıdaki biçime sahiptir:

```case label_1, label_2, ..., label_n -> expression;|throw-statement;|block```

Java runtime'ı okun solundaki etiketlerden herhangi biriyle eşleştiğinde, okun sağındaki kodu çalıştırır ve düşmez;
switch expression'ı (veya statement'inda ki) diğer kodları çalıştırmaz. Okun sağındaki kod bir expression ise, bu
expression'ın değeri switch expression'ın değeridir.

**Yield kullanımı : **

```
public static void main(String[] args) {
    Day day = Day.WEDNESDAY;
    int numLetters = switch (day) {
        case MONDAY, FRIDAY, SUNDAY -> {
            System.out.println(6);
            yield 6;
        }
        case TUESDAY -> {
            System.out.println(7);
            yield 7;
        }
        case THURSDAY, SATURDAY -> {
            System.out.println(8);
            yield 8;
        }
        case WEDNESDAY -> {
            System.out.println(9);
            yield 9;
        }
        default -> {
            throw new IllegalStateException("Invalid day : " + day);
        }
    };
}
```

2 - Aşağıdaki kod parçacığının çıktısı nedir?

```
int moon = 9, star = 2 + 2 * 3;
float sun = star > 10 ? 1 : 3;
double jupiter = (sun + moon) - 1.0f;
int mars = --moon <= 8 ? 2 : 3;
System.out.println(sun+", "+jupiter+", "+mars);
```

* A. 1, 11, 2
* B. 3.0, 11.0, 2
* C. 1.0, 11.0, 3
* D. 3.0, 13.0, 3
* E. 3.0f, 12, 2
* F. Kod derlenmiyor çünkü assignment'lardan biri açık bir numeric cast gerektiriyor

**Cevap :** B. Başlangıçta, moon değişkenine 9, star değişkenine ise 8 değeri atanır. Çarpma operatörü (*) toplama
operatöründen (+) daha yüksek önceliğe sahip olduğu için önce değerlendirilir. star 10’dan büyük olmadığı için, sun
değişkenine 3 değeri atanır ve bu değer atama işlemi sırasında 3.0f olarak promoted ettirilir. jupiter değişkeninin
değeri (3.0f + 9) - 1.0 ifadesinden hesaplanır ve bu sonuç 11.0f olur. Bu değer, atama sırasında otomatik olarak double
türüne promoted ettirilir. Son atamada, moon değişkeni 9’dan 8’e düşürülür ve ifadenin sonucu olarak 8 döndürülür. 8'in
8’e eşit veya küçük olması doğru olduğu için, mars değişkenine 2 değeri atanır. Nihai çıktı 3.0, 11.0, 2 olup, doğru
cevap B seçeneğidir. Java, hem float hem de double türündeki değerlerin ondalık kısmını yazdırırken, float türü için f
harfini göstermez.

3 - Hangi değişiklikler bağımsız olarak yapıldığında aşağıdaki kod parçacığının runtime'da 100 yazdırmasını
garanti edilir? (Geçerli olan tümünü seçin.)

```
List<Integer> data = new ArrayList<>();
IntStream.range(0,100).parallel().forEach(s -> data.add(s));
System.out.println(data.size());
```

* A. Data'yı bir instance variable ile degistirin ve volatile olarak markla
* B. Stream operation'larından parallel() kaldırın
* C. forEach()'i forEachOrdered() ile degiştirin
* D. parallel()'i serial()'i ile değiştirin
* E. Lambda'nın body'sini synchonized block'u ile wrap edin
* F. Kod parçacığı olduğu gibi her zaman 100 yazdıracaktır.

B, C, E. Kod, herhangi bir değişiklik yapılmadan 100 değerini yazdırabilir, ancak data thread-safe olmadığından, bu
behavior garanti edilmez. Bu nedenle, F seçeneği yanlıştır. A seçeneği de yanlıştır, çünkü volatile
anahtar kelimesi thread safe'i garanti etmez. B ve C seçenekleri doğrudur, çünkü her ikisi de akışın (stream)
add() işlemini senkronize bir şekilde uygulamasını sağlar. D seçeneği yanlıştır, çünkü serial() bir stream methodu
değildir. E seçeneği doğrudur. Senkronizasyon, her thread'in beklemesine neden olur, böylece List her seferinde
tek bir öğe ile değiştirilir.

4 - Bu kodun çıktısı nedir?

```
20: Predicate<String> empty = String::isEmpty;
21: Predicate<String> notEmpty = empty.negate();
22:
23: var result = Stream.generate(() -> "")
24:     .filter(notEmpty)
25:     .collect(Collectors.groupingBy(k -> k))
26:     .entrySet()
27:     .stream()
28:     .map(Entry::getValue)
29:     .flatMap(Collection::stream)
30:     .collect(Collectors.partitioningBy(notEmpty));
31: System.out.println(result);
```

* A. It outputs {}
* B. It outputs {false=[], true=[]}
* C. Kod compile edilmez
* D. Code terminate olmaz

D. Öncelikle, bu karmaşık kod derlenir. Ancak, source sonsuz bir stream'dir. filter işlemi, her öğeyi sırayla kontrol
ederek boş olmayan bir öğe olup olmadığını kontrol eder. Filtreyi geçen hiçbir öğe olmadığında, kod sona ermez. Bu
nedenle, D seçeneği doğrudur. Daha fazla bilgi için 10. Bölüme bakın.

5 - Aşağıdaki programın sonucu nedir?

```
1: public class MathFunctions {
2:      public static void addToInt(int x, int amountToAdd) {
3:          x = x + amountToAdd;
4:      }
5:      public static void main(String[] args) {
6:          var a = 15;
7:          var b = 10;
8:          MathFunctions.addToInt(a, b);
9:          System.out.println(a); 
10:     } 
11: }
```

* A. 10
* B. 15
* C. 25
* D. Satır 3'te compiler hatası
* E. Satır 8'de compiler hatası
* F. Yukarıdakilerin hiçbiri

**Cevap : ** B. Kod başarıyla compile edilir, bu yüzden D ve E seçenekleri yanlıştır. addToInt() methodu, ne yaparsa
yapsın, değişkene yalnızca bir kopyası parametre olarak aktarıldığı için a'nın değerini değiştiremez. Bu nedenle, a
değişmez ve 9. satırdaki çıktı 15 olur, bu da B seçeneğidir

6 - Aşağıdaki properties dosyalarına ve koda sahip olduğumuzu varsayalım. Sırasıyla 8. ve 9. satırlarda hangi değerler
yazdırılır?

```
Penguin.properties
name=Billy
age=1

Penguin_de.properties
name=Chilly
age=4

Penguin_en.properties
name=Willy

5: Locale fr = new Locale("fr");
6: Locale.setDefault(new Locale("en", "US"));
7: var b = ResourceBundle.getBundle("Penguin", fr);
8: System.out.println(b.getString("name"));
9: System.out.println(b.getString("age"));
```

* A. Billy and 1
* B. Billy and null
* C. Willy and 1
* D. Willy and null
* E. Chilly and null
* F. Code compile edilmez

**Cevap :** C. Java, 7. satırda eşleşen kaynak paketi olarak Penguin_en.properties dosyasını kullanacaktır. Fransızca
için bir eşleşme olmadığından, varsayılan yerel ayar kullanılır. 8. satırda Penguin_en.properties dosyasında eşleşen bir
anahtar bulunur. 9. satırda ise Penguin_en.properties dosyasında bir eşleşme bulunamadığından, hiyerarşide daha
yukarıya, Penguin.properties dosyasına bakılması gerekir. Bu nedenle doğru cevap C seçeneğidir.

7 - Aşağıdaki kodla neyin basılacağı garanti edilir? (Geçerli olanların tümünü seçin)

```
int[] array = {6,9,8};
System.out.println("B" + Arrays.binarySearch(array,9));
System.out.println("C" + Arrays.compare(array,new int[] {6, 9, 8}));
System.out.println("M" + Arrays.mismatch(array,new int[] {6, 9, 8}));
```

* A. B1
* B. B2
* C. C-1
* D. C0
* E. M-1
* F. M0
* G. Code compile edilmez

**Cevap :** D, E. Array, declaration ile aynı satırda olduğundan anonymous initializer kullanmasına izin verilir. Array
sorted olmadığı için binary search sonuçları tanımlı değildir. Soru garanti edilen çıktıyı sorduğundan, A ve B
seçenekleri yanlıştır. D seçeneği doğrudur çünkü compare() methodu, array'ler aynı uzunlukta ve aynı öğelere sahip
olduğunda 0 döndürür. E seçeneği de doğrudur çünkü mismatch() methodu array'ler eşdeğer olduğunda -1 döndürür.

8 - Aşağıdaki kodu tamamlayan functional interface'ler nelerdir, r değişkeninin mevcut olduğu varsayılırsa? (Tüm doğru
seçenekleri seçin.)

```
6: ________ x = r.negate();
7: ________ y = () -> System.out.println();
8: ________ z = (a, b) -> a - b;
```

```
* A. BinaryPredicate<Integer, Integer>
* B. Comparable<Integer>
* C. Comparator<Integer>
* D. Consumer<Integer>
* E. Predicate<Integer>
* F. Runnable
* G. Runnable<Integer>
```

**Cevap :** C, E, F. İlk olarak, A seçeneği yanlıştır çünkü interface'in BiPredicate olması gerekir, BinaryPredicate
değil. 6. satır, negate() methodunun Predicate üzerinde bir kolaylık methodu olduğunu bilmenizi gerektirir; bu nedenle,
E seçeneği doğrudur. 7. satır, parametre almaz ve herhangi bir değer döndürmez, bu da onu bir Runnable yapar.
Runnable'ın generic kullanmadığını unutmayın, bu da F seçeneğini doğru yapar. Son olarak, 8. satır iki parametre alır ve
bir int döndürür; C seçeneği doğrudur. Comparable ise sizi yanıltmak için verilmiştir çünkü tek abstract methodunda
yalnızca bir parametre alır.

9 - Diyelim ki com.vet adında bir module'unuz var. Geçerli bir module oluşturmak için aşağıdaki module-info.java
dosyasını nereye yerleştirebilirsiniz?

```
public module com.vet {
    exports com.vet;
}
```

* A. com klasörü ile aynı seviyede
* B. vet klasörü ile aynı seviyede
* C. vet folder'inin icinde
* D. Yukarıdakinlerden hiçbiri

**Cevap :** D. Bu, geçerli bir module-info.java dosyası olsaydı, module'un root dizinine yerleştirilmesi gerekirdi; bu
da A seçeneğidir. Ancak, bir module public erişim belirleyicisini kullanamaz. Dosyanın projedeki konumundan bağımsız
olarak derlenememesi nedeniyle D seçeneği doğrudur.

10 - Aşağıdaki programın çıktısı nedir? (Geçerli olan her şeyi seçin.)

```
1: interface HasTail { private int getTailLength(); }
2: abstract class Puma implements HasTail {
3:      String getTailLength() { return "4"; }
4: }
6: 5: public class Cougar implements HasTail {
        public static void main(String[] args) {
7:          var puma = new Puma() {};7: 
8:          System.out.println(puma.getTailLength());
9:      }
10:     public int getTailLength(int length) { return 2; }
11: }
```

* A. 2
* B. 4
* C. line1'den dolayı kod derlenmez
* D. line3'den dolayı kod derlenmez
* E. line5'den dolayı kod derlenmez
* F. line7'den dolayı kod derlenmez
* G. line10'den dolayı kod derlenmez
* H. Sağlanan koddan çıkış belirlenemez.

**Cevap :** C. Interface'de ki getTailLength() methodu private olduğundan, bir gövde içermesi gerekir. Bu nedenle,
derlenmeyen tek satır 1. satırdır ve doğru cevap C seçeneğidir. 3. satır, method için farklı bir dönüş türü kullanır,
ancak interface'de private olduğu için bir override olarak kabul edilmez. 7. satırda, abstract Puma parent class'ını
kullanarak bir anonymous sınıf tanımlandığını unutmayın.

11 - Tadpole.java dosyasında compiler hatasına neden olan satırlar hangileridir? (Tüm doğru seçenekleri seçin.)

```
// Frog.java
1: package animal;
2: public class Frog {
3:      protected void ribbit() { }
4:      void jump() { }
5: }

// Tadpole.java
1: package other;
2: import animal.*;
3: public class Tadpole extends Frog {
4:       public static void main(String[] args) {
5:          Tadpole t = new Tadpole();
6:          t.ribbit();
7:          t.jump();
8:          Frog f = new Tadpole();
9:          f.ribbit();
10:         f.jump();
11: } }
```

* A. Line 5
* B. Line 6
* C. Line 7
* D. Line 8
* E. Line 9
* F. Line 10
* G. Bütün satırlar compile edilir

**Cevap :** C, E, F. jump() methodu paket erişimine sahiptir, yani yalnızca aynı paketten erişilebilir. Tadpole, Frog
ile aynı pakette olmadığı için 7. ve 10. satırlar derleyici hatalarına neden olur; bu da C ve F seçeneklerini doğru
yapar. ribbit() methodu ise korumalı (protected) erişime sahiptir; bu, yalnızca bir subclass referansından veya aynı
paketten erişilebileceği anlamına gelir. 6. satırda sorun yoktur çünkü Tadpole bir subclass. 9. satır ise derlenmez
ve nihai cevabımız E seçeneğidir, çünkü değişken referansı Frog türündedir ve protected methoda erişim sağlamaz.

12 - Bu kodu derlemek için boşlukları aşağıdakilerden hangisi doldurabilir?

```
_________ a = _________.getConnection(
    url, userName, password
);
_________ b = a.prepareStatement(sql);
_________ c = b.executeQuery();
if (c.next()) System.out.println(c.getString(1));
```

* A. Connection, Driver, PreparedStatement, ResultSet
* B. Connection, DriverManager, PreparedStatement, ResultSet
* C. Connection, DataSource, PreparedStatement, ResultSet
* D. Driver, Connection, PreparedStatement, ResultSet
* E. DriverManager, Connection, PreparedStatement, ResultSet
* F. DataSource, Connection, PreparedStatement, ResultSet

**Cevap :** B. DataSource sınavda yer almadığı için onu içeren herhangi bir soru yanlıştır. Bir sorgu çalıştırmada
kullanılan ana değişkenler Connection, PreparedStatement ve ResultSet'tir. Bir Connection, DriverManager aracılığıyla
elde edilir; bu nedenle B seçeneği doğrudur.

13 - Aşağıdaki statement'lardan hangileri boşluğu doldurarak kodun başarıyla derlenmesini sağlar? (Tüm doğru seçenekleri
seçin.)

```Set<? extends RuntimeException> mySet = new __________();```

* A. HashSet<? extends RuntimeException>
* B. HashSet<Exception>
* C. TreeSet<RuntimeException>
* D. TreeSet<NullPointerException>
* E. Yukarıdakinlerden hiçbiri

**Cevap :** C, D. mySet bildirimi, RuntimeException türünde bir üst sınır tanımlar. Bu, sınıfların tür parametresi
olarak RuntimeException veya RuntimeException'ın herhangi bir subclass'ını belirleyebileceği anlamına gelir. B seçeneği
yanlıştır çünkü Exception, RuntimeException'ın bir subclass'ı değil, superclass'ıdır. A seçeneği de yanlıştır çünkü
joker karakter (wildcard) assignment'in sağ tarafında bulunamaz. C ve D seçenekleri compile edilir ve doğru cevaplardır.

14 - birds.dat dosyasının var olduğu, erişilebilir olduğu ve bir Bird nesnesi için veriler içerdiği varsayıldığında,
aşağıdaki kodun yürütülmesinin sonucu nedir? (Tüm doğru seçenekleri seçin.)

```
1: import java.io.*;
2: public class Bird {
3:      private String name;
4:      private transient Integer age;
5:
6:      // GETTERS / SETTERS omitted
7:
8:      public static void main(String[] args) {
9:          try(var is = new ObjectInputStream(
10:             new BufferedInputStream(
11:             new FileInputStream("birds.dat")))) {
12:             Bird b = is.readObject();
13:             System.out.println(b.age);
14: } } }
```

* A. Compile edilir ve runtime'da 0 yazdırır.
* B. Compile edilir ve runtime'da null yazdırır.
* C. Compile edilir ve runtime'da sayılar yazdırır.
* D. 9 ve 11. satırlardan dolayı kod derlenmez
* E. 12. satırlardan dolayı kod derlenmez
* F. Compile edilir ancak runtime'da exception fırlatır

**Cevap :** D, E. Satır 10, unhandled bir checked IOException içerirken, satır 11 unhandled bir checked
FileNotFoundException içerir; bu durum, D seçeneğinin doğru olduğunu gösterir. Satır 12 derlenemez çünkü is.readObject()
işlemi, b'ye atanabilmesi için Bird nesnesine dönüştürülmelidir. Ayrıca, satır 12'de unhandled iki checked exception (
IOException ve ClassNotFoundException) bulunduğu için seçenek E de doğrudur. Satır 12'de bir tür dönüştürme işlemi
eklenip, ana main() metodunda satır 8'de çeşitli checked exception’lar belirtilecek şekilde güncellenirse, kod derlenir
ancak runtime'da bir exception fırlatır; çünkü Bird sınıfı Serializable interface'ini implement etmemektedir. Son
olarak, eğer sınıf Serializable'ı implement etseydi, program runtime'da null yazdırırdı; çünkü transient alan olan
age'in varsayılan değeri budur (null)

15 - Aşağıdakilerden hangisi bir sınıfın geçerli instance member'larıdır (Geçerli olan tümünü seçin.)

```
A. var var = 3;
B. Var case = new Var();
C. void var() {}
D. int Var() { var _ = 7; return _;}
E. String new = "var";
F. var var() { return null; }
```

**Cevap :** C. Seçenek A yanlıştır, çünkü var yalnızca local variables'lar için tür olarak kullanılabilir, instance
member'lar için kullanılamaz. Seçenek B ve E yanlıştır, çünkü new ve case reserved sözcüklerdir ve identifiers
olarak kullanılamazlar. Seçenek C doğrudur, çünkü var bir metot adı olarak kullanılabilir. Seçenek D yanlıştır, çünkü
tek bir alt çizgi (_) identifier olarak kullanılamaz. Son olarak, seçenek F yanlıştır, çünkü bir methodun dönüş türü
olarak var belirtilemez.

16 - Bu kod çalıştırılmadan önce tablo boşsa hangisi doğrudur? (Geçerli olan tümünü seçin.)

```
var sql = "INSERT INTO people VALUES(?, ?, ?)";
conn.setAutoCommit(false);
try (var ps = conn.prepareStatement(sql,
    ResultSet.TYPE_SCROLL_SENSITIVE,
    ResultSet.CONCUR_UPDATABLE)) {
    
    ps.setInt(1, 1);
    ps.setString(2, "Joslyn");
    ps.setString(3, "NY");
    ps.executeUpdate();

    Savepoint sp = conn.setSavepoint();
    ps.setInt(1, 2);
    ps.setString(2, "Kara");
    ps.executeUpdate();
    conn._____________ ;
}
```

* A - Boş satır rollback() içeriyorsa, tabloda satır yoktur.
* B - Boş satır rollback() içeriyorsa, tabloda bir satır vardır.
* C - Boş satır rollback(sp) içeriyorsa, tabloda satır yoktur.
* D - Boş satır rollback(sp) içeriyorsa, tabloda bir satır vardır.
* E - Code compile edilmez
* F - Second update tüm parametreleri set etmediği için kod bir exception fırlatır.

**Cevap :** A, D. Bu kod doğrudur, bu da seçenek E ve F’yi elemektedir. JDBC, eğer değiştirmezseniz mevcut parametre
kümesini kullanır. Bu, Kara’nın satırının üçüncü parametre olarak NY kullanacak şekilde ayarlanacağı anlamına gelir. Bir
Savepoint'e geri döndüğünüzde, o noktadan bu yana yapılan değişiklikler silinir. Bu durumda Kara elenir ve Joslyn
kalır, bu da seçeneğin D doğru olduğunu gösterir. Savepoint olmadan geri döndürme işlemi, bizi işlemin başına
geri götürür; bu, seçenek A’dır. Daha fazla bilgi için 15. Bölüm’e bakınız.

17 - path1'in içeriği "Howdy" metniyle başlıyorsa, aşağıdakilerden hangileri doğrudur? (İkisini seçin.)

```System.out.println(Files.mismatch(path1,path2));```

* A - Eğer path2 mevcut değilse, kod -1 yazdırır
* B - Eğer path2 mevcut değilse, kod 0 yazdırır
* C - Eğer path2 mevcut değilse, kod bir exception fırlatır.
* D - Eğer path2'nin içeriği Hello ile başlıyorsa, kod -1 yazdırır.
* E - Eğer path2'nin içeriği Hello ile başlıyorsa, kod 0 yazdırır.
* F - path2'nin içeriği Hello ile başlıyorsa, kod 1 yazdırır.

**Cevap :** C, F. Seçenek C doğrudur, çünkü mismatch() methodunda dosyalar mevcut değilse, her iki dosya da aynı dosyaya
atıfta bulunmadıkça bir exception fırlatılır. Ayrıca, seçenek F de doğrudur, çünkü farklı olan ilk index döndürülür; bu,
ikinci karakterdir. Java sıfır tabanlı indeks kullandığından, bu indeks 1’dir.

18 - Programın başarıyla compile edilmesini sağlamak için boşluğa aşağıdaki türlerden hangileri yerleştirilebilir? (
Hepsini seçin.)

```
1: import java.util.*;
2: final class Amphibian {}
3: abstract class Tadpole extends Amphibian {}
4: public class FindAllTadpoles {
5:      public static void main(String... args) {
6:      var tadpoles = new ArrayList<Tadpole>();
7:      for (var amphibian : tadpoles) {
8:          _________ tadpole = amphibian;
9: } } }
```

* A. List<Tadpole>
* B. Boolean
* C. Amphibian
* D. Tadpole
* E. Object
* F. Yukarıdakinlerden hiçbiri

Amphibian sınıfı final olarak işaretlenmiştir; bu da satır 3'ün bir compiler hatası oluşturduğu ve F seçeneğinin doğru
olduğu anlamına gelir.

19 - Aşağıdaki programın compile edilmesi ve çalıştırılmasının sonucu nedir?

```
1: public class FeedingSchedule {
2:      public static void main(String[] args) {
3:      var x = 5;
4:      var j = 0;
5:      OUTER: for (var i = 0; i < 3;)
6:          INNER: do {
7:              i++;
8:              x++;
9:              if (x> 10) break INNER;
10:             x += 4;
11:             j++;
12:         } while (j <= 2);
13:     System.out.println(x);
14: } }
```

* A. 10
* B. 11
* C. 12
* D. 17
* E. Satır 5'den dolayı code compile edilemez
* F. Satır 6'dan dolayı code compile edilemez

**Cevap :** C. Kod, herhangi bir sorun olmadan derlenir ve çalışır; dolayısıyla seçenekler E ve F yanlıştır. Bu tür bir
problem en iyi şekilde bir döngü yinelemesi (iteration) kademesinde incelenir:

* OUTER döngünün ilk iteration'ın da i 0'dır, bu nedenle döngü devam eder.

* INNER'ın ilk iteration'ının da, i 1'e, x ise 6'ya güncellenir. if statement çalıştırılmaz ve x 10’a, j ise 1’e
  yükseltilir.

* INNER'ın ikinci iteration'ın da (çünkü j = 1 ve 1 <= 2), i 2'ye ve x 11'e güncellenir. Bu noktada, if dalı programın
  geri kalanı boyunca true olarak değerlendirilecektir; bu da her ulaşıldığında INNER'dan çıkılmasına neden olur.

* OUTER'ın ikinci iteration'ın da (çünkü i = 2), i 3'e ve x 12'ye güncellenir. Daha önce olduğu gibi, x hâlâ 10'dan
  büyük olduğu için INNER kırılır.

* OUTER üçüncü iteration'ın da, OUTER kırılır, çünkü i zaten 3'ten küçük değildir. x'in en son değeri, 12, yazdırılır;
  dolayısıyla cevap seçenek C'dir.

20 - Yazdırıldığında, hangi String bu metin bloğu ile aynı değeri verir?

```
var pooh = """
  "Oh, bother." -Pooh
  """.indent(1);
System.out.print(pooh);
```

```
A. "\n\"Oh, bother.\" -Pooh\n"
B. "\n \"Oh, bother.\" -Pooh\n"
C. " \"Oh, bother.\" -Pooh\n"
D. "\n\"Oh, bother.\" -Pooh"
E. "\n \"Oh, bother.\" -Pooh"
F. " \"Oh, bother.\" -Pooh"
G. Yukarıdakinlerden hiçbiri
```

**Cevap :** C. Öncelikle, metin bloğunun kapanış """ ifadesinin ayrı bir satırda olduğunu not edin; bu, sonunda bir yeni
satır olduğu anlamına gelir ve bu durum seçenek D, E ve F'yi hariç tutar. Ayrıca, metin blokları yeni bir satırla
başlamaz; bu da seçenek A ve B'yi hariç tutar. Dolayısıyla, seçenek C doğrudur.

21 - A(n) ___________ module always contains a module-info.java file, while a(n) ___________ module always exports all
its packages to other modules.

* A. automatic, named
* B. automatic, unnamed
* C. named, automatic
* D. named, unnamed
* E. unnamed, automatic
* F. unnamed, named
* G. Yukarıdakinlerden hiçbiri

**Cevap :** C. Sadece adlandırılmış modüllerin bir module-info.java dosyasına sahip olması gerekmektedir; bu da seçenek
A, B, E ve F'yi hariç tutar. Adlandırılmamış modüller, diğer modül türleri tarafından okunamaz; bu da seçenek D'yi hariç
tutar. Otomatik modüller her zaman tüm paketleri diğer modüllere ihraç eder, bu nedenle cevap seçenek C’dir.

22 - Aşağıdaki kodun sonucu nedir?

```
22: var treeMap = new TreeMap<Character, Integer>();
23: treeMap.put('k', 1);
24: treeMap.put('k', 2);
25: treeMap.put('m', 3);
26: treeMap.put('M', 4);
27: treeMap.replaceAll((k, v) -> v + v);
28: treeMap.keySet()
29: .forEach(k -> System.out.print(treeMap.get(k)));
```

A. 268
B. 468
C. 2468
D. 826
E. 846
F. 8246
G. Yukarıdakinlerden hiçbiri

**Cevap :** E. Aynı key bir Map içine konulduğunda, orijinal değeri override eder. Bu, satır 23'ün atlanabileceği
ve kodun aynı olacağı anlamına gelir; map'de yalnızca üç key/value çifti vardır. TreeMap, key'lerini sıralar ve
bu da sıralamanın M, ardından k ve ardından m şeklinde olmasını sağlar. Doğal sıralama düzeninin büyük harflerin küçük
harflerden önce geldiğini unutmayın. replaceAll() methodu map'de ki her bir öğeye uygulanır ve değeri iki katına
çıkarır. Son olarak, her bir key'i döngü ile geçerek 846 yazdırır ve bu nedenle seçenek E doğrudur.

23 - Aşağıdaki satırlardan hangisi "true" yazdırmak için boşluğu doldurabilir? (Geçerli olan tümünü seçin.)

```
10: public static void main(String[] args) {
11:     System.out.println(test(_______________));
12: }
13: private static boolean test(Function<Integer, Boolean> b) {
14:   return b.apply(5);
15: }
```

```
A. i::equals(5)
B. i -> {i == 5;}
C. (i) -> i == 5
D. (int i) -> i == 5
E. (int i) -> {return i == 5;}
F. (i) -> {return i == 5;}
```

**Cevap :** C, F. Seçenek A bir method referansı gibi görünüyor. Ancak, geçerli bir methodu çağırmıyor ve method
referansları parametre almaz. Predicate interface'i tek bir parametre alır ve bir boolean döner. Tek parametreye sahip
lambda ifadeleri, parametre listesinin etrafındaki parantezleri atlayabilir; bu da seçeneğin C doğru olduğunu gösterir.
Tek bir statement gövdesinde olduğunda return ifadesi isteğe bağlıdır; bu da seçeneğin F doğru olduğunu gösterir.
Seçenek B yanlıştır, çünkü gövde etrafında süslü parantezler varsa bir return ifadesi kullanılmalıdır. Seçenek D ve E
yanlıştır, çünkü Predicate tür Integer, lambda'da ise int'tir. Otomatik kutulama (autoboxing) collection'lar için
çalışır, Predicate'leri çıkarım yaparken çalışmaz. Eğer bu iki tür Integer olarak değiştirilirse, doğru olurlar.

24 - "True" kelimesi kaç kez basılmıştır?

```
var s1 = "Java";
var s2 = "Java";
var s3 = s1.indent(1).strip();
var s4 = s3.intern();
var sb1 = new StringBuilder();
sb1.append("Ja").append("va");

System.out.println(s1 == s2);
System.out.println(s1.equals(s2));
System.out.println(s1 == s3);
System.out.println(s1 == s4);
System.out.println(sb1.toString() == s1);
System.out.println(sb1.toString().equals(s1));
```

* A. Once
* B. Twice
* C. Three times
* D. Four times
* E. Five times
* F. Code compile edilmez

**Cevap :** D. String literal'ları string havuzundan (string pool) kullanılır. Bu, s1 ve s2'nin aynı nesneye işaret
ettiği ve eşit olduğu anlamına gelir. Bu nedenle, ilk iki yazdırma ifadesi true yazdırır. indent() ve strip() methodları
yeni String nesneleri oluşturduğundan üçüncü ifade false yazdırır; ancak intern() methodu String'i string havuzundaki
nesneye geri döndürür. Bu nedenle, dördüncü yazdırma ifadesi true yazdırır. Beşinci yazdırma ifadesi false yazdırır,
çünkü toString() bir değeri hesaplamak için bir method kullanır ve bu string havuzundan değildir. Son yazdırma ifadesi
tekrar true yazdırır, çünkü equals() String nesnelerinin değerlerine bakar. Dördü true olduğu için, cevap D seçeneğidir.

25 - Aşağıdaki programın çıktısı nedir?

```
1: class Deer {
2:    public Deer() {System.out.print("Deer");}
3:    public Deer(int age) {System.out.print("DeerAge");}
4:    protected boolean hasHorns() { return false; }
5: }
6: public class Reindeer extends Deer {
7:    public Reindeer(int age) {System.out.print("Reindeer");}
8:    public boolean hasHorns() { return true; }
9:    public static void main(String[] args) {
10:     Deer deer = new Reindeer(5);
11:     System.out.println("," + deer.hasHorns());
12: } }
```

* A. ReindeerDeer,false
* B. DeerAgeReindeer,true
* C. DeerReindeer,true
* D. DeerReindeer,false
* E. ReindeerDeer,true
* F. DeerAgeReindeer,false
* G. Code 4. satırdan dolayı compile edilmez
* H. Code 12. satırdan dolayı compile edilmez

**Cevap :** Reindeer nesnesi, bir int değeri alan constructor kullanılarak oluşturulur. Parent class constructor'ına
açık bir çağrı olmadığı için, derleyici, satır 7'deki constructor'ın ilk satırı olarak super() ifadesini ekler. Parent
class constructor'ı çağrılır ve satır 2'de Deer yazdırılır. Akış, satır 7'deki constructor'a geri döner ve Reindeer
yazdırılır. Ardından, hasHorns() methodu çağrılır. Referans tipi Deer ve alttaki nesne tipi Reindeerdir. Reindeer
hasHorns() methodunu doğru bir şekilde override ettiğinden, Reindeer içindeki sürüm çağrılır ve satır 11 true yazdırır.
Bu nedenle, seçenek C doğrudur.

26 - Aşağıdakilerden hangisi "true"? (Geçerli olan tümünü seçin.)

```
private static void magic(Stream<Integer> s) {
  Optional o = s
    .filter(x -> x < 5)
    .limit(3)
    .max((x, y) -> x-y);
  System.out.println(o.get());
}
```

* A. magic(Stream.empty()); sonsuza kadar calışır
* B. magic(Stream.empty()); exception fırlatır
* C. magic(Stream.iterate(1, x -> x++)); sonsuza kadar çalışır
* D. magic(Stream.iterate(1, x -> x++)); exception fırlatır
* E. magic(Stream.of(5, 10)); sonsuza kadar çalışır
* F. magic(Stream.of(5, 10)); exception fırlatır
* G. Method compile edilmez

**Cevap :** B, F. Boş bir Optional üzerinde get() çağrısı yapmak bir exception fırlatır, bu da seçeneğin B doğru
olduğunu gösterir. Seçenek F de doğrudur, çünkü filter() methodu, get() çağrısından önce Optional'ı empty hale getirir.
Seçenek C yanlıştır, çünkü infinite stream limit() ara operation'ı ile sonlu hale getirilmiştir. Seçenek A ve E
yanlıştır, çünkü source stream'ler infinite değildir. Bu nedenle, max() çağrısı yalnızca üç öğeyi görür ve sona erer.

27 - Aşağıdaki bildirimlerin aynı dosyada bildirilen top-level tipler olduğunu varsayarsak, hangisi başarıyla
derlenir? (Geçerli olan tümünü seçin.)

```
record Music() {
    final int score = 10;
}

record Song(String lyrics) {
    Song {
      this.lyrics = lyrics + "Hello World";
    }
}

sealed class Dance {}

record March() {
    @Override String toString() { return null; }
}

class Ballet extends Dance {}
```

* A. Music
* B. Song
* C. Dance
* D. March
* E. Ballet
* F. Compile edilemez

**Cevap :** C. Music compile edilemez çünkü record'lar, record bildiriminin dışında belirtilmeyen instance variable'ları
içeremez; bu durum, değişmezliği (immutability) bozabilir. Song compile edilmez çünkü kompakt yapıcı (compact
constructor) bir instance variable'ini set edemez. Eğer bu compact constructor'dan çıkarılırsa, record derlenecektir;
çünkü compact constructor'lar input parametrelerini değiştirebilir. March compile edilemez çünkü geçersiz bir override'a
sahiptir; toString() methodunun görünürlüğünü public'den paket erişimine (package access) düşürmektedir. Ballet compile
edilmez çünkü bir sealed sınıfın subclass'ı final, sealed veya non-sealed olarak işaretlenmelidir. Derlenen tek sınıf
Dance olduğu için, cevap C seçeneğidir.

28 - Aşağıdaki expression'lar dan hangisi hatasız derlenir? (Geçerli olanların tümünü seçin.)

* A. int monday = 3 + 2.0;
* B. double tuesday = 5_6L;
* C. boolean wednesday = 1 > 2 ? !true;
* D. short thursday = (short)Integer.MAX_VALUE;
* E. long friday = 8.0L;
* F. var saturday = 2_.0;
* G. Yukarıdakinlerden hiçbiri

**Cevap :** B, D. Seçenek A derlenmez, çünkü ifade 3 + 2.0 bir double olarak değerlendirilir ve bir double'ın bir int'e
atanabilmesi için açık bir dönüşüm gereklidir. Seçenek B, bir long değerinin bir double'a açıkça dönüştürülebileceği
için sorunsuz bir şekilde derlenir. Seçenek C derlenmez çünkü üçlü operatör (? :) bir : karakterini ve ardından ikinci
bir ifadeyi içermez. Seçenek D doğrudur. int değeri short'tan daha büyük olsa da, açıkça short'a dönüştürülmüştür; bu da
değerin short içine sığması için döngüsel (wrap around) olacağı anlamına gelir. Seçenek E yanlıştır, çünkü long (L)
ekini kullanırken ondalık (.) kullanamazsınız. Son olarak, seçenek F yanlıştır, çünkü bir alt çizgi ondalık noktasının
yanında kullanılamaz.

29 - Aşağıdaki uygulamanın çalıştırılmasının sonucu nedir?

```
final var cb = new CyclicBarrier(3,
    () -> System.out.println("Clean!")); // u1

ExecutorService service = Executors.newSingleThreadExecutor();
    try {
        IntStream.generate(() -> 1)
          .limit(12)
          .parallel()
          .forEach(i -> service.submit(() -> cb.await())); // u2
} finally { service.shutdown(); }
```

* A. En azından bir kez Clean! çıktısı
* B. Tam dört kez Clean! çıktısı verir.
* C. Code u1 commentinden dolayi compile edilmez
* D. Code u2 commentinden dolayi compile edilmez
* E. Compile edilir fakat runtime'da exception fırlatır
* F. Derlenir ancak runtime'da sonsuza kadar bekler

**Cevap :** F. Kod, herhangi bir sorun olmadan derlenir. Bu kodu anlamanın anahtarı, thread executor'ımızın yalnızca bir
iş parçacığı (thread) içermesi, ancak CyclicBarrier sınırımızın 3 olmasıdır. 12 görev başarıyla hizmete sunulmuş olsa
da, ilk görev await() çağrısında sonsuza kadar bloklanacaktır. Baraj asla ulaşılmadığı için, hiçbir şey yazdırılmaz ve
program takılır; bu da seçeneğin F doğru olduğunu gösterir.

30 - Aşağıdaki methodla ilgili hangi statement (ifade) doğrudur?

```
5: public static void main(String... unused) {
6:    System.out.print("a");
7:    try (StringBuilder reader = new StringBuilder()) {
8:        System.out.print("b");
9:        throw new IllegalArgumentException();
10:   } catch (Exception e || RuntimeException e) {
11:       System.out.print("c");
12:       throw new FileNotFoundException();
13:   } finally {
14:   System.out.print("d");
15: } }
```

* A. Compile edilir ve abc print edilir
* B. Compile edilir ve abd print edilir
* C. Compile edilir ve abcd print edilir
* D. Bir satır compiler hatası içeriyor.
* E. İki satır compiler hatası içeriyor.
* F. Üç satır compiler hatası içeriyor.
* G. Compile edilir ancak runtime da bir exception yazdırır.

**Cevap :** F. Satır 5, satır 12'de fırlatılan FileNotFoundException yönetilmediği veya method tarafından bildirilmediği
için derlenmez. Satır 7, StringBuilder'ın AutoCloseable'ı implement etmediği ve bu nedenle bir try-with-resources
statement'i ile uyumlu olmadığı için derlenmez. Son olarak, satır 10, RuntimeException'ın çoklu yakalama bloğunda bir
Exception subclass'ı olması nedeniyle compile edilmez; bu da onu gereksiz kılar. Bu method üç compiler hatası içerdiği
için, seçenek F doğru cevaptır.

