# Exam Essentials

String kullanarak kodun çıktısını belirleyebilmek için, String'lerin concatenating kurallarını ve yaygın String
methodlarının nasıl kullanıldığını bilmemiz gerekir. String'lerin değiştirilemez olduğunu (immutable) bilmek önemlidir.
Index'lerinin sıfır tabanlı olduğunu ve substring() methodunun ikinci parametredeki index değerinden önceki karakterlere
kadar olan alt string'i aldığını özellikle dikkate alınız.

StringBuilder'ın çıktısını belirleyebilmek için, StringBuilder'ın mutable olduğunu ve yaygın StringBuilder methodlarını
nasıl kullanacağınızı bilmeniz gerekir. substring() methodunun StringBuilder'ın değerini değiştirmediğini, ancak
append(), delete() ve insert() methodlarının değiştirdiğini unutmayın. Ayrıca, çoğu StringBuilder methodunun
StringBuilder'ın geçerli instance'ina bir referans döndürdüğünü unutmayın.

== operatörü object eşitliğini kontrol eder. equals() ise çağrıldığı object'in implementation'ına bağlıdır. String
sınıfı için equals(), içindeki karakterleri kontrol eder.

Array kullanarak kodun çıktısını belirleyebilmek için, tek boyutlu ve çok boyutlu dizileri nasıl declare ve instantiate
edeceğinizi bilmeniz gerekir. Her bir elemana erişebilmeli ve bir array'in sınırlarının dışına çıkıldığında ne
olacağını bilmelisiniz. Searching ve sorting işlemlerinde doğru ve yanlış çıktıları ayırt edebilmelisiniz.

Matematik methodlarının return type'larını tanımlayın. Aktarılan primitive'e bağlı olarak, Math methodları farklı
primitive sonuçlar döndürebilir.

Dates ve Times'ların geçersiz kullanımlarını tanıyın. LocalDate, time alanlarını içermez ve LocalTime, date alanlarını
içermez. Yanlış time'da yapılan işlemlere dikkat edin. Ayrıca, time eklemeyi veya çıkarmayı ve sonucu görmezden gelmeyi
göz önünde bulundurun. Zaman dilimleri ve gün ışığından yararlanma süresi dahil olmak üzere tarih matematiği konusunda
rahat olun.