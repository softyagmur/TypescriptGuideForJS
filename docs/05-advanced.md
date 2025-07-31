# İleri Seviye Konular

Bu bölümde TypeScript'in gelişmiş özelliklerini öğreneceksiniz.

## Union ve Intersection Types
```typescript
let id: number | string;

interface A { a: number; }
interface B { b: string; }
let obj: A & B = { a: 1, b: "test" };
```

## Type Guards
```typescript
function printId(id: number | string) {
  if (typeof id === "string") {
    console.log(id.toUpperCase());
  } else {
    console.log(id);
  }
}
```

## Utility Types
- `Partial<T>`: Tüm alanları opsiyonel yapar
- `Readonly<T>`: Tüm alanları salt okunur yapar
- `Record<K, T>`: Belirli anahtarlar ve değerler

## Tip Çıkarımı (Type Inference)
TypeScript çoğu zaman tipleri otomatik olarak çıkarabilir.

## Modüller
Kodunuzu modüllere ayırarak daha düzenli hale getirebilirsiniz.
