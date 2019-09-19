---
title: Как сериализовать JSON-.NET
author: tdykstra
ms.author: tdykstra
ms.date: 09/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 8ccd7afe4abb928e7723aa740507774012fc85d1
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2019
ms.locfileid: "71083112"
---
# <a name="how-to-serialize-json-in-net"></a><span data-ttu-id="8dc7c-102">Как сериализовать JSON в .NET</span><span class="sxs-lookup"><span data-stu-id="8dc7c-102">How to serialize JSON in .NET</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8dc7c-103">Документация по сериализации JSON находится в стадии разработки.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-103">The JSON serialization documentation is under construction.</span></span> <span data-ttu-id="8dc7c-104">В этой статье не рассматриваются все сценарии.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-104">This article doesn't cover all scenarios.</span></span> <span data-ttu-id="8dc7c-105">Дополнительные сведения см. в описании [проблем с System. Text. JSON](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) в репозитории DotNet/Corefx в GitHub, особенно в [формате JSON-функциональность-doc](https://github.com/dotnet/corefx/labels/json-functionality-doc).</span><span class="sxs-lookup"><span data-stu-id="8dc7c-105">For more information, examine [System.Text.Json issues](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) in the dotnet/corefx repository on GitHub, especially those labeled [json-functionality-doc](https://github.com/dotnet/corefx/labels/json-functionality-doc).</span></span>

<span data-ttu-id="8dc7c-106">В этой статье показано, как использовать <xref:System.Text.Json> пространство имен для сериализации и десериализации в нотация объектов JavaScript (JSON) и обратно.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-106">This article shows how to use the <xref:System.Text.Json> namespace to serialize and deserialize to and from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="8dc7c-107">В направлениях и образце кода библиотека используется напрямую, а не с помощью платформы, такой как [ASP.NET Core](/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="8dc7c-107">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

## <a name="namespaces"></a><span data-ttu-id="8dc7c-108">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="8dc7c-108">Namespaces</span></span>

<span data-ttu-id="8dc7c-109"><xref:System.Text.Json> Пространство имен содержит все точки входа и основные типы.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-109">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="8dc7c-110"><xref:System.Text.Json.Serialization> Пространство имен содержит атрибуты и API для сложных сценариев и настройки, характерные для сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-110">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="8dc7c-111">Поэтому в примерах кода, приведенных в этой статье, требуется одна или обе `using` следующие директивы:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-111">Therefore, the code examples shown in this article require one or both of the following `using` directives:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

<span data-ttu-id="8dc7c-112">Атрибуты из <xref:System.Runtime.Serialization> пространства имен в настоящее время не `System.Text.Json`поддерживаются в.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-112">Attributes from the <xref:System.Runtime.Serialization> namespace aren't currently supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="8dc7c-113">Как записывать объекты .NET в JSON (сериализовать)</span><span class="sxs-lookup"><span data-stu-id="8dc7c-113">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="8dc7c-114">Чтобы записать JSON в строку, вызовите <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-114">To write JSON to a string, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="8dc7c-115">В следующем примере используется перегрузка с параметром универсального типа:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-115">The following example uses an overload with a generic type parameter:</span></span>

```csharp
WeatherForecast weatherForecast;
//...
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

<span data-ttu-id="8dc7c-116">Можно опустить параметр универсального типа и вместо этого использовать вывод универсального типа:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-116">You can omit the generic type parameter and use generic type inference instead:</span></span>

```csharp
WeatherForecast weatherForecast;
//...
string json = JsonSerializer.Serialize(weatherForecast);
```

<span data-ttu-id="8dc7c-117">Ниже приведен пример типа для сериализации, который содержит коллекции и вложенные классы:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-117">Here's an example type to be serialized, which contains collections and nested classes:</span></span>

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

<span data-ttu-id="8dc7c-118">Выходные данные JSON по умолчанию минифицированные:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-118">The JSON output is minified by default:</span></span> 

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureC":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":{"DegreesCelsius":20},"Low":{"DegreesCelsius":-10}},"Hot":{"High":{"DegreesCelsius":60},"Low":{"DegreesCelsius":20}}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="8dc7c-119">В следующем примере показан один и тот же формат JSON, форматированный (т. е. который печатается с пробелами и отступами):</span><span class="sxs-lookup"><span data-stu-id="8dc7c-119">The following example shows the same JSON, formatted (that is, pretty-printed with whitespace and indentation):</span></span>

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

<span data-ttu-id="8dc7c-120">Перегрузки <xref:System.Text.Json.JsonSerializer.Serialize%2A> позволяют <xref:System.IO.Stream>выполнять сериализацию в.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-120">Overloads of <xref:System.Text.Json.JsonSerializer.Serialize%2A> let you serialize to a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="8dc7c-121">Доступны асинхронные версии `Stream` перегрузок.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-121">Async versions of the `Stream` overloads are available.</span></span>

### <a name="serialize-to-utf-8"></a><span data-ttu-id="8dc7c-122">Сериализация в UTF-8</span><span class="sxs-lookup"><span data-stu-id="8dc7c-122">Serialize to UTF-8</span></span>

<span data-ttu-id="8dc7c-123">Чтобы выполнить сериализацию в UTF-8, вызовите <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> метод:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-123">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

```csharp
byte[] utf8Json = JsonSerializer.SerializeToUtf8Bytes<WeatherForecast>(weatherForecast);
```

<span data-ttu-id="8dc7c-124">В качестве альтернативы <xref:System.Text.Json.JsonSerializer.Serialize%2A> можно использовать перегрузку <xref:System.Text.Json.Utf8JsonWriter> , которая принимает.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-124">As an alternative, a <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is available.</span></span>

<span data-ttu-id="8dc7c-125">Сериализация в UTF-8 происходит примерно на 5-10% быстрее, чем при использовании строковых методов.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-125">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="8dc7c-126">Разница заключается в том, что байты (как UTF-8) не нужно преобразовывать в строки (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="8dc7c-126">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="8dc7c-127">Поведение сериализации</span><span class="sxs-lookup"><span data-stu-id="8dc7c-127">Serialization behavior</span></span>

* <span data-ttu-id="8dc7c-128">По умолчанию все открытые свойства сериализуются.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-128">By default, all public properties are serialized.</span></span> <span data-ttu-id="8dc7c-129">Можно [указать свойства для исключения](#exclude-properties).</span><span class="sxs-lookup"><span data-stu-id="8dc7c-129">You can [specify properties to exclude](#exclude-properties).</span></span>
* <span data-ttu-id="8dc7c-130">[Кодировщик по умолчанию](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) выводит символы, не входящие в набор ASCII, символы, УЧИТЫВАЮЩие HTML, в диапазоне ASCII и символы, которые должны быть экранированы в соответствии со [спецификацией JSON](https://tools.ietf.org/html/rfc8259#section-7).</span><span class="sxs-lookup"><span data-stu-id="8dc7c-130">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="8dc7c-131">По умолчанию JSON — минифицированные.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-131">By default, JSON is minified.</span></span> <span data-ttu-id="8dc7c-132">JSON можно [довольно просто распечатать](#serialize-to-formatted-json).</span><span class="sxs-lookup"><span data-stu-id="8dc7c-132">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="8dc7c-133">По умолчанию регистр имен JSON соответствует именам .NET.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-133">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="8dc7c-134">Можно [настроить регистр имен JSON](#customize-json-names).</span><span class="sxs-lookup"><span data-stu-id="8dc7c-134">You can [customize JSON name casing](#customize-json-names).</span></span>
* <span data-ttu-id="8dc7c-135">Обнаружены циклические ссылки и создаются исключения.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-135">Circular references are detected and exceptions thrown.</span></span> <span data-ttu-id="8dc7c-136">Дополнительные сведения см. в [статье о проблемах циклических ссылок](https://github.com/dotnet/corefx/issues/38579) в репозитории DotNet/Corefx в GitHub.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-136">For more information, see the [issue on circular references](https://github.com/dotnet/corefx/issues/38579) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="8dc7c-137">В настоящее время поля исключаются.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-137">Currently, fields are excluded.</span></span>

<span data-ttu-id="8dc7c-138">Поддерживаемые типы:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-138">Supported types include:</span></span>

* <span data-ttu-id="8dc7c-139">Примитивы .NET, которые сопоставляются с примитивами JavaScript, например числовыми типами, строками и логическими значениями.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-139">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="8dc7c-140">Определяемые пользователем [простые старые объекты CLR (POCO)](https://stackoverflow.com/questions/250001/poco-definition).</span><span class="sxs-lookup"><span data-stu-id="8dc7c-140">User-defined [Plain Old CLR Objects (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).</span></span>
* <span data-ttu-id="8dc7c-141">Одномерные массивы (`ArrayName[][]`).</span><span class="sxs-lookup"><span data-stu-id="8dc7c-141">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="8dc7c-142">`Dictionary<string,TValue>`где `TValue` — `object` ,`JsonElement`или POCO.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-142">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="8dc7c-143">Коллекции из следующих пространств имен.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-143">Collections from the following namespaces.</span></span> <span data-ttu-id="8dc7c-144">Дополнительные сведения см. в [статье о поддержке коллекций](https://github.com/dotnet/corefx/issues/36643) в репозитории DotNet/corefx на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-144">For more information, see the [issue on collection support](https://github.com/dotnet/corefx/issues/36643) in the dotnet/corefx repository on GitHub.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="8dc7c-145">Чтение JSON в объектах .NET (десериализация)</span><span class="sxs-lookup"><span data-stu-id="8dc7c-145">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="8dc7c-146">Чтобы выполнить десериализацию из строки, вызовите <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> метод, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-146">To deserialize from a string, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method, as shown in the following example:</span></span>

```csharp
string json = ... ;

var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json);
```

<span data-ttu-id="8dc7c-147">Пример см. в разделе « [сериализация](#how-to-write-net-objects-to-json-serialize) ».</span><span class="sxs-lookup"><span data-stu-id="8dc7c-147">For an example, see the [serialize](#how-to-write-net-objects-to-json-serialize) section.</span></span> <span data-ttu-id="8dc7c-148">Объекты JSON и .NET одинаковы, но направление обратно.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-148">The JSON and .NET object are the same, but the direction is reversed.</span></span>

<span data-ttu-id="8dc7c-149">Перегрузки <xref:System.Text.Json.JsonSerializer.Deserialize*> позволяют выполнить десериализацию `Stream`из.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-149">Overloads of <xref:System.Text.Json.JsonSerializer.Deserialize*> let you deserialize from a `Stream`.</span></span>  <span data-ttu-id="8dc7c-150">Доступны асинхронные версии `Stream` перегрузок.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-150">Async versions of the `Stream` overloads are available.</span></span>

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="8dc7c-151">Десериализация из UTF-8</span><span class="sxs-lookup"><span data-stu-id="8dc7c-151">Deserialize from UTF-8</span></span>

<span data-ttu-id="8dc7c-152">Для десериализации из UTF-8 вызовите <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> перегрузку, `Utf8JsonReader` которая принимает `ReadOnlySpan<byte>`или, как показано в следующих примерах:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-152">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples:</span></span>

```csharp
byte[] utf8Json;
//...
var readOnlySpan = new ReadOnlySpan<byte>(utf8Json);
weatherForecast = JsonSerializer.Deserialize<WeatherForecastMin>(readOnlySpan);
```

```csharp
byte[] utf8Json;
//...
var utf8Reader = new Utf8JsonReader(utf8Json);
weatherForecast = JsonSerializer.Deserialize<WeatherForecastMin>(ref utf8Reader);
```

## <a name="deserialization-behavior"></a><span data-ttu-id="8dc7c-153">Поведение десериализации</span><span class="sxs-lookup"><span data-stu-id="8dc7c-153">Deserialization behavior</span></span>

* <span data-ttu-id="8dc7c-154">По умолчанию при сопоставлении имен свойств учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-154">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="8dc7c-155">Можно [указать нечувствительность к регистру](#case-insensitive-property-matching).</span><span class="sxs-lookup"><span data-stu-id="8dc7c-155">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="8dc7c-156">Если JSON содержит значение для свойства, доступного только для чтения, значение игнорируется и исключение не создается.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-156">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="8dc7c-157">Десериализация в ссылочные типы без конструктора, не имеющего параметров, не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-157">Deserialization to reference types without a parameterless constructor isn't supported.</span></span>
* <span data-ttu-id="8dc7c-158">Десериализация в неизменяемые объекты или свойства только для чтения не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-158">Deserialization to immutable objects or read-only properties isn't supported.</span></span> <span data-ttu-id="8dc7c-159">Дополнительные сведения см. в статье о [проблемах в службе поддержки неизменяемых объектов](https://github.com/dotnet/corefx/issues/38569) в GitHub и [о проблемах с поддержкой свойств только для чтения](https://github.com/dotnet/corefx/issues/38163) в репозитории DotNet/corefx в GitHub.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-159">For more information, see the GitHub [issue on immutable object support](https://github.com/dotnet/corefx/issues/38569) and the [issue on read-only property support](https://github.com/dotnet/corefx/issues/38163) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="8dc7c-160">По умолчанию перечисления поддерживаются в виде чисел.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-160">By default, enums are supported as numbers.</span></span>
* <span data-ttu-id="8dc7c-161">Поля не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-161">Fields aren't supported.</span></span>
* <span data-ttu-id="8dc7c-162">По умолчанию комментарии или замыкающие запятые в JSON вызывают исключения.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-162">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="8dc7c-163">При необходимости можно [Разрешить комментарии и конечные запятые](#allow-comments-and-trailing-commas) .</span><span class="sxs-lookup"><span data-stu-id="8dc7c-163">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas) if needed.</span></span>
* <span data-ttu-id="8dc7c-164">[Максимальная глубина по умолчанию](xref:System.Text.Json.JsonReaderOptions.MaxDepth) — 64.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-164">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="8dc7c-165">Сериализовать в форматированный JSON</span><span class="sxs-lookup"><span data-stu-id="8dc7c-165">Serialize to formatted JSON</span></span>

<span data-ttu-id="8dc7c-166">Чтобы довольно просто распечатать выходные данные JSON, задайте <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> для `true`параметра значение:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-166">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    WriteIndented = true,
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="8dc7c-167">Ниже приведен пример типа для сериализации и вывода JSON:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-167">Here's an example type to be serialized and JSON output:</span></span>

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

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="8dc7c-168">Разрешить комментарии и завершающие запятые</span><span class="sxs-lookup"><span data-stu-id="8dc7c-168">Allow comments and trailing commas</span></span>

<span data-ttu-id="8dc7c-169">По умолчанию комментарии и конечные запятые не разрешены в JSON.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-169">By default comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="8dc7c-170">Чтобы разрешить комментарии в JSON, присвойте <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> `JsonCommentHandling.Skip`свойству значение.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-170">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span> <span data-ttu-id="8dc7c-171">Чтобы разрешить замыкающие запятые, присвойте <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> `true`свойству значение.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-171">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="8dc7c-172">В следующем примере показано, как разрешить оба:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-172">The following example shows how to allow both:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    ReadCommentHandling = JsonCommentHandling.Skip,
    AllowTrailingCommas = true
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json);
```

<span data-ttu-id="8dc7c-173">Вот пример JSON с комментариями и завершающей запятой:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-173">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="customize-json-names"></a><span data-ttu-id="8dc7c-174">Настройка имен JSON</span><span class="sxs-lookup"><span data-stu-id="8dc7c-174">Customize JSON names</span></span>

<span data-ttu-id="8dc7c-175">По умолчанию имена и ключи словарей не изменяются в выходных данных JSON, включая регистр.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-175">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="8dc7c-176">В этом разделе объясняется, как выполнять следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-176">This section explains how to:</span></span>

* <span data-ttu-id="8dc7c-177">Настройка отдельных имен свойств</span><span class="sxs-lookup"><span data-stu-id="8dc7c-177">Customize individual property names</span></span>
* <span data-ttu-id="8dc7c-178">Преобразовать все имена свойств в неоднородный регистр</span><span class="sxs-lookup"><span data-stu-id="8dc7c-178">Convert all property names to camel case</span></span>
* <span data-ttu-id="8dc7c-179">Реализация политики именования пользовательских свойств</span><span class="sxs-lookup"><span data-stu-id="8dc7c-179">Implement a custom property naming policy</span></span>
* <span data-ttu-id="8dc7c-180">Преобразовать ключи словаря в стиль Camel</span><span class="sxs-lookup"><span data-stu-id="8dc7c-180">Convert dictionary keys to camel case</span></span>

<span data-ttu-id="8dc7c-181">В настоящее время не поддерживается автоматическое преобразование перечислений в Camel.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-181">Currently, there's no support for automatically converting enums to camel case.</span></span> <span data-ttu-id="8dc7c-182">Дополнительные сведения см. в статье о проблемах, описанных в разделе [о поддержке вариантов перечисления Camel](https://github.com/dotnet/corefx/issues/37725) в репозитории DotNet/Corefx в GitHub.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-182">For more information, see the [issue on enum camel case support](https://github.com/dotnet/corefx/issues/37725) in the dotnet/corefx repository on GitHub.</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="8dc7c-183">Настройка отдельных имен свойств</span><span class="sxs-lookup"><span data-stu-id="8dc7c-183">Customize individual property names</span></span>

<span data-ttu-id="8dc7c-184">Чтобы задать имя отдельных свойств, используйте атрибут [[жсонпропертинаме]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) .</span><span class="sxs-lookup"><span data-stu-id="8dc7c-184">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="8dc7c-185">Ниже приведен пример типа для сериализации и результирующего JSON:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-185">Here's an example type to serialize and resulting JSON:</span></span>

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

<span data-ttu-id="8dc7c-186">Имя свойства, заданное этим атрибутом:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-186">The property name set by this attribute:</span></span>

* <span data-ttu-id="8dc7c-187">Применяется в обоих направлениях для сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-187">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="8dc7c-188">Имеет приоритет над политиками именования свойств.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-188">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="8dc7c-189">Использовать прописные буквы для всех имен свойств JSON</span><span class="sxs-lookup"><span data-stu-id="8dc7c-189">Use camel case for all JSON property names</span></span>

<span data-ttu-id="8dc7c-190">Чтобы использовать прописные буквы для всех имен свойств JSON, <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> задайте `JsonNamingPolicy.CamelCase`для значение, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-190">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="8dc7c-191">Ниже приведен пример класса для сериализации и вывода JSON.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-191">Here's an example class to serialize and JSON output:</span></span>

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
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureC": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="8dc7c-192">Политика именования свойств case:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-192">The camel case property naming policy:</span></span>

* <span data-ttu-id="8dc7c-193">Применяется к сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-193">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="8dc7c-194">Переопределяется `[JsonPropertyName]` атрибутами.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-194">Is overridden by `[JsonPropertyName]` attributes.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="8dc7c-195">Использование настраиваемой политики именования свойств JSON</span><span class="sxs-lookup"><span data-stu-id="8dc7c-195">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="8dc7c-196">Чтобы использовать пользовательскую политику именования свойств JSON, создайте класс, производный от <xref:System.Text.Json.JsonNamingPolicy> , и <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> Переопределите метод, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-196">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

```csharp
class UpperCaseNamingPolicy : JsonNamingPolicy
{
    public override string ConvertName(string name)
    {
        return name.ToUpper();
    }
}
```

<span data-ttu-id="8dc7c-197">Затем задайте <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> для свойства экземпляр класса политики именования:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-197">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = new UpperCaseNamingPolicy()
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="8dc7c-198">Ниже приведен пример класса для сериализации и вывода JSON.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-198">Here's an example class to serialize and JSON output:</span></span>

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

<span data-ttu-id="8dc7c-199">Политика именования свойств JSON:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-199">The JSON property naming policy:</span></span>

* <span data-ttu-id="8dc7c-200">Применяется к сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-200">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="8dc7c-201">Переопределяется `[JsonPropertyName]` атрибутами.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-201">Is overridden by `[JsonPropertyName]` attributes.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="8dc7c-202">Ключи словаря символов в стиле Camel</span><span class="sxs-lookup"><span data-stu-id="8dc7c-202">Camel case dictionary keys</span></span>

<span data-ttu-id="8dc7c-203">Если свойство сериализуемого объекта имеет тип `Dictionary<string,TValue>` `string` , ключи можно преобразовать в стиль Camel.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-203">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="8dc7c-204">Для этого задайте для <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> `JsonNamingPolicy.CamelCase`значение, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-204">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    DictionaryKeyPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="8dc7c-205">Ниже приведен пример объекта для сериализации и вывода JSON.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-205">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="8dc7c-206">Свойство.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-206">Property</span></span> |<span data-ttu-id="8dc7c-207">Значение</span><span class="sxs-lookup"><span data-stu-id="8dc7c-207">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="8dc7c-208">Дата</span><span class="sxs-lookup"><span data-stu-id="8dc7c-208">Date</span></span>    | <span data-ttu-id="8dc7c-209">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="8dc7c-209">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="8dc7c-210">температурек</span><span class="sxs-lookup"><span data-stu-id="8dc7c-210">TemperatureC</span></span>| <span data-ttu-id="8dc7c-211">25</span><span class="sxs-lookup"><span data-stu-id="8dc7c-211">25</span></span> |
| <span data-ttu-id="8dc7c-212">Сводка</span><span class="sxs-lookup"><span data-stu-id="8dc7c-212">Summary</span></span>| <span data-ttu-id="8dc7c-213">Без</span><span class="sxs-lookup"><span data-stu-id="8dc7c-213">Hot</span></span>|
| <span data-ttu-id="8dc7c-214">температуреранжес</span><span class="sxs-lookup"><span data-stu-id="8dc7c-214">TemperatureRanges</span></span> | <span data-ttu-id="8dc7c-215">Холодный, 20</span><span class="sxs-lookup"><span data-stu-id="8dc7c-215">Cold, 20</span></span><br><span data-ttu-id="8dc7c-216">Горячий, 40</span><span class="sxs-lookup"><span data-stu-id="8dc7c-216">Hot, 40</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "cold": 20,
    "hot": 40
  }
}
```

<span data-ttu-id="8dc7c-217">Политика именования Camel применяется только к сериализации.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-217">The camel case naming policy applies to serialization only.</span></span>

## <a name="exclude-properties"></a><span data-ttu-id="8dc7c-218">Исключить свойства</span><span class="sxs-lookup"><span data-stu-id="8dc7c-218">Exclude properties</span></span>

<span data-ttu-id="8dc7c-219">По умолчанию все открытые свойства сериализуются.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-219">By default, all public properties are serialized.</span></span> <span data-ttu-id="8dc7c-220">Если вы не хотите, чтобы некоторые из них отображались в выходных данных JSON, у вас есть несколько вариантов.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-220">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="8dc7c-221">В этом разделе объясняется, как исключить:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-221">This section explains how to exclude:</span></span>

* <span data-ttu-id="8dc7c-222">Отдельные свойства</span><span class="sxs-lookup"><span data-stu-id="8dc7c-222">Individual properties</span></span>
* <span data-ttu-id="8dc7c-223">Все свойства только для чтения</span><span class="sxs-lookup"><span data-stu-id="8dc7c-223">All read-only properties</span></span>
* <span data-ttu-id="8dc7c-224">Все свойства значений NULL</span><span class="sxs-lookup"><span data-stu-id="8dc7c-224">All null-value properties</span></span> 

### <a name="exclude-individual-properties"></a><span data-ttu-id="8dc7c-225">Исключить отдельные свойства</span><span class="sxs-lookup"><span data-stu-id="8dc7c-225">Exclude individual properties</span></span>

<span data-ttu-id="8dc7c-226">Чтобы игнорировать отдельные свойства, используйте атрибут [[жсонигноре]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) .</span><span class="sxs-lookup"><span data-stu-id="8dc7c-226">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="8dc7c-227">Ниже приведен пример типа для сериализации и вывода JSON.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-227">Here's an example type to serialize and JSON output:</span></span>

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

### <a name="exclude-all-read-only-properties"></a><span data-ttu-id="8dc7c-228">Исключить все свойства только для чтения</span><span class="sxs-lookup"><span data-stu-id="8dc7c-228">Exclude all read-only properties</span></span>

<span data-ttu-id="8dc7c-229">Чтобы исключить все свойства только для чтения, задайте <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> для `true`значение, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-229">To exclude all read-only properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    IgnoreReadOnlyProperties = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="8dc7c-230">Ниже приведен пример типа для сериализации и вывода JSON.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-230">Here's an example type to serialize and JSON output:</span></span>

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

<span data-ttu-id="8dc7c-231">Этот параметр применяется только к сериализации.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-231">This option applies only to serialization.</span></span> <span data-ttu-id="8dc7c-232">Во время десериализации свойства, доступные только для чтения, по умолчанию игнорируются.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-232">During deserialization, read-only properties are ignored by default.</span></span> <span data-ttu-id="8dc7c-233">Свойство доступно только для чтения, если оно содержит открытый метод получения, но не является открытым методом задания.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-233">A property is read-only if it contains a public getter but not a public setter.</span></span>

### <a name="exclude-all-null-value-properties"></a><span data-ttu-id="8dc7c-234">Исключить все свойства значений NULL</span><span class="sxs-lookup"><span data-stu-id="8dc7c-234">Exclude all null value properties</span></span>

<span data-ttu-id="8dc7c-235">Чтобы исключить все свойства значений NULL, присвойте <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> `true`свойству значение, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-235">To exclude all null value properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    IgnoreNullValues = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="8dc7c-236">Ниже приведен пример объекта для сериализации и вывода JSON.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-236">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="8dc7c-237">Свойство.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-237">Property</span></span> |<span data-ttu-id="8dc7c-238">Значение</span><span class="sxs-lookup"><span data-stu-id="8dc7c-238">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="8dc7c-239">Дата</span><span class="sxs-lookup"><span data-stu-id="8dc7c-239">Date</span></span>    | <span data-ttu-id="8dc7c-240">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="8dc7c-240">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="8dc7c-241">температурек</span><span class="sxs-lookup"><span data-stu-id="8dc7c-241">TemperatureC</span></span>| <span data-ttu-id="8dc7c-242">25</span><span class="sxs-lookup"><span data-stu-id="8dc7c-242">25</span></span> |
| <span data-ttu-id="8dc7c-243">Сводка</span><span class="sxs-lookup"><span data-stu-id="8dc7c-243">Summary</span></span>| <span data-ttu-id="8dc7c-244">null</span><span class="sxs-lookup"><span data-stu-id="8dc7c-244">null</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25
}
```

<span data-ttu-id="8dc7c-245">Этот параметр применяется к сериализации и десериализации.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-245">This setting applies to serialization and deserialization.</span></span> <span data-ttu-id="8dc7c-246">Во время десериализации значения NULL в JSON пропускаются только в том случае, если они являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-246">During deserialization, null values in the JSON are ignored only if they are valid.</span></span> <span data-ttu-id="8dc7c-247">Значения NULL для типов значений, не допускающих значения NULL, вызывают исключения.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-247">Null values for non-nullable value types cause exceptions.</span></span> <span data-ttu-id="8dc7c-248">Дополнительные сведения см. в описании [проблемы с типами значений, не допускающими значения NULL](https://github.com/dotnet/corefx/issues/40922) , в репозитории DotNet/Corefx в GitHub.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-248">For more information, see the [issue on non-nullable value types](https://github.com/dotnet/corefx/issues/40922) in the dotnet/corefx repository on GitHub.</span></span>

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="8dc7c-249">Сопоставление свойств без учета регистра</span><span class="sxs-lookup"><span data-stu-id="8dc7c-249">Case-insensitive property matching</span></span>

<span data-ttu-id="8dc7c-250">По умолчанию десериализация выполняет поиск совпадения имен свойств с учетом регистра между JSON и свойствами целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-250">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="8dc7c-251">Чтобы изменить это поведение, задайте для <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> `true`свойства значение.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-251">To change that behavior, set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNameCaseInsensitive = true,
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(weatherForecast, options);
```

<span data-ttu-id="8dc7c-252">Ниже приведен пример JSON с именами свойств «Case Camel».</span><span class="sxs-lookup"><span data-stu-id="8dc7c-252">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="8dc7c-253">Его можно десериализовать в следующий тип, который содержит имена свойств case в стиле Pascal.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-253">It can be deserialized into the following type that has Pascal case property names.</span></span>

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

## <a name="include-properties-of-derived-classes"></a><span data-ttu-id="8dc7c-254">Включить свойства производных классов</span><span class="sxs-lookup"><span data-stu-id="8dc7c-254">Include properties of derived classes</span></span>

<span data-ttu-id="8dc7c-255">Сериализация с помощью полиморфизма не поддерживается при указании во время компиляции типа для сериализации.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-255">Polymorphic serialization isn't supported when you specify at compile time the type to be serialized.</span></span> <span data-ttu-id="8dc7c-256">Например, предположим, что у вас `WeatherForecast` есть класс и производный `WeatherForecastWithWind`класс:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-256">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastWithWind`:</span></span>

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

<span data-ttu-id="8dc7c-257">И предположим, что тип, переданный в, или выводимый `Serialize` методом во `WeatherForecast`время компиляции:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-257">And suppose the type passed to, or inferred by, the `Serialize` method at compile time is `WeatherForecast`:</span></span>

```csharp
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

```csharp
WeatherForecast weatherForecast;
//...
json = JsonSerializer.Serialize(weatherForecast);
```

<span data-ttu-id="8dc7c-258">В этом случае `WindSpeed` свойство не сериализуется, даже `weatherForecast` если объект фактически `WeatherForecastWithWind` является объектом.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-258">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastWithWind` object.</span></span> <span data-ttu-id="8dc7c-259">Сериализуются только свойства базового класса:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-259">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="8dc7c-260">Это поведение предназначено для предотвращения случайного раскрытия данных в производном от среды CLR типе.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-260">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="8dc7c-261">Для сериализации свойств производного типа используйте один из следующих подходов:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-261">To serialize the properties of the derived type, use one of the following approaches:</span></span>

* <span data-ttu-id="8dc7c-262">Вызовите перегрузку <xref:System.Text.Json.JsonSerializer.Serialize%2A> , которая позволяет указать тип во время выполнения:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-262">Call an overload of <xref:System.Text.Json.JsonSerializer.Serialize%2A> that lets you specify the type at runtime:</span></span>

  ```csharp
  json = JsonSerializer.Serialize(weatherForecast, weatherForecast.GetType());
  ```

* <span data-ttu-id="8dc7c-263">Объявите объект, который должен быть сериализован `object`как.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-263">Declare the object to be serialized as `object`.</span></span>

  ```csharp
  json = JsonSerializer.Serialize<object>(weatherForecast);
  ```

<span data-ttu-id="8dc7c-264">В предыдущем примере сценария оба подхода приводят к тому `WindSpeed` , что свойство будет включаться в выходные данные JSON:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-264">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "WindSpeed": 35
}
```

## <a name="handle-overflow-json"></a><span data-ttu-id="8dc7c-265">Маркер переполнения токена JSON</span><span class="sxs-lookup"><span data-stu-id="8dc7c-265">Handle overflow JSON</span></span>

<span data-ttu-id="8dc7c-266">При десериализации в JSON могут быть получены данные, которые не представлены свойствами целевого типа.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-266">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="8dc7c-267">Например, предположим, что целевой тип:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-267">For example, suppose your target type is this:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

<span data-ttu-id="8dc7c-268">И JSON для десериализации:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-268">And the JSON to be deserialized is this:</span></span>

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

<span data-ttu-id="8dc7c-269">Если выполнить десериализацию JSON, показанного в указанном типе `DatesAvailable` , `SummaryWords` свойства и будут потеряны.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-269">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="8dc7c-270">Чтобы записать дополнительные данные, такие как эти свойства, примените атрибут [жсонекстенсиондата](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) к свойству типа `Dictionary<string,object>` или `Dictionary<string,JsonElement>`:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-270">To capture extra data such as these properties, apply the [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

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

<span data-ttu-id="8dc7c-271">При десериализации JSON, показанного ранее, в этот тип данных дополнительные данные становятся парами "ключ-значение" `ExtensionData` свойства:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-271">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="8dc7c-272">Свойство.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-272">Property</span></span> |<span data-ttu-id="8dc7c-273">Значение</span><span class="sxs-lookup"><span data-stu-id="8dc7c-273">Value</span></span>  |<span data-ttu-id="8dc7c-274">Примечания</span><span class="sxs-lookup"><span data-stu-id="8dc7c-274">Notes</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="8dc7c-275">Дата</span><span class="sxs-lookup"><span data-stu-id="8dc7c-275">Date</span></span>    | <span data-ttu-id="8dc7c-276">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="8dc7c-276">8/1/2019 12:00:00 AM -07:00</span></span>||
| <span data-ttu-id="8dc7c-277">температурек</span><span class="sxs-lookup"><span data-stu-id="8dc7c-277">TemperatureC</span></span>| <span data-ttu-id="8dc7c-278">0</span><span class="sxs-lookup"><span data-stu-id="8dc7c-278">0</span></span> | <span data-ttu-id="8dc7c-279">Несовпадение с учетом регистра (`temperatureC` в JSON), поэтому свойство не задано.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-279">Case-sensitive mismatch (`temperatureC` in the JSON), so the property isn't set.</span></span> |
| <span data-ttu-id="8dc7c-280">Сводка</span><span class="sxs-lookup"><span data-stu-id="8dc7c-280">Summary</span></span> | <span data-ttu-id="8dc7c-281">Без</span><span class="sxs-lookup"><span data-stu-id="8dc7c-281">Hot</span></span> ||
| <span data-ttu-id="8dc7c-282">ExtensionData</span><span class="sxs-lookup"><span data-stu-id="8dc7c-282">ExtensionData</span></span> | <span data-ttu-id="8dc7c-283">Температурек: 25</span><span class="sxs-lookup"><span data-stu-id="8dc7c-283">temperatureC: 25</span></span> |<span data-ttu-id="8dc7c-284">Так как регистр не соответствует, это свойство JSON является дополнительным и становится парой "ключ-значение" в словаре.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-284">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span>|
|| <span data-ttu-id="8dc7c-285">Датесаваилабле:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-285">DatesAvailable:</span></span><br>  <span data-ttu-id="8dc7c-286">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="8dc7c-286">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="8dc7c-287">8/2/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="8dc7c-287">8/2/2019 12:00:00 AM -07:00</span></span> |<span data-ttu-id="8dc7c-288">Дополнительное свойство из JSON преобразуется в пару "ключ-значение" с массивом в качестве объекта значения.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-288">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|
| |<span data-ttu-id="8dc7c-289">Суммаривордс:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-289">SummaryWords:</span></span><br><span data-ttu-id="8dc7c-290">Здорово</span><span class="sxs-lookup"><span data-stu-id="8dc7c-290">Cool</span></span><br><span data-ttu-id="8dc7c-291">Ветрено</span><span class="sxs-lookup"><span data-stu-id="8dc7c-291">Windy</span></span><br><span data-ttu-id="8dc7c-292">хумид</span><span class="sxs-lookup"><span data-stu-id="8dc7c-292">Humid</span></span> |<span data-ttu-id="8dc7c-293">Дополнительное свойство из JSON преобразуется в пару "ключ-значение" с массивом в качестве объекта значения.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-293">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|

<span data-ttu-id="8dc7c-294">При сериализации целевого объекта пары "ключ-значение" данных расширения становятся свойствами JSON так же, как и во входящем JSON:</span><span class="sxs-lookup"><span data-stu-id="8dc7c-294">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

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

<span data-ttu-id="8dc7c-295">Обратите внимание `ExtensionData` , что имя свойства не отображается в JSON.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-295">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="8dc7c-296">Такое поведение позволяет JSON выполнить цикл обработки без потери дополнительных данных, которые в противном случае не будут десериализованы.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-296">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="use-utf8jsonwriter-directly"></a><span data-ttu-id="8dc7c-297">Использование Utf8JsonWriter напрямую</span><span class="sxs-lookup"><span data-stu-id="8dc7c-297">Use Utf8JsonWriter directly</span></span>

<span data-ttu-id="8dc7c-298">В следующем примере показано, <xref:System.Text.Json.Utf8JsonWriter> как использовать класс напрямую.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-298">The following example shows how to use the <xref:System.Text.Json.Utf8JsonWriter> class directly.</span></span>

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

## <a name="use-utf8jsonreader-directly"></a><span data-ttu-id="8dc7c-299">Использование Utf8JsonReader напрямую</span><span class="sxs-lookup"><span data-stu-id="8dc7c-299">Use Utf8JsonReader directly</span></span>

<span data-ttu-id="8dc7c-300">В следующем примере показано, <xref:System.Text.Json.Utf8JsonReader> как использовать класс напрямую.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-300">The following example shows how to use the <xref:System.Text.Json.Utf8JsonReader> class directly.</span></span> <span data-ttu-id="8dc7c-301">В коде предполагается, `jsonUtf8` что переменная является массивом байтов, который содержит допустимый код JSON, закодированный как UTF-8.</span><span class="sxs-lookup"><span data-stu-id="8dc7c-301">The code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

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

## <a name="additional-resources"></a><span data-ttu-id="8dc7c-302">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="8dc7c-302">Additional resources</span></span>

* [<span data-ttu-id="8dc7c-303">Общие сведения о System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="8dc7c-303">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="8dc7c-304">Справочник по API System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="8dc7c-304">System.Text.Json API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="8dc7c-305">Поддержка DateTime и DateTimeOffset в System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="8dc7c-305">DateTime and DateTimeOffset support in System.Text.Json</span></span>](../datetime/system-text-json-support.md)
