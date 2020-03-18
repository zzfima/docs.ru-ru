---
ms.openlocfilehash: 8d3a8712528d2d35c706cc26b8c388b65d6ad506
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "77449230"
---
### <a name="better-argument-validation-in-the-pkcs8privatekeyinfo-constructor"></a><span data-ttu-id="ca85f-101">Улучшенная проверка аргументов в конструкторе Pkcs8PrivateKeyInfo</span><span class="sxs-lookup"><span data-stu-id="ca85f-101">Better argument validation in the Pkcs8PrivateKeyInfo constructor</span></span>

<span data-ttu-id="ca85f-102">Начиная с .NET Core 3.0, предварительная версия 9, конструктор `Pkcs8PrivateKeyInfo` проверяет параметр `algorithmParameters` как одно значение в кодировке BER.</span><span class="sxs-lookup"><span data-stu-id="ca85f-102">Starting with .NET Core 3.0 Preview 9, the `Pkcs8PrivateKeyInfo` constructor validates the `algorithmParameters` parameter as a single BER-encoded value.</span></span>

#### <a name="change-description"></a><span data-ttu-id="ca85f-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="ca85f-103">Change description</span></span>

<span data-ttu-id="ca85f-104">До .NET Core 3.0, предварительная версия 9 [конструктор `Pkcs8PrivateKeyInfo`](xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.%23ctor(System.Security.Cryptography.Oid,System.Nullable%7BSystem.ReadOnlyMemory%7BSystem.Byte%7D%7D,System.ReadOnlyMemory%7BSystem.Byte%7D,System.Boolean)) не проверял аргумент `algorithmParameters`.</span><span class="sxs-lookup"><span data-stu-id="ca85f-104">Before .NET Core 3.0 Preview 9, the [`Pkcs8PrivateKeyInfo` constructor](xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.%23ctor(System.Security.Cryptography.Oid,System.Nullable%7BSystem.ReadOnlyMemory%7BSystem.Byte%7D%7D,System.ReadOnlyMemory%7BSystem.Byte%7D,System.Boolean)) did not validate the `algorithmParameters` argument.</span></span>  <span data-ttu-id="ca85f-105">Когда этот аргумент представляет недопустимое значение, конструктор выполняет задачу, но вызов любого из методов <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encode>, <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.TryEncode%2A>, <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encrypt%2A> или <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.TryEncrypt%2A> выдает исключение <xref:System.ArgumentException> для неподдерживаемого аргумента (`preEncodedValue`) или <xref:System.Security.Cryptography.CryptographicException>.</span><span class="sxs-lookup"><span data-stu-id="ca85f-105">When this argument represented an invalid value, the constructor would succeed, but a call to any of the <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encode>, <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.TryEncode%2A>, <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encrypt%2A>, or <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.TryEncrypt%2A> methods would throw either an <xref:System.ArgumentException> for an argument they did not accept (`preEncodedValue`) or a <xref:System.Security.Cryptography.CryptographicException>.</span></span>

<span data-ttu-id="ca85f-106">При запуске с помощью .NET Core 3.0, версий, предшествующих предварительной версии 9, следующий код выдает исключение только при вызове метода <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encode>:</span><span class="sxs-lookup"><span data-stu-id="ca85f-106">If run with .NET Core 3.0 before Preview 9, the following code throws an exception only when the <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encode> method is called:</span></span>

```csharp
byte[] algorithmParameters = { 0x05, 0x00, 0x05, 0x00 };

var info = new Pkcs8PrivateKeyInfo(algorithmId, algorithmParameters, privateKey);
// This line throws an ArgumentException for `preEncodedValue`:
byte[] encoded = info.Encode();
```

<span data-ttu-id="ca85f-107">Начиная с .NET Core 3.0 (предварительная версия 9), аргумент проверяется в конструкторе, и появление недопустимого значения приводит к тому, что метод вызывает исключение <xref:System.Security.Cryptography.CryptographicException>.</span><span class="sxs-lookup"><span data-stu-id="ca85f-107">Starting with .NET Core 3.0 Preview 9, the argument is validated in the constructor, and an invalid value results in the method throwing a <xref:System.Security.Cryptography.CryptographicException>.</span></span> <span data-ttu-id="ca85f-108">Это изменение позволяет связать исключение с источником ошибки данных.</span><span class="sxs-lookup"><span data-stu-id="ca85f-108">This change moves the exception closer to the source of the data error.</span></span> <span data-ttu-id="ca85f-109">Пример:</span><span class="sxs-lookup"><span data-stu-id="ca85f-109">For example:</span></span>

```csharp
byte[] algorithmParameters = { 0x05, 0x00, 0x05, 0x00 };

// This line throws a CryptographicException
var info = new Pkcs8PrivateKeyInfo(algorithmId, algorithmParameters, privateKey);
```

#### <a name="version-introduced"></a><span data-ttu-id="ca85f-110">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="ca85f-110">Version introduced</span></span>

<span data-ttu-id="ca85f-111">3.0, предварительная версия 9</span><span class="sxs-lookup"><span data-stu-id="ca85f-111">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ca85f-112">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="ca85f-112">Recommended action</span></span>

<span data-ttu-id="ca85f-113">Убедитесь, что предоставлены только допустимые значения `algorithmParameters` и что при вызовах конструктора `Pkcs8PrivateKeyInfo` проверяются и <xref:System.ArgumentException>, и <xref:System.Security.Cryptography.CryptographicException>, если требуется обработка исключений.</span><span class="sxs-lookup"><span data-stu-id="ca85f-113">Ensure that only valid `algorithmParameters` values are provided, or that calls to the `Pkcs8PrivateKeyInfo` constructor test for both <xref:System.ArgumentException> and <xref:System.Security.Cryptography.CryptographicException> if exception handling is desired.</span></span>

### <a name="category"></a><span data-ttu-id="ca85f-114">Категория</span><span class="sxs-lookup"><span data-stu-id="ca85f-114">Category</span></span>

<span data-ttu-id="ca85f-115">Шифрование</span><span class="sxs-lookup"><span data-stu-id="ca85f-115">Cryptography</span></span>

### <a name="affected-apis"></a><span data-ttu-id="ca85f-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="ca85f-116">Affected APIs</span></span>

- <span data-ttu-id="ca85f-117">[Конструктор Pkcs8PrivateKeyInfo](xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.%23ctor(System.Security.Cryptography.Oid,System.Nullable%7BSystem.ReadOnlyMemory%7BSystem.Byte%7D%7D,System.ReadOnlyMemory%7BSystem.Byte%7D,System.Boolean))</span><span class="sxs-lookup"><span data-stu-id="ca85f-117">[Pkcs8PrivateKeyInfo constructor](xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.%23ctor(System.Security.Cryptography.Oid,System.Nullable%7BSystem.ReadOnlyMemory%7BSystem.Byte%7D%7D,System.ReadOnlyMemory%7BSystem.Byte%7D,System.Boolean))</span></span>

<!--

### Affected APIs

- `M:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.#ctor(System.Security.Cryptography.Oid,System.Nullable{System.ReadOnlyMemory{System.Byte}},System.ReadOnlyMemory{System.Byte},System.Boolean)`

-->
