
# Nesneler, Sınıflar ve Arayüzler

Bu bölümde TypeScript'te nesne yapıları, sınıflar (classes) ve arayüzler (interfaces) konularını öğreneceksiniz. Her başlık altında kısa açıklama ve örnekler bulacaksınız.

## Nesne Tipleri

Bir nesnenin sahip olması gereken alanları ve tiplerini doğrudan belirtebilirsiniz:

```typescript
const kisi: { isim: string; yas: number } = {
  isim: "Yağmur", // isim alanı string tipinde
  yas: 16          // yas alanı number tipinde
};
// Bu şekilde, nesnenin hangi alanlara sahip olacağını ve tiplerini açıkça belirtmiş olursunuz.
```

## Sınıflar (Classes)

Sınıflar, nesne tabanlı programlamada tekrar kullanılabilir ve organize kod yazmak için kullanılır. Bir sınıf, özellikler (property) ve metotlar (method) içerebilir.

```typescript
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

const kopek = new Hayvan("Karabas");
kopek.sesCikar(); // "Ses çıkarıyor"
```

## Kalıtım (Inheritance)

Bir sınıf başka bir sınıftan özellik ve metotları miras alabilir. Alt sınıf, üst sınıfın metotlarını kendine göre özelleştirebilir (override).

```typescript
class Kedi extends Hayvan {
  constructor(isim: string) {
    // Üst sınıfın (Hayvan) constructor'ı çağrılır
    super(isim);
  }

  sesCikar(): void {
    // Kedi sınıfı, Hayvan sınıfındaki sesCikar metodunu kendine göre özelleştirir
    console.log("Miyav!");
  }
}

const pamuk = new Kedi("Pamuk");
pamuk.sesCikar(); // "Miyav!"
```

## Arayüzler (Interfaces)

Arayüzler, nesnelerin hangi alanlara ve metotlara sahip olması gerektiğini belirler. Kodun daha okunabilir ve sürdürülebilir olmasını sağlar.

```typescript
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
// Bu şekilde, bir nesnenin belirli bir yapıya uymasını garanti altına alırsınız.
```
