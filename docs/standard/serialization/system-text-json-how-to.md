---
title: Как сериализовать и десериализовать JSON с C# помощью-.NET
author: tdykstra
ms.author: tdykstra
ms.date: 09/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 3d3dc0011562e25854938aff857f2832a5978b49
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283336"
---
# <a name="how-to-serialize-and-deserialize-json-in-net"></a><span data-ttu-id="e3af8-102">Как сериализовать и десериализовать JSON в .NET</span><span class="sxs-lookup"><span data-stu-id="e3af8-102">How to serialize and deserialize JSON in .NET</span></span>

<span data-ttu-id="e3af8-103">В этой статье показано, как использовать пространство имен <xref:System.Text.Json> для сериализации и десериализации в нотация объектов JavaScript (JSON) и обратно.</span><span class="sxs-lookup"><span data-stu-id="e3af8-103">This article shows how to use the <xref:System.Text.Json> namespace to serialize and deserialize to and from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="e3af8-104">В направлениях и образце кода библиотека используется напрямую, а не с помощью платформы, такой как [ASP.NET Core](/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="e3af8-104">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

<span data-ttu-id="e3af8-105">Большинство примеров кода сериализации задают <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType>, чтобы `true`ся для «удобного» печати JSON (с отступами и пробелами для удобочитаемости).</span><span class="sxs-lookup"><span data-stu-id="e3af8-105">Most of the serialization sample code sets <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true` to "pretty-print" the JSON (with indentation and whitespace for human readability).</span></span> <span data-ttu-id="e3af8-106">Для использования в рабочей среде для этого параметра обычно принимается значение по умолчанию `false`.</span><span class="sxs-lookup"><span data-stu-id="e3af8-106">For production use, you would typically accept the default value of `false` for this setting.</span></span>

## <a name="namespaces"></a><span data-ttu-id="e3af8-107">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="e3af8-107">Namespaces</span></span>

<span data-ttu-id="e3af8-108">Пространство имен <xref:System.Text.Json> содержит все точки входа и основные типы.</span><span class="sxs-lookup"><span data-stu-id="e3af8-108">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="e3af8-109">Пространство имен <xref:System.Text.Json.Serialization> содержит атрибуты и интерфейсы API для сложных сценариев и настройки, характерные для сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="e3af8-109">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="e3af8-110">В примерах кода, приведенных в этой статье, требуются директивы `using` для одного или обоих пространств имен:</span><span class="sxs-lookup"><span data-stu-id="e3af8-110">The code examples shown in this article require `using` directives for one or both of these namespaces:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

<span data-ttu-id="e3af8-111">Атрибуты из пространства имен <xref:System.Runtime.Serialization> в настоящее время не поддерживаются в `System.Text.Json`.</span><span class="sxs-lookup"><span data-stu-id="e3af8-111">Attributes from the <xref:System.Runtime.Serialization> namespace aren't currently supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="e3af8-112">Как записывать объекты .NET в JSON (сериализовать)</span><span class="sxs-lookup"><span data-stu-id="e3af8-112">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="e3af8-113">Чтобы записать JSON в строку или в файл, вызовите метод <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e3af8-113">To write JSON to a string or to a file, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="e3af8-114">В следующем примере показано создание JSON в виде строки:</span><span class="sxs-lookup"><span data-stu-id="e3af8-114">The following example creates JSON as a string:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerialize)]

<span data-ttu-id="e3af8-115">В следующем примере синхронный код используется для создания JSON-файла:</span><span class="sxs-lookup"><span data-stu-id="e3af8-115">The following example uses synchronous code to create a JSON file:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetSerialize)]

<span data-ttu-id="e3af8-116">В следующем примере асинхронный код используется для создания JSON-файла:</span><span class="sxs-lookup"><span data-stu-id="e3af8-116">The following example uses asynchronous code to create a JSON file:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetSerialize)]

<span data-ttu-id="e3af8-117">В предыдущих примерах для сериализуемого типа используется определение типа.</span><span class="sxs-lookup"><span data-stu-id="e3af8-117">The preceding examples use type inference for the type being serialized.</span></span> <span data-ttu-id="e3af8-118">Перегрузка `Serialize()` принимает параметр универсального типа:</span><span class="sxs-lookup"><span data-stu-id="e3af8-118">An overload of `Serialize()` takes a generic type parameter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializeWithGenericParameter)]

### <a name="serialization-example"></a><span data-ttu-id="e3af8-119">Пример сериализации</span><span class="sxs-lookup"><span data-stu-id="e3af8-119">Serialization example</span></span>

<span data-ttu-id="e3af8-120">Ниже приведен пример класса, который содержит коллекции и вложенный класс:</span><span class="sxs-lookup"><span data-stu-id="e3af8-120">Here's an example class that contains collections and a nested class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPOCOs)]

<span data-ttu-id="e3af8-121">Выходные данные JSON из сериализации экземпляра предыдущего типа выглядят так, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="e3af8-121">The JSON output from serializing an instance of the preceding type looks like the following example.</span></span> <span data-ttu-id="e3af8-122">Выходные данные JSON по умолчанию минифицированные:</span><span class="sxs-lookup"><span data-stu-id="e3af8-122">The JSON output is minified by default:</span></span> 

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="e3af8-123">В следующем примере показан один и тот же формат JSON, форматированный (т. е. который печатается с пробелами и отступами):</span><span class="sxs-lookup"><span data-stu-id="e3af8-123">The following example shows the same JSON, formatted (that is, pretty-printed with whitespace and indentation):</span></span>

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

### <a name="serialize-to-utf-8"></a><span data-ttu-id="e3af8-124">Сериализация в UTF-8</span><span class="sxs-lookup"><span data-stu-id="e3af8-124">Serialize to UTF-8</span></span>

<span data-ttu-id="e3af8-125">Чтобы выполнить сериализацию в UTF-8, вызовите метод <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="e3af8-125">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetSerialize)]

<span data-ttu-id="e3af8-126">Также доступна перегрузка <xref:System.Text.Json.JsonSerializer.Serialize%2A>, которая принимает <xref:System.Text.Json.Utf8JsonWriter>.</span><span class="sxs-lookup"><span data-stu-id="e3af8-126">A <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is also available.</span></span>

<span data-ttu-id="e3af8-127">Сериализация в UTF-8 происходит примерно на 5-10% быстрее, чем при использовании строковых методов.</span><span class="sxs-lookup"><span data-stu-id="e3af8-127">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="e3af8-128">Разница заключается в том, что байты (как UTF-8) не нужно преобразовывать в строки (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="e3af8-128">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="e3af8-129">Поведение сериализации</span><span class="sxs-lookup"><span data-stu-id="e3af8-129">Serialization behavior</span></span>

* <span data-ttu-id="e3af8-130">По умолчанию все открытые свойства сериализуются.</span><span class="sxs-lookup"><span data-stu-id="e3af8-130">By default, all public properties are serialized.</span></span> <span data-ttu-id="e3af8-131">Можно [указать свойства для исключения](#exclude-properties-from-serialization).</span><span class="sxs-lookup"><span data-stu-id="e3af8-131">You can [specify properties to exclude](#exclude-properties-from-serialization).</span></span>
* <span data-ttu-id="e3af8-132">[Кодировщик по умолчанию](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) выводит символы, не входящие в набор ASCII, символы, УЧИТЫВАЮЩИЕ формат ASCII, и символы, которые должны быть экранированы в соответствии со [спецификацией RFC 8259 JSON](https://tools.ietf.org/html/rfc8259#section-7).</span><span class="sxs-lookup"><span data-stu-id="e3af8-132">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="e3af8-133">По умолчанию JSON — минифицированные.</span><span class="sxs-lookup"><span data-stu-id="e3af8-133">By default, JSON is minified.</span></span> <span data-ttu-id="e3af8-134">JSON можно [довольно просто распечатать](#serialize-to-formatted-json).</span><span class="sxs-lookup"><span data-stu-id="e3af8-134">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="e3af8-135">По умолчанию регистр имен JSON соответствует именам .NET.</span><span class="sxs-lookup"><span data-stu-id="e3af8-135">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="e3af8-136">Можно [настроить регистр имен JSON](#customize-json-names-and-values).</span><span class="sxs-lookup"><span data-stu-id="e3af8-136">You can [customize JSON name casing](#customize-json-names-and-values).</span></span>
* <span data-ttu-id="e3af8-137">Обнаружены циклические ссылки и создаются исключения.</span><span class="sxs-lookup"><span data-stu-id="e3af8-137">Circular references are detected and exceptions thrown.</span></span> <span data-ttu-id="e3af8-138">Дополнительные сведения см. в [статье о выпуске 38579 в циклических ссылках](https://github.com/dotnet/corefx/issues/38579) в репозитории DotNet/corefx на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="e3af8-138">For more information, see [issue 38579 on circular references](https://github.com/dotnet/corefx/issues/38579) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="e3af8-139">В настоящее время поля исключаются.</span><span class="sxs-lookup"><span data-stu-id="e3af8-139">Currently, fields are excluded.</span></span>

<span data-ttu-id="e3af8-140">Поддерживаемые типы:</span><span class="sxs-lookup"><span data-stu-id="e3af8-140">Supported types include:</span></span>

* <span data-ttu-id="e3af8-141">Примитивы .NET, которые сопоставляются с примитивами JavaScript, например числовыми типами, строками и логическими значениями.</span><span class="sxs-lookup"><span data-stu-id="e3af8-141">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="e3af8-142">Определяемые пользователем [простые старые объекты CLR (POCO)](https://stackoverflow.com/questions/250001/poco-definition).</span><span class="sxs-lookup"><span data-stu-id="e3af8-142">User-defined [Plain Old CLR Objects (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).</span></span>
* <span data-ttu-id="e3af8-143">Одномерное и зубчатые массивы (`ArrayName[][]`).</span><span class="sxs-lookup"><span data-stu-id="e3af8-143">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="e3af8-144">`Dictionary<string,TValue>`, где `TValue` — `object`, `JsonElement`или POCO.</span><span class="sxs-lookup"><span data-stu-id="e3af8-144">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="e3af8-145">Коллекции из следующих пространств имен.</span><span class="sxs-lookup"><span data-stu-id="e3af8-145">Collections from the following namespaces.</span></span> <span data-ttu-id="e3af8-146">Дополнительные сведения см. в [статье о поддержке коллекций](https://github.com/dotnet/corefx/issues/36643) в репозитории DotNet/corefx на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="e3af8-146">For more information, see the [issue on collection support](https://github.com/dotnet/corefx/issues/36643) in the dotnet/corefx repository on GitHub.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

<span data-ttu-id="e3af8-147">Можно [реализовать пользовательские преобразователи](system-text-json-converters-how-to.md) для обработки дополнительных типов или для предоставления функциональных возможностей, которые не поддерживаются встроенными преобразователями.</span><span class="sxs-lookup"><span data-stu-id="e3af8-147">You can [implement custom converters](system-text-json-converters-how-to.md) to handle additional types or to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="e3af8-148">Чтение JSON в объектах .NET (десериализация)</span><span class="sxs-lookup"><span data-stu-id="e3af8-148">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="e3af8-149">Чтобы выполнить десериализацию из строки или файла, вызовите метод <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e3af8-149">To deserialize from a string or a file, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="e3af8-150">В следующем примере показано чтение JSON из строки и создание экземпляра класса `WeatherForecast`, показанного ранее для [примера сериализации](#serialization-example):</span><span class="sxs-lookup"><span data-stu-id="e3af8-150">The following example reads JSON from a string and creates an instance of the `WeatherForecast` class shown earlier for the [serialization example](#serialization-example):</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetDeserialize)]

<span data-ttu-id="e3af8-151">Чтобы выполнить десериализацию из файла с помощью синхронного кода, считайте файл в строку, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e3af8-151">To deserialize from a file by using synchronous code, read the file into a string, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetDeserialize)]

<span data-ttu-id="e3af8-152">Чтобы выполнить десериализацию из файла с помощью асинхронного кода, вызовите метод <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A>:</span><span class="sxs-lookup"><span data-stu-id="e3af8-152">To deserialize from a file by using asynchronous code, call the <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> method:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetDeserialize)]

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="e3af8-153">Десериализация из UTF-8</span><span class="sxs-lookup"><span data-stu-id="e3af8-153">Deserialize from UTF-8</span></span>

<span data-ttu-id="e3af8-154">Для десериализации из UTF-8 вызовите перегрузку <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>, которая принимает `Utf8JsonReader` или `ReadOnlySpan<byte>`, как показано в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="e3af8-154">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples.</span></span> <span data-ttu-id="e3af8-155">В примерах предполагается, что JSON находится в массиве байтов с именем jsonUtf8Bytes.</span><span class="sxs-lookup"><span data-stu-id="e3af8-155">The examples assume the JSON is in a byte array named jsonUtf8Bytes.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize1)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize2)]

## <a name="deserialization-behavior"></a><span data-ttu-id="e3af8-156">Поведение десериализации</span><span class="sxs-lookup"><span data-stu-id="e3af8-156">Deserialization behavior</span></span>

* <span data-ttu-id="e3af8-157">По умолчанию при сопоставлении имен свойств учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="e3af8-157">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="e3af8-158">Можно [указать нечувствительность к регистру](#case-insensitive-property-matching).</span><span class="sxs-lookup"><span data-stu-id="e3af8-158">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="e3af8-159">Если JSON содержит значение для свойства, доступного только для чтения, значение игнорируется и исключение не создается.</span><span class="sxs-lookup"><span data-stu-id="e3af8-159">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="e3af8-160">Десериализация в ссылочные типы без конструктора, не имеющего параметров, не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="e3af8-160">Deserialization to reference types without a parameterless constructor isn't supported.</span></span>
* <span data-ttu-id="e3af8-161">Десериализация в неизменяемые объекты или свойства только для чтения не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="e3af8-161">Deserialization to immutable objects or read-only properties isn't supported.</span></span> <span data-ttu-id="e3af8-162">Дополнительные сведения см. в разделе [Ошибка GitHub 38569 при поддержке неизменяемых объектов](https://github.com/dotnet/corefx/issues/38569) и [выпуске 38163 на странице Поддержка свойств только для чтения](https://github.com/dotnet/corefx/issues/38163) в репозитории DotNet/corefx в GitHub.</span><span class="sxs-lookup"><span data-stu-id="e3af8-162">For more information, see GitHub [issue 38569 on immutable object support](https://github.com/dotnet/corefx/issues/38569) and [issue 38163 on read-only property support](https://github.com/dotnet/corefx/issues/38163) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="e3af8-163">По умолчанию перечисления поддерживаются в виде чисел.</span><span class="sxs-lookup"><span data-stu-id="e3af8-163">By default, enums are supported as numbers.</span></span> <span data-ttu-id="e3af8-164">[Имена перечислений можно сериализовать как строки](#enums-as-strings).</span><span class="sxs-lookup"><span data-stu-id="e3af8-164">You can [serialize enum names as strings](#enums-as-strings).</span></span>
* <span data-ttu-id="e3af8-165">Поля не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="e3af8-165">Fields aren't supported.</span></span>
* <span data-ttu-id="e3af8-166">По умолчанию комментарии или замыкающие запятые в JSON вызывают исключения.</span><span class="sxs-lookup"><span data-stu-id="e3af8-166">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="e3af8-167">Можно [Разрешить комментарии и завершающие запятые](#allow-comments-and-trailing-commas).</span><span class="sxs-lookup"><span data-stu-id="e3af8-167">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas).</span></span>
* <span data-ttu-id="e3af8-168">[Максимальная глубина по умолчанию](xref:System.Text.Json.JsonReaderOptions.MaxDepth) — 64.</span><span class="sxs-lookup"><span data-stu-id="e3af8-168">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="e3af8-169">Вы можете [реализовать пользовательские преобразователи](system-text-json-converters-how-to.md) для предоставления функциональных возможностей, которые не поддерживаются встроенными преобразователями.</span><span class="sxs-lookup"><span data-stu-id="e3af8-169">You can [implement custom converters](system-text-json-converters-how-to.md) to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="e3af8-170">Сериализовать в форматированный JSON</span><span class="sxs-lookup"><span data-stu-id="e3af8-170">Serialize to formatted JSON</span></span>

<span data-ttu-id="e3af8-171">Чтобы довольно просто распечатать выходные данные JSON, задайте для <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="e3af8-171">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializePrettyPrint)]

<span data-ttu-id="e3af8-172">Ниже приведен пример типа для сериализации и печати выходных данных JSON:</span><span class="sxs-lookup"><span data-stu-id="e3af8-172">Here's an example type to be serialized and pretty-printed JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="customize-json-names-and-values"></a><span data-ttu-id="e3af8-173">Настройка имен и значений JSON</span><span class="sxs-lookup"><span data-stu-id="e3af8-173">Customize JSON names and values</span></span>

<span data-ttu-id="e3af8-174">По умолчанию имена и ключи словарей не изменяются в выходных данных JSON, включая регистр.</span><span class="sxs-lookup"><span data-stu-id="e3af8-174">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="e3af8-175">Значения перечисления представлены в виде чисел.</span><span class="sxs-lookup"><span data-stu-id="e3af8-175">Enum values are represented as numbers.</span></span> <span data-ttu-id="e3af8-176">В этом разделе объясняется, как выполнять следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="e3af8-176">This section explains how to:</span></span>

* [<span data-ttu-id="e3af8-177">Настройка отдельных имен свойств</span><span class="sxs-lookup"><span data-stu-id="e3af8-177">Customize individual property names</span></span>](#customize-individual-property-names)
* [<span data-ttu-id="e3af8-178">Преобразовать все имена свойств в неоднородный регистр</span><span class="sxs-lookup"><span data-stu-id="e3af8-178">Convert all property names to camel case</span></span>](#use-camel-case-for-all-json-property-names)
* [<span data-ttu-id="e3af8-179">Реализация политики именования пользовательских свойств</span><span class="sxs-lookup"><span data-stu-id="e3af8-179">Implement a custom property naming policy</span></span>](#use-a-custom-json-property-naming-policy)
* [<span data-ttu-id="e3af8-180">Преобразовать ключи словаря в стиль Camel</span><span class="sxs-lookup"><span data-stu-id="e3af8-180">Convert dictionary keys to camel case</span></span>](#camel-case-dictionary-keys)
* [<span data-ttu-id="e3af8-181">Преобразование перечислений в строки и Camel</span><span class="sxs-lookup"><span data-stu-id="e3af8-181">Convert enums to strings and camel case</span></span>](#enums-as-strings) 

<span data-ttu-id="e3af8-182">Для других сценариев, требующих специальной обработки имен и значений свойств JSON, можно [реализовать пользовательские преобразователи](system-text-json-converters-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="e3af8-182">For other scenarios that require special handling of JSON property names and values, you can [implement custom converters](system-text-json-converters-how-to.md).</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="e3af8-183">Настройка отдельных имен свойств</span><span class="sxs-lookup"><span data-stu-id="e3af8-183">Customize individual property names</span></span>

<span data-ttu-id="e3af8-184">Чтобы задать имя отдельных свойств, используйте атрибут [[жсонпропертинаме]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) .</span><span class="sxs-lookup"><span data-stu-id="e3af8-184">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="e3af8-185">Ниже приведен пример типа для сериализации и результирующего JSON:</span><span class="sxs-lookup"><span data-stu-id="e3af8-185">Here's an example type to serialize and resulting JSON:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="e3af8-186">Имя свойства, заданное этим атрибутом:</span><span class="sxs-lookup"><span data-stu-id="e3af8-186">The property name set by this attribute:</span></span>

* <span data-ttu-id="e3af8-187">Применяется в обоих направлениях для сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="e3af8-187">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="e3af8-188">Имеет приоритет над политиками именования свойств.</span><span class="sxs-lookup"><span data-stu-id="e3af8-188">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="e3af8-189">Использовать прописные буквы для всех имен свойств JSON</span><span class="sxs-lookup"><span data-stu-id="e3af8-189">Use camel case for all JSON property names</span></span>

<span data-ttu-id="e3af8-190">Чтобы использовать прописные буквы для всех имен свойств JSON, задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> значение `JsonNamingPolicy.CamelCase`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e3af8-190">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundTripCamelCasePropertyNames.cs?name=Serialize)]

<span data-ttu-id="e3af8-191">Ниже приведен пример класса для сериализации и вывода JSON.</span><span class="sxs-lookup"><span data-stu-id="e3af8-191">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="e3af8-192">Политика именования свойств case:</span><span class="sxs-lookup"><span data-stu-id="e3af8-192">The camel case property naming policy:</span></span>

* <span data-ttu-id="e3af8-193">Применяется к сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="e3af8-193">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="e3af8-194">Переопределяется атрибутами `[JsonPropertyName]`.</span><span class="sxs-lookup"><span data-stu-id="e3af8-194">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="e3af8-195">Именно поэтому имя свойства JSON, `Wind` в примере, не является ни прописным.</span><span class="sxs-lookup"><span data-stu-id="e3af8-195">This is why the JSON property name `Wind` in the example is not camel case.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="e3af8-196">Использование настраиваемой политики именования свойств JSON</span><span class="sxs-lookup"><span data-stu-id="e3af8-196">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="e3af8-197">Чтобы использовать пользовательскую политику именования свойств JSON, создайте класс, производный от <xref:System.Text.Json.JsonNamingPolicy>, и переопределите метод <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A>, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e3af8-197">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/UpperCaseNamingPolicy.cs)]

<span data-ttu-id="e3af8-198">Затем задайте для свойства <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> экземпляр класса политики именования:</span><span class="sxs-lookup"><span data-stu-id="e3af8-198">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripPropertyNamingPolicy.cs?name=SnippetSerialize)]

<span data-ttu-id="e3af8-199">Ниже приведен пример класса для сериализации и вывода JSON.</span><span class="sxs-lookup"><span data-stu-id="e3af8-199">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="e3af8-200">Политика именования свойств JSON:</span><span class="sxs-lookup"><span data-stu-id="e3af8-200">The JSON property naming policy:</span></span>

* <span data-ttu-id="e3af8-201">Применяется к сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="e3af8-201">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="e3af8-202">Переопределяется атрибутами `[JsonPropertyName]`.</span><span class="sxs-lookup"><span data-stu-id="e3af8-202">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="e3af8-203">Именно поэтому имя свойства JSON `Wind` в примере — не верхний регистр.</span><span class="sxs-lookup"><span data-stu-id="e3af8-203">This is why the JSON property name `Wind` in the example is not upper case.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="e3af8-204">Ключи словаря символов в стиле Camel</span><span class="sxs-lookup"><span data-stu-id="e3af8-204">Camel case dictionary keys</span></span>

<span data-ttu-id="e3af8-205">Если свойство сериализуемого объекта имеет тип `Dictionary<string,TValue>`, `string` ключи можно преобразовать в стиль Camel.</span><span class="sxs-lookup"><span data-stu-id="e3af8-205">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="e3af8-206">Для этого задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> значение `JsonNamingPolicy.CamelCase`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e3af8-206">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCamelCaseDictionaryKeys.cs?name=SnippetSerialize)]

<span data-ttu-id="e3af8-207">Сериализация объекта с помощью словаря с именем `TemperatureRanges`, имеющего пары "ключ-значение" `"ColdMinTemp", 20` и `"HotMinTemp", 40` привести к выходным данным JSON, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e3af8-207">Serializing an object with a dictionary named `TemperatureRanges` that has key-value pairs `"ColdMinTemp", 20` and `"HotMinTemp", 40` would result in JSON output like the following example:</span></span>

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

<span data-ttu-id="e3af8-208">Политика именования Camel для ключей словаря применяется только к сериализации.</span><span class="sxs-lookup"><span data-stu-id="e3af8-208">The camel case naming policy for dictionary keys applies to serialization only.</span></span> <span data-ttu-id="e3af8-209">При десериализации словаря ключи будут соответствовать JSON-файлу, даже если для `DictionaryKeyPolicy`указан параметр `JsonNamingPolicy.CamelCase`.</span><span class="sxs-lookup"><span data-stu-id="e3af8-209">If you deserialize a dictionary, the keys will match the JSON file even if you specify `JsonNamingPolicy.CamelCase` for the `DictionaryKeyPolicy`.</span></span>

### <a name="enums-as-strings"></a><span data-ttu-id="e3af8-210">Перечисление как строки</span><span class="sxs-lookup"><span data-stu-id="e3af8-210">Enums as strings</span></span>

<span data-ttu-id="e3af8-211">По умолчанию перечисления сериализуются как числа.</span><span class="sxs-lookup"><span data-stu-id="e3af8-211">By default, enums are serialized as numbers.</span></span> <span data-ttu-id="e3af8-212">Чтобы сериализовать имена перечислений как строки, используйте <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span><span class="sxs-lookup"><span data-stu-id="e3af8-212">To serialize enum names as strings, use the <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span></span>

<span data-ttu-id="e3af8-213">Например, предположим, что необходимо сериализовать следующий класс, имеющий перечисление:</span><span class="sxs-lookup"><span data-stu-id="e3af8-213">For example, suppose you need to serialize the following class that has an enum:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithEnum)]

<span data-ttu-id="e3af8-214">Если сводка имеет `Hot`, по умолчанию сериализованный JSON имеет числовое значение 3:</span><span class="sxs-lookup"><span data-stu-id="e3af8-214">If the Summary is `Hot`, by default the serialized JSON has the numeric value 3:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

<span data-ttu-id="e3af8-215">Следующий пример кода сериализует имена перечислений вместо числовых значений и преобразует имена в Camel:</span><span class="sxs-lookup"><span data-stu-id="e3af8-215">The following sample code serializes the enum names instead of the numeric values, and converts the names to camel case:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetSerialize)]

<span data-ttu-id="e3af8-216">Итоговый код JSON выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e3af8-216">The resulting JSON looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

<span data-ttu-id="e3af8-217">Имена строк перечисления можно также десериализовать, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e3af8-217">Enum string names can be deserialized as well, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetDeserialize)]

## <a name="exclude-properties-from-serialization"></a><span data-ttu-id="e3af8-218">Исключить свойства из сериализации</span><span class="sxs-lookup"><span data-stu-id="e3af8-218">Exclude properties from serialization</span></span>

<span data-ttu-id="e3af8-219">По умолчанию все открытые свойства сериализуются.</span><span class="sxs-lookup"><span data-stu-id="e3af8-219">By default, all public properties are serialized.</span></span> <span data-ttu-id="e3af8-220">Если вы не хотите, чтобы некоторые из них отображались в выходных данных JSON, у вас есть несколько вариантов.</span><span class="sxs-lookup"><span data-stu-id="e3af8-220">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="e3af8-221">В этом разделе объясняется, как исключить:</span><span class="sxs-lookup"><span data-stu-id="e3af8-221">This section explains how to exclude:</span></span>

* [<span data-ttu-id="e3af8-222">Отдельные свойства</span><span class="sxs-lookup"><span data-stu-id="e3af8-222">Individual properties</span></span>](#exclude-individual-properties)
* [<span data-ttu-id="e3af8-223">Все свойства только для чтения</span><span class="sxs-lookup"><span data-stu-id="e3af8-223">All read-only properties</span></span>](#exclude-all-read-only-properties)
* [<span data-ttu-id="e3af8-224">Все свойства значений NULL</span><span class="sxs-lookup"><span data-stu-id="e3af8-224">All null-value properties</span></span>](#exclude-all-null-value-properties)

### <a name="exclude-individual-properties"></a><span data-ttu-id="e3af8-225">Исключить отдельные свойства</span><span class="sxs-lookup"><span data-stu-id="e3af8-225">Exclude individual properties</span></span>

<span data-ttu-id="e3af8-226">Чтобы игнорировать отдельные свойства, используйте атрибут [[жсонигноре]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) .</span><span class="sxs-lookup"><span data-stu-id="e3af8-226">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="e3af8-227">Ниже приведен пример типа для сериализации и вывода JSON.</span><span class="sxs-lookup"><span data-stu-id="e3af8-227">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithIgnoreAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

### <a name="exclude-all-read-only-properties"></a><span data-ttu-id="e3af8-228">Исключить все свойства только для чтения</span><span class="sxs-lookup"><span data-stu-id="e3af8-228">Exclude all read-only properties</span></span>

<span data-ttu-id="e3af8-229">Свойство доступно только для чтения, если оно содержит открытый метод получения, но не является открытым методом задания.</span><span class="sxs-lookup"><span data-stu-id="e3af8-229">A property is read-only if it contains a public getter but not a public setter.</span></span> <span data-ttu-id="e3af8-230">Чтобы исключить все свойства только для чтения, задайте для <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> значение `true`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e3af8-230">To exclude all read-only properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeExcludeReadOnlyProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="e3af8-231">Ниже приведен пример типа для сериализации и вывода JSON.</span><span class="sxs-lookup"><span data-stu-id="e3af8-231">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithROProperty)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="e3af8-232">Этот параметр применяется только к сериализации.</span><span class="sxs-lookup"><span data-stu-id="e3af8-232">This option applies only to serialization.</span></span> <span data-ttu-id="e3af8-233">Во время десериализации свойства, доступные только для чтения, по умолчанию игнорируются.</span><span class="sxs-lookup"><span data-stu-id="e3af8-233">During deserialization, read-only properties are ignored by default.</span></span>

### <a name="exclude-all-null-value-properties"></a><span data-ttu-id="e3af8-234">Исключить все свойства значений NULL</span><span class="sxs-lookup"><span data-stu-id="e3af8-234">Exclude all null value properties</span></span>

<span data-ttu-id="e3af8-235">Чтобы исключить все свойства значений NULL, задайте для свойства <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> значение `true`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e3af8-235">To exclude all null value properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeExcludeNullValueProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="e3af8-236">Ниже приведен пример объекта для сериализации и вывода JSON.</span><span class="sxs-lookup"><span data-stu-id="e3af8-236">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="e3af8-237">Свойство</span><span class="sxs-lookup"><span data-stu-id="e3af8-237">Property</span></span> |<span data-ttu-id="e3af8-238">значения</span><span class="sxs-lookup"><span data-stu-id="e3af8-238">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="e3af8-239">Дата</span><span class="sxs-lookup"><span data-stu-id="e3af8-239">Date</span></span>    | <span data-ttu-id="e3af8-240">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="e3af8-240">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="e3af8-241">температурецелсиус</span><span class="sxs-lookup"><span data-stu-id="e3af8-241">TemperatureCelsius</span></span>| <span data-ttu-id="e3af8-242">25</span><span class="sxs-lookup"><span data-stu-id="e3af8-242">25</span></span> |
| <span data-ttu-id="e3af8-243">Сводка</span><span class="sxs-lookup"><span data-stu-id="e3af8-243">Summary</span></span>| <span data-ttu-id="e3af8-244">null</span><span class="sxs-lookup"><span data-stu-id="e3af8-244">null</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

<span data-ttu-id="e3af8-245">Этот параметр применяется к сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="e3af8-245">This setting applies to serialization and deserialization.</span></span> <span data-ttu-id="e3af8-246">Сведения о том, как это влияет на десериализацию, см. в разделе [игнорирование значения NULL при десериализации](#ignore-null-when-deserializing).</span><span class="sxs-lookup"><span data-stu-id="e3af8-246">For information about its effect on deserialization, see [Ignore null when deserializing](#ignore-null-when-deserializing).</span></span>

## <a name="customize-character-encoding"></a><span data-ttu-id="e3af8-247">Настройка кодировки символов</span><span class="sxs-lookup"><span data-stu-id="e3af8-247">Customize character encoding</span></span>

<span data-ttu-id="e3af8-248">По умолчанию сериализатор выполняет escape-последовательность символов, отличных от ASCII.</span><span class="sxs-lookup"><span data-stu-id="e3af8-248">By default, the serializer escapes all non-ASCII characters.</span></span>  <span data-ttu-id="e3af8-249">То есть он заменяет их `\uxxxx`, где `xxxx` является кодом Юникода символа.</span><span class="sxs-lookup"><span data-stu-id="e3af8-249">That is, it replaces them with `\uxxxx` where `xxxx` is the Unicode code of the character.</span></span>  <span data-ttu-id="e3af8-250">Например, если для свойства `Summary` задано значение кириллицы жарко, `WeatherForecast` объект сериализуется, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e3af8-250">For example, if the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a><span data-ttu-id="e3af8-251">Сериализация наборов символов языка</span><span class="sxs-lookup"><span data-stu-id="e3af8-251">Serialize language character sets</span></span>

<span data-ttu-id="e3af8-252">Чтобы сериализовать наборы символов одного или нескольких языков без экранирования, укажите [Диапазоны Юникода](xref:System.Text.Unicode.UnicodeRanges) при создании экземпляра <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e3af8-252">To serialize the character set(s) of one or more languages without escaping, specify [Unicode range(s)](xref:System.Text.Unicode.UnicodeRanges) when creating an instance of <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetLanguageSets)]

<span data-ttu-id="e3af8-253">Этот код не поддерживает символы кириллицы или греческого языка.</span><span class="sxs-lookup"><span data-stu-id="e3af8-253">This code doesn't escape Cyrillic or Greek characters.</span></span> <span data-ttu-id="e3af8-254">Если свойство `Summary` имеет значение кириллицы жарко, то `WeatherForecast` объект сериализуется, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e3af8-254">If the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

<span data-ttu-id="e3af8-255">Чтобы сериализовать все языковые наборы без экранирования, используйте <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e3af8-255">To serialize all language sets without escaping, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span></span>

### <a name="serialize-specific-characters"></a><span data-ttu-id="e3af8-256">Сериализация конкретных символов</span><span class="sxs-lookup"><span data-stu-id="e3af8-256">Serialize specific characters</span></span>

<span data-ttu-id="e3af8-257">Альтернативой является указание отдельных символов, которые нужно разрешить, без экранирования.</span><span class="sxs-lookup"><span data-stu-id="e3af8-257">An alternative is to specify individual characters that you want to allow through without being escaped.</span></span> <span data-ttu-id="e3af8-258">В следующем примере сериализуются только первые два символа жарко:</span><span class="sxs-lookup"><span data-stu-id="e3af8-258">The following example serializes only the first two characters of жарко:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetSelectedCharacters)]

<span data-ttu-id="e3af8-259">Ниже приведен пример JSON, созданный с помощью приведенного выше кода.</span><span class="sxs-lookup"><span data-stu-id="e3af8-259">Here's an example of JSON produced by the preceding code:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a><span data-ttu-id="e3af8-260">Сериализовать все символы</span><span class="sxs-lookup"><span data-stu-id="e3af8-260">Serialize all characters</span></span>

<span data-ttu-id="e3af8-261">Чтобы избежать экранирования, можно использовать <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e3af8-261">To minimize escaping you can use <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUnsafeRelaxed)]

> [!CAUTION]
> <span data-ttu-id="e3af8-262">По сравнению с кодировщиком по умолчанию `UnsafeRelaxedJsonEscaping` кодировщик является более строгим, что позволяет передавать символы без экранирования:</span><span class="sxs-lookup"><span data-stu-id="e3af8-262">Compared to the default encoder, the `UnsafeRelaxedJsonEscaping` encoder is more permissive about allowing characters to pass through unescaped:</span></span>
>
> * <span data-ttu-id="e3af8-263">Он не выполняет escape-символы с учетом HTML, например `<`, `>`, `&`и `'`.</span><span class="sxs-lookup"><span data-stu-id="e3af8-263">It doesn't escape HTML-sensitive characters such as `<`, `>`, `&`, and `'`.</span></span>
> * <span data-ttu-id="e3af8-264">Она не предоставляет никаких дополнительных средств защиты от атак с помощью XSS или раскрытия информации, например, которые могут возникать из-за того, что клиент и сервер не согласны с набором *символов*.</span><span class="sxs-lookup"><span data-stu-id="e3af8-264">It doesn't offer any additional defense-in-depth protections against XSS or information disclosure attacks, such as those which might result from the client and server disagreeing on the *charset*.</span></span>
>
> <span data-ttu-id="e3af8-265">Используйте ненадежный кодировщик, только если известно, что клиент будет интерпретировать полученные полезные данные как JSON в кодировке UTF-8.</span><span class="sxs-lookup"><span data-stu-id="e3af8-265">Use the unsafe encoder only when it's known that the client will be interpreting the resulting payload as UTF-8 encoded JSON.</span></span> <span data-ttu-id="e3af8-266">Например, его можно использовать, если сервер отправляет заголовок ответа `Content-Type: application/json; charset=utf-8`.</span><span class="sxs-lookup"><span data-stu-id="e3af8-266">For example, you can use it if the server is sending the response header `Content-Type: application/json; charset=utf-8`.</span></span> <span data-ttu-id="e3af8-267">Никогда не разрешайте вывод необработанных `UnsafeRelaxedJsonEscaping` в HTML-страницу или элемент `<script>`.</span><span class="sxs-lookup"><span data-stu-id="e3af8-267">Never allow the raw `UnsafeRelaxedJsonEscaping` output to be emitted into an HTML page or a `<script>` element.</span></span>

## <a name="serialize-properties-of-derived-classes"></a><span data-ttu-id="e3af8-268">Сериализация свойств производных классов</span><span class="sxs-lookup"><span data-stu-id="e3af8-268">Serialize properties of derived classes</span></span>

<span data-ttu-id="e3af8-269">Сериализация с помощью полиморфизма не поддерживается при указании во время компиляции типа для сериализации.</span><span class="sxs-lookup"><span data-stu-id="e3af8-269">Polymorphic serialization isn't supported when you specify at compile time the type to be serialized.</span></span> <span data-ttu-id="e3af8-270">Например, предположим, что у вас есть класс `WeatherForecast` и производный класс `WeatherForecastWithWind`:</span><span class="sxs-lookup"><span data-stu-id="e3af8-270">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastWithWind`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFDerived)]

<span data-ttu-id="e3af8-271">И предположим, что аргумент типа метода `Serialize` во время компиляции `WeatherForecast`:</span><span class="sxs-lookup"><span data-stu-id="e3af8-271">And suppose the type argument of the `Serialize` method at compile time is `WeatherForecast`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeDefault)]

<span data-ttu-id="e3af8-272">В этом сценарии свойство `WindSpeed` не сериализуется, даже если объект `weatherForecast` фактически является `WeatherForecastWithWind`ным объектом.</span><span class="sxs-lookup"><span data-stu-id="e3af8-272">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastWithWind` object.</span></span> <span data-ttu-id="e3af8-273">Сериализуются только свойства базового класса:</span><span class="sxs-lookup"><span data-stu-id="e3af8-273">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="e3af8-274">Это поведение предназначено для предотвращения случайного раскрытия данных в производном от среды CLR типе.</span><span class="sxs-lookup"><span data-stu-id="e3af8-274">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="e3af8-275">Для сериализации свойств производного типа используйте один из следующих подходов:</span><span class="sxs-lookup"><span data-stu-id="e3af8-275">To serialize the properties of the derived type, use one of the following approaches:</span></span>

* <span data-ttu-id="e3af8-276">Вызовите перегрузку <xref:System.Text.Json.JsonSerializer.Serialize%2A>, которая позволяет указать тип во время выполнения:</span><span class="sxs-lookup"><span data-stu-id="e3af8-276">Call an overload of <xref:System.Text.Json.JsonSerializer.Serialize%2A> that lets you specify the type at runtime:</span></span>

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeGetType)]

* <span data-ttu-id="e3af8-277">Объявите объект, который должен быть сериализован как `object`.</span><span class="sxs-lookup"><span data-stu-id="e3af8-277">Declare the object to be serialized as `object`.</span></span>

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeObject)]

<span data-ttu-id="e3af8-278">В предыдущем примере сценария оба подхода приводят к тому, что `WindSpeed` свойство включается в выходные данные JSON:</span><span class="sxs-lookup"><span data-stu-id="e3af8-278">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "WindSpeed": 35
}
```

<span data-ttu-id="e3af8-279">Дополнительные сведения о полиморфизмной десериализации см. в разделе [Поддержка полиморфизма](system-text-json-converters-how-to.md#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="e3af8-279">For information about polymorphic deserialization, see [Support polymorphic deserialization](system-text-json-converters-how-to.md#support-polymorphic-deserialization).</span></span>

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="e3af8-280">Разрешить комментарии и завершающие запятые</span><span class="sxs-lookup"><span data-stu-id="e3af8-280">Allow comments and trailing commas</span></span>

<span data-ttu-id="e3af8-281">По умолчанию в JSON не допускаются комментарии и конечные запятые.</span><span class="sxs-lookup"><span data-stu-id="e3af8-281">By default, comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="e3af8-282">Чтобы разрешить комментарии в JSON, задайте для свойства <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> значение `JsonCommentHandling.Skip`.</span><span class="sxs-lookup"><span data-stu-id="e3af8-282">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span>
<span data-ttu-id="e3af8-283">Чтобы разрешить замыкающие запятые, задайте для свойства <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="e3af8-283">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="e3af8-284">В следующем примере показано, как разрешить оба:</span><span class="sxs-lookup"><span data-stu-id="e3af8-284">The following example shows how to allow both:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCommasComments.cs?name=SnippetDeserialize)]

<span data-ttu-id="e3af8-285">Вот пример JSON с комментариями и завершающей запятой:</span><span class="sxs-lookup"><span data-stu-id="e3af8-285">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="e3af8-286">Сопоставление свойств без учета регистра</span><span class="sxs-lookup"><span data-stu-id="e3af8-286">Case-insensitive property matching</span></span>

<span data-ttu-id="e3af8-287">По умолчанию десериализация выполняет поиск совпадения имен свойств с учетом регистра между JSON и свойствами целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="e3af8-287">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="e3af8-288">Чтобы изменить это поведение, задайте для <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="e3af8-288">To change that behavior, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCaseInsensitive.cs?name=SnippetDeserialize)]

<span data-ttu-id="e3af8-289">Ниже приведен пример JSON с именами свойств «Case Camel».</span><span class="sxs-lookup"><span data-stu-id="e3af8-289">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="e3af8-290">Его можно десериализовать в следующий тип, который содержит имена свойств case в стиле Pascal.</span><span class="sxs-lookup"><span data-stu-id="e3af8-290">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="handle-overflow-json"></a><span data-ttu-id="e3af8-291">Маркер переполнения токена JSON</span><span class="sxs-lookup"><span data-stu-id="e3af8-291">Handle overflow JSON</span></span>

<span data-ttu-id="e3af8-292">При десериализации в JSON могут быть получены данные, которые не представлены свойствами целевого типа.</span><span class="sxs-lookup"><span data-stu-id="e3af8-292">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="e3af8-293">Например, предположим, что целевой тип:</span><span class="sxs-lookup"><span data-stu-id="e3af8-293">For example, suppose your target type is this:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="e3af8-294">И JSON для десериализации:</span><span class="sxs-lookup"><span data-stu-id="e3af8-294">And the JSON to be deserialized is this:</span></span>

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

<span data-ttu-id="e3af8-295">При десериализации JSON, показанного в указанном типе, свойства `DatesAvailable` и `SummaryWords` не будут переходятся и теряются.</span><span class="sxs-lookup"><span data-stu-id="e3af8-295">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="e3af8-296">Чтобы записать дополнительные данные, такие как эти свойства, примените атрибут [жсонекстенсиондата](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) к свойству типа `Dictionary<string,object>` или `Dictionary<string,JsonElement>`:</span><span class="sxs-lookup"><span data-stu-id="e3af8-296">To capture extra data such as these properties, apply the [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithExtensionData)]

<span data-ttu-id="e3af8-297">При десериализации JSON, показанного ранее, в этот тип данных дополнительные данные становятся парами "ключ-значение" свойства `ExtensionData`:</span><span class="sxs-lookup"><span data-stu-id="e3af8-297">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="e3af8-298">Свойство</span><span class="sxs-lookup"><span data-stu-id="e3af8-298">Property</span></span> |<span data-ttu-id="e3af8-299">значения</span><span class="sxs-lookup"><span data-stu-id="e3af8-299">Value</span></span>  |<span data-ttu-id="e3af8-300">Примечания</span><span class="sxs-lookup"><span data-stu-id="e3af8-300">Notes</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="e3af8-301">Дата</span><span class="sxs-lookup"><span data-stu-id="e3af8-301">Date</span></span>    | <span data-ttu-id="e3af8-302">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="e3af8-302">8/1/2019 12:00:00 AM -07:00</span></span>||
| <span data-ttu-id="e3af8-303">температурецелсиус</span><span class="sxs-lookup"><span data-stu-id="e3af8-303">TemperatureCelsius</span></span>| <span data-ttu-id="e3af8-304">0</span><span class="sxs-lookup"><span data-stu-id="e3af8-304">0</span></span> | <span data-ttu-id="e3af8-305">Несовпадение с учетом регистра (`temperatureCelsius` в JSON), поэтому свойство не задано.</span><span class="sxs-lookup"><span data-stu-id="e3af8-305">Case-sensitive mismatch (`temperatureCelsius` in the JSON), so the property isn't set.</span></span> |
| <span data-ttu-id="e3af8-306">Сводка</span><span class="sxs-lookup"><span data-stu-id="e3af8-306">Summary</span></span> | <span data-ttu-id="e3af8-307">Высокий</span><span class="sxs-lookup"><span data-stu-id="e3af8-307">Hot</span></span> ||
| <span data-ttu-id="e3af8-308">ExtensionData</span><span class="sxs-lookup"><span data-stu-id="e3af8-308">ExtensionData</span></span> | <span data-ttu-id="e3af8-309">Температурецелсиус: 25</span><span class="sxs-lookup"><span data-stu-id="e3af8-309">temperatureCelsius: 25</span></span> |<span data-ttu-id="e3af8-310">Так как регистр не соответствует, это свойство JSON является дополнительным и становится парой "ключ-значение" в словаре.</span><span class="sxs-lookup"><span data-stu-id="e3af8-310">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span>|
|| <span data-ttu-id="e3af8-311">Датесаваилабле:</span><span class="sxs-lookup"><span data-stu-id="e3af8-311">DatesAvailable:</span></span><br>  <span data-ttu-id="e3af8-312">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="e3af8-312">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="e3af8-313">8/2/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="e3af8-313">8/2/2019 12:00:00 AM -07:00</span></span> |<span data-ttu-id="e3af8-314">Дополнительное свойство из JSON преобразуется в пару "ключ-значение" с массивом в качестве объекта значения.</span><span class="sxs-lookup"><span data-stu-id="e3af8-314">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|
| |<span data-ttu-id="e3af8-315">Суммаривордс:</span><span class="sxs-lookup"><span data-stu-id="e3af8-315">SummaryWords:</span></span><br><span data-ttu-id="e3af8-316">Здорово</span><span class="sxs-lookup"><span data-stu-id="e3af8-316">Cool</span></span><br><span data-ttu-id="e3af8-317">Ветрено</span><span class="sxs-lookup"><span data-stu-id="e3af8-317">Windy</span></span><br><span data-ttu-id="e3af8-318">хумид</span><span class="sxs-lookup"><span data-stu-id="e3af8-318">Humid</span></span> |<span data-ttu-id="e3af8-319">Дополнительное свойство из JSON преобразуется в пару "ключ-значение" с массивом в качестве объекта значения.</span><span class="sxs-lookup"><span data-stu-id="e3af8-319">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|

<span data-ttu-id="e3af8-320">При сериализации целевого объекта пары "ключ-значение" данных расширения становятся свойствами JSON так же, как и во входящем JSON:</span><span class="sxs-lookup"><span data-stu-id="e3af8-320">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

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

<span data-ttu-id="e3af8-321">Обратите внимание, что имя свойства `ExtensionData` не отображается в JSON.</span><span class="sxs-lookup"><span data-stu-id="e3af8-321">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="e3af8-322">Такое поведение позволяет JSON выполнить цикл обработки без потери дополнительных данных, которые в противном случае не будут десериализованы.</span><span class="sxs-lookup"><span data-stu-id="e3af8-322">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="ignore-null-when-deserializing"></a><span data-ttu-id="e3af8-323">Игнорировать null при десериализации</span><span class="sxs-lookup"><span data-stu-id="e3af8-323">Ignore null when deserializing</span></span>

<span data-ttu-id="e3af8-324">По умолчанию, если свойство в JSON имеет значение null, соответствующему свойству в целевом объекте присваивается значение null.</span><span class="sxs-lookup"><span data-stu-id="e3af8-324">By default, if a property in JSON is null, the corresponding property in the target object is set to null.</span></span> <span data-ttu-id="e3af8-325">В некоторых сценариях свойство Target может иметь значение по умолчанию, и вы не хотите, чтобы значение NULL переопределяло по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e3af8-325">In some scenarios, the target property might have a default value, and you don't want a null value to override the default.</span></span>

<span data-ttu-id="e3af8-326">Например, предположим, что целевой объект представляет следующий код:</span><span class="sxs-lookup"><span data-stu-id="e3af8-326">For example, suppose the following code represents your target object:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

<span data-ttu-id="e3af8-327">Предположим, что десериализуется следующий JSON:</span><span class="sxs-lookup"><span data-stu-id="e3af8-327">And suppose the following JSON is deserialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": null
}
```

<span data-ttu-id="e3af8-328">После десериализации свойство `Summary` объекта `WeatherForecastWithDefault` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="e3af8-328">After deserialization, the `Summary` property of the `WeatherForecastWithDefault` object is null.</span></span>

<span data-ttu-id="e3af8-329">Чтобы изменить это поведение, задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> значение `true`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e3af8-329">To change this behavior, set <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeIgnoreNull.cs?name=SnippetDeserialize)]

<span data-ttu-id="e3af8-330">При использовании этого параметра свойство `Summary` объекта `WeatherForecastWithDefault` является значением по умолчанию "нет сводки" после десериализации.</span><span class="sxs-lookup"><span data-stu-id="e3af8-330">With this option, the `Summary` property of the `WeatherForecastWithDefault` object is the default value "No summary" after deserialization.</span></span>

<span data-ttu-id="e3af8-331">Значения NULL в JSON пропускаются только в том случае, если они являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="e3af8-331">Null values in the JSON are ignored only if they are valid.</span></span> <span data-ttu-id="e3af8-332">Значения NULL для типов значений, не допускающих значения NULL, вызывают исключения.</span><span class="sxs-lookup"><span data-stu-id="e3af8-332">Null values for non-nullable value types cause exceptions.</span></span> <span data-ttu-id="e3af8-333">Дополнительные сведения см. в [статье о выпуске 40922 для типов значений, не допускающих значения NULL](https://github.com/dotnet/corefx/issues/40922) , в репозитории DotNet/Corefx в GitHub.</span><span class="sxs-lookup"><span data-stu-id="e3af8-333">For more information, see [issue 40922 on non-nullable value types](https://github.com/dotnet/corefx/issues/40922) in the dotnet/corefx repository on GitHub.</span></span>

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a><span data-ttu-id="e3af8-334">Utf8JsonReader, Utf8JsonWriter и Жсондокумент</span><span class="sxs-lookup"><span data-stu-id="e3af8-334">Utf8JsonReader, Utf8JsonWriter, and JsonDocument</span></span>

<span data-ttu-id="e3af8-335"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> — это однопроходный модуль чтения текста JSON в кодировке UTF-8 из `ReadOnlySpan<byte>` с высокой производительностью и низким уровнем распределения.</span><span class="sxs-lookup"><span data-stu-id="e3af8-335"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>`.</span></span> <span data-ttu-id="e3af8-336">`Utf8JsonReader` — это тип низкого уровня, который можно использовать для создания пользовательских средств синтаксического анализа и десериализаторов.</span><span class="sxs-lookup"><span data-stu-id="e3af8-336">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="e3af8-337">Метод <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> использует `Utf8JsonReader`, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="e3af8-337">The <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method uses `Utf8JsonReader` under the covers.</span></span>

<span data-ttu-id="e3af8-338"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> — это высокопроизводительный способ записи текста JSON в кодировке UTF-8 из распространенных типов .NET, таких как `String`, `Int32`и `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="e3af8-338"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="e3af8-339">Модуль записи — это тип низкого уровня, который можно использовать для создания пользовательских сериализаторов.</span><span class="sxs-lookup"><span data-stu-id="e3af8-339">The writer is a low-level type that can be used to build custom serializers.</span></span> <span data-ttu-id="e3af8-340">Метод <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> использует `Utf8JsonWriter`, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="e3af8-340">The <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method uses `Utf8JsonWriter` under the covers.</span></span>

<span data-ttu-id="e3af8-341"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> предоставляет возможность создания модель DOM (DOM) только для чтения с помощью `Utf8JsonReader`.</span><span class="sxs-lookup"><span data-stu-id="e3af8-341"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> provides the ability to build a read-only Document Object Model (DOM) by using `Utf8JsonReader`.</span></span> <span data-ttu-id="e3af8-342">Модель DOM предоставляет произвольный доступ к данным в полезных данных JSON.</span><span class="sxs-lookup"><span data-stu-id="e3af8-342">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="e3af8-343">Доступ к элементам JSON, составляющим полезные данные, можно получить с помощью типа <xref:System.Text.Json.JsonElement>.</span><span class="sxs-lookup"><span data-stu-id="e3af8-343">The JSON elements that compose the payload can be accessed via the <xref:System.Text.Json.JsonElement> type.</span></span> <span data-ttu-id="e3af8-344">Тип `JsonElement` предоставляет перечислители массивов и объектов вместе с интерфейсами API для преобразования текста JSON в общие типы .NET.</span><span class="sxs-lookup"><span data-stu-id="e3af8-344">The `JsonElement` type provides array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="e3af8-345">`JsonDocument` предоставляет свойство <xref:System.Text.Json.JsonDocument.RootElement>.</span><span class="sxs-lookup"><span data-stu-id="e3af8-345">`JsonDocument` exposes a <xref:System.Text.Json.JsonDocument.RootElement> property.</span></span>

<span data-ttu-id="e3af8-346">В следующих разделах показано, как использовать эти средства для чтения и записи данных JSON.</span><span class="sxs-lookup"><span data-stu-id="e3af8-346">The following sections show how to use these tools for reading and writing JSON.</span></span>

## <a name="use-jsondocument-for-access-to-data"></a><span data-ttu-id="e3af8-347">Использование Жсондокумент для доступа к данным</span><span class="sxs-lookup"><span data-stu-id="e3af8-347">Use JsonDocument for access to data</span></span>

<span data-ttu-id="e3af8-348">В следующем примере показано, как использовать класс <xref:System.Text.Json.JsonDocument> для произвольного доступа к данным в строке JSON:</span><span class="sxs-lookup"><span data-stu-id="e3af8-348">The following example shows how to use the <xref:System.Text.Json.JsonDocument> class for random access to data in a JSON string:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades1)]

<span data-ttu-id="e3af8-349">Предыдущий код:</span><span class="sxs-lookup"><span data-stu-id="e3af8-349">The preceding code:</span></span>

* <span data-ttu-id="e3af8-350">Предполагается, что анализируемый JSON находится в строке с именем `jsonString`.</span><span class="sxs-lookup"><span data-stu-id="e3af8-350">Assumes the JSON to analyze is in a string named `jsonString`.</span></span>
* <span data-ttu-id="e3af8-351">Вычисляет среднее значение для объектов в массиве `Students`, имеющих свойство `Grade`.</span><span class="sxs-lookup"><span data-stu-id="e3af8-351">Calculates an average grade for objects in a `Students` array that have a `Grade` property.</span></span> 
* <span data-ttu-id="e3af8-352">Назначает значение по умолчанию 70 для учащихся, у которых нет категории.</span><span class="sxs-lookup"><span data-stu-id="e3af8-352">Assigns a default grade of 70 for students who don't have a grade.</span></span>
* <span data-ttu-id="e3af8-353">Подсчитывает число учащихся путем увеличения `count` переменной с каждой итерацией.</span><span class="sxs-lookup"><span data-stu-id="e3af8-353">Counts students by incrementing a `count` variable with each iteration.</span></span> <span data-ttu-id="e3af8-354">Альтернативой является вызов <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e3af8-354">An alternative is to call <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, as shown in the following example:</span></span>

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades2)]

<span data-ttu-id="e3af8-355">Ниже приведен пример JSON, обрабатываемого этим кодом:</span><span class="sxs-lookup"><span data-stu-id="e3af8-355">Here's an example of the JSON that this code processes:</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-jsondocument-to-write-json"></a><span data-ttu-id="e3af8-356">Использование Жсондокумент для записи JSON</span><span class="sxs-lookup"><span data-stu-id="e3af8-356">Use JsonDocument to write JSON</span></span>

<span data-ttu-id="e3af8-357">В следующем примере показано, как записать JSON из <xref:System.Text.Json.JsonDocument>.</span><span class="sxs-lookup"><span data-stu-id="e3af8-357">The following example shows how to write JSON from a <xref:System.Text.Json.JsonDocument>:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentWriteJson.cs?name=SnippetSerialize)]

<span data-ttu-id="e3af8-358">Предыдущий код:</span><span class="sxs-lookup"><span data-stu-id="e3af8-358">The preceding code:</span></span>

* <span data-ttu-id="e3af8-359">Считывает JSON-файл, загружает данные в `JsonDocument`и записывает форматированный (довольно печатный) JSON в файл.</span><span class="sxs-lookup"><span data-stu-id="e3af8-359">Reads a JSON file, loads the data into a `JsonDocument`, and writes formatted (pretty-printed) JSON to a file.</span></span>
* <span data-ttu-id="e3af8-360">Использует <xref:System.Text.Json.JsonDocumentOptions>, чтобы указать, что комментарии во входном JSON разрешены, но игнорируются.</span><span class="sxs-lookup"><span data-stu-id="e3af8-360">Uses <xref:System.Text.Json.JsonDocumentOptions> to specify that comments in the input JSON are allowed but ignored.</span></span>
* <span data-ttu-id="e3af8-361">По завершении вызывается <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> для модуля записи.</span><span class="sxs-lookup"><span data-stu-id="e3af8-361">When finished, calls <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> on the writer.</span></span> <span data-ttu-id="e3af8-362">В качестве альтернативы можно разрешить Автоочистку модуля записи при его удалении.</span><span class="sxs-lookup"><span data-stu-id="e3af8-362">An alternative is to let the writer autoflush when it's disposed.</span></span> 

<span data-ttu-id="e3af8-363">Ниже приведен пример входных данных JSON для обработки в примере кода:</span><span class="sxs-lookup"><span data-stu-id="e3af8-363">Here's an example of JSON input to be processed by the example code:</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Grades.json)]

<span data-ttu-id="e3af8-364">В результате получается следующий качественный вывод JSON:</span><span class="sxs-lookup"><span data-stu-id="e3af8-364">The result is the following pretty-printed JSON output:</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-utf8jsonwriter"></a><span data-ttu-id="e3af8-365">Использование Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="e3af8-365">Use Utf8JsonWriter</span></span>

<span data-ttu-id="e3af8-366">В следующем примере показано, как использовать класс <xref:System.Text.Json.Utf8JsonWriter>:</span><span class="sxs-lookup"><span data-stu-id="e3af8-366">The following example shows how to use the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8WriterToStream.cs?name=SnippetSerialize)]

## <a name="use-utf8jsonreader"></a><span data-ttu-id="e3af8-367">Использование Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="e3af8-367">Use Utf8JsonReader</span></span>

<span data-ttu-id="e3af8-368">В следующем примере показано, как использовать класс <xref:System.Text.Json.Utf8JsonReader>:</span><span class="sxs-lookup"><span data-stu-id="e3af8-368">The following example shows how to use the <xref:System.Text.Json.Utf8JsonReader> class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromBytes.cs?name=SnippetDeserialize)]

<span data-ttu-id="e3af8-369">В приведенном выше коде предполагается, что `jsonUtf8` переменной является массив байтов, который содержит допустимый формат JSON, закодированный как UTF-8.</span><span class="sxs-lookup"><span data-stu-id="e3af8-369">The preceding code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

### <a name="filter-data-using-utf8jsonreader"></a><span data-ttu-id="e3af8-370">Фильтрация данных с помощью Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="e3af8-370">Filter data using Utf8JsonReader</span></span>

<span data-ttu-id="e3af8-371">В следующем примере показано, как синхронно прочитать файл и выполнить поиск значения:</span><span class="sxs-lookup"><span data-stu-id="e3af8-371">The following example shows how to read a file synchronously and search for a value:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromFile.cs)]

<span data-ttu-id="e3af8-372">Предыдущий код:</span><span class="sxs-lookup"><span data-stu-id="e3af8-372">The preceding code:</span></span>

* <span data-ttu-id="e3af8-373">Предполагается, что файл кодируется как UTF-16 и перекодируется в UTF-8.</span><span class="sxs-lookup"><span data-stu-id="e3af8-373">Assumes the file is encoded as UTF-16 and transcodes it into UTF-8.</span></span> <span data-ttu-id="e3af8-374">Файл, закодированный как UTF-8, можно прочитать непосредственно в `ReadOnlySpan<byte>`с помощью следующего кода:</span><span class="sxs-lookup"><span data-stu-id="e3af8-374">A file encoded as UTF-8 can be read directly into a `ReadOnlySpan<byte>`, by using the following code:</span></span>

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName); 
  ```

* <span data-ttu-id="e3af8-375">Предполагается, что JSON содержит массив объектов, и каждый объект может содержать свойство "Name" типа String.</span><span class="sxs-lookup"><span data-stu-id="e3af8-375">Assumes the JSON contains an array of objects and each object may contain a "name" property of type string.</span></span>
* <span data-ttu-id="e3af8-376">Подсчитывает объекты и `name` значения свойств, заканчивающиеся на университет.</span><span class="sxs-lookup"><span data-stu-id="e3af8-376">Counts objects and `name` property values that end with "University".</span></span>

<span data-ttu-id="e3af8-377">Ниже приведен пример JSON, который можно считать с помощью приведенного выше кода.</span><span class="sxs-lookup"><span data-stu-id="e3af8-377">Here's a JSON sample that the preceding code can read.</span></span> <span data-ttu-id="e3af8-378">Полученное итоговое сообщение "2 из 4 имеют имена, заканчивающиеся на" Университет ":</span><span class="sxs-lookup"><span data-stu-id="e3af8-378">The resulting summary message is "2 out of 4 have names that end with 'University'":</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Universities.json)]

## <a name="additional-resources"></a><span data-ttu-id="e3af8-379">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="e3af8-379">Additional resources</span></span>

* [<span data-ttu-id="e3af8-380">Общие сведения о System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="e3af8-380">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="e3af8-381">Справочник по API System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="e3af8-381">System.Text.Json API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="e3af8-382">Запись пользовательских преобразователей для System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="e3af8-382">Write custom converters for System.Text.Json</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="e3af8-383">Поддержка DateTime и DateTimeOffset в System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="e3af8-383">DateTime and DateTimeOffset support in System.Text.Json</span></span>](../datetime/system-text-json-support.md)
* [<span data-ttu-id="e3af8-384">Проблемы GitHub в репозитории DotNet/corefx с меткой JSON-функциональность-doc</span><span class="sxs-lookup"><span data-stu-id="e3af8-384">GitHub issues in the dotnet/corefx repository labeled json-functionality-doc</span></span>](https://github.com/dotnet/corefx/labels/json-functionality-doc) 
