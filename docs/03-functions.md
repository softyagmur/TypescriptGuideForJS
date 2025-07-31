# Fonksiyonlar

Bu bölümde TypeScript'te fonksiyon tanımlama, parametre ve dönüş tipleri, opsiyonel ve varsayılan parametreler ile generics (jenerik) fonksiyonları öğreneceksiniz.

## Fonksiyon Tanımlama

```typescript
// Fonksiyon nasıl oluşturulur?
// function fonksiyonIsmi(param1: tip1, param2: tip2): donusTipi {
//   // fonksiyonun gövdesi
//   return ...;
// }

// Açıklama:
// - function: Fonksiyon tanımlamak için kullanılır.
// - fonksiyonIsmi: Fonksiyonun adı buraya yazılır.
// - (param1: tip1, param2: tip2): Parantez içinde her parametrenin adı ve tipi belirtilir.
// - : donusTipi: Fonksiyonun döndürdüğü değerin tipi buraya yazılır.

// Örnek fonksiyon:
function topla(a: number, b: number): number {
  // a ve b parametreleri number tipindedir, fonksiyon sonucu da number döner
  return a + b;
}

const sonuc = topla(5, 7); // sonuc: 12
```

## Opsiyonel ve Varsayılan Parametreler

```typescript
// Opsiyonel parametreli fonksiyon örneği
function selamla(isim: string, yas?: number): string {
  // yas parametresi verilirse mesajda yaş da gösterilir, verilmezse sadece isim gösterilir
  return yas ? `Merhaba ${isim}, yaşın ${yas}` : `Merhaba ${isim}`;
}

// Varsayılan parametreli fonksiyon örneği
function carp(a: number, b: number = 2): number {
  // b parametresi verilmezse otomatik olarak 2 kullanılır
  return a * b;
}
```

## Generics (Jenerik Fonksiyonlar)

```typescript
// Generics (jenerik) fonksiyon örneği
// T tipi, fonksiyon çağrılırken otomatik olarak belirlenir
function identity<T>(deger: T): T {
  // Aldığı değeri (hangi tipte olursa olsun) aynen geri döndürür
  return deger;
}

const sayi = identity<number>(5); // sayi: number tipinde
const metin = identity<string>("merhaba"); // metin: string tipinde
```

## Fonksiyon Tipleri

Fonksiyonların tipini değişkenlere atayabilirsiniz:

```typescript
// Fonksiyon tipini değişkene atama örneği
// (a: number, b: number) => number ifadesi, iki adet number parametre alıp number döndüren bir fonksiyon tipidir
let toplaFn: (a: number, b: number) => number = topla;
// Artık toplaFn değişkeni, topla fonksiyonunu referans eder ve aynı şekilde kullanılabilir
const sonuc2 = toplaFn(3, 4); // sonuc2: 7
```
