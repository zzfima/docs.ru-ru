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
ms.openlocfilehash: f0245feb710f33d5fcea2a7125b8753ba6064018
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740429"
---
# <a name="how-to-serialize-and-deserialize-json-in-net"></a><span data-ttu-id="bd008-102">Как сериализовать и десериализовать JSON в .NET</span><span class="sxs-lookup"><span data-stu-id="bd008-102">How to serialize and deserialize JSON in .NET</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd008-103">Документация по сериализации JSON находится в стадии разработки.</span><span class="sxs-lookup"><span data-stu-id="bd008-103">The JSON serialization documentation is under construction.</span></span> <span data-ttu-id="bd008-104">В этой статье не рассматриваются все сценарии.</span><span class="sxs-lookup"><span data-stu-id="bd008-104">This article doesn't cover all scenarios.</span></span> <span data-ttu-id="bd008-105">Дополнительные сведения см. в описании [проблем с System. Text. JSON](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) в репозитории DotNet/Corefx в GitHub, особенно в [формате JSON-функциональность-doc](https://github.com/dotnet/corefx/labels/json-functionality-doc).</span><span class="sxs-lookup"><span data-stu-id="bd008-105">For more information, examine [System.Text.Json issues](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) in the dotnet/corefx repository on GitHub, especially those labeled [json-functionality-doc](https://github.com/dotnet/corefx/labels/json-functionality-doc).</span></span>

<span data-ttu-id="bd008-106">В этой статье показано, как использовать пространство имен <xref:System.Text.Json> для сериализации и десериализации в нотация объектов JavaScript (JSON) и обратно.</span><span class="sxs-lookup"><span data-stu-id="bd008-106">This article shows how to use the <xref:System.Text.Json> namespace to serialize and deserialize to and from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="bd008-107">В направлениях и образце кода библиотека используется напрямую, а не с помощью платформы, такой как [ASP.NET Core](/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="bd008-107">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

## <a name="namespaces"></a><span data-ttu-id="bd008-108">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="bd008-108">Namespaces</span></span>

<span data-ttu-id="bd008-109">Пространство имен <xref:System.Text.Json> содержит все точки входа и основные типы.</span><span class="sxs-lookup"><span data-stu-id="bd008-109">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="bd008-110">Пространство имен <xref:System.Text.Json.Serialization> содержит атрибуты и интерфейсы API для сложных сценариев и настройки, характерные для сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="bd008-110">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="bd008-111">В примерах кода, приведенных в этой статье, требуются директивы `using` для одного или обоих пространств имен:</span><span class="sxs-lookup"><span data-stu-id="bd008-111">The code examples shown in this article require `using` directives for one or both of these namespaces:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

<span data-ttu-id="bd008-112">Атрибуты из пространства имен <xref:System.Runtime.Serialization> в настоящее время не поддерживаются в `System.Text.Json`.</span><span class="sxs-lookup"><span data-stu-id="bd008-112">Attributes from the <xref:System.Runtime.Serialization> namespace aren't currently supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="bd008-113">Как записывать объекты .NET в JSON (сериализовать)</span><span class="sxs-lookup"><span data-stu-id="bd008-113">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="bd008-114">Чтобы записать JSON в строку или в файл, вызовите метод <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bd008-114">To write JSON to a string or to a file, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="bd008-115">В следующем примере показано создание JSON в виде строки:</span><span class="sxs-lookup"><span data-stu-id="bd008-115">The following example creates JSON as a string:</span></span>

```csharp
string json = JsonSerializer.Serialize(weatherForecast);
```

<span data-ttu-id="bd008-116">В следующем примере синхронный код используется для создания JSON-файла:</span><span class="sxs-lookup"><span data-stu-id="bd008-116">The following example uses synchronous code to create a JSON file:</span></span>

```csharp
File.WriteAllText(outputFileName, JsonSerializer.Serialize(weatherForecast));
```

<span data-ttu-id="bd008-117">В следующем примере асинхронный код используется для создания JSON-файла:</span><span class="sxs-lookup"><span data-stu-id="bd008-117">The following example uses asynchronous code to create a JSON file:</span></span>

```csharp
using (FileStream fs = File.Create(outputFileName))
{
    await JsonSerializer.SerializeAsync(fs, weatherForecast);
}
```

<span data-ttu-id="bd008-118">В предыдущих примерах для сериализуемого типа используется определение типа.</span><span class="sxs-lookup"><span data-stu-id="bd008-118">The preceding examples use type inference for the type being serialized.</span></span> <span data-ttu-id="bd008-119">Перегрузка `Serialize()` принимает параметр универсального типа:</span><span class="sxs-lookup"><span data-stu-id="bd008-119">An overload of `Serialize()` takes a generic type parameter:</span></span>

```csharp
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

### <a name="serialization-example"></a><span data-ttu-id="bd008-120">Пример сериализации</span><span class="sxs-lookup"><span data-stu-id="bd008-120">Serialization example</span></span>

<span data-ttu-id="bd008-121">Ниже приведен пример типа, который содержит коллекции и вложенные классы:</span><span class="sxs-lookup"><span data-stu-id="bd008-121">Here's an example type that contains collections and nested classes:</span></span>

```csharp
public class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    public IList<DateTimeOffset> DatesAvailable { get; set;}
    public Dictionary<string, HighLowTemperatures> TemperatureRanges { get; set; }
    public string [] SummaryWords { get; set; }
}

public class HighLowTemperatures
{
    public Temperature High { get; set; }
    public Temperature Low { get; set; }
}

public class Temperature
{
    public int DegreesCelsius { get; set; }
}
```

<span data-ttu-id="bd008-122">Выходные данные JSON из сериализации экземпляра предыдущего типа выглядят так, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="bd008-122">The JSON output from serializing an instance of the preceding type looks like the following example.</span></span> <span data-ttu-id="bd008-123">Выходные данные JSON по умолчанию минифицированные:</span><span class="sxs-lookup"><span data-stu-id="bd008-123">The JSON output is minified by default:</span></span> 

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureC":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":{"DegreesCelsius":20},"Low":{"DegreesCelsius":-10}},"Hot":{"High":{"DegreesCelsius":60},"Low":{"DegreesCelsius":20}}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="bd008-124">В следующем примере показан один и тот же формат JSON, форматированный (т. е. который печатается с пробелами и отступами):</span><span class="sxs-lookup"><span data-stu-id="bd008-124">The following example shows the same JSON, formatted (that is, pretty-printed with whitespace and indentation):</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "TemperatureRanges": {
    "Cold": {
      "High": {
        "DegreesCelsius": 20
      },
      "Low": {
        "DegreesCelsius": -10
      }
    },
    "Hot": {
      "High": {
        "DegreesCelsius": 60
      },
      "Low": {
        "DegreesCelsius": 20
      }
    }
  },
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

### <a name="serialize-to-utf-8"></a><span data-ttu-id="bd008-125">Сериализация в UTF-8</span><span class="sxs-lookup"><span data-stu-id="bd008-125">Serialize to UTF-8</span></span>

<span data-ttu-id="bd008-126">Чтобы выполнить сериализацию в UTF-8, вызовите метод <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="bd008-126">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

```csharp
byte[] jsonUtf8Bytes = JsonSerializer.SerializeToUtf8Bytes<WeatherForecast>(weatherForecast);
```

<span data-ttu-id="bd008-127">Также доступна перегрузка <xref:System.Text.Json.JsonSerializer.Serialize%2A>, которая принимает <xref:System.Text.Json.Utf8JsonWriter>.</span><span class="sxs-lookup"><span data-stu-id="bd008-127">A <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is also available.</span></span>

<span data-ttu-id="bd008-128">Сериализация в UTF-8 происходит примерно на 5-10% быстрее, чем при использовании строковых методов.</span><span class="sxs-lookup"><span data-stu-id="bd008-128">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="bd008-129">Разница заключается в том, что байты (как UTF-8) не нужно преобразовывать в строки (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="bd008-129">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="bd008-130">Поведение сериализации</span><span class="sxs-lookup"><span data-stu-id="bd008-130">Serialization behavior</span></span>

* <span data-ttu-id="bd008-131">По умолчанию все открытые свойства сериализуются.</span><span class="sxs-lookup"><span data-stu-id="bd008-131">By default, all public properties are serialized.</span></span> <span data-ttu-id="bd008-132">Можно [указать свойства для исключения](#exclude-properties-from-serialization).</span><span class="sxs-lookup"><span data-stu-id="bd008-132">You can [specify properties to exclude](#exclude-properties-from-serialization).</span></span>
* <span data-ttu-id="bd008-133">[Кодировщик по умолчанию](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) выводит символы, не входящие в набор ASCII, символы, УЧИТЫВАЮЩие HTML, в диапазоне ASCII и символы, которые должны быть экранированы в соответствии со [спецификацией JSON](https://tools.ietf.org/html/rfc8259#section-7).</span><span class="sxs-lookup"><span data-stu-id="bd008-133">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="bd008-134">По умолчанию JSON — минифицированные.</span><span class="sxs-lookup"><span data-stu-id="bd008-134">By default, JSON is minified.</span></span> <span data-ttu-id="bd008-135">JSON можно [довольно просто распечатать](#serialize-to-formatted-json).</span><span class="sxs-lookup"><span data-stu-id="bd008-135">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="bd008-136">По умолчанию регистр имен JSON соответствует именам .NET.</span><span class="sxs-lookup"><span data-stu-id="bd008-136">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="bd008-137">Можно [настроить регистр имен JSON](#customize-json-names-and-values).</span><span class="sxs-lookup"><span data-stu-id="bd008-137">You can [customize JSON name casing](#customize-json-names-and-values).</span></span>
* <span data-ttu-id="bd008-138">Обнаружены циклические ссылки и создаются исключения.</span><span class="sxs-lookup"><span data-stu-id="bd008-138">Circular references are detected and exceptions thrown.</span></span> <span data-ttu-id="bd008-139">Дополнительные сведения см. в [статье о проблемах циклических ссылок](https://github.com/dotnet/corefx/issues/38579) в репозитории DotNet/Corefx в GitHub.</span><span class="sxs-lookup"><span data-stu-id="bd008-139">For more information, see the [issue on circular references](https://github.com/dotnet/corefx/issues/38579) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="bd008-140">В настоящее время поля исключаются.</span><span class="sxs-lookup"><span data-stu-id="bd008-140">Currently, fields are excluded.</span></span>

<span data-ttu-id="bd008-141">Поддерживаемые типы:</span><span class="sxs-lookup"><span data-stu-id="bd008-141">Supported types include:</span></span>

* <span data-ttu-id="bd008-142">Примитивы .NET, которые сопоставляются с примитивами JavaScript, например числовыми типами, строками и логическими значениями.</span><span class="sxs-lookup"><span data-stu-id="bd008-142">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="bd008-143">Определяемые пользователем [простые старые объекты CLR (POCO)](https://stackoverflow.com/questions/250001/poco-definition).</span><span class="sxs-lookup"><span data-stu-id="bd008-143">User-defined [Plain Old CLR Objects (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).</span></span>
* <span data-ttu-id="bd008-144">Одномерное и зубчатые массивы (`ArrayName[][]`).</span><span class="sxs-lookup"><span data-stu-id="bd008-144">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="bd008-145">`Dictionary<string,TValue>`, где `TValue` — `object`, `JsonElement`или POCO.</span><span class="sxs-lookup"><span data-stu-id="bd008-145">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="bd008-146">Коллекции из следующих пространств имен.</span><span class="sxs-lookup"><span data-stu-id="bd008-146">Collections from the following namespaces.</span></span> <span data-ttu-id="bd008-147">Дополнительные сведения см. в [статье о поддержке коллекций](https://github.com/dotnet/corefx/issues/36643) в репозитории DotNet/corefx на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="bd008-147">For more information, see the [issue on collection support](https://github.com/dotnet/corefx/issues/36643) in the dotnet/corefx repository on GitHub.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

<span data-ttu-id="bd008-148">Можно [реализовать пользовательские преобразователи](system-text-json-converters-how-to.md) для обработки дополнительных типов или предоставления функциональных возможностей, которые не поддерживаются встроенными преобразователями.</span><span class="sxs-lookup"><span data-stu-id="bd008-148">You can [implement custom converters](system-text-json-converters-how-to.md) to handle additional types or provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="bd008-149">Чтение JSON в объектах .NET (десериализация)</span><span class="sxs-lookup"><span data-stu-id="bd008-149">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="bd008-150">Чтобы выполнить десериализацию из строки или файла, вызовите метод <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bd008-150">To deserialize from a string or a file, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="bd008-151">В следующем примере показано чтение JSON из строки:</span><span class="sxs-lookup"><span data-stu-id="bd008-151">The following example reads JSON from a string:</span></span>

```csharp
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(jsonString);
```

<span data-ttu-id="bd008-152">Чтобы выполнить десериализацию из файла с помощью синхронного кода, считайте файл в строку, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="bd008-152">To deserialize from a file by using synchronous code, read the file into a string, as shown in the following example:</span></span>

```csharp
string jsonString = File.ReadAllText(inputFileName);
weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(jsonString);
```

<span data-ttu-id="bd008-153">Чтобы выполнить десериализацию из файла с помощью асинхронного кода, вызовите метод <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A>:</span><span class="sxs-lookup"><span data-stu-id="bd008-153">To deserialize from a file by using asynchronous code, call the <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> method:</span></span>

```csharp
using (FileStream fs = File.OpenRead(inputFileName))
{
    weatherForecast = await JsonSerializer.DeserializeAsync<WeatherForecast>(fs);
}
```

<span data-ttu-id="bd008-154">Пример типа и соответствующий JSON см. в разделе [Пример сериализации](#serialization-example) .</span><span class="sxs-lookup"><span data-stu-id="bd008-154">For an example type and corresponding JSON, see the [Serialization example](#serialization-example) section.</span></span>

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="bd008-155">Десериализация из UTF-8</span><span class="sxs-lookup"><span data-stu-id="bd008-155">Deserialize from UTF-8</span></span>

<span data-ttu-id="bd008-156">Для десериализации из UTF-8 вызовите перегрузку <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>, которая принимает `Utf8JsonReader` или `ReadOnlySpan<byte>`, как показано в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="bd008-156">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples.</span></span> <span data-ttu-id="bd008-157">В примерах предполагается, что JSON находится в массиве байтов с именем jsonUtf8Bytes.</span><span class="sxs-lookup"><span data-stu-id="bd008-157">The examples assume the JSON is in a byte array named jsonUtf8Bytes.</span></span>

```csharp
var readOnlySpan = new ReadOnlySpan<byte>(jsonUtf8Bytes);
weatherForecast = JsonSerializer.Deserialize<WeatherForecastMin>(readOnlySpan);
```

```csharp
var utf8Reader = new Utf8JsonReader(jsonUtf8Bytes);
weatherForecast = JsonSerializer.Deserialize<WeatherForecastMin>(ref utf8Reader);
```

## <a name="deserialization-behavior"></a><span data-ttu-id="bd008-158">Поведение десериализации</span><span class="sxs-lookup"><span data-stu-id="bd008-158">Deserialization behavior</span></span>

* <span data-ttu-id="bd008-159">По умолчанию при сопоставлении имен свойств учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="bd008-159">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="bd008-160">Можно [указать нечувствительность к регистру](#case-insensitive-property-matching).</span><span class="sxs-lookup"><span data-stu-id="bd008-160">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="bd008-161">Если JSON содержит значение для свойства, доступного только для чтения, значение игнорируется и исключение не создается.</span><span class="sxs-lookup"><span data-stu-id="bd008-161">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="bd008-162">Десериализация в ссылочные типы без конструктора, не имеющего параметров, не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="bd008-162">Deserialization to reference types without a parameterless constructor isn't supported.</span></span>
* <span data-ttu-id="bd008-163">Десериализация в неизменяемые объекты или свойства только для чтения не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="bd008-163">Deserialization to immutable objects or read-only properties isn't supported.</span></span> <span data-ttu-id="bd008-164">Дополнительные сведения см. в статье о [проблемах в службе поддержки неизменяемых объектов](https://github.com/dotnet/corefx/issues/38569) в GitHub и [о проблемах с поддержкой свойств только для чтения](https://github.com/dotnet/corefx/issues/38163) в репозитории DotNet/corefx в GitHub.</span><span class="sxs-lookup"><span data-stu-id="bd008-164">For more information, see the GitHub [issue on immutable object support](https://github.com/dotnet/corefx/issues/38569) and the [issue on read-only property support](https://github.com/dotnet/corefx/issues/38163) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="bd008-165">По умолчанию перечисления поддерживаются в виде чисел.</span><span class="sxs-lookup"><span data-stu-id="bd008-165">By default, enums are supported as numbers.</span></span> <span data-ttu-id="bd008-166">[Имена перечислений можно сериализовать как строки](#enums-as-strings).</span><span class="sxs-lookup"><span data-stu-id="bd008-166">You can [serialize enum names as strings](#enums-as-strings).</span></span>
* <span data-ttu-id="bd008-167">Поля не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="bd008-167">Fields aren't supported.</span></span>
* <span data-ttu-id="bd008-168">По умолчанию комментарии или замыкающие запятые в JSON вызывают исключения.</span><span class="sxs-lookup"><span data-stu-id="bd008-168">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="bd008-169">Можно [Разрешить комментарии и завершающие запятые](#allow-comments-and-trailing-commas).</span><span class="sxs-lookup"><span data-stu-id="bd008-169">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas).</span></span>
* <span data-ttu-id="bd008-170">[Максимальная глубина по умолчанию](xref:System.Text.Json.JsonReaderOptions.MaxDepth) — 64.</span><span class="sxs-lookup"><span data-stu-id="bd008-170">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="bd008-171">Вы можете [реализовать пользовательские преобразователи](system-text-json-converters-how-to.md) для предоставления функциональных возможностей, которые не поддерживаются встроенными преобразователями.</span><span class="sxs-lookup"><span data-stu-id="bd008-171">You can [implement custom converters](system-text-json-converters-how-to.md) to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="bd008-172">Сериализовать в форматированный JSON</span><span class="sxs-lookup"><span data-stu-id="bd008-172">Serialize to formatted JSON</span></span>

<span data-ttu-id="bd008-173">Чтобы довольно просто распечатать выходные данные JSON, задайте для <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="bd008-173">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    WriteIndented = true,
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="bd008-174">Ниже приведен пример типа для сериализации и печати выходных данных JSON:</span><span class="sxs-lookup"><span data-stu-id="bd008-174">Here's an example type to be serialized and pretty-printed JSON output:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

## <a name="customize-json-names-and-values"></a><span data-ttu-id="bd008-175">Настройка имен и значений JSON</span><span class="sxs-lookup"><span data-stu-id="bd008-175">Customize JSON names and values</span></span>

<span data-ttu-id="bd008-176">По умолчанию имена и ключи словарей не изменяются в выходных данных JSON, включая регистр.</span><span class="sxs-lookup"><span data-stu-id="bd008-176">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="bd008-177">Значения перечисления представлены в виде чисел.</span><span class="sxs-lookup"><span data-stu-id="bd008-177">Enum values are represented as numbers.</span></span> <span data-ttu-id="bd008-178">В этом разделе объясняется, как выполнять следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="bd008-178">This section explains how to:</span></span>

* <span data-ttu-id="bd008-179">Настройка отдельных имен свойств</span><span class="sxs-lookup"><span data-stu-id="bd008-179">Customize individual property names</span></span>
* <span data-ttu-id="bd008-180">Преобразовать все имена свойств в неоднородный регистр</span><span class="sxs-lookup"><span data-stu-id="bd008-180">Convert all property names to camel case</span></span>
* <span data-ttu-id="bd008-181">Реализация политики именования пользовательских свойств</span><span class="sxs-lookup"><span data-stu-id="bd008-181">Implement a custom property naming policy</span></span>
* <span data-ttu-id="bd008-182">Преобразовать ключи словаря в стиль Camel</span><span class="sxs-lookup"><span data-stu-id="bd008-182">Convert dictionary keys to camel case</span></span>
* <span data-ttu-id="bd008-183">Преобразование перечислений в строки и Camel</span><span class="sxs-lookup"><span data-stu-id="bd008-183">Convert enums to strings and camel case</span></span> 

<span data-ttu-id="bd008-184">Для других сценариев, требующих специальной обработки имен и значений свойств JSON, можно [реализовать пользовательские преобразователи](system-text-json-converters-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="bd008-184">For other scenarios that require special handling of JSON property names and values, you can [implement custom converters](system-text-json-converters-how-to.md).</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="bd008-185">Настройка отдельных имен свойств</span><span class="sxs-lookup"><span data-stu-id="bd008-185">Customize individual property names</span></span>

<span data-ttu-id="bd008-186">Чтобы задать имя отдельных свойств, используйте атрибут [[жсонпропертинаме]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) .</span><span class="sxs-lookup"><span data-stu-id="bd008-186">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="bd008-187">Ниже приведен пример типа для сериализации и результирующего JSON:</span><span class="sxs-lookup"><span data-stu-id="bd008-187">Here's an example type to serialize and resulting JSON:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    [JsonPropertyName("Wind")]
    public int WindSpeed { get; set; }
}
```

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="bd008-188">Имя свойства, заданное этим атрибутом:</span><span class="sxs-lookup"><span data-stu-id="bd008-188">The property name set by this attribute:</span></span>

* <span data-ttu-id="bd008-189">Применяется в обоих направлениях для сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="bd008-189">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="bd008-190">Имеет приоритет над политиками именования свойств.</span><span class="sxs-lookup"><span data-stu-id="bd008-190">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="bd008-191">Использовать прописные буквы для всех имен свойств JSON</span><span class="sxs-lookup"><span data-stu-id="bd008-191">Use camel case for all JSON property names</span></span>

<span data-ttu-id="bd008-192">Чтобы использовать прописные буквы для всех имен свойств JSON, задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> значение `JsonNamingPolicy.CamelCase`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="bd008-192">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="bd008-193">Ниже приведен пример класса для сериализации и вывода JSON.</span><span class="sxs-lookup"><span data-stu-id="bd008-193">Here's an example class to serialize and JSON output:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureCelsius { get; set; }
    public string Summary { get; set; }
    [JsonPropertyName("Wind")]
    public int WindSpeed { get; set; }
}
```

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="bd008-194">Политика именования свойств case:</span><span class="sxs-lookup"><span data-stu-id="bd008-194">The camel case property naming policy:</span></span>

* <span data-ttu-id="bd008-195">Применяется к сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="bd008-195">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="bd008-196">Переопределяется атрибутами `[JsonPropertyName]`.</span><span class="sxs-lookup"><span data-stu-id="bd008-196">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="bd008-197">Именно поэтому имя свойства JSON, `Wind` в примере, не является ни прописным.</span><span class="sxs-lookup"><span data-stu-id="bd008-197">This is why the JSON property name `Wind` in the example is not camel case.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="bd008-198">Использование настраиваемой политики именования свойств JSON</span><span class="sxs-lookup"><span data-stu-id="bd008-198">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="bd008-199">Чтобы использовать пользовательскую политику именования свойств JSON, создайте класс, производный от <xref:System.Text.Json.JsonNamingPolicy>, и переопределите метод <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A>, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="bd008-199">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

```csharp
class UpperCaseNamingPolicy : JsonNamingPolicy
{
    public override string ConvertName(string name)
    {
        return name.ToUpper();
    }
}
```

<span data-ttu-id="bd008-200">Затем задайте для свойства <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> экземпляр класса политики именования:</span><span class="sxs-lookup"><span data-stu-id="bd008-200">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = new UpperCaseNamingPolicy()
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="bd008-201">Ниже приведен пример класса для сериализации и вывода JSON.</span><span class="sxs-lookup"><span data-stu-id="bd008-201">Here's an example class to serialize and JSON output:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    [JsonPropertyName("Wind")]
    public int WindSpeed { get; set; }
}
```

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATUREC": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="bd008-202">Политика именования свойств JSON:</span><span class="sxs-lookup"><span data-stu-id="bd008-202">The JSON property naming policy:</span></span>

* <span data-ttu-id="bd008-203">Применяется к сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="bd008-203">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="bd008-204">Переопределяется атрибутами `[JsonPropertyName]`.</span><span class="sxs-lookup"><span data-stu-id="bd008-204">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="bd008-205">Именно поэтому имя свойства JSON `Wind` в примере — не верхний регистр.</span><span class="sxs-lookup"><span data-stu-id="bd008-205">This is why the JSON property name `Wind` in the example is not upper case.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="bd008-206">Ключи словаря символов в стиле Camel</span><span class="sxs-lookup"><span data-stu-id="bd008-206">Camel case dictionary keys</span></span>

<span data-ttu-id="bd008-207">Если свойство сериализуемого объекта имеет тип `Dictionary<string,TValue>`, `string` ключи можно преобразовать в стиль Camel.</span><span class="sxs-lookup"><span data-stu-id="bd008-207">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="bd008-208">Для этого задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> значение `JsonNamingPolicy.CamelCase`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="bd008-208">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    DictionaryKeyPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="bd008-209">Сериализация объекта с помощью словаря с именем `TemperatureRanges`, имеющего пары "ключ-значение" `"ColdMinTemp", 20` и `"HotMinTemp", 40` привести к выходным данным JSON, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="bd008-209">Serializing an object with a dictionary named `TemperatureRanges` that has key-value pairs `"ColdMinTemp", 20` and `"HotMinTemp", 40` would result in JSON output like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "coldMinTemp": 20,
    "hotMinTemp": 40
  }
}
```

<span data-ttu-id="bd008-210">Политика именования Camel для ключей словаря применяется только к сериализации.</span><span class="sxs-lookup"><span data-stu-id="bd008-210">The camel case naming policy for dictionary keys applies to serialization only.</span></span> <span data-ttu-id="bd008-211">При десериализации словаря ключи будут соответствовать JSON-файлу, даже если для `DictionaryKeyPolicy`указан параметр `JsonNamingPolicy.CamelCase`.</span><span class="sxs-lookup"><span data-stu-id="bd008-211">If you deserialize a dictionary, the keys will match the JSON file even if you specify `JsonNamingPolicy.CamelCase` for the `DictionaryKeyPolicy`.</span></span>

### <a name="enums-as-strings"></a><span data-ttu-id="bd008-212">Перечисление как строки</span><span class="sxs-lookup"><span data-stu-id="bd008-212">Enums as strings</span></span>

<span data-ttu-id="bd008-213">По умолчанию перечисления сериализуются как числа.</span><span class="sxs-lookup"><span data-stu-id="bd008-213">By default, enums are serialized as numbers.</span></span> <span data-ttu-id="bd008-214">Чтобы сериализовать имена перечислений как строки, используйте <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span><span class="sxs-lookup"><span data-stu-id="bd008-214">To serialize enum names as strings, use the <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span></span>

<span data-ttu-id="bd008-215">Например, предположим, что необходимо сериализовать следующий класс, имеющий перечисление:</span><span class="sxs-lookup"><span data-stu-id="bd008-215">For example, suppose you need to serialize the following class that has an enum:</span></span>

```csharp
class WeatherForecastWithEnum
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public Summary Summary { get; set; }
}

public enum Summary
{
    Cold, Cool, Warm, Hot
}
```

<span data-ttu-id="bd008-216">Если сводка имеет `Hot`, по умолчанию сериализованный JSON имеет числовое значение 3:</span><span class="sxs-lookup"><span data-stu-id="bd008-216">If the Summary is `Hot`, by default the serialized JSON has the numeric value 3:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": 3
}
```

<span data-ttu-id="bd008-217">Следующий пример кода сериализует имена перечислений и преобразует их в стиль Camel:</span><span class="sxs-lookup"><span data-stu-id="bd008-217">The following sample code serializes the enum names instead, and converts them to camel case:</span></span>

```csharp
options = new JsonSerializerOptions();
options.Converters.Add(new JsonStringEnumConverter(JsonNamingPolicy.CamelCase));
jsonWithEnumsAsStrings = JsonSerializer.Serialize(weatherForecastWithEnum, options);
```

<span data-ttu-id="bd008-218">Итоговый код JSON выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="bd008-218">The resulting JSON looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "hot"
}
```

<span data-ttu-id="bd008-219">Поддержка перечислений в качестве строк также применяется к десериализации, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="bd008-219">The support for enums as strings applies to deserialization also, as shown in the following example:</span></span>

```csharp
options = new JsonSerializerOptions();
options.Converters.Add(new JsonStringEnumConverter(JsonNamingPolicy.CamelCase));
weatherForecastWithEnum = JsonSerializer.Deserialize<WeatherForecastWithEnum>(jsonWithEnumsAsStrings, options);
```

## <a name="exclude-properties-from-serialization"></a><span data-ttu-id="bd008-220">Исключить свойства из сериализации</span><span class="sxs-lookup"><span data-stu-id="bd008-220">Exclude properties from serialization</span></span>

<span data-ttu-id="bd008-221">По умолчанию все открытые свойства сериализуются.</span><span class="sxs-lookup"><span data-stu-id="bd008-221">By default, all public properties are serialized.</span></span> <span data-ttu-id="bd008-222">Если вы не хотите, чтобы некоторые из них отображались в выходных данных JSON, у вас есть несколько вариантов.</span><span class="sxs-lookup"><span data-stu-id="bd008-222">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="bd008-223">В этом разделе объясняется, как исключить:</span><span class="sxs-lookup"><span data-stu-id="bd008-223">This section explains how to exclude:</span></span>

* <span data-ttu-id="bd008-224">Отдельные свойства</span><span class="sxs-lookup"><span data-stu-id="bd008-224">Individual properties</span></span>
* <span data-ttu-id="bd008-225">Все свойства только для чтения</span><span class="sxs-lookup"><span data-stu-id="bd008-225">All read-only properties</span></span>
* <span data-ttu-id="bd008-226">Все свойства значений NULL</span><span class="sxs-lookup"><span data-stu-id="bd008-226">All null-value properties</span></span> 

### <a name="exclude-individual-properties"></a><span data-ttu-id="bd008-227">Исключить отдельные свойства</span><span class="sxs-lookup"><span data-stu-id="bd008-227">Exclude individual properties</span></span>

<span data-ttu-id="bd008-228">Чтобы игнорировать отдельные свойства, используйте атрибут [[жсонигноре]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) .</span><span class="sxs-lookup"><span data-stu-id="bd008-228">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="bd008-229">Ниже приведен пример типа для сериализации и вывода JSON.</span><span class="sxs-lookup"><span data-stu-id="bd008-229">Here's an example type to serialize and JSON output:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    [JsonIgnore]
    public int WindSpeed { get; set; }
}
```

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

### <a name="exclude-all-read-only-properties"></a><span data-ttu-id="bd008-230">Исключить все свойства только для чтения</span><span class="sxs-lookup"><span data-stu-id="bd008-230">Exclude all read-only properties</span></span>

<span data-ttu-id="bd008-231">Свойство доступно только для чтения, если оно содержит открытый метод получения, но не является открытым методом задания.</span><span class="sxs-lookup"><span data-stu-id="bd008-231">A property is read-only if it contains a public getter but not a public setter.</span></span> <span data-ttu-id="bd008-232">Чтобы исключить все свойства только для чтения, задайте для <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> значение `true`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="bd008-232">To exclude all read-only properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    IgnoreReadOnlyProperties = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="bd008-233">Ниже приведен пример типа для сериализации и вывода JSON.</span><span class="sxs-lookup"><span data-stu-id="bd008-233">Here's an example type to serialize and JSON output:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    public int WindSpeed { get; private set; }
}
```

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="bd008-234">Этот параметр применяется только к сериализации.</span><span class="sxs-lookup"><span data-stu-id="bd008-234">This option applies only to serialization.</span></span> <span data-ttu-id="bd008-235">Во время десериализации свойства, доступные только для чтения, по умолчанию игнорируются.</span><span class="sxs-lookup"><span data-stu-id="bd008-235">During deserialization, read-only properties are ignored by default.</span></span>

### <a name="exclude-all-null-value-properties"></a><span data-ttu-id="bd008-236">Исключить все свойства значений NULL</span><span class="sxs-lookup"><span data-stu-id="bd008-236">Exclude all null value properties</span></span>

<span data-ttu-id="bd008-237">Чтобы исключить все свойства значений NULL, задайте для свойства <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> значение `true`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="bd008-237">To exclude all null value properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    IgnoreNullValues = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="bd008-238">Ниже приведен пример объекта для сериализации и вывода JSON.</span><span class="sxs-lookup"><span data-stu-id="bd008-238">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="bd008-239">свойство;</span><span class="sxs-lookup"><span data-stu-id="bd008-239">Property</span></span> |<span data-ttu-id="bd008-240">значения</span><span class="sxs-lookup"><span data-stu-id="bd008-240">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="bd008-241">дата.</span><span class="sxs-lookup"><span data-stu-id="bd008-241">Date</span></span>    | <span data-ttu-id="bd008-242">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="bd008-242">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="bd008-243">температурек</span><span class="sxs-lookup"><span data-stu-id="bd008-243">TemperatureC</span></span>| <span data-ttu-id="bd008-244">25</span><span class="sxs-lookup"><span data-stu-id="bd008-244">25</span></span> |
| <span data-ttu-id="bd008-245">Сводка</span><span class="sxs-lookup"><span data-stu-id="bd008-245">Summary</span></span>| <span data-ttu-id="bd008-246">null</span><span class="sxs-lookup"><span data-stu-id="bd008-246">null</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25
}
```

<span data-ttu-id="bd008-247">Этот параметр применяется к сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="bd008-247">This setting applies to serialization and deserialization.</span></span> <span data-ttu-id="bd008-248">Сведения о том, как это влияет на десериализацию, см. в разделе [игнорирование значения NULL при десериализации](#ignore-null-when-deserializing).</span><span class="sxs-lookup"><span data-stu-id="bd008-248">For information about its effect on deserialization, see [Ignore null when deserializing](#ignore-null-when-deserializing).</span></span>

## <a name="customize-character-encoding"></a><span data-ttu-id="bd008-249">Настройка кодировки символов</span><span class="sxs-lookup"><span data-stu-id="bd008-249">Customize character encoding</span></span>

<span data-ttu-id="bd008-250">По умолчанию сериализатор выполняет escape-последовательность символов, отличных от ASCII.</span><span class="sxs-lookup"><span data-stu-id="bd008-250">By default, the serializer escapes all non-ASCII characters.</span></span>  <span data-ttu-id="bd008-251">То есть он заменяет их `\uxxxx`, где `xxxxx` является кодом Юникода символа.</span><span class="sxs-lookup"><span data-stu-id="bd008-251">That is, it replaces them with `\uxxxx` where `xxxxx` is the Unicode code of the character.</span></span>  <span data-ttu-id="bd008-252">Например, если для свойства `Summary` задано значение кириллицы жарко, `WeatherForecast` объект сериализуется, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="bd008-252">For example, if the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a><span data-ttu-id="bd008-253">Сериализация наборов символов языка</span><span class="sxs-lookup"><span data-stu-id="bd008-253">Serialize language character sets</span></span>

<span data-ttu-id="bd008-254">Чтобы сериализовать наборы символов одного или нескольких языков, укажите [Диапазоны Юникода](xref:System.Text.Unicode.UnicodeRanges) при создании экземпляра <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="bd008-254">To serialize the character set(s) of one or more languages, specify [Unicode range(s)](xref:System.Text.Unicode.UnicodeRanges) when creating an instance of <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, as shown in the following example:</span></span>

```csharp
using System.Text.Encodings.Web;
using System.Text.Json;
using System.Text.Unicode;
```

```csharp
var options = new JsonSerializerOptions
{
    Encoder = JavaScriptEncoder.Create(UnicodeRanges.Cyrillic, UnicodeRanges.GreekExtended)
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="bd008-255">Этот код выполняет сериализацию символов кириллицы и греческого языка.</span><span class="sxs-lookup"><span data-stu-id="bd008-255">This code serializes Cyrillic and Greek characters.</span></span> <span data-ttu-id="bd008-256">Символы кириллицы показаны в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="bd008-256">Cyrillic characters are shown in the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "жарко",
}
```

<span data-ttu-id="bd008-257">Чтобы указать все языки, используйте <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bd008-257">To specify all languages, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span></span>

### <a name="serialize-specific-characters"></a><span data-ttu-id="bd008-258">Сериализация конкретных символов</span><span class="sxs-lookup"><span data-stu-id="bd008-258">Serialize specific characters</span></span>

<span data-ttu-id="bd008-259">Альтернативой является указание отдельных символов, которые нужно разрешить, без экранирования.</span><span class="sxs-lookup"><span data-stu-id="bd008-259">An alternative is to specify individual characters that you want to allow through without being escaped.</span></span> <span data-ttu-id="bd008-260">В следующем примере сериализуются только первые два символа жарко:</span><span class="sxs-lookup"><span data-stu-id="bd008-260">The following example serializes only the first two characters of жарко:</span></span>

```csharp
using System.Text.Encodings.Web;
using System.Text.Json;
using System.Text.Unicode;
```

```csharp
var encoderSettings = new TextEncoderSettings();
encoderSettings.AllowCharacters('\u0436', '\u0430');
options = new JsonSerializerOptions
{
    Encoder = JavaScriptEncoder.Create(encoderSettings)
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="bd008-261">Ниже приведен пример JSON, созданный с помощью приведенного выше кода.</span><span class="sxs-lookup"><span data-stu-id="bd008-261">Here's an example of JSON produced by the preceding code:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a><span data-ttu-id="bd008-262">Сериализовать все символы</span><span class="sxs-lookup"><span data-stu-id="bd008-262">Serialize all characters</span></span>

<span data-ttu-id="bd008-263">Чтобы избежать экранирования, можно использовать <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="bd008-263">To minimize escaping you can use <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, as shown in the following example:</span></span>

```csharp
using System.Text.Encodings.Web;
using System.Text.Json;
```

```csharp
options = new JsonSerializerOptions
{
    Encoder = JavaScriptEncoder.UnsafeRelaxedJsonEscaping
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

> [!CAUTION]
> <span data-ttu-id="bd008-264">В отличие от кодировщика по умолчанию, кодировщик `UnsafeRelaxedJsonEscaping`:</span><span class="sxs-lookup"><span data-stu-id="bd008-264">Unlike the default encoder, the `UnsafeRelaxedJsonEscaping` encoder:</span></span>
>
> * <span data-ttu-id="bd008-265">Не выполняет escape-символы с учетом HTML, например `<`, `>`, `&`и `'`.</span><span class="sxs-lookup"><span data-stu-id="bd008-265">Doesn't escape HTML-sensitive characters such as `<`, `>`, `&`, and `'`.</span></span>
> * <span data-ttu-id="bd008-266">Не предоставляет каких-либо дополнительных средств защиты от атак XSS или раскрытия информации, например, которые могут быть вызваны клиентом и сервером, который согласен с набором *символов*.</span><span class="sxs-lookup"><span data-stu-id="bd008-266">Doesn't offer any additional defense-in-depth protections against XSS or information disclosure attacks, such as those which might result from the client and server disagreeing on the *charset*.</span></span>
> * <span data-ttu-id="bd008-267">Является более разрешающей, чем кодировщик по умолчанию, для которого разрешено прохождение символов без экранирования.</span><span class="sxs-lookup"><span data-stu-id="bd008-267">Is more permissive than the default encoder on which characters are allowed to pass through unescaped.</span></span>
>
> <span data-ttu-id="bd008-268">Используйте ненадежный кодировщик, только если известно, что клиент будет интерпретировать полученные полезные данные как JSON в кодировке UTF-8.</span><span class="sxs-lookup"><span data-stu-id="bd008-268">Use the unsafe encoder only when it's known that the client will be interpreting the resulting payload as UTF-8 encoded JSON.</span></span> <span data-ttu-id="bd008-269">Например, его можно использовать, если сервер отправляет заголовок ответа `Content-Type: application/json; charset=utf-8`.</span><span class="sxs-lookup"><span data-stu-id="bd008-269">For example, you can use it if the server is sending the response header `Content-Type: application/json; charset=utf-8`.</span></span> <span data-ttu-id="bd008-270">Никогда не разрешайте вывод необработанных `UnsafeRelaxedJsonEscaping` в HTML-страницу или элемент `<script>`.</span><span class="sxs-lookup"><span data-stu-id="bd008-270">Never allow the raw `UnsafeRelaxedJsonEscaping` output to be emitted into an HTML page or a `<script>` element.</span></span>

## <a name="serialize-properties-of-derived-classes"></a><span data-ttu-id="bd008-271">Сериализация свойств производных классов</span><span class="sxs-lookup"><span data-stu-id="bd008-271">Serialize properties of derived classes</span></span>

<span data-ttu-id="bd008-272">Сериализация с помощью полиморфизма не поддерживается при указании во время компиляции типа для сериализации.</span><span class="sxs-lookup"><span data-stu-id="bd008-272">Polymorphic serialization isn't supported when you specify at compile time the type to be serialized.</span></span> <span data-ttu-id="bd008-273">Например, предположим, что у вас есть класс `WeatherForecast` и производный класс `WeatherForecastWithWind`:</span><span class="sxs-lookup"><span data-stu-id="bd008-273">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastWithWind`:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
class WeatherForecastWithWind : WeatherForecast
{
    public int WindSpeed { get; set; }
}
```

<span data-ttu-id="bd008-274">И предположим, что аргумент типа метода `Serialize` во время компиляции `WeatherForecast`:</span><span class="sxs-lookup"><span data-stu-id="bd008-274">And suppose the type argument of the `Serialize` method at compile time is `WeatherForecast`:</span></span>

```csharp
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

<span data-ttu-id="bd008-275">В этом сценарии свойство `WindSpeed` не сериализуется, даже если объект `weatherForecast` фактически является `WeatherForecastWithWind`ным объектом.</span><span class="sxs-lookup"><span data-stu-id="bd008-275">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastWithWind` object.</span></span> <span data-ttu-id="bd008-276">Сериализуются только свойства базового класса:</span><span class="sxs-lookup"><span data-stu-id="bd008-276">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="bd008-277">Это поведение предназначено для предотвращения случайного раскрытия данных в производном от среды CLR типе.</span><span class="sxs-lookup"><span data-stu-id="bd008-277">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="bd008-278">Для сериализации свойств производного типа используйте один из следующих подходов:</span><span class="sxs-lookup"><span data-stu-id="bd008-278">To serialize the properties of the derived type, use one of the following approaches:</span></span>

* <span data-ttu-id="bd008-279">Вызовите перегрузку <xref:System.Text.Json.JsonSerializer.Serialize%2A>, которая позволяет указать тип во время выполнения:</span><span class="sxs-lookup"><span data-stu-id="bd008-279">Call an overload of <xref:System.Text.Json.JsonSerializer.Serialize%2A> that lets you specify the type at runtime:</span></span>

  ```csharp
  json = JsonSerializer.Serialize(weatherForecast, weatherForecast.GetType());
  ```

* <span data-ttu-id="bd008-280">Объявите объект, который должен быть сериализован как `object`.</span><span class="sxs-lookup"><span data-stu-id="bd008-280">Declare the object to be serialized as `object`.</span></span>

  ```csharp
  json = JsonSerializer.Serialize<object>(weatherForecast);
  ```

<span data-ttu-id="bd008-281">В предыдущем примере сценария оба подхода приводят к тому, что `WindSpeed` свойство включается в выходные данные JSON:</span><span class="sxs-lookup"><span data-stu-id="bd008-281">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "WindSpeed": 35
}
```

<span data-ttu-id="bd008-282">Дополнительные сведения о полиморфизмной десериализации см. в разделе [Поддержка полиморфизма](system-text-json-converters-how-to.md#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="bd008-282">For information about polymorphic deserialization, see [Support polymorphic deserialization](system-text-json-converters-how-to.md#support-polymorphic-deserialization).</span></span>

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="bd008-283">Разрешить комментарии и завершающие запятые</span><span class="sxs-lookup"><span data-stu-id="bd008-283">Allow comments and trailing commas</span></span>

<span data-ttu-id="bd008-284">По умолчанию в JSON не допускаются комментарии и конечные запятые.</span><span class="sxs-lookup"><span data-stu-id="bd008-284">By default, comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="bd008-285">Чтобы разрешить комментарии в JSON, задайте для свойства <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> значение `JsonCommentHandling.Skip`.</span><span class="sxs-lookup"><span data-stu-id="bd008-285">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span> <span data-ttu-id="bd008-286">Чтобы разрешить замыкающие запятые, задайте для свойства <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="bd008-286">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="bd008-287">В следующем примере показано, как разрешить оба:</span><span class="sxs-lookup"><span data-stu-id="bd008-287">The following example shows how to allow both:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    ReadCommentHandling = JsonCommentHandling.Skip,
    AllowTrailingCommas = true
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json);
```

<span data-ttu-id="bd008-288">Вот пример JSON с комментариями и завершающей запятой:</span><span class="sxs-lookup"><span data-stu-id="bd008-288">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="bd008-289">Сопоставление свойств без учета регистра</span><span class="sxs-lookup"><span data-stu-id="bd008-289">Case-insensitive property matching</span></span>

<span data-ttu-id="bd008-290">По умолчанию десериализация выполняет поиск совпадения имен свойств с учетом регистра между JSON и свойствами целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="bd008-290">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="bd008-291">Чтобы изменить это поведение, задайте для <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="bd008-291">To change that behavior, set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNameCaseInsensitive = true,
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(weatherForecast, options);
```

<span data-ttu-id="bd008-292">Ниже приведен пример JSON с именами свойств «Case Camel».</span><span class="sxs-lookup"><span data-stu-id="bd008-292">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="bd008-293">Его можно десериализовать в следующий тип, который содержит имена свойств case в стиле Pascal.</span><span class="sxs-lookup"><span data-stu-id="bd008-293">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureC": 25,
  "summary": "Hot",
}
```

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

## <a name="handle-overflow-json"></a><span data-ttu-id="bd008-294">Маркер переполнения токена JSON</span><span class="sxs-lookup"><span data-stu-id="bd008-294">Handle overflow JSON</span></span>

<span data-ttu-id="bd008-295">При десериализации в JSON могут быть получены данные, которые не представлены свойствами целевого типа.</span><span class="sxs-lookup"><span data-stu-id="bd008-295">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="bd008-296">Например, предположим, что целевой тип:</span><span class="sxs-lookup"><span data-stu-id="bd008-296">For example, suppose your target type is this:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

<span data-ttu-id="bd008-297">И JSON для десериализации:</span><span class="sxs-lookup"><span data-stu-id="bd008-297">And the JSON to be deserialized is this:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "temperatureC": 25,
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

<span data-ttu-id="bd008-298">При десериализации JSON, показанного в указанном типе, свойства `DatesAvailable` и `SummaryWords` не будут переходятся и теряются.</span><span class="sxs-lookup"><span data-stu-id="bd008-298">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="bd008-299">Чтобы записать дополнительные данные, такие как эти свойства, примените атрибут [жсонекстенсиондата](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) к свойству типа `Dictionary<string,object>` или `Dictionary<string,JsonElement>`:</span><span class="sxs-lookup"><span data-stu-id="bd008-299">To capture extra data such as these properties, apply the [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    [JsonExtensionData]
    public Dictionary<string, object> ExtensionData { get; set; }
}
```

<span data-ttu-id="bd008-300">При десериализации JSON, показанного ранее, в этот тип данных дополнительные данные становятся парами "ключ-значение" свойства `ExtensionData`:</span><span class="sxs-lookup"><span data-stu-id="bd008-300">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="bd008-301">свойство;</span><span class="sxs-lookup"><span data-stu-id="bd008-301">Property</span></span> |<span data-ttu-id="bd008-302">значения</span><span class="sxs-lookup"><span data-stu-id="bd008-302">Value</span></span>  |<span data-ttu-id="bd008-303">Примечания</span><span class="sxs-lookup"><span data-stu-id="bd008-303">Notes</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="bd008-304">дата.</span><span class="sxs-lookup"><span data-stu-id="bd008-304">Date</span></span>    | <span data-ttu-id="bd008-305">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="bd008-305">8/1/2019 12:00:00 AM -07:00</span></span>||
| <span data-ttu-id="bd008-306">температурек</span><span class="sxs-lookup"><span data-stu-id="bd008-306">TemperatureC</span></span>| <span data-ttu-id="bd008-307">0</span><span class="sxs-lookup"><span data-stu-id="bd008-307">0</span></span> | <span data-ttu-id="bd008-308">Несовпадение с учетом регистра (`temperatureC` в JSON), поэтому свойство не задано.</span><span class="sxs-lookup"><span data-stu-id="bd008-308">Case-sensitive mismatch (`temperatureC` in the JSON), so the property isn't set.</span></span> |
| <span data-ttu-id="bd008-309">Сводка</span><span class="sxs-lookup"><span data-stu-id="bd008-309">Summary</span></span> | <span data-ttu-id="bd008-310">Без</span><span class="sxs-lookup"><span data-stu-id="bd008-310">Hot</span></span> ||
| <span data-ttu-id="bd008-311">ExtensionData</span><span class="sxs-lookup"><span data-stu-id="bd008-311">ExtensionData</span></span> | <span data-ttu-id="bd008-312">Температурек: 25</span><span class="sxs-lookup"><span data-stu-id="bd008-312">temperatureC: 25</span></span> |<span data-ttu-id="bd008-313">Так как регистр не соответствует, это свойство JSON является дополнительным и становится парой "ключ-значение" в словаре.</span><span class="sxs-lookup"><span data-stu-id="bd008-313">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span>|
|| <span data-ttu-id="bd008-314">Датесаваилабле:</span><span class="sxs-lookup"><span data-stu-id="bd008-314">DatesAvailable:</span></span><br>  <span data-ttu-id="bd008-315">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="bd008-315">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="bd008-316">8/2/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="bd008-316">8/2/2019 12:00:00 AM -07:00</span></span> |<span data-ttu-id="bd008-317">Дополнительное свойство из JSON преобразуется в пару "ключ-значение" с массивом в качестве объекта значения.</span><span class="sxs-lookup"><span data-stu-id="bd008-317">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|
| |<span data-ttu-id="bd008-318">Суммаривордс:</span><span class="sxs-lookup"><span data-stu-id="bd008-318">SummaryWords:</span></span><br><span data-ttu-id="bd008-319">Здорово</span><span class="sxs-lookup"><span data-stu-id="bd008-319">Cool</span></span><br><span data-ttu-id="bd008-320">Ветрено</span><span class="sxs-lookup"><span data-stu-id="bd008-320">Windy</span></span><br><span data-ttu-id="bd008-321">хумид</span><span class="sxs-lookup"><span data-stu-id="bd008-321">Humid</span></span> |<span data-ttu-id="bd008-322">Дополнительное свойство из JSON преобразуется в пару "ключ-значение" с массивом в качестве объекта значения.</span><span class="sxs-lookup"><span data-stu-id="bd008-322">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|

<span data-ttu-id="bd008-323">При сериализации целевого объекта пары "ключ-значение" данных расширения становятся свойствами JSON так же, как и во входящем JSON:</span><span class="sxs-lookup"><span data-stu-id="bd008-323">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 0,
  "Summary": "Hot",
  "temperatureC": 25,
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

<span data-ttu-id="bd008-324">Обратите внимание, что имя свойства `ExtensionData` не отображается в JSON.</span><span class="sxs-lookup"><span data-stu-id="bd008-324">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="bd008-325">Такое поведение позволяет JSON выполнить цикл обработки без потери дополнительных данных, которые в противном случае не будут десериализованы.</span><span class="sxs-lookup"><span data-stu-id="bd008-325">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="ignore-null-when-deserializing"></a><span data-ttu-id="bd008-326">Игнорировать null при десериализации</span><span class="sxs-lookup"><span data-stu-id="bd008-326">Ignore null when deserializing</span></span>

<span data-ttu-id="bd008-327">По умолчанию, если свойство в JSON имеет значение null, соответствующему свойству в целевом объекте присваивается значение null.</span><span class="sxs-lookup"><span data-stu-id="bd008-327">By default, if a property in JSON is null, the corresponding property in the target object is set to null.</span></span> <span data-ttu-id="bd008-328">В некоторых сценариях свойство Target может иметь значение по умолчанию, и вы не хотите, чтобы значение NULL переопределяло по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bd008-328">In some scenarios, the target property might have a default value, and you don't want a null value to override the default.</span></span>

<span data-ttu-id="bd008-329">Например, предположим, что целевой объект представляет следующий код:</span><span class="sxs-lookup"><span data-stu-id="bd008-329">For example, suppose the following code represents your target object:</span></span>

```csharp
class WeatherForecastWithDefault
{
    public WeatherForecastWithDefault()
    {
        Summary = "No summary";
    }
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

<span data-ttu-id="bd008-330">Предположим, что десериализуется следующий JSON:</span><span class="sxs-lookup"><span data-stu-id="bd008-330">And suppose the following JSON is deserialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": null,
}
```

<span data-ttu-id="bd008-331">После десериализации свойство `Summary` объекта `WeatherForecastWithDefault` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="bd008-331">After deserialization, the `Summary` property of the `WeatherForecastWithDefault` object is null.</span></span>

<span data-ttu-id="bd008-332">Чтобы изменить это поведение, задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> значение `true`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="bd008-332">To change this behavior, set <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    IgnoreNullValues = true
};
weatherForecast = JsonSerializer.Deserialize<WeatherForecastWithDefault>(json, options);
```

<span data-ttu-id="bd008-333">При использовании этого параметра свойство `Summary` объекта `WeatherForecastWithDefault` является значением по умолчанию "нет сводки" после десериализации.</span><span class="sxs-lookup"><span data-stu-id="bd008-333">With this option, the `Summary` property of the `WeatherForecastWithDefault` object is the default value "No summary" after deserialization.</span></span>

<span data-ttu-id="bd008-334">Значения NULL в JSON пропускаются только в том случае, если они являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="bd008-334">Null values in the JSON are ignored only if they are valid.</span></span> <span data-ttu-id="bd008-335">Значения NULL для типов значений, не допускающих значения NULL, вызывают исключения.</span><span class="sxs-lookup"><span data-stu-id="bd008-335">Null values for non-nullable value types cause exceptions.</span></span> <span data-ttu-id="bd008-336">Дополнительные сведения см. в описании [проблемы с типами значений, не допускающими значения NULL](https://github.com/dotnet/corefx/issues/40922) , в репозитории DotNet/Corefx в GitHub.</span><span class="sxs-lookup"><span data-stu-id="bd008-336">For more information, see the [issue on non-nullable value types](https://github.com/dotnet/corefx/issues/40922) in the dotnet/corefx repository on GitHub.</span></span>

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a><span data-ttu-id="bd008-337">Utf8JsonReader, Utf8JsonWriter и Жсондокумент</span><span class="sxs-lookup"><span data-stu-id="bd008-337">Utf8JsonReader, Utf8JsonWriter, and JsonDocument</span></span>

<span data-ttu-id="bd008-338"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> — это однопроходный модуль чтения текста JSON в кодировке UTF-8 из `ReadOnlySpan<byte>` с высокой производительностью и низким уровнем распределения.</span><span class="sxs-lookup"><span data-stu-id="bd008-338"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>`.</span></span> <span data-ttu-id="bd008-339">`Utf8JsonReader` — это тип низкого уровня, который можно использовать для создания пользовательских средств синтаксического анализа и десериализаторов.</span><span class="sxs-lookup"><span data-stu-id="bd008-339">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="bd008-340">Метод <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> использует `Utf8JsonReader`, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="bd008-340">The <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method uses `Utf8JsonReader` under the covers.</span></span>

<span data-ttu-id="bd008-341"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> — это высокопроизводительный способ записи текста JSON в кодировке UTF-8 из распространенных типов .NET, таких как `String`, `Int32`и `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="bd008-341"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="bd008-342">Модуль записи — это тип низкого уровня, который можно использовать для создания пользовательских сериализаторов.</span><span class="sxs-lookup"><span data-stu-id="bd008-342">The writer is a low-level type that can be used to build custom serializers.</span></span> <span data-ttu-id="bd008-343">Метод <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> использует `Utf8JsonWriter`, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="bd008-343">The <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method uses `Utf8JsonWriter` under the covers.</span></span>

<span data-ttu-id="bd008-344"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> предоставляет возможность создания модель DOM (DOM) только для чтения с помощью `Utf8JsonReader`.</span><span class="sxs-lookup"><span data-stu-id="bd008-344"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> provides the ability to build a read-only Document Object Model (DOM) by using `Utf8JsonReader`.</span></span> <span data-ttu-id="bd008-345">Модель DOM предоставляет произвольный доступ к данным в полезных данных JSON.</span><span class="sxs-lookup"><span data-stu-id="bd008-345">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="bd008-346">Доступ к элементам JSON, составляющим полезные данные, можно получить с помощью типа <xref:System.Text.Json.JsonElement>.</span><span class="sxs-lookup"><span data-stu-id="bd008-346">The JSON elements that compose the payload can be accessed via the <xref:System.Text.Json.JsonElement> type.</span></span> <span data-ttu-id="bd008-347">`JsonElement` предоставляет перечислители массивов и объектов вместе с интерфейсами API для преобразования текста JSON в общие типы .NET.</span><span class="sxs-lookup"><span data-stu-id="bd008-347">The `JsonElement` provides array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="bd008-348">`JsonDocument` предоставляет свойство <xref:System.Text.Json.JsonDocument.RootElement>.</span><span class="sxs-lookup"><span data-stu-id="bd008-348">`JsonDocument` exposes a <xref:System.Text.Json.JsonDocument.RootElement> property.</span></span>

<span data-ttu-id="bd008-349">В следующих разделах показано, как использовать эти средства для чтения и записи данных JSON.</span><span class="sxs-lookup"><span data-stu-id="bd008-349">The following sections show how to use these tools for reading and writing JSON.</span></span>

## <a name="use-jsondocument-for-access-to-data"></a><span data-ttu-id="bd008-350">Использование Жсондокумент для доступа к данным</span><span class="sxs-lookup"><span data-stu-id="bd008-350">Use JsonDocument for access to data</span></span>

<span data-ttu-id="bd008-351">В следующем примере показано, как использовать класс <xref:System.Text.Json.JsonDocument> для произвольного доступа к данным:</span><span class="sxs-lookup"><span data-stu-id="bd008-351">The following example shows how to use the <xref:System.Text.Json.JsonDocument> class for random access to data:</span></span>

```csharp
double sum = 0;
int count = 0;

using (JsonDocument document = JsonDocument.Parse(jsonString))
{
    JsonElement root = document.RootElement;
    JsonElement studentsElement = root.GetProperty("Students");
    foreach (JsonElement student in studentsElement.EnumerateArray())
    {
        if (student.TryGetProperty("Grade", out JsonElement gradeElement))
        {
            sum += gradeElement.GetDouble();
        }
        else
        {
            sum += 70;
        }
        count++;
    }
}

double average = sum / count;
Console.WriteLine($"Average grade: {average}");
```

<span data-ttu-id="bd008-352">Предыдущий код:</span><span class="sxs-lookup"><span data-stu-id="bd008-352">The preceding code:</span></span>

* <span data-ttu-id="bd008-353">Предполагается, что анализируемый JSON находится в строке с именем `jsonString`.</span><span class="sxs-lookup"><span data-stu-id="bd008-353">Assumes the JSON to analyze is in a string named `jsonString`.</span></span>
* <span data-ttu-id="bd008-354">Вычисляет среднее значение для объектов в массиве `Students`, имеющих свойство `Grade`.</span><span class="sxs-lookup"><span data-stu-id="bd008-354">Calculates an average grade for objects in a `Students` array that have a `Grade` property.</span></span> 
* <span data-ttu-id="bd008-355">Назначает значение по умолчанию 70 для учащихся, у которых нет категории.</span><span class="sxs-lookup"><span data-stu-id="bd008-355">Assigns a default grade of 70 for students who don't have a grade.</span></span>
* <span data-ttu-id="bd008-356">Подсчитывает число учащихся путем увеличения `count` переменной с каждой итерацией.</span><span class="sxs-lookup"><span data-stu-id="bd008-356">Counts students by incrementing a `count` variable with each iteration.</span></span> <span data-ttu-id="bd008-357">Альтернативой является вызов <xref:System.Text.Json.JsonElement.GetArrayLength%2A>.</span><span class="sxs-lookup"><span data-stu-id="bd008-357">An alternative is to call <xref:System.Text.Json.JsonElement.GetArrayLength%2A>:</span></span>

  ```csharp
  count = studentsElement.GetArrayLength();
  ```

<span data-ttu-id="bd008-358">Ниже приведен пример JSON, обрабатываемого этим кодом:</span><span class="sxs-lookup"><span data-stu-id="bd008-358">Here's an example of the JSON that this code processes:</span></span>

```json
{
  "Class Name": "Science",
  "Teacher's Name": "Jane",
  "Semester": "2019-01-01",
  "Students": [
    {
      "Name": "John",
      "Grade": 94.3
    },
    {
      "Name": "James",
      "Grade": 81.0
    },
    {
      "Name": "Julia",
      "Grade": 91.9
    },
    {
      "Name": "Jessica",
      "Grade": 72.4
    },
    {
      "Name": "Johnathan"
    }
  ],
  "Final": true
}
```

## <a name="use-jsondocument-to-write-json"></a><span data-ttu-id="bd008-359">Использование Жсондокумент для записи JSON</span><span class="sxs-lookup"><span data-stu-id="bd008-359">Use JsonDocument to write JSON</span></span>

<span data-ttu-id="bd008-360">В следующем примере показано, как записать JSON из <xref:System.Text.Json.JsonDocument>.</span><span class="sxs-lookup"><span data-stu-id="bd008-360">The following example shows how to write JSON from a <xref:System.Text.Json.JsonDocument>:</span></span>

```csharp
string jsonString = File.ReadAllText(inputFileName);

var writerOptions = new JsonWriterOptions { Indented = true };
var documentOptions = new JsonDocumentOptions { CommentHandling = JsonCommentHandling.Skip };

using (FileStream fs = File.Create(outputFileName))
using (var writer = new Utf8JsonWriter(fs, options: writerOptions))
using (JsonDocument document = JsonDocument.Parse(jsonString, documentOptions))
{
    JsonElement root = document.RootElement;

    if (root.ValueKind == JsonValueKind.Object)
    {
        writer.WriteStartObject();
    }
    else
    {
        return;
    }

    foreach (JsonProperty property in root.EnumerateObject())
    {
        property.WriteTo(writer);
    }

    writer.WriteEndObject();

    writer.Flush();
}
```

<span data-ttu-id="bd008-361">Предыдущий код:</span><span class="sxs-lookup"><span data-stu-id="bd008-361">The preceding code:</span></span>

* <span data-ttu-id="bd008-362">Считывает JSON-файл, загружает данные в `JsonDocument`и записывает форматированный (довольно печатный) JSON в файл.</span><span class="sxs-lookup"><span data-stu-id="bd008-362">Reads a JSON file, loads the data into a `JsonDocument`, and writes formatted (pretty-printed) JSON to a file.</span></span>
* <span data-ttu-id="bd008-363">Использует <xref:System.Text.Json.JsonDocumentOptions>, чтобы указать, что комментарии во входном JSON разрешены, но игнорируются.</span><span class="sxs-lookup"><span data-stu-id="bd008-363">Uses <xref:System.Text.Json.JsonDocumentOptions> to specify that comments in the input JSON are allowed but ignored.</span></span>
* <span data-ttu-id="bd008-364">По завершении вызывается <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> для модуля записи.</span><span class="sxs-lookup"><span data-stu-id="bd008-364">When finished, calls <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> on the writer.</span></span> <span data-ttu-id="bd008-365">В качестве альтернативы можно разрешить Автоочистку модуля записи при его удалении.</span><span class="sxs-lookup"><span data-stu-id="bd008-365">An alternative is to let the writer autoflush when it's disposed.</span></span> 

<span data-ttu-id="bd008-366">Ниже приведен пример входных данных JSON для обработки в примере кода:</span><span class="sxs-lookup"><span data-stu-id="bd008-366">Here's an example of JSON input to be processed by the example code:</span></span>

```json
{"Class Name": "Science","Teacher's Name": "Jane","Semester": "2019-01-01","Students": [{"Name": "John","Grade": 94.3},{"Name": "James","Grade": 81.0},{"Name": "Julia","Grade": 91.9},{"Name": "Jessica","Grade": 72.4},{"Name": "Johnathan"}],"Final": true}
```

<span data-ttu-id="bd008-367">В результате получается следующий качественный вывод JSON:</span><span class="sxs-lookup"><span data-stu-id="bd008-367">The result is the following pretty-printed JSON output:</span></span>

```json
{
  "Class Name": "Science",
  "Teacher\u0027s Name": "Jane",
  "Semester": "2019-01-01",
  "Students": [
    {
      "Name": "John",
      "Grade": 94.3
    },
    {
      "Name": "James",
      "Grade": 81.0
    },
    {
      "Name": "Julia",
      "Grade": 91.9
    },
    {
      "Name": "Jessica",
      "Grade": 72.4
    },
    {
      "Name": "Johnathan"
    }
  ],
  "Final": true
}
```

## <a name="use-utf8jsonwriter"></a><span data-ttu-id="bd008-368">Использование Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="bd008-368">Use Utf8JsonWriter</span></span>

<span data-ttu-id="bd008-369">В следующем примере показано, как использовать класс <xref:System.Text.Json.Utf8JsonWriter>:</span><span class="sxs-lookup"><span data-stu-id="bd008-369">The following example shows how to use the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

```csharp
var options = new JsonWriterOptions
{
    Indented = true
};

using (var stream = new MemoryStream())
{
    using (var writer = new Utf8JsonWriter(stream, options))
    {
        writer.WriteStartObject();
        writer.WriteString("date", DateTimeOffset.UtcNow);
        writer.WriteNumber("temp", 42);
        writer.WriteEndObject();
    }

    string json = Encoding.UTF8.GetString(stream.ToArray());
    Console.WriteLine(json);
}
```

## <a name="use-utf8jsonreader"></a><span data-ttu-id="bd008-370">Использование Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="bd008-370">Use Utf8JsonReader</span></span>

<span data-ttu-id="bd008-371">В следующем примере показано, как использовать класс <xref:System.Text.Json.Utf8JsonReader>:</span><span class="sxs-lookup"><span data-stu-id="bd008-371">The following example shows how to use the <xref:System.Text.Json.Utf8JsonReader> class:</span></span>

```csharp
var options = new JsonReaderOptions
{
    AllowTrailingCommas = true,
    CommentHandling = JsonCommentHandling.Skip
};
Utf8JsonReader reader = new Utf8JsonReader(jsonUtf8, options);

while (reader.Read())
{
    Console.Write(reader.TokenType);

    switch (reader.TokenType)
    {
        case JsonTokenType.PropertyName:
        case JsonTokenType.String:
            {
                string text = reader.GetString();
                Console.Write(" ");
                Console.Write(text);
                break;
            }

        case JsonTokenType.Number:
            {
                int value = reader.GetInt32();
                Console.Write(" ");
                Console.Write(value);
                break;
            }

            // Other token types elided for brevity
    }

    Console.WriteLine();
}
```

<span data-ttu-id="bd008-372">В приведенном выше коде предполагается, что `jsonUtf8` переменной является массив байтов, который содержит допустимый формат JSON, закодированный как UTF-8.</span><span class="sxs-lookup"><span data-stu-id="bd008-372">The preceding code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

### <a name="filter-data-using-utf8jsonreader"></a><span data-ttu-id="bd008-373">Фильтрация данных с помощью Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="bd008-373">Filter data using Utf8JsonReader</span></span>

<span data-ttu-id="bd008-374">В следующем примере показано, как синхронно прочитать файл и выполнить поиск значения:</span><span class="sxs-lookup"><span data-stu-id="bd008-374">The following example shows how to read a file synchronously and search for a value:</span></span>

```csharp
class Program
{
    private static readonly byte[] s_nameUtf8 = Encoding.UTF8.GetBytes("name");
    private static readonly byte[] s_universityUtf8 = Encoding.UTF8.GetBytes("University");

    private static void ReaderFromFileSync(string fileName)
    {
         string jsonString = File.ReadAllText(fileName);
         ReadOnlySpan<byte> jsonReadOnlySpan = Encoding.UTF8.GetBytes(jsonString);

        int count = 0;
        int total = 0;

        var json = new Utf8JsonReader(jsonReadOnlySpan, isFinalBlock: true, state: default);

        while (json.Read())
        {
            JsonTokenType tokenType = json.TokenType;

            switch (tokenType)
            {
                case JsonTokenType.StartObject:
                    total++;
                    break;
                case JsonTokenType.PropertyName:
                    if (json.ValueSpan.SequenceEqual(s_nameUtf8))
                    {
                        bool result = json.Read();

                        Debug.Assert(result);  // Assume valid JSON
                        Debug.Assert(json.TokenType == JsonTokenType.String);   // Assume known, valid JSON schema

                        if (json.ValueSpan.EndsWith(s_universityUtf8))
                        {
                            count++;
                        }
                    }
                    break;
            }
        }
        Console.WriteLine($"{count} out of {total} have names that end with 'University'");
    }
}
```

<span data-ttu-id="bd008-375">Предыдущий код:</span><span class="sxs-lookup"><span data-stu-id="bd008-375">The preceding code:</span></span>

* <span data-ttu-id="bd008-376">Предполагается, что файл кодируется как UTF-16 и перекодируется в UTF-8.</span><span class="sxs-lookup"><span data-stu-id="bd008-376">Assumes the file is encoded as UTF-16 and transcodes it into UTF-8.</span></span> <span data-ttu-id="bd008-377">Файл, закодированный как UTF-8, можно прочитать непосредственно в `ReadOnlySpan<byte>`с помощью следующего кода:</span><span class="sxs-lookup"><span data-stu-id="bd008-377">A file encoded as UTF-8 can be read directly into a `ReadOnlySpan<byte>`, by using the following code:</span></span>

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName); 
  ```

* <span data-ttu-id="bd008-378">Предполагается, что JSON содержит массив объектов, и каждый объект может содержать свойство "Name" типа String.</span><span class="sxs-lookup"><span data-stu-id="bd008-378">Assumes the JSON contains an array of objects and each object may contain a "name" property of type string.</span></span>
* <span data-ttu-id="bd008-379">Подсчитывает объекты и `name` значения свойств, заканчивающиеся на университет.</span><span class="sxs-lookup"><span data-stu-id="bd008-379">Counts objects and `name` property values that end with "University".</span></span>

<span data-ttu-id="bd008-380">Ниже приведен пример JSON, который можно считать с помощью приведенного выше кода.</span><span class="sxs-lookup"><span data-stu-id="bd008-380">Here's a JSON sample that the preceding code can read.</span></span> <span data-ttu-id="bd008-381">Полученное итоговое сообщение "2 из 4 имеют имена, заканчивающиеся на" Университет ":</span><span class="sxs-lookup"><span data-stu-id="bd008-381">The resulting summary message is "2 out of 4 have names that end with 'University'":</span></span>

```json
[
  {
    "web_pages": [ "https://contoso.edu/" ],
    "alpha_two_code": "US",
    "state-province": null,
    "country": "United States",
    "domains": [ "contoso.edu" ],
    "name": "Contoso Community College"
  },
  {
    "web_pages": [ "http://fabrikam.edu/" ],
    "alpha_two_code": "US",
    "state-province": null,
    "country": "United States",
    "domains": [ "fabrikam.edu" ],
    "name": "Fabrikam Community College"
  },
  {
    "web_pages": [ "http://www.contosouniversity.edu/" ],
    "alpha_two_code": "US",
    "state-province": null,
    "country": "United States",
    "domains": [ "contosouniversity.edu" ],
    "name": "Contoso University"
  },
  {
    "web_pages": [ "http://www.fabrikamuniversity.edu/" ],
    "alpha_two_code": "US",
    "state-province": null,
    "country": "United States",
    "domains": [ "fabrikamuniversity.edu" ],
    "name": "Fabrikam University"
  }
]
```

## <a name="additional-resources"></a><span data-ttu-id="bd008-382">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="bd008-382">Additional resources</span></span>

* [<span data-ttu-id="bd008-383">Общие сведения о System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="bd008-383">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="bd008-384">Справочник по API System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="bd008-384">System.Text.Json API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="bd008-385">Запись пользовательских преобразователей для System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="bd008-385">Write custom converters for System.Text.Json</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="bd008-386">Поддержка DateTime и DateTimeOffset в System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="bd008-386">DateTime and DateTimeOffset support in System.Text.Json</span></span>](../datetime/system-text-json-support.md)
