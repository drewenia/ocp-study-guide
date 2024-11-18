# Exam Essentials (Sınav Temelleri)

Java operatörlerini kullanan kod yazabilmelisiniz. Bu bölüm, geniş bir operatör sembolleri yelpazesini ele aldı. Kitabın
geri kalanında onlara aşina olabilmek için geri dönüp birkaç kez gözden geçirin.

Hangi operatörlerin hangi veri türleriyle ilişkili olduğunu tanıyabilmelisiniz. Bazı operatörler yalnızca sayısal
primitive data type'larına, bazıları yalnızca boolean değerlere ve bazıları yalnızca Object'lere uygulanabilir. Operatör
ve operand(lar)ın uyumsuz olduğu durumları fark etmeniz önemlidir, çünkü bu tür bir sorun muhtemelen sınav sorularında
karşınıza çıkacaktır.

Casting'in gerektiği veya numeric promotion'ın gerçekleştiği durumları anlayın. İki farklı data type'ına ait operandları
birleştirdiğinizde, compiler'ın ortaya çıkan data type'ını nasıl handle edeceğine karar vermesi gerekir. Daha küçük bir
data type'ından daha büyük bir data type'ına dönüştürme yaparken, numeric promotion otomatik olarak uygulanır. Daha
büyük bir data type'ından daha küçük bir data type'ına dönüştürme yaparken ise cast etme gereklidir.

Java operator precedence'ini anlayın. Çalışacağınız çoğu Java operatörü binary olsa da, expression'ların sayısı
genellikle ikiden fazladır. Bu nedenle, Java'nın her bir operatör sembolünü hangi sırayla değerlendireceğini anlamanız
gerekir.

Operator precedence'ini override etmek parantez kullanarak kod yazabilmelisiniz. Öncelik sırasını manuel olarak
değiştirmek için kodunuzda parantez kullanmayı öğrenin.

