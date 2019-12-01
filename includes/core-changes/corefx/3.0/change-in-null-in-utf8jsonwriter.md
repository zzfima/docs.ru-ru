---
ms.openlocfilehash: 7c39fe7ffd59fa7a5564bb45f32a6a2fbe0ddb33
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568206"
---
### <a name="change-in-semantics-of-stringnull-in-utf8jsonwriter"></a><span data-ttu-id="3d6e8-101">Изменения семантики `(string)null` в Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="3d6e8-101">Change in semantics of `(string)null` in Utf8JsonWriter</span></span>

<span data-ttu-id="3d6e8-102">В .NET Core 3.0 (предварительная версия 7) строка со значением NULL обрабатывается как пустая строка в <xref:System.Text.Json.Utf8JsonWriter>.</span><span class="sxs-lookup"><span data-stu-id="3d6e8-102">In .NET Core 3.0 Preview 7, the null string is treated as the empty string in <xref:System.Text.Json.Utf8JsonWriter>.</span></span> <span data-ttu-id="3d6e8-103">Начиная с .NET Core 3.0 (предварительная версия 8) строка со значением NULL вызывает исключение, если она используется в качестве имени свойства, а также создает токен JSON со значением NULL при использовании в качестве значения.</span><span class="sxs-lookup"><span data-stu-id="3d6e8-103">Starting with .NET Core 3.0 Preview 8, the null string throws an exception when used as a property name, and it emits the JSON null token when used as a value.</span></span>

#### <a name="change-description"></a><span data-ttu-id="3d6e8-104">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="3d6e8-104">Change description</span></span>

<span data-ttu-id="3d6e8-105">В .NET Core 3.0 (предварительная версия 7) строка `null` обрабатывалась как `""` при записи имен значений и при записи самих значений.</span><span class="sxs-lookup"><span data-stu-id="3d6e8-105">In .NET Core 3.0 Preview 7, the `null` string was treated as `""` both when writing property names and when writing values.</span></span>  

<span data-ttu-id="3d6e8-106">Начиная с .NET Core 3.0 (предварительная версия 8) имя свойства со значением `null` вызывает исключение `ArgumentNullException`, а значение `null` обрабатывается как вызов к <xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A?displayProperty=nameWithType> или <xref:System.Text.Json.Utf8JsonWriter.WriteNullValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3d6e8-106">Starting with .NET Core 3.0 Preview 8, a `null` property name throws an `ArgumentNullException`, and a `null` value is treated as a call to <xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A?displayProperty=nameWithType> or <xref:System.Text.Json.Utf8JsonWriter.WriteNullValue?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="3d6e8-107">Рассмотрим следующий код.</span><span class="sxs-lookup"><span data-stu-id="3d6e8-107">Consider the following code:</span></span>

```csharp
string propertyName1 = null;
string propertyValue1 = null;
string propertyName2 = "prop2";
string propertyValue2 = null;
string simpleValue1 = null;

using (Utf8JsonWriter writer = new Utf8JsonWriter(stream))
{
    writer.WriteStartArray();

    writer.WriteStartObject();
    writer.WriteString(propertyName1, propertyValue1);
    writer.WriteString(propertyName2, propertyValue2);
    writer.WriteEndObject();

    writer.WriteStringValue(simpleValue1);

    writer.WriteEndArray();
}
```

<span data-ttu-id="3d6e8-108">При запуске с помощью .NET Core 3.0 (предварительная версия 7) модуль записи выводит следующие данные:</span><span class="sxs-lookup"><span data-stu-id="3d6e8-108">If run with .NET Core 3.0 Preview 7, the writer produces the following output:</span></span>

```js
[{"":"","prop2":""},""]
```

<span data-ttu-id="3d6e8-109">Начиная с .NET Core 3.0 (предварительная версия 8) вызов к `writer.WriteString(propertyName1, propertyValue1)` вызывает исключение <xref:System.ArgumentNullException>.</span><span class="sxs-lookup"><span data-stu-id="3d6e8-109">Starting with .NET Core 3.0 Preview 8, the call to `writer.WriteString(propertyName1, propertyValue1)` throws an <xref:System.ArgumentNullException>.</span></span>  <span data-ttu-id="3d6e8-110">Если `propertyName1 = null` заменить на `propertyName1 = string.Empty`, выходные данные будут такими:</span><span class="sxs-lookup"><span data-stu-id="3d6e8-110">If `propertyName1 = null` is replaced with `propertyName1 = string.Empty`, the output would now be:</span></span>

```js
[{"":null,"prop2":null},null]
```

<span data-ttu-id="3d6e8-111">Это изменение поможет вызывающим объектам более согласованно реагировать на значения `null`.</span><span class="sxs-lookup"><span data-stu-id="3d6e8-111">This change was made to better align with caller expectations for `null` values.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3d6e8-112">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="3d6e8-112">Version introduced</span></span>

<span data-ttu-id="3d6e8-113">3.0 (предварительная версия 8)</span><span class="sxs-lookup"><span data-stu-id="3d6e8-113">3.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3d6e8-114">Рекомендуемое действие</span><span class="sxs-lookup"><span data-stu-id="3d6e8-114">Recommended action</span></span>

<span data-ttu-id="3d6e8-115">При записи имен и значений свойств с помощью класса <xref:System.Text.Json.Utf8JsonWriter>:</span><span class="sxs-lookup"><span data-stu-id="3d6e8-115">When writing property names and values with the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

- <span data-ttu-id="3d6e8-116">убедитесь, что строки без значений `null` используются в качестве имен свойств;</span><span class="sxs-lookup"><span data-stu-id="3d6e8-116">Ensure non-`null` strings are used as property names.</span></span>

- <span data-ttu-id="3d6e8-117">если нужно воспроизвести прежнее поведение, используйте вызов с объединением значений NULL, например `writer.WriteString(propertyName1 ?? "", propertyValue1)`;</span><span class="sxs-lookup"><span data-stu-id="3d6e8-117">If the previous behavior is desired, use a null coalescing invocation; for example, `writer.WriteString(propertyName1 ?? "", propertyValue1)`.</span></span>

- <span data-ttu-id="3d6e8-118">если нежелательно, чтобы выполнялась запись литерала `null` для строкового значения `null`, используйте вызов с объединением значений NULL, например `writer.WriteString(propertyName2, propertyValue2 ?? "")`.</span><span class="sxs-lookup"><span data-stu-id="3d6e8-118">If writing a `null` literal for a `null` string value is not desirable, use a null coalescing invocation; for example, `writer.WriteString(propertyName2, propertyValue2 ?? "")`.</span></span>

#### <a name="category"></a><span data-ttu-id="3d6e8-119">Категория</span><span class="sxs-lookup"><span data-stu-id="3d6e8-119">Category</span></span>

<span data-ttu-id="3d6e8-120">CoreFX</span><span class="sxs-lookup"><span data-stu-id="3d6e8-120">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3d6e8-121">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="3d6e8-121">Affected APIs</span></span>

- <xref:System.Text.Json.Utf8JsonWriter.WriteBase64String(System.String,System.ReadOnlySpan%7BSystem.Byte%7D)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteBoolean(System.String,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNull(System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Int32)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Int64)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.UInt32)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.UInt64)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Single)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Double)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Decimal)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteStartArray(System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteStartObject(System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.ReadOnlySpan%7BSystem.Byte%7D)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.ReadOnlySpan%7BSystem.Char%7D)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.Text.Json.JsonEncodedText)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.DateTime)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.DateTimeOffset)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.Guid)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue(System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WritePropertyName(System.String)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Text.Json.Utf8JsonWriter.WriteBase64String(System.String,System.ReadOnlySpan{System.Byte})`
- `M:System.Text.Json.Utf8JsonWriter.WriteBoolean(System.String,System.Boolean)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNull(System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Int32)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Int64)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.UInt32)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.UInt64)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Single)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Double)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Decimal)`
- `M:System.Text.Json.Utf8JsonWriter.WriteStartArray(System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WriteStartObject(System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.ReadOnlySpan{System.Byte})`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.ReadOnlySpan{System.Char})`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.Text.Json.JsonEncodedText)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.DateTime)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.DateTimeOffset)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.Guid)`
- `M:System.Text.Json.Utf8JsonWriter.WriteStringValue(System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WritePropertyName(System.String)`

-->
