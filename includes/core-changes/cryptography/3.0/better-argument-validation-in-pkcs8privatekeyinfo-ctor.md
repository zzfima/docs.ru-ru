---
ms.openlocfilehash: a9b6af31b68c25ab58c52757f48ed23cca3f5a35
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568004"
---
### <a name="better-argument-validation-in-the-pkcs8privatekeyinfo-constructor"></a>Улучшенная проверка аргументов в конструкторе Pkcs8PrivateKeyInfo

Начиная с .NET Core 3.0, предварительная версия 9, конструктор `Pkcs8PrivateKeyInfo` проверяет параметр `algorithmParameters` как одно значение в кодировке BER.

#### <a name="change-description"></a>Описание изменений

До .NET Core 3.0, предварительная версия 9 [конструктор `Pkcs8PrivateKeyInfo`](xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.%23ctor(System.Security.Cryptography.Oid,System.Nullable%7BSystem.ReadOnlyMemory%7BSystem.Byte%7D%7D,System.ReadOnlyMemory%7BSystem.Byte%7D,System.Boolean)) не проверял аргумент `algorithmParameters`.  Когда этот аргумент представляет недопустимое значение, конструктор выполняет задачу, но вызов любого из методов <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encode>, <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.TryEncode%2A>, <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encrypt%2A> или <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.TryEncrypt%2A> выдает исключение <xref:System.ArgumentException> для неподдерживаемого аргумента (`preEncodedValue`) или <xref:System.Security.Cryptography.CryptographicException>.

При запуске с помощью .NET Core 3.0, версий, предшествующих предварительной версии 9, следующий код выдает исключение только при вызове метода <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encode>:

```csharp
byte[] algorithmParameters = { 0x05, 0x00, 0x05, 0x00 };

var info = new Pkcs8PrivateKeyInfo(algorithmId, algorithmParameters, privateKey);
// This line throws an ArgumentException for `preEncodedValue`:
byte[] encoded = info.Encode();
```

Начиная с .NET Core 3.0 (предварительная версия 9), аргумент проверяется в конструкторе, и появление недопустимого значения приводит к тому, что метод вызывает исключение <xref:System.Security.Cryptography.CryptographicException>. Это изменение позволяет связать исключение с источником ошибки данных. Например:

```csharp
byte[] algorithmParameters = { 0x05, 0x00, 0x05, 0x00 };

// This line throws a CryptographicException
var info = new Pkcs8PrivateKeyInfo(algorithmId, algorithmParameters, privateKey);
```

#### <a name="version-introduced"></a>Представленная версия

3.0, предварительная версия 9

#### <a name="recommended-action"></a>Рекомендуемое действие

Убедитесь, что предоставлены только допустимые значения `algorithmParameters` и что при вызовах конструктора `Pkcs8PrivateKeyInfo` проверяются и <xref:System.Security.Cryptography.CryptographicException>, и <xref:System.ArgumentException>, если требуется обработка исключений.

### <a name="category"></a>Категория

Шифрование

### <a name="affected-apis"></a>Затронутые API

- [Конструктор Pkcs8PrivateKeyInfo](xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.%23ctor(System.Security.Cryptography.Oid,System.Nullable%7BSystem.ReadOnlyMemory%7BSystem.Byte%7D%7D,System.ReadOnlyMemory%7BSystem.Byte%7D,System.Boolean))

<!--

### Affected APIs

- `M:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.#ctor(System.Security.Cryptography.Oid,System.Nullable{System.ReadOnlyMemory{System.Byte}},System.ReadOnlyMemory{System.Byte},System.Boolean))

-->
