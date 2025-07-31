# Nesneler, Sınıflar ve Arayüzler

Bu bölümde TypeScript'te nesne yapıları, sınıflar (classes) ve arayüzler (interfaces) konularını öğreneceksiniz.

## Nesne Tipleri

```typescript
// Bir nesne (object) tanımı ve tip belirtimi
const kisi: { isim: string; yas: number } = {
  isim: "Yağmur", // isim alanı string tipinde
  yas: 16, // yas alanı number tipinde
};
// Bu şekilde nesnenin sahip olması gereken alanları ve tiplerini belirtebilirsiniz.
```

## Sınıflar

```typescript
// Sınıf (class) tanımı
class Hayvan {
  isim: string; // Her hayvanın bir ismi olacak

  constructor(isim: string) {
    // Sınıf oluşturulurken isim parametresi alınır ve this.isim'e atanır
    this.isim = isim;
  }

  sesCikar(): void {
    // Hayvanın ses çıkarmasını simüle eden bir metot
    console.log("Ses çıkarıyor");
  }
}
// Sınıflar, nesne tabanlı programlamada tekrar kullanılabilir ve organize kod yazmak için kullanılır.
```

## Kalıtım

```typescript
// Kalıtım (inheritance) örneği
class Kedi extends Hayvan {
  constructor(isim: string) {
    // Üst sınıfın (Hayvan) constructor'ı çağrılır
    super(isim);
  }

  sesCikar(): void {
    // Kedi sınıfı, Hayvan sınıfındaki sesCikar metodunu kendine göre özelleştirir (override)
    console.log("Miyav!");
  }
}
// Bu şekilde bir sınıf başka bir sınıftan özellik ve metotları miras alabilir.
```

## Arayüzler

```typescript
// Arayüz (interface) tanımı
interface Arac {
  marka: string; // Aracın markası
  model: string; // Aracın modeli
  calistir(): void; // Aracın çalıştırılmasını sağlayan metot
}

// Bir nesne, Arac arayüzünü uygulayacak şekilde tanımlanıyor
const araba: Arac = {
  marka: "Porsche",
  model: "Taycan",
  calistir() {
    // Aracın çalıştırılması simüle ediliyor
    console.log("Araba çalıştı");
  },
};
// Arayüzler, nesnelerin hangi alanlara ve metotlara sahip olması gerektiğini belirler.
```
