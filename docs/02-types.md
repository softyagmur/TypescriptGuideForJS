# Temel Tipler

Bu bölümde TypeScript'in sunduğu temel tipleri ve tip sistemini öğreneceksiniz.

## Temel Tipler

- `number`: Sayısal değerler
- `bigint`: Çok büyük sayılar için özel tip. JavaScript'te `number` tipi yaklaşık olarak ±9,007,199,254,740,991 (2^53 - 1) aralığında değer alabilir. Eğer bu sınırdan daha büyük veya daha küçük tam sayılarla çalışmanız gerekiyorsa `bigint` kullanılır. Genellikle finans, kriptografi veya çok büyük veri işlemlerinde ihtiyaç duyulur. Günlük uygulamalarda nadiren kullanılır.
- `string`: Metin değerleri
- `boolean`: Doğru/yanlış değerleri
- `array`: Dizi tipleri
- `tuple`: Sabit uzunlukta dizi
- `enum`: Sabit değerler listesi
- `any`: Herhangi bir tip
- `void`: Geri dönüş değeri olmayan fonksiyonlar
- `null` ve `undefined`: Boş değerler

## Örnekler

```typescript
const sayi: number = 17; // number tipi: Sayısal bir değer
const isim: string = "İbrahim"; // string tipi: Metinsel bir değer
const aktif: boolean = true; // boolean tipi: Doğru/yanlış (true/false) değeri yani bilgisayardaki 0 ile 1 gibi
const sayilarDizisi: number[] = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]; // number[] tipi: Sayılardan oluşan bir dizi
const metinlerDizisi: string[] = ["1", "2", "3"]; // string[] tipi: Metinlerden oluşan bir dizi
const tupleOrnegi: [string, number] = ["Yaşınız:", 86]; // tuple tipi: Sıralı ve sabit uzunlukta farklı tipte değerler içeren dizi
enum Renk {
  kirmizi,
  yesil,
  mavi,
} // enum tipi: Sabit değerler kümesi (kirmizi=0, yesil=1, mavi=2)
const renk: Renk = Renk.kirmizi; // enum kullanımı: renk değişkeni sadece Renk enum'undaki değerleri alabilir
```

## Tip Atamaları

TypeScript'te değişkenlere tip atamak, kodunuzu daha güvenli ve hatasız hale getirir. Ayrıca büyük ve karmaşık projelerde, kodunuzu başkalarıyla paylaşırken veya uzun zaman sonra tekrar gözden geçirirken, değişkenlerin ve fonksiyonların ne amaçla kullanıldığını çok daha kolay anlayabilirsiniz. Tipler sayesinde, yanlış veri kullanımlarının önüne geçilir ve kodun bakımı kolaylaşır.
