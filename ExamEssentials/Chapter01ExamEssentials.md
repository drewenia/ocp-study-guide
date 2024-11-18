# Exam Essentials (Sınav temelleri)

Bir main() methodu kullanarak kod yazabilmek. main() methodu genellikle public static void main(String[] args) olarak
yazılır. Argümanlar args[0] ile başlayarak referans alınır. Geçersiz bir argümana erişmek, kodun bir exception
fırlatmasına neden olur.

Package ve import'ların kullanımının etkisini anlamak. Package'ler Java class'larını içerir. Sınıflar, sınıf adı
veya wildcard'lar (*) ile import edilebilir. Wildcard'lar sub-directory'lere bakmaz. Bir çakışma durumunda, sınıf adı
ile yapılan import önceliklidir. Package ve import statement'ları optional'dır. Mevcut olduklarında, her ikisi de bu
sırayla sınıf bildiriminden önce gelir.

Bir constructor' tanıyabilmek. Return type'ı olmayan bir method gibidir.

Legal ve illegal declaration'ları ve initialization'ları tanıyabilmek. Aynı type'ı paylaştıklarında birden fazla
variable aynı statement'da declare edilebilir ve initialize edilebilir. Local variable'lar açıkça initialization
gerektirir; diğerleri o type için varsayılan değeri kullanır. Identifier'lar harfler, sayılar, para birimi sembolleri
veya _ içerebilir, ancak sayılarla başlayamaz. Ayrıca, yalnızca tek bir alt çizgi karakteri _ olarak bir identifier
tanımlayamazsınız. Numeric literaller, iki rakam arasında alt çizgi içerebilir, örneğin 1_000, ancak başka yerlerde,
örneğin _100_.0_ gibi yerlerde alt çizgi bulunamaz.

String blocks oluşturmayı anlamak. Bir metin bloğu, ilk satırda """ ile başlar. Content bir sonraki satırda başlar. Son
satır """ ile biter. Eğer """ kendi satırında ise, sona bir satır sonu eklenir.

"var" ifadesini doğru şekilde kullanabilmek. var bir local variable için kullanılır. var, declare edildiği satırda
initialize edilir ve değeri değiştirilebilir, ancak type'ı değiştirilemez. "var" bir type belirtilmeden null değeriyle
initialize edilemez ve birden fazla variable declaration'ı için kullanılamaz.

Variable'ların hangi durumlarda scope içine alındığını ve dışına çıktığını belirleyebilmek. Tüm variable'lar,
declare edildiklerinde scope içine girer. Local Variable'lar, declare edildikleri blok sona erdiğinde scope dışına
çıkar. Instance variable'ları, object Garbage Collection için uygun hale geldiğinde scope dışına çıkar. Class
variable'ları, program çalıştığı sürece scope'da kalır.

Bir Object'in Garbage Collection için uygun hale geldiğini nasıl anlayacağınızı bilmek. Kodu izlerken referansları ve
Object'leri takip etmek için bir diyagram çizin. Bir kutuya (Object) hiçbir ok işaret etmediğinde, o object garbage
collection için uygun hale gelmiştir.