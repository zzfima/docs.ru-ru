---
title: Как сериализовать и десериализовать JSON с C# помощью-.NET
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 8025f84f2425f5b91e08b28ddb24d105d8c4d1a3
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159589"
---
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a><span data-ttu-id="4298c-102">Сериализация и десериализация (маршалирование и распаковки) JSON в .NET</span><span class="sxs-lookup"><span data-stu-id="4298c-102">How to serialize and deserialize (marshal and unmarshal) JSON in .NET</span></span>

<span data-ttu-id="4298c-103">В этой статье показано, как использовать пространство имен <xref:System.Text.Json> для сериализации и десериализации в нотация объектов JavaScript (JSON) и обратно.</span><span class="sxs-lookup"><span data-stu-id="4298c-103">This article shows how to use the <xref:System.Text.Json> namespace to serialize and deserialize to and from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="4298c-104">В направлениях и образце кода библиотека используется напрямую, а не с помощью платформы, такой как [ASP.NET Core](/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="4298c-104">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

<span data-ttu-id="4298c-105">Большинство примеров кода сериализации задают <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType>, чтобы `true`ся для «удобного» печати JSON (с отступами и пробелами для удобочитаемости).</span><span class="sxs-lookup"><span data-stu-id="4298c-105">Most of the serialization sample code sets <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true` to "pretty-print" the JSON (with indentation and whitespace for human readability).</span></span> <span data-ttu-id="4298c-106">Для использования в рабочей среде для этого параметра обычно принимается значение по умолчанию `false`.</span><span class="sxs-lookup"><span data-stu-id="4298c-106">For production use, you would typically accept the default value of `false` for this setting.</span></span>

## <a name="namespaces"></a><span data-ttu-id="4298c-107">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="4298c-107">Namespaces</span></span>

<span data-ttu-id="4298c-108">Пространство имен <xref:System.Text.Json> содержит все точки входа и основные типы.</span><span class="sxs-lookup"><span data-stu-id="4298c-108">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="4298c-109">Пространство имен <xref:System.Text.Json.Serialization> содержит атрибуты и интерфейсы API для сложных сценариев и настройки, характерные для сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="4298c-109">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="4298c-110">В примерах кода, приведенных в этой статье, требуются директивы `using` для одного или обоих пространств имен:</span><span class="sxs-lookup"><span data-stu-id="4298c-110">The code examples shown in this article require `using` directives for one or both of these namespaces:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

<span data-ttu-id="4298c-111">Атрибуты из пространства имен <xref:System.Runtime.Serialization> в настоящее время не поддерживаются в `System.Text.Json`.</span><span class="sxs-lookup"><span data-stu-id="4298c-111">Attributes from the <xref:System.Runtime.Serialization> namespace aren't currently supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="4298c-112">Как записывать объекты .NET в JSON (сериализовать)</span><span class="sxs-lookup"><span data-stu-id="4298c-112">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="4298c-113">Чтобы записать JSON в строку или в файл, вызовите метод <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4298c-113">To write JSON to a string or to a file, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="4298c-114">В следующем примере показано создание JSON в виде строки:</span><span class="sxs-lookup"><span data-stu-id="4298c-114">The following example creates JSON as a string:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerialize)]

<span data-ttu-id="4298c-115">В следующем примере синхронный код используется для создания JSON-файла:</span><span class="sxs-lookup"><span data-stu-id="4298c-115">The following example uses synchronous code to create a JSON file:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetSerialize)]

<span data-ttu-id="4298c-116">В следующем примере асинхронный код используется для создания JSON-файла:</span><span class="sxs-lookup"><span data-stu-id="4298c-116">The following example uses asynchronous code to create a JSON file:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetSerialize)]

<span data-ttu-id="4298c-117">В предыдущих примерах для сериализуемого типа используется определение типа.</span><span class="sxs-lookup"><span data-stu-id="4298c-117">The preceding examples use type inference for the type being serialized.</span></span> <span data-ttu-id="4298c-118">Перегрузка `Serialize()` принимает параметр универсального типа:</span><span class="sxs-lookup"><span data-stu-id="4298c-118">An overload of `Serialize()` takes a generic type parameter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializeWithGenericParameter)]

### <a name="serialization-example"></a><span data-ttu-id="4298c-119">Пример сериализации</span><span class="sxs-lookup"><span data-stu-id="4298c-119">Serialization example</span></span>

<span data-ttu-id="4298c-120">Ниже приведен пример класса, который содержит коллекции и вложенный класс:</span><span class="sxs-lookup"><span data-stu-id="4298c-120">Here's an example class that contains collections and a nested class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPOCOs)]

<span data-ttu-id="4298c-121">Выходные данные JSON из сериализации экземпляра предыдущего типа выглядят так, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="4298c-121">The JSON output from serializing an instance of the preceding type looks like the following example.</span></span> <span data-ttu-id="4298c-122">Выходные данные JSON по умолчанию минифицированные:</span><span class="sxs-lookup"><span data-stu-id="4298c-122">The JSON output is minified by default:</span></span>

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="4298c-123">В следующем примере показан один и тот же формат JSON, форматированный (т. е. который печатается с пробелами и отступами):</span><span class="sxs-lookup"><span data-stu-id="4298c-123">The following example shows the same JSON, formatted (that is, pretty-printed with whitespace and indentation):</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "TemperatureRanges": {
    "Cold": {
      "High": 20,
      "Low": -10
    },
    "Hot": {
      "High": 60,
      "Low": 20
    }
  },
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

### <a name="serialize-to-utf-8"></a><span data-ttu-id="4298c-124">Сериализация в UTF-8</span><span class="sxs-lookup"><span data-stu-id="4298c-124">Serialize to UTF-8</span></span>

<span data-ttu-id="4298c-125">Чтобы выполнить сериализацию в UTF-8, вызовите метод <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="4298c-125">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetSerialize)]

<span data-ttu-id="4298c-126">Также доступна перегрузка <xref:System.Text.Json.JsonSerializer.Serialize%2A>, которая принимает <xref:System.Text.Json.Utf8JsonWriter>.</span><span class="sxs-lookup"><span data-stu-id="4298c-126">A <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is also available.</span></span>

<span data-ttu-id="4298c-127">Сериализация в UTF-8 происходит примерно на 5-10% быстрее, чем при использовании строковых методов.</span><span class="sxs-lookup"><span data-stu-id="4298c-127">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="4298c-128">Разница заключается в том, что байты (как UTF-8) не нужно преобразовывать в строки (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="4298c-128">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="4298c-129">Поведение сериализации</span><span class="sxs-lookup"><span data-stu-id="4298c-129">Serialization behavior</span></span>

* <span data-ttu-id="4298c-130">По умолчанию все открытые свойства сериализуются.</span><span class="sxs-lookup"><span data-stu-id="4298c-130">By default, all public properties are serialized.</span></span> <span data-ttu-id="4298c-131">Можно [указать свойства для исключения](#exclude-properties-from-serialization).</span><span class="sxs-lookup"><span data-stu-id="4298c-131">You can [specify properties to exclude](#exclude-properties-from-serialization).</span></span>
* <span data-ttu-id="4298c-132">[Кодировщик по умолчанию](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) выводит символы, не входящие в набор ASCII, символы, УЧИТЫВАЮЩИЕ формат ASCII, и символы, которые должны быть экранированы в соответствии со [спецификацией RFC 8259 JSON](https://tools.ietf.org/html/rfc8259#section-7).</span><span class="sxs-lookup"><span data-stu-id="4298c-132">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="4298c-133">По умолчанию JSON — минифицированные.</span><span class="sxs-lookup"><span data-stu-id="4298c-133">By default, JSON is minified.</span></span> <span data-ttu-id="4298c-134">JSON можно [довольно просто распечатать](#serialize-to-formatted-json).</span><span class="sxs-lookup"><span data-stu-id="4298c-134">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="4298c-135">По умолчанию регистр имен JSON соответствует именам .NET.</span><span class="sxs-lookup"><span data-stu-id="4298c-135">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="4298c-136">Можно [настроить регистр имен JSON](#customize-json-names-and-values).</span><span class="sxs-lookup"><span data-stu-id="4298c-136">You can [customize JSON name casing](#customize-json-names-and-values).</span></span>
* <span data-ttu-id="4298c-137">Обнаружены циклические ссылки и создаются исключения.</span><span class="sxs-lookup"><span data-stu-id="4298c-137">Circular references are detected and exceptions thrown.</span></span>
* <span data-ttu-id="4298c-138">В настоящее время поля исключаются.</span><span class="sxs-lookup"><span data-stu-id="4298c-138">Currently, fields are excluded.</span></span>

<span data-ttu-id="4298c-139">Поддерживаемые типы:</span><span class="sxs-lookup"><span data-stu-id="4298c-139">Supported types include:</span></span>

* <span data-ttu-id="4298c-140">Примитивы .NET, которые сопоставляются с примитивами JavaScript, например числовыми типами, строками и логическими значениями.</span><span class="sxs-lookup"><span data-stu-id="4298c-140">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="4298c-141">Определяемые пользователем [простые старые объекты CLR (POCO)](https://stackoverflow.com/questions/250001/poco-definition).</span><span class="sxs-lookup"><span data-stu-id="4298c-141">User-defined [Plain Old CLR Objects (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).</span></span>
* <span data-ttu-id="4298c-142">Одномерное и зубчатые массивы (`ArrayName[][]`).</span><span class="sxs-lookup"><span data-stu-id="4298c-142">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="4298c-143">`Dictionary<string,TValue>`, где `TValue` — `object`, `JsonElement`или POCO.</span><span class="sxs-lookup"><span data-stu-id="4298c-143">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="4298c-144">Коллекции из следующих пространств имен.</span><span class="sxs-lookup"><span data-stu-id="4298c-144">Collections from the following namespaces.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

<span data-ttu-id="4298c-145">Можно [реализовать пользовательские преобразователи](system-text-json-converters-how-to.md) для обработки дополнительных типов или для предоставления функциональных возможностей, которые не поддерживаются встроенными преобразователями.</span><span class="sxs-lookup"><span data-stu-id="4298c-145">You can [implement custom converters](system-text-json-converters-how-to.md) to handle additional types or to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="4298c-146">Чтение JSON в объектах .NET (десериализация)</span><span class="sxs-lookup"><span data-stu-id="4298c-146">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="4298c-147">Чтобы выполнить десериализацию из строки или файла, вызовите метод <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4298c-147">To deserialize from a string or a file, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="4298c-148">В следующем примере показано чтение JSON из строки и создание экземпляра класса `WeatherForecast`, показанного ранее для [примера сериализации](#serialization-example):</span><span class="sxs-lookup"><span data-stu-id="4298c-148">The following example reads JSON from a string and creates an instance of the `WeatherForecast` class shown earlier for the [serialization example](#serialization-example):</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetDeserialize)]

<span data-ttu-id="4298c-149">Чтобы выполнить десериализацию из файла с помощью синхронного кода, считайте файл в строку, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="4298c-149">To deserialize from a file by using synchronous code, read the file into a string, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetDeserialize)]

<span data-ttu-id="4298c-150">Чтобы выполнить десериализацию из файла с помощью асинхронного кода, вызовите метод <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A>:</span><span class="sxs-lookup"><span data-stu-id="4298c-150">To deserialize from a file by using asynchronous code, call the <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> method:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetDeserialize)]

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="4298c-151">Десериализация из UTF-8</span><span class="sxs-lookup"><span data-stu-id="4298c-151">Deserialize from UTF-8</span></span>

<span data-ttu-id="4298c-152">Для десериализации из UTF-8 вызовите перегрузку <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>, которая принимает `Utf8JsonReader` или `ReadOnlySpan<byte>`, как показано в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="4298c-152">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples.</span></span> <span data-ttu-id="4298c-153">В примерах предполагается, что JSON находится в массиве байтов с именем jsonUtf8Bytes.</span><span class="sxs-lookup"><span data-stu-id="4298c-153">The examples assume the JSON is in a byte array named jsonUtf8Bytes.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize1)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize2)]

## <a name="deserialization-behavior"></a><span data-ttu-id="4298c-154">Поведение десериализации</span><span class="sxs-lookup"><span data-stu-id="4298c-154">Deserialization behavior</span></span>

* <span data-ttu-id="4298c-155">По умолчанию при сопоставлении имен свойств учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="4298c-155">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="4298c-156">Можно [указать нечувствительность к регистру](#case-insensitive-property-matching).</span><span class="sxs-lookup"><span data-stu-id="4298c-156">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="4298c-157">Если JSON содержит значение для свойства, доступного только для чтения, значение игнорируется и исключение не создается.</span><span class="sxs-lookup"><span data-stu-id="4298c-157">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="4298c-158">Десериализация в ссылочные типы без конструктора, не имеющего параметров, не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="4298c-158">Deserialization to reference types without a parameterless constructor isn't supported.</span></span>
* <span data-ttu-id="4298c-159">Десериализация в неизменяемые объекты или свойства только для чтения не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="4298c-159">Deserialization to immutable objects or read-only properties isn't supported.</span></span>
* <span data-ttu-id="4298c-160">По умолчанию перечисления поддерживаются в виде чисел.</span><span class="sxs-lookup"><span data-stu-id="4298c-160">By default, enums are supported as numbers.</span></span> <span data-ttu-id="4298c-161">[Имена перечислений можно сериализовать как строки](#enums-as-strings).</span><span class="sxs-lookup"><span data-stu-id="4298c-161">You can [serialize enum names as strings](#enums-as-strings).</span></span>
* <span data-ttu-id="4298c-162">Поля не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="4298c-162">Fields aren't supported.</span></span>
* <span data-ttu-id="4298c-163">По умолчанию комментарии или замыкающие запятые в JSON вызывают исключения.</span><span class="sxs-lookup"><span data-stu-id="4298c-163">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="4298c-164">Можно [Разрешить комментарии и завершающие запятые](#allow-comments-and-trailing-commas).</span><span class="sxs-lookup"><span data-stu-id="4298c-164">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas).</span></span>
* <span data-ttu-id="4298c-165">[Максимальная глубина по умолчанию](xref:System.Text.Json.JsonReaderOptions.MaxDepth) — 64.</span><span class="sxs-lookup"><span data-stu-id="4298c-165">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="4298c-166">Вы можете [реализовать пользовательские преобразователи](system-text-json-converters-how-to.md) для предоставления функциональных возможностей, которые не поддерживаются встроенными преобразователями.</span><span class="sxs-lookup"><span data-stu-id="4298c-166">You can [implement custom converters](system-text-json-converters-how-to.md) to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="4298c-167">Сериализовать в форматированный JSON</span><span class="sxs-lookup"><span data-stu-id="4298c-167">Serialize to formatted JSON</span></span>

<span data-ttu-id="4298c-168">Чтобы довольно просто распечатать выходные данные JSON, задайте для <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="4298c-168">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializePrettyPrint)]

<span data-ttu-id="4298c-169">Ниже приведен пример типа для сериализации и печати выходных данных JSON:</span><span class="sxs-lookup"><span data-stu-id="4298c-169">Here's an example type to be serialized and pretty-printed JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="customize-json-names-and-values"></a><span data-ttu-id="4298c-170">Настройка имен и значений JSON</span><span class="sxs-lookup"><span data-stu-id="4298c-170">Customize JSON names and values</span></span>

<span data-ttu-id="4298c-171">По умолчанию имена и ключи словарей не изменяются в выходных данных JSON, включая регистр.</span><span class="sxs-lookup"><span data-stu-id="4298c-171">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="4298c-172">Значения перечисления представлены в виде чисел.</span><span class="sxs-lookup"><span data-stu-id="4298c-172">Enum values are represented as numbers.</span></span> <span data-ttu-id="4298c-173">В этом разделе объясняется, как выполнить такие задачи:</span><span class="sxs-lookup"><span data-stu-id="4298c-173">This section explains how to:</span></span>

* [<span data-ttu-id="4298c-174">Настройка отдельных имен свойств</span><span class="sxs-lookup"><span data-stu-id="4298c-174">Customize individual property names</span></span>](#customize-individual-property-names)
* [<span data-ttu-id="4298c-175">Преобразовать все имена свойств в неоднородный регистр</span><span class="sxs-lookup"><span data-stu-id="4298c-175">Convert all property names to camel case</span></span>](#use-camel-case-for-all-json-property-names)
* [<span data-ttu-id="4298c-176">Реализация политики именования пользовательских свойств</span><span class="sxs-lookup"><span data-stu-id="4298c-176">Implement a custom property naming policy</span></span>](#use-a-custom-json-property-naming-policy)
* [<span data-ttu-id="4298c-177">Преобразовать ключи словаря в стиль Camel</span><span class="sxs-lookup"><span data-stu-id="4298c-177">Convert dictionary keys to camel case</span></span>](#camel-case-dictionary-keys)
* [<span data-ttu-id="4298c-178">Преобразование перечислений в строки и Camel</span><span class="sxs-lookup"><span data-stu-id="4298c-178">Convert enums to strings and camel case</span></span>](#enums-as-strings)

<span data-ttu-id="4298c-179">Для других сценариев, требующих специальной обработки имен и значений свойств JSON, можно [реализовать пользовательские преобразователи](system-text-json-converters-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="4298c-179">For other scenarios that require special handling of JSON property names and values, you can [implement custom converters](system-text-json-converters-how-to.md).</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="4298c-180">Настройка отдельных имен свойств</span><span class="sxs-lookup"><span data-stu-id="4298c-180">Customize individual property names</span></span>

<span data-ttu-id="4298c-181">Чтобы задать имя отдельных свойств, используйте атрибут [[жсонпропертинаме]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) .</span><span class="sxs-lookup"><span data-stu-id="4298c-181">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="4298c-182">Ниже приведен пример типа для сериализации и результирующего JSON:</span><span class="sxs-lookup"><span data-stu-id="4298c-182">Here's an example type to serialize and resulting JSON:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="4298c-183">Имя свойства, заданное этим атрибутом:</span><span class="sxs-lookup"><span data-stu-id="4298c-183">The property name set by this attribute:</span></span>

* <span data-ttu-id="4298c-184">Применяется в обоих направлениях для сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="4298c-184">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="4298c-185">Имеет приоритет над политиками именования свойств.</span><span class="sxs-lookup"><span data-stu-id="4298c-185">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="4298c-186">Использовать прописные буквы для всех имен свойств JSON</span><span class="sxs-lookup"><span data-stu-id="4298c-186">Use camel case for all JSON property names</span></span>

<span data-ttu-id="4298c-187">Чтобы использовать прописные буквы для всех имен свойств JSON, задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> значение `JsonNamingPolicy.CamelCase`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="4298c-187">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundTripCamelCasePropertyNames.cs?name=Serialize)]

<span data-ttu-id="4298c-188">Ниже приведен пример класса для сериализации и вывода JSON.</span><span class="sxs-lookup"><span data-stu-id="4298c-188">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="4298c-189">Политика именования свойств case:</span><span class="sxs-lookup"><span data-stu-id="4298c-189">The camel case property naming policy:</span></span>

* <span data-ttu-id="4298c-190">Применяется к сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="4298c-190">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="4298c-191">Переопределяется атрибутами `[JsonPropertyName]`.</span><span class="sxs-lookup"><span data-stu-id="4298c-191">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="4298c-192">Именно поэтому имя свойства JSON, `Wind` в примере, не является ни прописным.</span><span class="sxs-lookup"><span data-stu-id="4298c-192">This is why the JSON property name `Wind` in the example is not camel case.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="4298c-193">Использование настраиваемой политики именования свойств JSON</span><span class="sxs-lookup"><span data-stu-id="4298c-193">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="4298c-194">Чтобы использовать пользовательскую политику именования свойств JSON, создайте класс, производный от <xref:System.Text.Json.JsonNamingPolicy>, и переопределите метод <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A>, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="4298c-194">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/UpperCaseNamingPolicy.cs)]

<span data-ttu-id="4298c-195">Затем задайте для свойства <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> экземпляр класса политики именования:</span><span class="sxs-lookup"><span data-stu-id="4298c-195">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripPropertyNamingPolicy.cs?name=SnippetSerialize)]

<span data-ttu-id="4298c-196">Ниже приведен пример класса для сериализации и вывода JSON.</span><span class="sxs-lookup"><span data-stu-id="4298c-196">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="4298c-197">Политика именования свойств JSON:</span><span class="sxs-lookup"><span data-stu-id="4298c-197">The JSON property naming policy:</span></span>

* <span data-ttu-id="4298c-198">Применяется к сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="4298c-198">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="4298c-199">Переопределяется атрибутами `[JsonPropertyName]`.</span><span class="sxs-lookup"><span data-stu-id="4298c-199">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="4298c-200">Именно поэтому имя свойства JSON `Wind` в примере — не верхний регистр.</span><span class="sxs-lookup"><span data-stu-id="4298c-200">This is why the JSON property name `Wind` in the example is not upper case.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="4298c-201">Ключи словаря символов в стиле Camel</span><span class="sxs-lookup"><span data-stu-id="4298c-201">Camel case dictionary keys</span></span>

<span data-ttu-id="4298c-202">Если свойство сериализуемого объекта имеет тип `Dictionary<string,TValue>`, `string` ключи можно преобразовать в стиль Camel.</span><span class="sxs-lookup"><span data-stu-id="4298c-202">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="4298c-203">Для этого задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> значение `JsonNamingPolicy.CamelCase`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="4298c-203">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCamelCaseDictionaryKeys.cs?name=SnippetSerialize)]

<span data-ttu-id="4298c-204">Сериализация объекта с помощью словаря с именем `TemperatureRanges`, имеющего пары "ключ-значение" `"ColdMinTemp", 20` и `"HotMinTemp", 40` привести к выходным данным JSON, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="4298c-204">Serializing an object with a dictionary named `TemperatureRanges` that has key-value pairs `"ColdMinTemp", 20` and `"HotMinTemp", 40` would result in JSON output like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "coldMinTemp": 20,
    "hotMinTemp": 40
  }
}
```

<span data-ttu-id="4298c-205">Политика именования Camel для ключей словаря применяется только к сериализации.</span><span class="sxs-lookup"><span data-stu-id="4298c-205">The camel case naming policy for dictionary keys applies to serialization only.</span></span> <span data-ttu-id="4298c-206">При десериализации словаря ключи будут соответствовать JSON-файлу, даже если для `DictionaryKeyPolicy`указан параметр `JsonNamingPolicy.CamelCase`.</span><span class="sxs-lookup"><span data-stu-id="4298c-206">If you deserialize a dictionary, the keys will match the JSON file even if you specify `JsonNamingPolicy.CamelCase` for the `DictionaryKeyPolicy`.</span></span>

### <a name="enums-as-strings"></a><span data-ttu-id="4298c-207">Перечисление как строки</span><span class="sxs-lookup"><span data-stu-id="4298c-207">Enums as strings</span></span>

<span data-ttu-id="4298c-208">По умолчанию перечисления сериализуются как числа.</span><span class="sxs-lookup"><span data-stu-id="4298c-208">By default, enums are serialized as numbers.</span></span> <span data-ttu-id="4298c-209">Чтобы сериализовать имена перечислений как строки, используйте <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span><span class="sxs-lookup"><span data-stu-id="4298c-209">To serialize enum names as strings, use the <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span></span>

<span data-ttu-id="4298c-210">Например, предположим, что необходимо сериализовать следующий класс, имеющий перечисление:</span><span class="sxs-lookup"><span data-stu-id="4298c-210">For example, suppose you need to serialize the following class that has an enum:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithEnum)]

<span data-ttu-id="4298c-211">Если сводка имеет `Hot`, по умолчанию сериализованный JSON имеет числовое значение 3:</span><span class="sxs-lookup"><span data-stu-id="4298c-211">If the Summary is `Hot`, by default the serialized JSON has the numeric value 3:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

<span data-ttu-id="4298c-212">Следующий пример кода сериализует имена перечислений вместо числовых значений и преобразует имена в Camel:</span><span class="sxs-lookup"><span data-stu-id="4298c-212">The following sample code serializes the enum names instead of the numeric values, and converts the names to camel case:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetSerialize)]

<span data-ttu-id="4298c-213">Итоговый код JSON выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4298c-213">The resulting JSON looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

<span data-ttu-id="4298c-214">Имена строк перечисления можно также десериализовать, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="4298c-214">Enum string names can be deserialized as well, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetDeserialize)]

## <a name="exclude-properties-from-serialization"></a><span data-ttu-id="4298c-215">Исключить свойства из сериализации</span><span class="sxs-lookup"><span data-stu-id="4298c-215">Exclude properties from serialization</span></span>

<span data-ttu-id="4298c-216">По умолчанию все открытые свойства сериализуются.</span><span class="sxs-lookup"><span data-stu-id="4298c-216">By default, all public properties are serialized.</span></span> <span data-ttu-id="4298c-217">Если вы не хотите, чтобы некоторые из них отображались в выходных данных JSON, у вас есть несколько вариантов.</span><span class="sxs-lookup"><span data-stu-id="4298c-217">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="4298c-218">В этом разделе объясняется, как исключить:</span><span class="sxs-lookup"><span data-stu-id="4298c-218">This section explains how to exclude:</span></span>

* [<span data-ttu-id="4298c-219">Отдельные свойства</span><span class="sxs-lookup"><span data-stu-id="4298c-219">Individual properties</span></span>](#exclude-individual-properties)
* [<span data-ttu-id="4298c-220">Все свойства только для чтения</span><span class="sxs-lookup"><span data-stu-id="4298c-220">All read-only properties</span></span>](#exclude-all-read-only-properties)
* [<span data-ttu-id="4298c-221">Все свойства значений NULL</span><span class="sxs-lookup"><span data-stu-id="4298c-221">All null-value properties</span></span>](#exclude-all-null-value-properties)

### <a name="exclude-individual-properties"></a><span data-ttu-id="4298c-222">Исключить отдельные свойства</span><span class="sxs-lookup"><span data-stu-id="4298c-222">Exclude individual properties</span></span>

<span data-ttu-id="4298c-223">Чтобы игнорировать отдельные свойства, используйте атрибут [[жсонигноре]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) .</span><span class="sxs-lookup"><span data-stu-id="4298c-223">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="4298c-224">Ниже приведен пример типа для сериализации и вывода JSON.</span><span class="sxs-lookup"><span data-stu-id="4298c-224">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithIgnoreAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

### <a name="exclude-all-read-only-properties"></a><span data-ttu-id="4298c-225">Исключить все свойства только для чтения</span><span class="sxs-lookup"><span data-stu-id="4298c-225">Exclude all read-only properties</span></span>

<span data-ttu-id="4298c-226">Свойство доступно только для чтения, если оно содержит открытый метод получения, но не является открытым методом задания.</span><span class="sxs-lookup"><span data-stu-id="4298c-226">A property is read-only if it contains a public getter but not a public setter.</span></span> <span data-ttu-id="4298c-227">Чтобы исключить все свойства только для чтения, задайте для <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> значение `true`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="4298c-227">To exclude all read-only properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeExcludeReadOnlyProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="4298c-228">Ниже приведен пример типа для сериализации и вывода JSON.</span><span class="sxs-lookup"><span data-stu-id="4298c-228">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithROProperty)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="4298c-229">Этот параметр применяется только к сериализации.</span><span class="sxs-lookup"><span data-stu-id="4298c-229">This option applies only to serialization.</span></span> <span data-ttu-id="4298c-230">Во время десериализации свойства, доступные только для чтения, по умолчанию игнорируются.</span><span class="sxs-lookup"><span data-stu-id="4298c-230">During deserialization, read-only properties are ignored by default.</span></span>

### <a name="exclude-all-null-value-properties"></a><span data-ttu-id="4298c-231">Исключить все свойства значений NULL</span><span class="sxs-lookup"><span data-stu-id="4298c-231">Exclude all null value properties</span></span>

<span data-ttu-id="4298c-232">Чтобы исключить все свойства значений NULL, задайте для свойства <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> значение `true`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="4298c-232">To exclude all null value properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeExcludeNullValueProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="4298c-233">Ниже приведен пример объекта для сериализации и вывода JSON.</span><span class="sxs-lookup"><span data-stu-id="4298c-233">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="4298c-234">Свойство</span><span class="sxs-lookup"><span data-stu-id="4298c-234">Property</span></span> |<span data-ttu-id="4298c-235">Значение</span><span class="sxs-lookup"><span data-stu-id="4298c-235">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="4298c-236">Дата</span><span class="sxs-lookup"><span data-stu-id="4298c-236">Date</span></span>    | <span data-ttu-id="4298c-237">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="4298c-237">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="4298c-238">температурецелсиус</span><span class="sxs-lookup"><span data-stu-id="4298c-238">TemperatureCelsius</span></span>| <span data-ttu-id="4298c-239">25</span><span class="sxs-lookup"><span data-stu-id="4298c-239">25</span></span> |
| <span data-ttu-id="4298c-240">Сводка</span><span class="sxs-lookup"><span data-stu-id="4298c-240">Summary</span></span>| <span data-ttu-id="4298c-241">null</span><span class="sxs-lookup"><span data-stu-id="4298c-241">null</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

<span data-ttu-id="4298c-242">Этот параметр применяется к сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="4298c-242">This setting applies to serialization and deserialization.</span></span> <span data-ttu-id="4298c-243">Сведения о том, как это влияет на десериализацию, см. в разделе [игнорирование значения NULL при десериализации](#ignore-null-when-deserializing).</span><span class="sxs-lookup"><span data-stu-id="4298c-243">For information about its effect on deserialization, see [Ignore null when deserializing](#ignore-null-when-deserializing).</span></span>

## <a name="customize-character-encoding"></a><span data-ttu-id="4298c-244">Настройка кодировки символов</span><span class="sxs-lookup"><span data-stu-id="4298c-244">Customize character encoding</span></span>

<span data-ttu-id="4298c-245">По умолчанию сериализатор выполняет escape-последовательность символов, отличных от ASCII.</span><span class="sxs-lookup"><span data-stu-id="4298c-245">By default, the serializer escapes all non-ASCII characters.</span></span>  <span data-ttu-id="4298c-246">То есть он заменяет их `\uxxxx`, где `xxxx` является кодом Юникода символа.</span><span class="sxs-lookup"><span data-stu-id="4298c-246">That is, it replaces them with `\uxxxx` where `xxxx` is the Unicode code of the character.</span></span>  <span data-ttu-id="4298c-247">Например, если для свойства `Summary` задано значение кириллицы жарко, `WeatherForecast` объект сериализуется, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="4298c-247">For example, if the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a><span data-ttu-id="4298c-248">Сериализация наборов символов языка</span><span class="sxs-lookup"><span data-stu-id="4298c-248">Serialize language character sets</span></span>

<span data-ttu-id="4298c-249">Чтобы сериализовать наборы символов одного или нескольких языков без экранирования, укажите [Диапазоны Юникода](xref:System.Text.Unicode.UnicodeRanges) при создании экземпляра <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="4298c-249">To serialize the character set(s) of one or more languages without escaping, specify [Unicode range(s)](xref:System.Text.Unicode.UnicodeRanges) when creating an instance of <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetLanguageSets)]

<span data-ttu-id="4298c-250">Этот код не поддерживает символы кириллицы или греческого языка.</span><span class="sxs-lookup"><span data-stu-id="4298c-250">This code doesn't escape Cyrillic or Greek characters.</span></span> <span data-ttu-id="4298c-251">Если свойство `Summary` имеет значение кириллицы жарко, то `WeatherForecast` объект сериализуется, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="4298c-251">If the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

<span data-ttu-id="4298c-252">Чтобы сериализовать все языковые наборы без экранирования, используйте <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4298c-252">To serialize all language sets without escaping, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span></span>

### <a name="serialize-specific-characters"></a><span data-ttu-id="4298c-253">Сериализация конкретных символов</span><span class="sxs-lookup"><span data-stu-id="4298c-253">Serialize specific characters</span></span>

<span data-ttu-id="4298c-254">Альтернативой является указание отдельных символов, которые нужно разрешить, без экранирования.</span><span class="sxs-lookup"><span data-stu-id="4298c-254">An alternative is to specify individual characters that you want to allow through without being escaped.</span></span> <span data-ttu-id="4298c-255">В следующем примере сериализуются только первые два символа жарко:</span><span class="sxs-lookup"><span data-stu-id="4298c-255">The following example serializes only the first two characters of жарко:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetSelectedCharacters)]

<span data-ttu-id="4298c-256">Ниже приведен пример JSON, созданный с помощью приведенного выше кода.</span><span class="sxs-lookup"><span data-stu-id="4298c-256">Here's an example of JSON produced by the preceding code:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a><span data-ttu-id="4298c-257">Сериализовать все символы</span><span class="sxs-lookup"><span data-stu-id="4298c-257">Serialize all characters</span></span>

<span data-ttu-id="4298c-258">Чтобы избежать экранирования, можно использовать <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="4298c-258">To minimize escaping you can use <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUnsafeRelaxed)]

> [!CAUTION]
> <span data-ttu-id="4298c-259">По сравнению с кодировщиком по умолчанию `UnsafeRelaxedJsonEscaping` кодировщик является более строгим, что позволяет передавать символы без экранирования:</span><span class="sxs-lookup"><span data-stu-id="4298c-259">Compared to the default encoder, the `UnsafeRelaxedJsonEscaping` encoder is more permissive about allowing characters to pass through unescaped:</span></span>
>
> * <span data-ttu-id="4298c-260">Он не выполняет escape-символы с учетом HTML, например `<`, `>`, `&`и `'`.</span><span class="sxs-lookup"><span data-stu-id="4298c-260">It doesn't escape HTML-sensitive characters such as `<`, `>`, `&`, and `'`.</span></span>
> * <span data-ttu-id="4298c-261">Она не предоставляет никаких дополнительных средств защиты от атак с помощью XSS или раскрытия информации, например, которые могут возникать из-за того, что клиент и сервер не согласны с набором *символов*.</span><span class="sxs-lookup"><span data-stu-id="4298c-261">It doesn't offer any additional defense-in-depth protections against XSS or information disclosure attacks, such as those which might result from the client and server disagreeing on the *charset*.</span></span>
>
> <span data-ttu-id="4298c-262">Используйте ненадежный кодировщик, только если известно, что клиент будет интерпретировать полученные полезные данные как JSON в кодировке UTF-8.</span><span class="sxs-lookup"><span data-stu-id="4298c-262">Use the unsafe encoder only when it's known that the client will be interpreting the resulting payload as UTF-8 encoded JSON.</span></span> <span data-ttu-id="4298c-263">Например, его можно использовать, если сервер отправляет заголовок ответа `Content-Type: application/json; charset=utf-8`.</span><span class="sxs-lookup"><span data-stu-id="4298c-263">For example, you can use it if the server is sending the response header `Content-Type: application/json; charset=utf-8`.</span></span> <span data-ttu-id="4298c-264">Никогда не разрешайте вывод необработанных `UnsafeRelaxedJsonEscaping` в HTML-страницу или элемент `<script>`.</span><span class="sxs-lookup"><span data-stu-id="4298c-264">Never allow the raw `UnsafeRelaxedJsonEscaping` output to be emitted into an HTML page or a `<script>` element.</span></span>

## <a name="serialize-properties-of-derived-classes"></a><span data-ttu-id="4298c-265">Сериализация свойств производных классов</span><span class="sxs-lookup"><span data-stu-id="4298c-265">Serialize properties of derived classes</span></span>

<span data-ttu-id="4298c-266">Сериализация иерархии полиморфизма типа не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="4298c-266">Serialization of a polymorphic type hierarchy is not supported.</span></span> <span data-ttu-id="4298c-267">Например, если свойство определено как интерфейс или абстрактный класс, сериализуются только свойства, определенные в интерфейсе или абстрактном классе, даже если тип среды выполнения имеет дополнительные свойства.</span><span class="sxs-lookup"><span data-stu-id="4298c-267">For example, if a property is defined as an interface or an abstract class, only the properties defined on the interface or abstract class are serialized, even if the runtime type has additional properties.</span></span> <span data-ttu-id="4298c-268">Исключения из этого поведения описаны в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="4298c-268">The exceptions to this behavior are explained in this section.</span></span>

<span data-ttu-id="4298c-269">Например, предположим, что у вас есть класс `WeatherForecast` и производный класс `WeatherForecastDerived`:</span><span class="sxs-lookup"><span data-stu-id="4298c-269">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastDerived`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFDerived)]

<span data-ttu-id="4298c-270">И предположим, что аргумент типа метода `Serialize` во время компиляции `WeatherForecast`:</span><span class="sxs-lookup"><span data-stu-id="4298c-270">And suppose the type argument of the `Serialize` method at compile time is `WeatherForecast`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeDefault)]

<span data-ttu-id="4298c-271">В этом сценарии свойство `WindSpeed` не сериализуется, даже если объект `weatherForecast` фактически является `WeatherForecastDerived`ным объектом.</span><span class="sxs-lookup"><span data-stu-id="4298c-271">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastDerived` object.</span></span> <span data-ttu-id="4298c-272">Сериализуются только свойства базового класса:</span><span class="sxs-lookup"><span data-stu-id="4298c-272">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="4298c-273">Это поведение предназначено для предотвращения случайного раскрытия данных в производном от среды CLR типе.</span><span class="sxs-lookup"><span data-stu-id="4298c-273">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="4298c-274">Чтобы сериализовать свойства производного типа в предыдущем примере, используйте один из следующих подходов:</span><span class="sxs-lookup"><span data-stu-id="4298c-274">To serialize the properties of the derived type in the preceding example, use one of the following approaches:</span></span>

* <span data-ttu-id="4298c-275">Вызовите перегрузку <xref:System.Text.Json.JsonSerializer.Serialize%2A>, которая позволяет указать тип во время выполнения:</span><span class="sxs-lookup"><span data-stu-id="4298c-275">Call an overload of <xref:System.Text.Json.JsonSerializer.Serialize%2A> that lets you specify the type at runtime:</span></span>

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeGetType)]

* <span data-ttu-id="4298c-276">Объявите объект, который должен быть сериализован как `object`.</span><span class="sxs-lookup"><span data-stu-id="4298c-276">Declare the object to be serialized as `object`.</span></span>

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeObject)]

<span data-ttu-id="4298c-277">В предыдущем примере сценария оба подхода приводят к тому, что `WindSpeed` свойство включается в выходные данные JSON:</span><span class="sxs-lookup"><span data-stu-id="4298c-277">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "WindSpeed": 35,
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

> [!IMPORTANT]
> <span data-ttu-id="4298c-278">Эти подходы обеспечивают одноэлементную сериализацию только для сериализации корневого объекта, а не для свойств этого корневого объекта.</span><span class="sxs-lookup"><span data-stu-id="4298c-278">These approaches provide polymorphic serialization only for the root object to be serialized, not for properties of that root object.</span></span>

<span data-ttu-id="4298c-279">Можно получить полиморфизм сериализации для объектов более низкого уровня, если они определены как тип `object`.</span><span class="sxs-lookup"><span data-stu-id="4298c-279">You can get polymorphic serialization for lower-level objects if you define them as type `object`.</span></span> <span data-ttu-id="4298c-280">Например, предположим, что у класса `WeatherForecast` есть свойство с именем `PreviousForecast`, которое может быть определено как тип `WeatherForecast` или `object`:</span><span class="sxs-lookup"><span data-stu-id="4298c-280">For example, suppose your `WeatherForecast` class has a property named `PreviousForecast` that can be defined as type `WeatherForecast` or `object`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPrevious)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPreviousAsObject)]

<span data-ttu-id="4298c-281">Если свойство `PreviousForecast` содержит экземпляр `WeatherForecastDerived`:</span><span class="sxs-lookup"><span data-stu-id="4298c-281">If the `PreviousForecast` property contains an instance of `WeatherForecastDerived`:</span></span>

* <span data-ttu-id="4298c-282">Выходные данные JSON из сериализации `WeatherForecastWithPrevious` **не включают** `WindSpeed`.</span><span class="sxs-lookup"><span data-stu-id="4298c-282">The JSON output from serializing `WeatherForecastWithPrevious` **doesn't include** `WindSpeed`.</span></span>
* <span data-ttu-id="4298c-283">Выходные данные JSON из сериализации `WeatherForecastWithPreviousAsObject` **включают** `WindSpeed`.</span><span class="sxs-lookup"><span data-stu-id="4298c-283">The JSON output from serializing `WeatherForecastWithPreviousAsObject` **includes** `WindSpeed`.</span></span>

<span data-ttu-id="4298c-284">Для сериализации `WeatherForecastWithPreviousAsObject`не нужно вызывать метод `Serialize<object>` или `GetType`, так как корневой объект не является производным от него.</span><span class="sxs-lookup"><span data-stu-id="4298c-284">To serialize `WeatherForecastWithPreviousAsObject`, it isn't necessary to call `Serialize<object>` or `GetType` because the root object isn't the one that may be of a derived type.</span></span> <span data-ttu-id="4298c-285">В следующем примере кода не вызывается `Serialize<object>` или `GetType`:</span><span class="sxs-lookup"><span data-stu-id="4298c-285">The following code example doesn't call `Serialize<object>` or `GetType`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeSecondLevel)]

<span data-ttu-id="4298c-286">Приведенный выше код правильно сериализует `WeatherForecastWithPreviousAsObject`:</span><span class="sxs-lookup"><span data-stu-id="4298c-286">The preceding code correctly serializes `WeatherForecastWithPreviousAsObject`:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "PreviousForecast": {
    "WindSpeed": 35,
    "Date": "2019-08-01T00:00:00-07:00",
    "TemperatureCelsius": 25,
    "Summary": "Hot"
  }
}
```

<span data-ttu-id="4298c-287">Тот же подход к определению свойств `object` работает с интерфейсами.</span><span class="sxs-lookup"><span data-stu-id="4298c-287">The same approach of defining properties as `object` works with interfaces.</span></span> <span data-ttu-id="4298c-288">Предположим, что у вас есть следующий интерфейс и реализация, и вы хотите сериализовать класс со свойствами, которые содержат экземпляры реализации:</span><span class="sxs-lookup"><span data-stu-id="4298c-288">Suppose you have the following interface and implementation, and you want to serialize a class with properties that contain implementation instances:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/IForecast.cs)]

<span data-ttu-id="4298c-289">При сериализации экземпляра `Forecasts`только `Tuesday` отображает свойство `WindSpeed`, так как `Tuesday` определяется как `object`.</span><span class="sxs-lookup"><span data-stu-id="4298c-289">When you serialize an instance of `Forecasts`, only `Tuesday` shows the `WindSpeed` property, because `Tuesday` is defined as `object`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeInterface)]

<span data-ttu-id="4298c-290">В следующем примере показан код JSON, полученный в результате предыдущего кода:</span><span class="sxs-lookup"><span data-stu-id="4298c-290">The following example shows the JSON that results from the preceding code:</span></span>

```json
{
  "Monday": {
    "Date": "2020-01-06T00:00:00-08:00",
    "TemperatureCelsius": 10,
    "Summary": "Cool"
  },
  "Tuesday": {
    "Date": "2020-01-07T00:00:00-08:00",
    "TemperatureCelsius": 11,
    "Summary": "Rainy",
    "WindSpeed": 10
  }
}
```

<span data-ttu-id="4298c-291">Дополнительные сведения о полиморфизме **сериализации**и сведения о **десериализации**см. в разделе [Миграция из Newtonsoft. JSON в System. Text. JSON](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).</span><span class="sxs-lookup"><span data-stu-id="4298c-291">For more information about polymorphic **serialization**, and for information about **deserialization**, see [How to migrate from Newtonsoft.Json to System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).</span></span>

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="4298c-292">Разрешить комментарии и завершающие запятые</span><span class="sxs-lookup"><span data-stu-id="4298c-292">Allow comments and trailing commas</span></span>

<span data-ttu-id="4298c-293">По умолчанию в JSON не допускаются комментарии и конечные запятые.</span><span class="sxs-lookup"><span data-stu-id="4298c-293">By default, comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="4298c-294">Чтобы разрешить комментарии в JSON, задайте для свойства <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> значение `JsonCommentHandling.Skip`.</span><span class="sxs-lookup"><span data-stu-id="4298c-294">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span>
<span data-ttu-id="4298c-295">Чтобы разрешить замыкающие запятые, задайте для свойства <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="4298c-295">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="4298c-296">В следующем примере показано, как разрешить оба:</span><span class="sxs-lookup"><span data-stu-id="4298c-296">The following example shows how to allow both:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCommasComments.cs?name=SnippetDeserialize)]

<span data-ttu-id="4298c-297">Вот пример JSON с комментариями и завершающей запятой:</span><span class="sxs-lookup"><span data-stu-id="4298c-297">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="4298c-298">Сопоставление свойств без учета регистра</span><span class="sxs-lookup"><span data-stu-id="4298c-298">Case-insensitive property matching</span></span>

<span data-ttu-id="4298c-299">По умолчанию десериализация выполняет поиск совпадения имен свойств с учетом регистра между JSON и свойствами целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="4298c-299">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="4298c-300">Чтобы изменить это поведение, задайте для <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="4298c-300">To change that behavior, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCaseInsensitive.cs?name=SnippetDeserialize)]

<span data-ttu-id="4298c-301">Ниже приведен пример JSON с именами свойств «Case Camel».</span><span class="sxs-lookup"><span data-stu-id="4298c-301">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="4298c-302">Его можно десериализовать в следующий тип, который содержит имена свойств case в стиле Pascal.</span><span class="sxs-lookup"><span data-stu-id="4298c-302">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="handle-overflow-json"></a><span data-ttu-id="4298c-303">Маркер переполнения токена JSON</span><span class="sxs-lookup"><span data-stu-id="4298c-303">Handle overflow JSON</span></span>

<span data-ttu-id="4298c-304">При десериализации в JSON могут быть получены данные, которые не представлены свойствами целевого типа.</span><span class="sxs-lookup"><span data-stu-id="4298c-304">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="4298c-305">Например, предположим, что целевой тип:</span><span class="sxs-lookup"><span data-stu-id="4298c-305">For example, suppose your target type is this:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="4298c-306">И JSON для десериализации:</span><span class="sxs-lookup"><span data-stu-id="4298c-306">And the JSON to be deserialized is this:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

<span data-ttu-id="4298c-307">При десериализации JSON, показанного в указанном типе, свойства `DatesAvailable` и `SummaryWords` не будут переходятся и теряются.</span><span class="sxs-lookup"><span data-stu-id="4298c-307">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="4298c-308">Чтобы записать дополнительные данные, такие как эти свойства, примените атрибут [жсонекстенсиондата](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) к свойству типа `Dictionary<string,object>` или `Dictionary<string,JsonElement>`:</span><span class="sxs-lookup"><span data-stu-id="4298c-308">To capture extra data such as these properties, apply the [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithExtensionData)]

<span data-ttu-id="4298c-309">При десериализации JSON, показанного ранее, в этот тип данных дополнительные данные становятся парами "ключ-значение" свойства `ExtensionData`:</span><span class="sxs-lookup"><span data-stu-id="4298c-309">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="4298c-310">Свойство</span><span class="sxs-lookup"><span data-stu-id="4298c-310">Property</span></span> |<span data-ttu-id="4298c-311">Значение</span><span class="sxs-lookup"><span data-stu-id="4298c-311">Value</span></span>  |<span data-ttu-id="4298c-312">Примечания</span><span class="sxs-lookup"><span data-stu-id="4298c-312">Notes</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="4298c-313">Дата</span><span class="sxs-lookup"><span data-stu-id="4298c-313">Date</span></span>    | <span data-ttu-id="4298c-314">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="4298c-314">8/1/2019 12:00:00 AM -07:00</span></span>||
| <span data-ttu-id="4298c-315">температурецелсиус</span><span class="sxs-lookup"><span data-stu-id="4298c-315">TemperatureCelsius</span></span>| <span data-ttu-id="4298c-316">0</span><span class="sxs-lookup"><span data-stu-id="4298c-316">0</span></span> | <span data-ttu-id="4298c-317">Несовпадение с учетом регистра (`temperatureCelsius` в JSON), поэтому свойство не задано.</span><span class="sxs-lookup"><span data-stu-id="4298c-317">Case-sensitive mismatch (`temperatureCelsius` in the JSON), so the property isn't set.</span></span> |
| <span data-ttu-id="4298c-318">Сводка</span><span class="sxs-lookup"><span data-stu-id="4298c-318">Summary</span></span> | <span data-ttu-id="4298c-319">Горячий</span><span class="sxs-lookup"><span data-stu-id="4298c-319">Hot</span></span> ||
| <span data-ttu-id="4298c-320">ExtensionData</span><span class="sxs-lookup"><span data-stu-id="4298c-320">ExtensionData</span></span> | <span data-ttu-id="4298c-321">Температурецелсиус: 25</span><span class="sxs-lookup"><span data-stu-id="4298c-321">temperatureCelsius: 25</span></span> |<span data-ttu-id="4298c-322">Так как регистр не соответствует, это свойство JSON является дополнительным и становится парой "ключ-значение" в словаре.</span><span class="sxs-lookup"><span data-stu-id="4298c-322">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span>|
|| <span data-ttu-id="4298c-323">Датесаваилабле:</span><span class="sxs-lookup"><span data-stu-id="4298c-323">DatesAvailable:</span></span><br>  <span data-ttu-id="4298c-324">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="4298c-324">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="4298c-325">8/2/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="4298c-325">8/2/2019 12:00:00 AM -07:00</span></span> |<span data-ttu-id="4298c-326">Дополнительное свойство из JSON преобразуется в пару "ключ-значение" с массивом в качестве объекта значения.</span><span class="sxs-lookup"><span data-stu-id="4298c-326">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|
| |<span data-ttu-id="4298c-327">Суммаривордс:</span><span class="sxs-lookup"><span data-stu-id="4298c-327">SummaryWords:</span></span><br><span data-ttu-id="4298c-328">Холодный</span><span class="sxs-lookup"><span data-stu-id="4298c-328">Cool</span></span><br><span data-ttu-id="4298c-329">Ветрено</span><span class="sxs-lookup"><span data-stu-id="4298c-329">Windy</span></span><br><span data-ttu-id="4298c-330">хумид</span><span class="sxs-lookup"><span data-stu-id="4298c-330">Humid</span></span> |<span data-ttu-id="4298c-331">Дополнительное свойство из JSON преобразуется в пару "ключ-значение" с массивом в качестве объекта значения.</span><span class="sxs-lookup"><span data-stu-id="4298c-331">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|

<span data-ttu-id="4298c-332">При сериализации целевого объекта пары "ключ-значение" данных расширения становятся свойствами JSON так же, как и во входящем JSON:</span><span class="sxs-lookup"><span data-stu-id="4298c-332">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 0,
  "Summary": "Hot",
  "temperatureCelsius": 25,
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

<span data-ttu-id="4298c-333">Обратите внимание, что имя свойства `ExtensionData` не отображается в JSON.</span><span class="sxs-lookup"><span data-stu-id="4298c-333">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="4298c-334">Такое поведение позволяет JSON выполнить цикл обработки без потери дополнительных данных, которые в противном случае не будут десериализованы.</span><span class="sxs-lookup"><span data-stu-id="4298c-334">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="ignore-null-when-deserializing"></a><span data-ttu-id="4298c-335">Игнорировать null при десериализации</span><span class="sxs-lookup"><span data-stu-id="4298c-335">Ignore null when deserializing</span></span>

<span data-ttu-id="4298c-336">По умолчанию, если свойство в JSON имеет значение null, соответствующему свойству в целевом объекте присваивается значение null.</span><span class="sxs-lookup"><span data-stu-id="4298c-336">By default, if a property in JSON is null, the corresponding property in the target object is set to null.</span></span> <span data-ttu-id="4298c-337">В некоторых сценариях свойство Target может иметь значение по умолчанию, и вы не хотите, чтобы значение NULL переопределяло по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4298c-337">In some scenarios, the target property might have a default value, and you don't want a null value to override the default.</span></span>

<span data-ttu-id="4298c-338">Например, предположим, что целевой объект представляет следующий код:</span><span class="sxs-lookup"><span data-stu-id="4298c-338">For example, suppose the following code represents your target object:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

<span data-ttu-id="4298c-339">Предположим, что десериализуется следующий JSON:</span><span class="sxs-lookup"><span data-stu-id="4298c-339">And suppose the following JSON is deserialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": null
}
```

<span data-ttu-id="4298c-340">После десериализации свойство `Summary` объекта `WeatherForecastWithDefault` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="4298c-340">After deserialization, the `Summary` property of the `WeatherForecastWithDefault` object is null.</span></span>

<span data-ttu-id="4298c-341">Чтобы изменить это поведение, задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> значение `true`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="4298c-341">To change this behavior, set <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeIgnoreNull.cs?name=SnippetDeserialize)]

<span data-ttu-id="4298c-342">При использовании этого параметра свойство `Summary` объекта `WeatherForecastWithDefault` является значением по умолчанию "нет сводки" после десериализации.</span><span class="sxs-lookup"><span data-stu-id="4298c-342">With this option, the `Summary` property of the `WeatherForecastWithDefault` object is the default value "No summary" after deserialization.</span></span>

<span data-ttu-id="4298c-343">Значения NULL в JSON пропускаются только в том случае, если они являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="4298c-343">Null values in the JSON are ignored only if they are valid.</span></span> <span data-ttu-id="4298c-344">Значения NULL для типов значений, не допускающих значения NULL, вызывают исключения.</span><span class="sxs-lookup"><span data-stu-id="4298c-344">Null values for non-nullable value types cause exceptions.</span></span>

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a><span data-ttu-id="4298c-345">Utf8JsonReader, Utf8JsonWriter и Жсондокумент</span><span class="sxs-lookup"><span data-stu-id="4298c-345">Utf8JsonReader, Utf8JsonWriter, and JsonDocument</span></span>

<span data-ttu-id="4298c-346"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> — это высокопроизводительное, медленное средство чтения, доступное только для прямого просмотра для текста JSON в кодировке UTF-8, чтение из `ReadOnlySpan<byte>` или `ReadOnlySequence<byte>`.</span><span class="sxs-lookup"><span data-stu-id="4298c-346"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>` or `ReadOnlySequence<byte>`.</span></span> <span data-ttu-id="4298c-347">`Utf8JsonReader` — это тип низкого уровня, который можно использовать для создания пользовательских средств синтаксического анализа и десериализаторов.</span><span class="sxs-lookup"><span data-stu-id="4298c-347">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="4298c-348">Метод <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> использует `Utf8JsonReader`, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="4298c-348">The <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method uses `Utf8JsonReader` under the covers.</span></span>

<span data-ttu-id="4298c-349"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> — это высокопроизводительный способ записи текста JSON в кодировке UTF-8 из распространенных типов .NET, таких как `String`, `Int32`и `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="4298c-349"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="4298c-350">Модуль записи — это тип низкого уровня, который можно использовать для создания пользовательских сериализаторов.</span><span class="sxs-lookup"><span data-stu-id="4298c-350">The writer is a low-level type that can be used to build custom serializers.</span></span> <span data-ttu-id="4298c-351">Метод <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> использует `Utf8JsonWriter`, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="4298c-351">The <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method uses `Utf8JsonWriter` under the covers.</span></span>

<span data-ttu-id="4298c-352"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> предоставляет возможность создания модель DOM (DOM) только для чтения с помощью `Utf8JsonReader`.</span><span class="sxs-lookup"><span data-stu-id="4298c-352"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> provides the ability to build a read-only Document Object Model (DOM) by using `Utf8JsonReader`.</span></span> <span data-ttu-id="4298c-353">Модель DOM предоставляет произвольный доступ к данным в полезных данных JSON.</span><span class="sxs-lookup"><span data-stu-id="4298c-353">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="4298c-354">Доступ к элементам JSON, составляющим полезные данные, можно получить с помощью типа <xref:System.Text.Json.JsonElement>.</span><span class="sxs-lookup"><span data-stu-id="4298c-354">The JSON elements that compose the payload can be accessed via the <xref:System.Text.Json.JsonElement> type.</span></span> <span data-ttu-id="4298c-355">Тип `JsonElement` предоставляет перечислители массивов и объектов вместе с интерфейсами API для преобразования текста JSON в общие типы .NET.</span><span class="sxs-lookup"><span data-stu-id="4298c-355">The `JsonElement` type provides array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="4298c-356">`JsonDocument` предоставляет свойство <xref:System.Text.Json.JsonDocument.RootElement>.</span><span class="sxs-lookup"><span data-stu-id="4298c-356">`JsonDocument` exposes a <xref:System.Text.Json.JsonDocument.RootElement> property.</span></span>

<span data-ttu-id="4298c-357">В следующих разделах показано, как использовать эти средства для чтения и записи данных JSON.</span><span class="sxs-lookup"><span data-stu-id="4298c-357">The following sections show how to use these tools for reading and writing JSON.</span></span>

## <a name="use-jsondocument-for-access-to-data"></a><span data-ttu-id="4298c-358">Использование Жсондокумент для доступа к данным</span><span class="sxs-lookup"><span data-stu-id="4298c-358">Use JsonDocument for access to data</span></span>

<span data-ttu-id="4298c-359">В следующем примере показано, как использовать класс <xref:System.Text.Json.JsonDocument> для произвольного доступа к данным в строке JSON:</span><span class="sxs-lookup"><span data-stu-id="4298c-359">The following example shows how to use the <xref:System.Text.Json.JsonDocument> class for random access to data in a JSON string:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades1)]

<span data-ttu-id="4298c-360">Предыдущий код:</span><span class="sxs-lookup"><span data-stu-id="4298c-360">The preceding code:</span></span>

* <span data-ttu-id="4298c-361">Предполагается, что анализируемый JSON находится в строке с именем `jsonString`.</span><span class="sxs-lookup"><span data-stu-id="4298c-361">Assumes the JSON to analyze is in a string named `jsonString`.</span></span>
* <span data-ttu-id="4298c-362">Вычисляет среднее значение для объектов в массиве `Students`, имеющих свойство `Grade`.</span><span class="sxs-lookup"><span data-stu-id="4298c-362">Calculates an average grade for objects in a `Students` array that have a `Grade` property.</span></span>
* <span data-ttu-id="4298c-363">Назначает значение по умолчанию 70 для учащихся, у которых нет категории.</span><span class="sxs-lookup"><span data-stu-id="4298c-363">Assigns a default grade of 70 for students who don't have a grade.</span></span>
* <span data-ttu-id="4298c-364">Подсчитывает число учащихся путем увеличения `count` переменной с каждой итерацией.</span><span class="sxs-lookup"><span data-stu-id="4298c-364">Counts students by incrementing a `count` variable with each iteration.</span></span> <span data-ttu-id="4298c-365">Альтернативой является вызов <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="4298c-365">An alternative is to call <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, as shown in the following example:</span></span>

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades2)]

<span data-ttu-id="4298c-366">Ниже приведен пример JSON, обрабатываемого этим кодом:</span><span class="sxs-lookup"><span data-stu-id="4298c-366">Here's an example of the JSON that this code processes:</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-jsondocument-to-write-json"></a><span data-ttu-id="4298c-367">Использование Жсондокумент для записи JSON</span><span class="sxs-lookup"><span data-stu-id="4298c-367">Use JsonDocument to write JSON</span></span>

<span data-ttu-id="4298c-368">В следующем примере показано, как записать JSON из <xref:System.Text.Json.JsonDocument>.</span><span class="sxs-lookup"><span data-stu-id="4298c-368">The following example shows how to write JSON from a <xref:System.Text.Json.JsonDocument>:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentWriteJson.cs?name=SnippetSerialize)]

<span data-ttu-id="4298c-369">Предыдущий код:</span><span class="sxs-lookup"><span data-stu-id="4298c-369">The preceding code:</span></span>

* <span data-ttu-id="4298c-370">Считывает JSON-файл, загружает данные в `JsonDocument`и записывает форматированный (довольно печатный) JSON в файл.</span><span class="sxs-lookup"><span data-stu-id="4298c-370">Reads a JSON file, loads the data into a `JsonDocument`, and writes formatted (pretty-printed) JSON to a file.</span></span>
* <span data-ttu-id="4298c-371">Использует <xref:System.Text.Json.JsonDocumentOptions>, чтобы указать, что комментарии во входном JSON разрешены, но игнорируются.</span><span class="sxs-lookup"><span data-stu-id="4298c-371">Uses <xref:System.Text.Json.JsonDocumentOptions> to specify that comments in the input JSON are allowed but ignored.</span></span>
* <span data-ttu-id="4298c-372">По завершении вызывается <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> для модуля записи.</span><span class="sxs-lookup"><span data-stu-id="4298c-372">When finished, calls <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> on the writer.</span></span> <span data-ttu-id="4298c-373">В качестве альтернативы можно разрешить Автоочистку модуля записи при его удалении.</span><span class="sxs-lookup"><span data-stu-id="4298c-373">An alternative is to let the writer autoflush when it's disposed.</span></span>

<span data-ttu-id="4298c-374">Ниже приведен пример входных данных JSON для обработки в примере кода:</span><span class="sxs-lookup"><span data-stu-id="4298c-374">Here's an example of JSON input to be processed by the example code:</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Grades.json)]

<span data-ttu-id="4298c-375">В результате получается следующий качественный вывод JSON:</span><span class="sxs-lookup"><span data-stu-id="4298c-375">The result is the following pretty-printed JSON output:</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-utf8jsonwriter"></a><span data-ttu-id="4298c-376">Использование Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="4298c-376">Use Utf8JsonWriter</span></span>

<span data-ttu-id="4298c-377">В следующем примере показано, как использовать класс <xref:System.Text.Json.Utf8JsonWriter>:</span><span class="sxs-lookup"><span data-stu-id="4298c-377">The following example shows how to use the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8WriterToStream.cs?name=SnippetSerialize)]

## <a name="use-utf8jsonreader"></a><span data-ttu-id="4298c-378">Использование Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="4298c-378">Use Utf8JsonReader</span></span>

<span data-ttu-id="4298c-379">В следующем примере показано, как использовать класс <xref:System.Text.Json.Utf8JsonReader>:</span><span class="sxs-lookup"><span data-stu-id="4298c-379">The following example shows how to use the <xref:System.Text.Json.Utf8JsonReader> class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromBytes.cs?name=SnippetDeserialize)]

<span data-ttu-id="4298c-380">В приведенном выше коде предполагается, что `jsonUtf8` переменной является массив байтов, который содержит допустимый формат JSON, закодированный как UTF-8.</span><span class="sxs-lookup"><span data-stu-id="4298c-380">The preceding code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

### <a name="filter-data-using-utf8jsonreader"></a><span data-ttu-id="4298c-381">Фильтрация данных с помощью Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="4298c-381">Filter data using Utf8JsonReader</span></span>

<span data-ttu-id="4298c-382">В следующем примере показано, как синхронно прочитать файл и выполнить поиск значения:</span><span class="sxs-lookup"><span data-stu-id="4298c-382">The following example shows how to read a file synchronously and search for a value:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromFile.cs)]

<span data-ttu-id="4298c-383">Предыдущий код:</span><span class="sxs-lookup"><span data-stu-id="4298c-383">The preceding code:</span></span>

* <span data-ttu-id="4298c-384">Предполагается, что JSON содержит массив объектов, и каждый объект может содержать свойство "Name" типа String.</span><span class="sxs-lookup"><span data-stu-id="4298c-384">Assumes the JSON contains an array of objects and each object may contain a "name" property of type string.</span></span>
* <span data-ttu-id="4298c-385">Подсчитывает объекты и значения свойств Name, заканчивающиеся на университет.</span><span class="sxs-lookup"><span data-stu-id="4298c-385">Counts objects and "name" property values that end with "University".</span></span>
* <span data-ttu-id="4298c-386">Предполагается, что файл кодируется как UTF-16 и перекодируется в UTF-8.</span><span class="sxs-lookup"><span data-stu-id="4298c-386">Assumes the file is encoded as UTF-16 and transcodes it into UTF-8.</span></span> <span data-ttu-id="4298c-387">Файл, закодированный как UTF-8, можно прочитать непосредственно в `ReadOnlySpan<byte>`с помощью следующего кода:</span><span class="sxs-lookup"><span data-stu-id="4298c-387">A file encoded as UTF-8 can be read directly into a `ReadOnlySpan<byte>`, by using the following code:</span></span>

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName);
  ```

  <span data-ttu-id="4298c-388">Если файл содержит метку порядка байтов (BOM) UTF-8, удалите ее перед передачей байтов в `Utf8JsonReader`, так как средство чтения ждет текст.</span><span class="sxs-lookup"><span data-stu-id="4298c-388">If the file contains a UTF-8 byte order mark (BOM), remove it before passing the bytes to the `Utf8JsonReader`, since the reader expects text.</span></span> <span data-ttu-id="4298c-389">В противном случае спецификация считается недопустимым JSON, а средство чтения создает исключение.</span><span class="sxs-lookup"><span data-stu-id="4298c-389">Otherwise, the BOM is considered invalid JSON, and the reader throws an exception.</span></span>

<span data-ttu-id="4298c-390">Ниже приведен пример JSON, который можно считать с помощью приведенного выше кода.</span><span class="sxs-lookup"><span data-stu-id="4298c-390">Here's a JSON sample that the preceding code can read.</span></span> <span data-ttu-id="4298c-391">Полученное итоговое сообщение "2 из 4 имеют имена, заканчивающиеся на" Университет ":</span><span class="sxs-lookup"><span data-stu-id="4298c-391">The resulting summary message is "2 out of 4 have names that end with 'University'":</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Universities.json)]

## <a name="additional-resources"></a><span data-ttu-id="4298c-392">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="4298c-392">Additional resources</span></span>

* <span data-ttu-id="4298c-393">[Обзор System.Text.Json](system-text-json-overview.md)</span><span class="sxs-lookup"><span data-stu-id="4298c-393">[System.Text.Json overview](system-text-json-overview.md)</span></span>
* [<span data-ttu-id="4298c-394">Написание пользовательских преобразователей</span><span class="sxs-lookup"><span data-stu-id="4298c-394">How to write custom converters</span></span>](system-text-json-converters-how-to.md)
* <span data-ttu-id="4298c-395">[Переход с Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="4298c-395">[How to migrate from Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span></span>
* <span data-ttu-id="4298c-396">[Поддержка DateTime и DateTimeOffset в System.Text.Json](../datetime/system-text-json-support.md)</span><span class="sxs-lookup"><span data-stu-id="4298c-396">[DateTime and DateTimeOffset support in System.Text.Json](../datetime/system-text-json-support.md)</span></span>
* <span data-ttu-id="4298c-397">[Справочник по System.Text.Json API](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="4298c-397">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
