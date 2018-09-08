# Cache

Sitenizin html çıktısını bir klasöre alıp gelen kullanıcalara html çıktısını göstermektedir. Böylece sitenize veritabanınıza yüklenme olmayacağı için doğal olarak saldırılardanda birnevi korunmuş olacaksınız. 

# Kullanımı
  Gayet basit. Sınıfı dahil edin ve çalıştırın bukadar. Sadece burdaki püf nokta sınıfın çalışmasını istediğiniz php dosyasının üst kısmına  eklemeniz olacak.
  ```sh
use ademozmermer\sCache;
```
Varsayılan ayarları kullanmak istiyorsanız, sınıfı çağırmanız yeterli olacaktır. Örn:
  ```sh
$sCache = new sCache();
```
# Default Ayarlar

  - Eğer zaman değeri belirtmediyseniz cache süreleri 60 saniyedir.
  - Özel bir cache yolu belirtmediyseniz anadizinde sCache dizini oluşturup onun içinde tutacaktır.
  - Cacheler md5 ile şifrelenip tutulmaktadır.
  - Eğer cache sıkıştırma özelliğini aktif etmez iseniz sıkıştırma yapmadan tutacaktır.
  - Eğer load özelliğini açmaz iseniz load değerleri gösterilmeyecektir. Ayarları düzenlemek için dizi olarak ayarları göndermeniz gerekir bunu nasıl yapacağınızı öğrenmek için alttaki koda bakarak yapabilirsiniz.
 
  ```sh
$options = [
            'time'   => 120, // 120 saniye yani 2 dakika    
            'dir'    => 'sCache2', // sCache2 klasörü oluşturup buraya yazılsın.    
            'buffer' => true, // html sayfalarımızın sıkıştırılmasını aktif edelim.    
            'load'   => true,  // sayfamızın sonunda load değerimiz görünsün.    
            'external'=>array('nocache.php','nocache2.php'), // Burada belirttiğiniz sayfalar ( dosyalar ) cachelenmez.    
];
$sCache = new sCache($options); // ayarları sınıfımıza gönderip sınıfı çalıştıralım.
```

"# sCache" 
