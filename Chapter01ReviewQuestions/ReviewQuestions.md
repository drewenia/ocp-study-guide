# Review Questions

1 - Which of the following are legal entry point methods that can be run from the command
line? (Choose all that apply.)

1 - Aşağıdakilerden hangisi command'den çalıştırılabilecek legal entry point methodlarıdır? (Geçerli olan tümünü
seçin.)

```
A. private static void main(String[] args)
B. public static final main(String[] args)
C. public void main(String[] args)
D. public static final void main(String[] args)
E. public static void main(String[] args)
F. public static main(String[] args)
```

**Cevap :** D, E. Seçenek E, canonical main() methodu imzasıdır. Bunu ezberlemeniz gerekir. Seçenek D, gereksiz final
anahtar kelimesiyle alternatif bir formdur. Seçenek A yanlıştır çünkü main() methodu public olmak zorundadır. Seçenekler
B ve F yanlıştır çünkü main() methodunun void return type'ı olmalıdır. Seçenek C yanlıştır çünkü main() methodu static
olmak zorundadır.

2 - Which answer options represent the order in which the following statements can be assembled into a program that will
compile successfully? (Choose all that apply.)

2 - Aşağıdaki statement'ların başarıyla compile edilen bir programda hangi sırayla birleştirilebileceğini temsil eden
cevap seçenekleri hangileridir? (Geçerli olan tüm seçenekleri seçin.)

```
X: class Rabbit {}
Y: import java.util.*;
Z: package animals;
```

```
A. X, Y, Z
B. Y, Z, X
C. Z, Y, X
D. Y, X
E. Z, X
F. X, Z
G. Yukarıdakinlerden hiçbiri
```

**Cevap :** C, D, E. Package ve import statement'larının her ikisi de optional'dır. Eğer her ikisi de varsa, sıralama
önce package, sonra import ve en son class olmalıdır. Seçenek A yanlıştır çünkü class, package ve import'tan önce yer
alıyor. Seçenek B yanlıştır çünkü import, package'tan önce yer alıyor. Seçenek F yanlıştır çünkü class, package'tan önce
yer alıyor.

3 - Which of the following are true? (Choose all that apply.)

3 - Aşağıdakilerden hangisi true? (Geçerli olan tümünü seçin.)

```
public class Bunny {
    public static void main(String[] x) {
    Bunny bun = new Bunny();
} }
```

```
A. Bunny is a class.
B. bun is a class.
C. main is a class.
D. Bunny is a reference to an object.
E. bun is a reference to an object.
F. main is a reference to an object.
G. The main() method doesn’t run because the parameter name is incorrect.
```

**Cevap :** A, E. Bunny bir sınıftır, bu da 'public class Bunny' declaration'ından anlaşılabilir. Varible bun bir
Object'e referanstır. main() methodu, bir programa entry point olarak standarttır. Seçenek G yanlıştır çünkü parametre
adı değil, parametre tipi önemlidir.

4 - Which of the following are valid Java identifiers? (Choose all that apply.)

4 - Aşağıdakilerden hangisi geçerli Java identifier'larıdır? (Geçerli olan tümünü seçin.)

```
A. _
B. _helloWorld$
C. true
D. java.lang
E. Public
F. 1980_s
G. _Q2_
```

**Cevap :** B, E, G. Seçenek A geçersizdir çünkü tek bir alt çizgi (_) izin verilen bir identifier değildir. Seçenek C
geçerli bir identifier değildir çünkü true bir Java reserved word'u. Seçenek D geçerli değildir çünkü identifier'lar da
nokta (.) kullanılamaz. Seçenek F geçerli değildir çünkü ilk karakter bir harf, dolar işareti ($) veya alt çizgi (_)
değildir. Seçenekler B, E ve G geçerlidir çünkü yalnızca geçerli karakterler içerirler.

5 - Which statements about the following program are correct? (Choose all that apply.)

5 - Aşağıdaki programla ilgili hangi statement'lar doğrudur? (Geçerli olan tümünü seçin.)

```
2: public class Bear {
3:      private Bear pandaBear;
4:      private void roar(Bear b) {
5:          System.out.println("Roar!");
6:          pandaBear = b;
7:      }
8:      public static void main(String[] args) {
9:          Bear brownBear = new Bear();
10:         Bear polarBear = new Bear();
11:         brownBear.roar(polarBear);
12:         polarBear = null;
13:         brownBear = null;
14:         System.gc(); } }
```

```
A. The object created on line 9 is eligible for garbage collection after line 13. 
A. Satır 9'da oluşturulan nesne, satır 13'ten sonra garbage collection için uygundur

B. The object created on line 9 is eligible for garbage collection after line 14. 
B. Satır 9'da oluşturulan nesne, satır 14'ten sonra garbage collection için uygundur

C. The object created on line 10 is eligible for garbage collection after line 12. 
C. Satır 10'da oluşturulan nesne, satır 12'ten sonra garbage collection için uygundur

D. The object created on line 10 is eligible for garbage collection after line 13. 
D. Satır 10'da oluşturulan nesne, satır 13'ten sonra garbage collection için uygundur

E. Garbage collection is guaranteed to run. 
E. Garbage Collection işleminin çalışması garanti edilir

F. Garbage collection might or might not run. 
F. Garbage Collection çalışabilir veya çalışmayabilir.

G. Code compile edilmez
```

**Cevap :** A, D, F. Garbage Collection işleminin çalıştırılacağı hiçbir zaman garanti edilmez, bu da F seçeneğini doğru
ve E seçeneğini yanlış yapar. Ardından, sınıf sorunsuz bir şekilde compile edilir ve çalışır, bu da G seçeneğini yanlış
yapar. 9. satırda oluşturulan Bear nesnesi, 13. satıra kadar brownBear referans değişkeni aracılığıyla erişilebilir; bu,
A seçeneğidir. 10. satırda oluşturulan Bear nesnesine hem polarBear referansı hem de brownBear.pandaBear referansı
aracılığıyla erişilebilir. 12. satırdan sonra nesneye hâlâ brownBear.pandaBear aracılığıyla erişilebilir. Ancak, 13.
satırdan sonra brownBear artık erişilebilir olmadığından nesneye artık erişilemez; bu da D seçeneğini nihai yanıt yapar.
brownBear roar methodunu çağırdığı anda polarBear'i methoda parametre olarak geçer ve method içerisinde
```pandaBear = b;``` komutu pandaBear referansına polarBear'i yerleştirir.

6 - Assuming the following class compiles, how many variables defined in the class or method are in scope on the line
marked on line 14?

6 - Aşağıdaki sınıfın compile edildiğini varsayarak, sınıf veya method içinde tanımlanan kaç değişkenin 14. satırda
scope'da olduğunu belirtiniz?

```
1: public class Camel {
2:      { int hairs = 3_000_0; } 
3:      long water, air=2;   
4:      boolean twoHumps = true; 
5:      public void spit(float distance) { 
6:          var path = ""; 
7:          { double teeth = 32 + distance++; } 
8:          while(water > 0) {
9:              int age = twoHumps ? 1 : 2; 
10:             short i=-1; 
11:             for(i=0; i<10; i++) {
12:                 var Private = 2;
13:             }
14:             // SCOPE
15:         }
16:     }
17: }
```

```
A. 2
B. 3
C. 4
D. 5
E. 6
F. 7
G. Yukarıdakinlerden hiçbiri
```

**Cevap :** F. Bu sorunu çözmek için süslü parantezleri {} izleyerek variable'ların scope içine ve dışına ne zaman
çıktığını görmeniz gerekir. 2. ve 7. satırlardaki variable'lar yalnızca tek bir satırlık bir blokta scope içindedir
kodun geri kalanından erişilemezler. 12. satırdaki değişken yalnızca for döngüsünde scope içindedir. Bunların hiçbiri
Satır 14'de scope'da değildir. Buna karşılık, 3. ve 4. satırlardaki üç instance variable tüm instance methodlarda
kullanılabilir. Ayrıca, 6. 9. ve 10 satırlardaki değişkenler, method ve while döngüsü hâlâ scope'da olduğu için
kullanılabilir. Bu toplamda 7 variable yapar, bu da F seçeneğidir.

```water, air, twoHumps, distance, path, age, short```

7 - Which are true about this code? (Choose all that apply.)

7 - Bu kod hakkında hangileri true? (Geçerli olan tümünü seçin.)

```
public class KitchenSink {
    private int numForks;
    public static void main(String[] args) {
        int numKnives;
        System.out.print("""
        "# forks = " + numForks +
        " # knives = " + numKnives +
        # cups = 0""");
    }
}
```

```
A. The output includes: # forks = 0.  
A. Çıktı şunları içerir: # forks = 0.

B. The output includes: # knives = 0 
B. Çıktı şunları içerir: # knives = 0

C. The output includes: # cups = 0. 
C. Çıktı şunları içerir: # cups = 0

D. The output includes a blank line. 
D. Çıktı boş bir satır içerir

E. The output includes one or more lines that begin with whitespace. 
E. Çıktı, boşluk ile başlayan bir veya daha fazla satır içerir.

F. The code does not compile. (Code compile edilmez)
```

**Cevap :** C, E. İlk olarak, bunun bir metin bloğu olduğunu ve """ içindeki kodun yalnızca metin olduğunu anlamak
gerekir. A ve B seçenekleri yanlıştır çünkü numForks ve numKnives variable'ları kullanılmamaktadır. Bu, numKnives
initialize edilmediği ve referans alınsaydı compile edilemeyeceği için uygundur. C seçeneği, metin eşleştiği için
doğrudur. D seçeneği yanlıştır çünkü metin bloğunun sonunda boş bir satır yoktur. Son olarak, E seçeneği de bir cevaptır
çünkü #knives girintilidir.

8 - Which of the following code snippets about var compile without issue when used in a method? (Choose all that apply)

8 - Var ile ilgili aşağıdaki kod parçacıklarından hangisi bir method içinde kullanıldığında sorunsuz compile edilir?
(Geçerli olan tümünü seçin)

```
A. var spring = null;
B. var fall = "leaves";
C. var evening = 2; evening = null;
D. var night = Integer.valueOf(3);
E. var day = 1/0;
F. var winter = 12, cold;
G. var fall = 2, autumn = 2;
H. var morning = ""; morning = null;
```

**Cevap :** B, D, E, H. "var" ile bir type belirtilmeden null değeri atanamaz, ancak temel tür bir primitive tür değilse
daha sonra null atanabilir. Bu nedenlerden dolayı, H seçeneği doğrudur, ancak A ve C seçenekleri yanlıştır. B ve D
seçenekleri, temel türlerin sırasıyla String ve Integer olması nedeniyle doğrudur. E seçeneği de geçerli bir sayısal
ifade olduğundan doğrudur. Sıfıra bölmenin çalışma zamanı hatası üretebileceğini biliyor olabilirsiniz, ancak soru
yalnızca kodun derlenip derlenmediğiyle ilgiliydi. Son olarak, F ve G seçenekleri yanlıştır çünkü var multiple-variable
assigment'i için kullanılamaz

9 - Which of the following are correct? (Choose all that apply.)

9 - Aşağıdakilerden hangisi doğrudur? (Geçerli olan tümünü seçin.)

```
A. An instance variable of type float defaults to 0. 
A. Instance variable olarak float'un default değeri 0

B. An instance variable of type char defaults to null. 
B. Instance variable olarak char'ın default değeri null

C. A local variable of type double defaults to 0.0. 
C. Local variable olarak double'ın default değeri 0.0

D. A local variable of type int defaults to null. 
D. Local variable olarak int'in default değeri null

E. A class variable of type String defaults to null. 
E. Class variable olarak String'in default değeri null

F. A class variable of type String defaults to the empty string "" 
F. Class variable olarak String'in default değeri ""

G. Yukarıdakinlerden hiçbiri
```

**Cevap :** E. C ve D seçenekleri yanlıştır çünkü local variable'ların default değerleri yoktur. A seçeneği yanlıştır
çünkü float bir decimal point'e sahip olmalıdır. B seçeneği yanlıştır çünkü primitive türler varsayılan olarak null
değildir. E seçeneği doğrudur ve F seçeneği yanlıştır çünkü Class variable'larında ki referans type'ları default olarak
null olur.

10 - Which of the following expressions, when inserted independently into the blank line, allow the code to compile? (
Choose all that apply.)

10 - Aşağıdaki expression'lardan hangileri, boş satıra bağımsız olarak yerleştirildiğinde kodun compile edilmesine izin
verir? (Uygulanan tüm seçenekleri seçin.)

```
public void printMagicData() {
    var magic = ;
    System.out.println(magic);
}
```

```
A. 3_1
B. 1_329_.0
C. 3_13.0_
D. 5_291._2
E. 2_234.0_0
F. 9___6
G. _1_3_5_0
```

**Cevap :** A, E, F. Bir alt çizgi (_), bir numeric literalin başında, sonunda veya decimal point'in (.) yanında
olmadığı sürece herhangi bir yerine yerleştirilebilir. Alt çizgiler, yan yana bile konulabilir. Bu nedenlerden dolayı,
A, E ve F seçenekleri doğrudur. B ve D seçenekleri yanlıştır çünkü alt çizgi (_), ondalık noktanın (.) yanındadır. C ve
G seçenekleri yanlıştır çünkü alt çizgi (_), literalin başına veya sonuna yerleştirilemez.

11 - Given the following two class files, what is the maximum number of imports that can be removed and have the code
still compile?

11 - Aşağıdaki iki class file'a bakarak, kodun hala compile edilmesi için en fazla kaç tane import kaldırılabilir?

```
// Water.java
package aquarium;
public class Water { }

// Tank.java
package aquarium;
import java.lang.*;
import java.lang.System;
import aquarium.Water;
import aquarium.*;
public class Tank {
    public void print(Water water) {
    System.out.println(water); } }
```

```
A. 0
B. 1
C. 2
D. 3
E. 4
F. Code compile edilmez
```

**Cevap :** E. İlk iki import, java.lang otomatik olarak import edildiği için kaldırılabilir. Tank ve Water aynı
package'de olduğundan, sonraki iki import da kaldırılabilir ve doğru cevap E seçeneğidir. Eğer Tank ve Water farklı
paketlerde olsaydı, bu iki importtan yalnızca biri kaldırılabilirdi. Bu durumda cevap D seçeneği olurdu.

12 - Which statements about the following class are correct? (Choose all that apply.)

12 - Aşağıdaki sınıfla ilgili hangi statement'lar doğrudur? (Geçerli olan tümünü seçiniz.)

```
1: public class ClownFish {
2:      int gills = 0, double weight=2;
3:      { int fins = gills; }
4:      void print(int length = 3) {
5:          System.out.println(gills);
6:          System.out.println(weight);
7:          System.out.println(fins);
8:          System.out.println(length);
9: } }
```

```
A. Satır 2 compile hatası üretir.
B. Satır 3 compile hatası üretir.
C. Satır 4 compile hatası üretir.
D. Satır 7 compile hatası üretir.
E. The code prints 0.
F. The code prints 2.0.
G. The code prints 2.
H. The code prints 3.
```

**Cevap :** A, C, D. 2. satır compile edilmez çünkü yalnızca bir type belirtilebilir; bu, A seçeneğini doğru yapar. 3.
satır bir instance initializer içinde kullanılmayan bir local variable tanımladığı için sorunsuzca compile edilir. 4.
satır compile edilmez çünkü Java, method parametrelerine default değerler atamayı desteklemez; bu, C seçeneğini doğru
yapar. Son olarak, 7. satır compile edilemez çünkü fins, yalnızca 3. satırdaki instance initializer içinde scope'da ve
erişilebilir durumdadır; bu da D seçeneğini doğru yapar.

13 - Given the following classes, which of the following snippets can independently be inserted in place of INSERT
IMPORTS HERE and have the code compile? (Choose all that apply.)

13 - Aşağıdaki sınıflar göz önüne alındığında, INSERT IMPORTS HERE yerine bağımsız olarak eklenip kodun derlenmesini
sağlayacak ifadelerden hangileri kullanılabilir? (Uygulanan tüm seçenekleri seçin.)

```
package aquarium;
public class Water {
    boolean salty = false;
}

package aquarium.jellies;
public class Water {
    boolean salty = true;
}

package employee;
INSERT IMPORTS HERE
public class WaterFiller {
    Water water;
}
```

```
A.  import aquarium.*;

B.  import aquarium.Water;
    import aquarium.jellies.*;

C.  import aquarium.*;
    import aquarium.jellies.Water;

D.  import aquarium.*;
    import aquarium.jellies.*;

E.  import aquarium.Water;
    import aquarium.jellies.Water;

F.  Bu import'ların hiçbiri kodun compile edilmesini sağlayamaz.
```

**Cevap :** A, B, C. A seçeneği doğrudur çünkü aquarium package'i altındaki tüm sınıfları, aquarium.Water dahil olmak
üzere import eder. B ve C seçenekleri doğrudur çünkü Water sınıfını ad ile import ederler. Sınıf adıyla yapılan import,
joker karakterlerden (wildcards) öncelikli olduğu için bunlar derlenir. D seçeneği yanlıştır çünkü Java, wildcard'lar
ile import edilen iki Water sınıfından hangisini kullanacağını bilemez. E seçeneği yanlıştır çünkü aynı sınıf adını iki
import ifadesinde belirtmek mümkün değildir.

14 - Which of the following statements about the code snippet are true? (Choose all that apply.)

14 - Kod parçacığı ile ilgili aşağıdaki statement'lardan hangileri doğrudur? (Geçerli olan tümünü seçin.)

```
3: short numPets = 5L;
4: int numGrains = 2.0;
5: String name = "Scruffy";
6: int d = numPets.length();
7: int e = numGrains.length;
8: int f = name.length();
```

```
A. Satır 3 compile error üretir 
B. Satır 4 compile error üretir
C. Satır 5 compile error üretir
D. Satır 6 compile error üretir 
E. Satır 7 compile error üretir 
F. Satır 8 compile error üretir 
```

**Cevap :** A, B, D, E. 3. satır compile edilemez çünkü L eki, literal değeri long yapar ve bu değer doğrudan bir short
içinde saklanamaz; bu, A seçeneğini doğru yapar. 4. satır compile edilemez çünkü int bir tam sayı türüdür, ancak 2.0 bir
double literal değeridir; bu da B seçeneğini doğru yapar. 5. satır sorunsuz şekilde derlenir. 6. ve 7. satırlar
derlenemez çünkü numPets ve numGrains her ikisi de primitive type'dır ve yalnızca referans türleri üzerinde method
çağrılabilir, primitive değerler üzerinde değil; bu da sırasıyla D ve E seçeneklerini doğru yapar. Son olarak, 8. satır
compile edilir çünkü String üzerinde tanımlı bir length() methodu vardır.

15 - Which of the following statements about garbage collection are correct? (Choose all that apply.)

15 - Garbage Collection ile ilgili aşağıdaki statement'lardan hangisi doğrudur? (Geçerli olan tümünü seçin.)

```
A. Calling System.gc() is guaranteed to free up memory by destroying objects eligible for garbage collection.
A. System.gc() çağrısının, Garbage Collection için uygun nesneleri yok ederek belleği boşaltacağı garanti edilir.

B. Garbage collection runs on a set schedule.
B. Garbage Collection, belirli bir schedule planına göre çalışır.

C. Garbage collection allows the JVM to reclaim memory for other objects.
C. Garbage collection, JVM'nin diğer nesneler için belleği geri kazanmasını sağlar.

D. Garbage collection runs when your program has used up half the available memory.
D. Garbage Collection, programınız mevcut belleğin yarısını kullandığında çalışır.

E. An object may be eligible for garbage collection but never removed from the heap.
E. Bir nesne, Garbage Collection'a uygun olabilir ancak heap alanından asla kaldırılmayabilir.

F. An object is eligible for garbage collection once no references to it are accessible in the program.
F. Bir nesne, programda ona ait hiçbir referans erişilebilir olmadığında Garbage Collection için uygun hale gelir.

G. Marking a variable final means its associated object will never be garbage collected.
G. Bir variable'in final olarak işaretlenmesi, ilişkili nesnenin asla Garbege Collection uygulanmayacağı anlamına gelir.
```

**Cevap :** C, E, F. Java'da Garbage Collection'ın ne zaman çalışacağına dair bir garanti yoktur. JVM, System.gc()
çağrılarını görmezden gelebilir. Bu nedenle, A, B ve D seçenekleri yanlıştır. C seçeneği doğrudur, çünkü Garbage
Collection'ın amacı, kullanılan belleği geri kazanmaktır. E seçeneği de doğrudur; bir nesne, program Garbage Collection
çalışmadan önce sona ererse asla garbage collection yapılmayabilir. F seçeneği de doğrudur ve Garbage Collection
algoritmalarının bir nesnenin Garbage Collection'a uygun olup olmadığını belirlemesinin birincil yoludur. Son olarak, G
seçeneği yanlıştır, çünkü bir variable'in final olarak işaretlenmesi, onun yalnızca kendi scope'u içinde sabit olduğu
anlamına gelir. Örneğin, final olarak işaretlenmiş bir local variable, method sona erdikten sonra, eğer bu nesneye başka
bir referans yoksa, Garbage Collection için uygun hale gelir.

16 - Which are true about this code? (Choose all that apply.)

16 - Bu kod hakkında hangileri true? (Geçerli olan tümünü seçin.)

```
var blocky = """
    squirrel \s
    pigeon  \
    termite""";
System.out.print(blocky);
```

```
A. It outputs two lines.
A. İki satır çıktı verir

B. It outputs three lines.
B. Üç satır çıktı verir

C. It outputs four lines.
C. Dört satır çıktı verir

D. There is one line with trailing whitespace.
D. Sonunda whitespace olan bir satır vardır.

E. There are two lines with trailing whitespace.
E. Sonunda whitespace olan iki satır vardır.

F. If we indented each line five characters, it would change the output.
F. Her satırı beş karakter indented (girintili) yapsaydık, çıktı değişirdi.
```

**Cevap :** A, D. Seçenek A doğrudur. İki satır vardır. Biri "squirrel" ile, diğeri "pigeon" ile başlar. Bir ters eğik
çizgi (\) satır sonunu atlamak anlamına gelir. Seçenek D de doğrudur, çünkü \s boşlukları korumak anlamına gelir. Bir
metin bloğunda, rastlantısal girintiler göz ardı edilir; bu da seçenek F'in yanlış olduğu anlamına gelir.

| \s kullanımına bir örnek |
|--------------------------|

```
jshell> String original = """
        Tim \s
        Peter\s
        Mike \s"""
        
original ==> "Tim  \nPeter \nMike  "
```

17 - What lines are printed by the following program? (Choose all that apply.)

17 - Aşağıdaki program tarafından hangi satırlar yazdırılır? (Geçerli olan tümünü seçin.)

```
1: public class WaterBottle {
2:      private String brand;
3:      private boolean empty;
4:      public static float code;
5:      public static void main(String[] args) {
6:          WaterBottle wb = new WaterBottle();
7:          System.out.println("Empty = " + wb.empty);
8:          System.out.println("Brand = " + wb.brand);
9:          System.out.println("Code = " + code);
10: } }
```

```
A. Satır 8 compiler hatası üretir 
B. Satır 9 compiler hatası üretir
C. Empty =
D. Empty = false
E. Brand =
F. Brand = null
G. Code = 0.0
H. Code = 0f
```

**Cevap :** D, F, G. Kod sorunsuz bir şekilde compile edilir ve çalışır, bu nedenle A ve B seçenekleri yanlıştır.
Bir boolean field varsayılan olarak "false" değerini alır, bu da D seçeneğini doğru yapar ve "Empty = false" yazdırılır.
Nesne referansları boş bir String'e değil, null değerine initialize edilir, bu nedenle F seçeneği doğrudur ve
"Brand = null" yazdırılır. Son olarak, floating-point sayıların default değeri 0.0'dır. Float değerler f ekini alarak
tanımlanabilse de, bu ek yazdırılmaz. Bu sebeplerle, G seçeneği doğrudur ve "Code = 0.0" yazdırılır.

18 - Which of the following statements about "var" are true? (Choose all that apply.)

18 - "var" ile ilgili aşağıdaki ifadelerden hangisi true? (Geçerli olan tümünü seçin.)

```
A. A var can be used as a constructor parameter.
A. Bir "var", constructor parametresi olarak kullanılabilir.

B. The type of a var is known at compile time.
B. Bir "var" ın type'ı compile time da bilinir.

C. A var cannot be used as an instance variable.
C. Bir "var", instance varible olarak kullanılamaz.

D. A var can be used in a multiple variable assignment statement.
D. Bir "var", multiple variable assigment statement'ın da kullanılabilir.

E. The value of a var cannot change at runtime.
E. Bir "var" ın değeri runtime da değişemez.

F. The type of a var cannot change at runtime.
F. Bir "var" ın type'ı runtime'da değişemez.

G. The word var is a reserved word in Java.
G. Java'da "var" kelimesi reserved bir kelimedir.
```

B, C, F. "var", bir constructor veya method parametresi ya da bir instance veya sınıf variable'i olarak kullanılamaz. Bu
durum, A seçeneğini yanlış, C seçeneğini ise doğru yapar. "var" type compile time da bilinir ve type'ı runtime'da
değiştirilemez; ancak değeri runtime'da değişebilir. Bu sebeplerle, B ve F seçenekleri doğrudur ve E seçeneği yanlıştır.
D seçeneği yanlıştır, çünkü "var", multiple variable'in tanımlandığı declaration'lar da kullanılamaz. Son olarak, G
seçeneği yanlıştır, çünkü var Java'da rezerve edilmiş bir kelime değildir.

19 - Which are true about the following code? (Choose all that apply.)

19 - Aşağıdaki kod hakkında hangileri true? (Geçerli olan tümünü seçin.)

```
var num1 = Long.parseLong("100");
var num2 = Long.valueOf("100");
System.out.println(Long.max(num1, num2));
```

```
A. The output is 100.
A. 100 çıktısı üretilir

B. The output is 200.
B. 200 çıktısı üretilir

C. The code does not compile.
C. Code compile edilmez

D. num1 is a primitive.
D. num1 primitive 

E. num2 is a primitive.
E. num2 pritimive
```

**Cevap :** A, D. İlk iki satır, bir String'i bir sayıya dönüştürmenin bir yolunu sağlar. İlk satır bir long primitive,
ikinci satır ise bir Long referans nesnesini temsil eder; bu da D seçeneğini doğru cevaplardan biri yapar. Kod doğrudur
ve maksimum değer 100'dür, bu da A seçeneğidir. E seçeneğinin yanlış olmasının sebebi ```Long.valueOf()``` methodunun
Long tipinde bir referans dönmesidir (Primitive değildir)

20 - Which statements about the following class are correct? (Choose all that apply.)

20 - Aşağıdaki sınıfla ilgili hangi statement'lar doğrudur? (Geçerli olan tümünü seçiniz.)

```
1: public class PoliceBox {
2:      String color;
3:      long age;
4:      public void PoliceBox() {
5:          color = "blue";
6:          age = 1200;
7:      }
8:      public static void main(String []time) {
9:          var p = new PoliceBox();
10:         var q = new PoliceBox();
11:         p.color = "green";
12:         p.age = 1400;
13:         p = q;
14:         System.out.println("Q1="+q.color);
15:         System.out.println("Q2="+q.age);
16:         System.out.println("P1="+p.color);
17:         System.out.println("P2="+p.age);
18: } }
```

```
A. It prints Q1=blue. 
A. Q1=blue print edilir.

B. It prints Q2=1200. 
B. Q2=1200 print edilir

C. It prints P1=null. 
C. P1=null print edilir

D. It prints P2=1400. 
D. P2=1400 print edilir

E. Line 4 does not compile. 
E. 4. Satır compile edilmez

F. Line 12 does not compile. 
F. 12. Satır compile edilmez

G. Line 13 does not compile. 
G. 13. Satır compile edilmez

H. Yukarıdakinlerden hiçbiri
```

**Cevap :** C. Dikkat edilmesi gereken önemli nokta, 4. satırın bir constructor tanımlamaması, bunun yerine PoliceBox()
adında bir method tanımlaması, çünkü return type void olarak belirtilmiş. Bu method programın çalışması sırasında asla
çağrılmaz ve bu nedenle color ve age variable'ları sırasıyla varsayılan değerler olan null ve 0L olarak atanır. 11. ve
12 . satırlar, p ile ilişkilendirilmiş bir nesnenin değerlerini değiştirir, ancak 13. satırda, p değişkeni q ile
ilişkilendirilmiş nesneyi işaret edecek şekilde değiştirilir ve bu nesne hala default değerlere sahiptir. Bu nedenle
program, Q1=null, Q2=0, P1=null, ve P2=0 değerlerini yazdırır ve C seçeneği tek doğru cevap olur.

21 - What is the output of executing the following class?

21 - Aşağıdaki sınıfın çalıştırılmasının çıktısı nedir?

```
1: public class Salmon {
2:      int count;
3:      { System.out.print(count+"-"); }
4:      { count++; }
5:      public Salmon() {
6:          count = 4;
7:          System.out.print(2+"-");
8:      }
9:      public static void main(String[] args) {
10:         System.out.print(7+"-");
11:         var s = new Salmon();
12:         System.out.print(s.count+"-"); } }
```

```
A. 7-0-2-1-

B. 7-0-1-

C. 0-7-2-1

D. 7-0-2-4-

E. 0-7-1-

F. The class does not compile because of line 3.
F. Satır 3 den ötürü class compile edilmez

G. The class does not compile because of line 4.
G. Satır 4 den ötürü class compile edilmez

H. Yukarıdakinlerden hiçbiri
```

**Cevap :** D. main() methodu ile başlıyoruz, bu method 10. satırda 7- yazdırır. Ardından, 11. satırda yeni bir Salmon
instance'i oluşturulur. Bu, sırasıyla 3. ve 4. satırlardaki iki instance initializer'in çalıştırılmasına neden olur.
int türündeki bir instance variable'in varsayılan değeri 0 olduğu için, önce 0- yazdırılır ve count değişkenine 1 değeri
atanır. Daha sonra constructor çağrılır. Bu, count değişkenine 4 değerini atar ve 2- yazdırır. Son olarak, 12. satır 4-
yazdırır, çünkü count değişkeninin değeri budur. Bunları birleştirince, çıktı şu şekilde olur: 7- 0- 2- 4-. Bu nedenle
doğru cevap D seçeneğidir.

22 - Given the following class, which of the following lines of code can independently replace INSERT CODE HERE to make
the code compile? (Choose all that apply.)

22 - Aşağıdaki sınıf göz önüne alındığında, kodun compile edilmesini sağlamak için aşağıdaki kod satırlarından hangisi
bağımsız olarak INSERT CODE HERE yerine kullanılabilir? (Geçerli olan tümünü seçin.)

```
public class Price {
    public void admission() {
        INSERT CODE HERE
        System.out.print(amount);
} }
```

```
A. int Amount = 0b11;
B. int amount = 9L;
C. int amount = 0xE;
D. int amount = 1_2.0;
E. double amount = 1_0_.0;
F. int amount = 0b101;
G. double amount = 9_2.1_2;
H. double amount = 1_2_.0_0;
```

**Cevap :** C, F, G. Öncelikle, 0b bir binary value prefix'i, 0x ise bir hexadecimal value prefix'i dir. Bu değerler,
int ve double dahil olmak üzere birçok primitive türe atanabilir, bu da C ve F seçeneklerini doğru yapar. A seçeneği
yanlıştır, çünkü variable'in adını Amount olarak belirlemek, bir sonraki satırda System.out.print(amount) çağrısının
compile edilmemesine neden olur. B seçeneği yanlıştır, çünkü 9L bir long type değerdir. Type long amount = 9L olarak
değiştirilirse kod compile edilir. D seçeneği yanlıştır, çünkü 1_2.0 bir double type değerdir. Type double amount =
1_2.0 olarak değiştirilirse kod compile edilir. E ve H seçenekleri yanlıştır, çünkü alt çizgi (_) decimal point'in (.)
yanında kullanılmıştır, buna izin verilmez. Son olarak, G seçeneği doğrudur, çünkü alt çizgi kullanımı ve atama biçimi
geçerlidir.

23 - Which statements about the following class are true? (Choose all that apply.)

23 - Aşağıdaki sınıfla ilgili hangi ifadeler true? (Geçerli olan tümünü seçin.)

```
1: public class River {
2:      int Depth = 1;
3:      float temp = 50.0;
4:      public void flow() {
5:          for (int i = 0; i < 1; i++) {
6:              int depth = 2;
7:              depth++;
8:              temp--;
9:          }
10:         System.out.println(depth);
11:         System.out.println(temp); }
12:     public static void main(String... s) {
13:         new River().flow();
14: } }
```

```
A. Line 3 generates a compiler error.
A. Satır 3 compile hatası üretir 

B. Line 6 generates a compiler error.
B. Satır 6 compile hatası üretir

C. Line 7 generates a compiler error.
C. Satır 7 compile hatası üretir

D. Line 10 generates a compiler error.
D. Satır 10 compile hatası üretir 

E. The program prints 3 on line 10.
E. Satır 10'da 3 print edilir

F. The program prints 4 on line 10.
F. Satır 10'da 4 print edilir

G. The program prints 50.0 on line 11.
G. Satır 11'de 50.0 print edilir

H. The program prints 49.0 on line 11.
H. Satır 11'de 49.0 print edilir
```

**Cevap :** A, D. İlk compiler hatası 3. satırda meydana gelir. temp variable'i bir float olarak tanımlanmıştır, ancak
atanan değer 50.0'dır; bu, F/f postfix'ini kullanmayan bir double değeri olarak kabul edilir. Çünkü bir double, bir
float içine sığmaz, bu nedenle 3. satır compile edilemez. Sonrasında, depth variable'i for döngüsü içinde
tanımlanmıştır ve yalnızca bu döngü içinde geçerliliğe sahiptir. Bu nedenle, 10. satırda değeri okunmaya çalışıldığında
bir compiler hatası oluşur. Bu sebeplerle, A ve D seçenekleri doğru cevaplardır.