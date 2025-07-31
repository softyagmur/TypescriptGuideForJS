# Fonksiyonlar

Bu bölümde TypeScript'te fonksiyon tanımlama, parametre ve dönüş tipleri, opsiyonel ve varsayılan parametreler ile generics (jenerik) fonksiyonları öğreneceksiniz.

## Fonksiyon Tanımlama

Bir fonksiyonun temel yapısı aşağıdaki gibidir:

```typescript
function fonksiyonIsmi(param1: tip1, param2: tip2): donusTipi {
  // Fonksiyonun gövdesi
  return ...;
}
```

- `fonksiyonIsmi`: Fonksiyonun adı
- `param1: tip1, param2: tip2`: Parametrelerin isimleri ve tipleri
- `: donusTipi`: Fonksiyonun döndürdüğü değerin tipi

### Örnek:

```typescript
function topla(a: number, b: number): number {
  // a ve b parametreleri number tipindedir, fonksiyon sonucu da number döner
  return a + b;
}

const sonuc = topla(5, 7); // sonuc: 12
```

## Opsiyonel ve Varsayılan Parametreler

Bir fonksiyonda bazı parametreler isteğe bağlı (opsiyonel) veya varsayılan değerli olabilir.

```typescript
// Opsiyonel parametreli fonksiyon
function selamla(isim: string, yas?: number): string {
  // yas parametresi verilirse mesajda yaş da gösterilir, verilmezse sadece isim gösterilir
  return yas ? `Merhaba ${isim}, yaşın ${yas}` : `Merhaba ${isim}`;
}

selamla("Ali"); // "Merhaba Ali"
selamla("Ayşe", 25); // "Merhaba Ayşe, yaşın 25"

// Varsayılan parametreli fonksiyon
function carp(a: number, b: number = 2): number {
  // b parametresi verilmezse otomatik olarak 2 kullanılır
  return a * b;
}

carp(3); // 6
carp(3, 4); // 12
```

## Generics (Jenerik Fonksiyonlar)

Generics, fonksiyonların farklı tiplerle çalışabilmesini sağlar.

```typescript
function identity<T>(deger: T): T {
  // Aldığı değeri (hangi tipte olursa olsun) aynen geri döndürür
  return deger;
}

const sayi = identity<number>(5); // sayi: number tipinde
const metin = identity<string>("merhaba"); // metin: string tipinde
```

## Fonksiyon Tipleri

Bir fonksiyonun tipini bir değişkene atayabilirsiniz. Böylece o değişken sadece belirli tipte fonksiyonları tutabilir.

```typescript
// (a: number, b: number) => number ifadesi, iki adet number parametre alıp number döndüren bir fonksiyon tipidir
const toplaFn: (a: number, b: number) => number = topla;
// Artık toplaFn değişkeni, topla fonksiyonunu referans eder ve aynı şekilde kullanılabilir
const sonuc2 = toplaFn(3, 4); // sonuc2: 7
```
