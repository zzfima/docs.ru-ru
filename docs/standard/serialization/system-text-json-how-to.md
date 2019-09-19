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
# <a name="how-to-serialize-json-in-net"></a>Как сериализовать JSON в .NET

> [!IMPORTANT]
> Документация по сериализации JSON находится в стадии разработки. В этой статье не рассматриваются все сценарии. Дополнительные сведения см. в описании [проблем с System. Text. JSON](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) в репозитории DotNet/Corefx в GitHub, особенно в [формате JSON-функциональность-doc](https://github.com/dotnet/corefx/labels/json-functionality-doc).

В этой статье показано, как использовать <xref:System.Text.Json> пространство имен для сериализации и десериализации в нотация объектов JavaScript (JSON) и обратно. В направлениях и образце кода библиотека используется напрямую, а не с помощью платформы, такой как [ASP.NET Core](/aspnet/core/).

## <a name="namespaces"></a>Пространства имен

<xref:System.Text.Json> Пространство имен содержит все точки входа и основные типы. <xref:System.Text.Json.Serialization> Пространство имен содержит атрибуты и API для сложных сценариев и настройки, характерные для сериализации и десериализации. Поэтому в примерах кода, приведенных в этой статье, требуется одна или обе `using` следующие директивы:

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

Атрибуты из <xref:System.Runtime.Serialization> пространства имен в настоящее время не `System.Text.Json`поддерживаются в.

## <a name="how-to-write-net-objects-to-json-serialize"></a>Как записывать объекты .NET в JSON (сериализовать)

Чтобы записать JSON в строку, вызовите <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> метод. В следующем примере используется перегрузка с параметром универсального типа:

```csharp
WeatherForecast weatherForecast;
//...
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

Можно опустить параметр универсального типа и вместо этого использовать вывод универсального типа:

```csharp
WeatherForecast weatherForecast;
//...
string json = JsonSerializer.Serialize(weatherForecast);
```

Ниже приведен пример типа для сериализации, который содержит коллекции и вложенные классы:

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

Выходные данные JSON по умолчанию минифицированные: 

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureC":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":{"DegreesCelsius":20},"Low":{"DegreesCelsius":-10}},"Hot":{"High":{"DegreesCelsius":60},"Low":{"DegreesCelsius":20}}},"SummaryWords":["Cool","Windy","Humid"]}
```

В следующем примере показан один и тот же формат JSON, форматированный (т. е. который печатается с пробелами и отступами):

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

Перегрузки <xref:System.Text.Json.JsonSerializer.Serialize%2A> позволяют <xref:System.IO.Stream>выполнять сериализацию в. Доступны асинхронные версии `Stream` перегрузок.

### <a name="serialize-to-utf-8"></a>Сериализация в UTF-8

Чтобы выполнить сериализацию в UTF-8, вызовите <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> метод:

```csharp
byte[] utf8Json = JsonSerializer.SerializeToUtf8Bytes<WeatherForecast>(weatherForecast);
```

В качестве альтернативы <xref:System.Text.Json.JsonSerializer.Serialize%2A> можно использовать перегрузку <xref:System.Text.Json.Utf8JsonWriter> , которая принимает.

Сериализация в UTF-8 происходит примерно на 5-10% быстрее, чем при использовании строковых методов. Разница заключается в том, что байты (как UTF-8) не нужно преобразовывать в строки (UTF-16).

## <a name="serialization-behavior"></a>Поведение сериализации

* По умолчанию все открытые свойства сериализуются. Можно [указать свойства для исключения](#exclude-properties).
* [Кодировщик по умолчанию](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) выводит символы, не входящие в набор ASCII, символы, УЧИТЫВАЮЩие HTML, в диапазоне ASCII и символы, которые должны быть экранированы в соответствии со [спецификацией JSON](https://tools.ietf.org/html/rfc8259#section-7).
* По умолчанию JSON — минифицированные. JSON можно [довольно просто распечатать](#serialize-to-formatted-json).
* По умолчанию регистр имен JSON соответствует именам .NET. Можно [настроить регистр имен JSON](#customize-json-names).
* Обнаружены циклические ссылки и создаются исключения. Дополнительные сведения см. в [статье о проблемах циклических ссылок](https://github.com/dotnet/corefx/issues/38579) в репозитории DotNet/Corefx в GitHub.
* В настоящее время поля исключаются.

Поддерживаемые типы:

* Примитивы .NET, которые сопоставляются с примитивами JavaScript, например числовыми типами, строками и логическими значениями.
* Определяемые пользователем [простые старые объекты CLR (POCO)](https://stackoverflow.com/questions/250001/poco-definition).
* Одномерные массивы (`ArrayName[][]`).
* `Dictionary<string,TValue>`где `TValue` — `object` ,`JsonElement`или POCO.
* Коллекции из следующих пространств имен. Дополнительные сведения см. в [статье о поддержке коллекций](https://github.com/dotnet/corefx/issues/36643) в репозитории DotNet/corefx на сайте GitHub.
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

## <a name="how-to-read-json-into-net-objects-deserialize"></a>Чтение JSON в объектах .NET (десериализация)

Чтобы выполнить десериализацию из строки, вызовите <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> метод, как показано в следующем примере:

```csharp
string json = ... ;

var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json);
```

Пример см. в разделе « [сериализация](#how-to-write-net-objects-to-json-serialize) ». Объекты JSON и .NET одинаковы, но направление обратно.

Перегрузки <xref:System.Text.Json.JsonSerializer.Deserialize*> позволяют выполнить десериализацию `Stream`из.  Доступны асинхронные версии `Stream` перегрузок.

### <a name="deserialize-from-utf-8"></a>Десериализация из UTF-8

Для десериализации из UTF-8 вызовите <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> перегрузку, `Utf8JsonReader` которая принимает `ReadOnlySpan<byte>`или, как показано в следующих примерах:

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

## <a name="deserialization-behavior"></a>Поведение десериализации

* По умолчанию при сопоставлении имен свойств учитывается регистр. Можно [указать нечувствительность к регистру](#case-insensitive-property-matching).
* Если JSON содержит значение для свойства, доступного только для чтения, значение игнорируется и исключение не создается.
* Десериализация в ссылочные типы без конструктора, не имеющего параметров, не поддерживается.
* Десериализация в неизменяемые объекты или свойства только для чтения не поддерживается. Дополнительные сведения см. в статье о [проблемах в службе поддержки неизменяемых объектов](https://github.com/dotnet/corefx/issues/38569) в GitHub и [о проблемах с поддержкой свойств только для чтения](https://github.com/dotnet/corefx/issues/38163) в репозитории DotNet/corefx в GitHub.
* По умолчанию перечисления поддерживаются в виде чисел.
* Поля не поддерживаются.
* По умолчанию комментарии или замыкающие запятые в JSON вызывают исключения. При необходимости можно [Разрешить комментарии и конечные запятые](#allow-comments-and-trailing-commas) .
* [Максимальная глубина по умолчанию](xref:System.Text.Json.JsonReaderOptions.MaxDepth) — 64.

## <a name="serialize-to-formatted-json"></a>Сериализовать в форматированный JSON

Чтобы довольно просто распечатать выходные данные JSON, задайте <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> для `true`параметра значение:

```csharp
var options = new JsonSerializerOptions
{
    WriteIndented = true,
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

Ниже приведен пример типа для сериализации и вывода JSON:

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

## <a name="allow-comments-and-trailing-commas"></a>Разрешить комментарии и завершающие запятые

По умолчанию комментарии и конечные запятые не разрешены в JSON. Чтобы разрешить комментарии в JSON, присвойте <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> `JsonCommentHandling.Skip`свойству значение. Чтобы разрешить замыкающие запятые, присвойте <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> `true`свойству значение. В следующем примере показано, как разрешить оба:

```csharp
var options = new JsonSerializerOptions
{
    ReadCommentHandling = JsonCommentHandling.Skip,
    AllowTrailingCommas = true
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json);
```

Вот пример JSON с комментариями и завершающей запятой:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="customize-json-names"></a>Настройка имен JSON

По умолчанию имена и ключи словарей не изменяются в выходных данных JSON, включая регистр. В этом разделе объясняется, как выполнять следующие задачи:

* Настройка отдельных имен свойств
* Преобразовать все имена свойств в неоднородный регистр
* Реализация политики именования пользовательских свойств
* Преобразовать ключи словаря в стиль Camel

В настоящее время не поддерживается автоматическое преобразование перечислений в Camel. Дополнительные сведения см. в статье о проблемах, описанных в разделе [о поддержке вариантов перечисления Camel](https://github.com/dotnet/corefx/issues/37725) в репозитории DotNet/Corefx в GitHub.

### <a name="customize-individual-property-names"></a>Настройка отдельных имен свойств

Чтобы задать имя отдельных свойств, используйте атрибут [[жсонпропертинаме]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) .

Ниже приведен пример типа для сериализации и результирующего JSON:

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

Имя свойства, заданное этим атрибутом:

* Применяется в обоих направлениях для сериализации и десериализации.
* Имеет приоритет над политиками именования свойств.

### <a name="use-camel-case-for-all-json-property-names"></a>Использовать прописные буквы для всех имен свойств JSON

Чтобы использовать прописные буквы для всех имен свойств JSON, <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> задайте `JsonNamingPolicy.CamelCase`для значение, как показано в следующем примере:

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

Ниже приведен пример класса для сериализации и вывода JSON.

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

Политика именования свойств case:

* Применяется к сериализации и десериализации.
* Переопределяется `[JsonPropertyName]` атрибутами.

### <a name="use-a-custom-json-property-naming-policy"></a>Использование настраиваемой политики именования свойств JSON

Чтобы использовать пользовательскую политику именования свойств JSON, создайте класс, производный от <xref:System.Text.Json.JsonNamingPolicy> , и <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> Переопределите метод, как показано в следующем примере:

```csharp
class UpperCaseNamingPolicy : JsonNamingPolicy
{
    public override string ConvertName(string name)
    {
        return name.ToUpper();
    }
}
```

Затем задайте <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> для свойства экземпляр класса политики именования:

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = new UpperCaseNamingPolicy()
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

Ниже приведен пример класса для сериализации и вывода JSON.

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

Политика именования свойств JSON:

* Применяется к сериализации и десериализации.
* Переопределяется `[JsonPropertyName]` атрибутами.

### <a name="camel-case-dictionary-keys"></a>Ключи словаря символов в стиле Camel

Если свойство сериализуемого объекта имеет тип `Dictionary<string,TValue>` `string` , ключи можно преобразовать в стиль Camel. Для этого задайте для <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> `JsonNamingPolicy.CamelCase`значение, как показано в следующем примере:

```csharp
var options = new JsonSerializerOptions
{
    DictionaryKeyPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

Ниже приведен пример объекта для сериализации и вывода JSON.

|Свойство. |Значение  |
|---------|---------|
| Дата    | 8/1/2019 12:00:00 AM-07:00|
| температурек| 25 |
| Сводка| Без|
| температуреранжес | Холодный, 20<br>Горячий, 40|

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

Политика именования Camel применяется только к сериализации.

## <a name="exclude-properties"></a>Исключить свойства

По умолчанию все открытые свойства сериализуются. Если вы не хотите, чтобы некоторые из них отображались в выходных данных JSON, у вас есть несколько вариантов. В этом разделе объясняется, как исключить:

* Отдельные свойства
* Все свойства только для чтения
* Все свойства значений NULL 

### <a name="exclude-individual-properties"></a>Исключить отдельные свойства

Чтобы игнорировать отдельные свойства, используйте атрибут [[жсонигноре]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) .

Ниже приведен пример типа для сериализации и вывода JSON.

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

### <a name="exclude-all-read-only-properties"></a>Исключить все свойства только для чтения

Чтобы исключить все свойства только для чтения, задайте <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> для `true`значение, как показано в следующем примере:

```csharp
var options = new JsonSerializerOptions
{
    IgnoreReadOnlyProperties = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

Ниже приведен пример типа для сериализации и вывода JSON.

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

Этот параметр применяется только к сериализации. Во время десериализации свойства, доступные только для чтения, по умолчанию игнорируются. Свойство доступно только для чтения, если оно содержит открытый метод получения, но не является открытым методом задания.

### <a name="exclude-all-null-value-properties"></a>Исключить все свойства значений NULL

Чтобы исключить все свойства значений NULL, присвойте <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> `true`свойству значение, как показано в следующем примере:

```csharp
var options = new JsonSerializerOptions
{
    IgnoreNullValues = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

Ниже приведен пример объекта для сериализации и вывода JSON.

|Свойство. |Значение  |
|---------|---------|
| Дата    | 8/1/2019 12:00:00 AM-07:00|
| температурек| 25 |
| Сводка| null|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25
}
```

Этот параметр применяется к сериализации и десериализации. Во время десериализации значения NULL в JSON пропускаются только в том случае, если они являются допустимыми. Значения NULL для типов значений, не допускающих значения NULL, вызывают исключения. Дополнительные сведения см. в описании [проблемы с типами значений, не допускающими значения NULL](https://github.com/dotnet/corefx/issues/40922) , в репозитории DotNet/Corefx в GitHub.

## <a name="case-insensitive-property-matching"></a>Сопоставление свойств без учета регистра

По умолчанию десериализация выполняет поиск совпадения имен свойств с учетом регистра между JSON и свойствами целевого объекта. Чтобы изменить это поведение, задайте для <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> `true`свойства значение.

```csharp
var options = new JsonSerializerOptions
{
    PropertyNameCaseInsensitive = true,
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(weatherForecast, options);
```

Ниже приведен пример JSON с именами свойств «Case Camel». Его можно десериализовать в следующий тип, который содержит имена свойств case в стиле Pascal.

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

## <a name="include-properties-of-derived-classes"></a>Включить свойства производных классов

Сериализация с помощью полиморфизма не поддерживается при указании во время компиляции типа для сериализации. Например, предположим, что у вас `WeatherForecast` есть класс и производный `WeatherForecastWithWind`класс:

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

И предположим, что тип, переданный в, или выводимый `Serialize` методом во `WeatherForecast`время компиляции:

```csharp
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

```csharp
WeatherForecast weatherForecast;
//...
json = JsonSerializer.Serialize(weatherForecast);
```

В этом случае `WindSpeed` свойство не сериализуется, даже `weatherForecast` если объект фактически `WeatherForecastWithWind` является объектом. Сериализуются только свойства базового класса:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

Это поведение предназначено для предотвращения случайного раскрытия данных в производном от среды CLR типе.

Для сериализации свойств производного типа используйте один из следующих подходов:

* Вызовите перегрузку <xref:System.Text.Json.JsonSerializer.Serialize%2A> , которая позволяет указать тип во время выполнения:

  ```csharp
  json = JsonSerializer.Serialize(weatherForecast, weatherForecast.GetType());
  ```

* Объявите объект, который должен быть сериализован `object`как.

  ```csharp
  json = JsonSerializer.Serialize<object>(weatherForecast);
  ```

В предыдущем примере сценария оба подхода приводят к тому `WindSpeed` , что свойство будет включаться в выходные данные JSON:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "WindSpeed": 35
}
```

## <a name="handle-overflow-json"></a>Маркер переполнения токена JSON

При десериализации в JSON могут быть получены данные, которые не представлены свойствами целевого типа. Например, предположим, что целевой тип:

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

И JSON для десериализации:

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

Если выполнить десериализацию JSON, показанного в указанном типе `DatesAvailable` , `SummaryWords` свойства и будут потеряны. Чтобы записать дополнительные данные, такие как эти свойства, примените атрибут [жсонекстенсиондата](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) к свойству типа `Dictionary<string,object>` или `Dictionary<string,JsonElement>`:

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

При десериализации JSON, показанного ранее, в этот тип данных дополнительные данные становятся парами "ключ-значение" `ExtensionData` свойства:

|Свойство. |Значение  |Примечания  |
|---------|---------|---------|
| Дата    | 8/1/2019 12:00:00 AM-07:00||
| температурек| 0 | Несовпадение с учетом регистра (`temperatureC` в JSON), поэтому свойство не задано. |
| Сводка | Без ||
| ExtensionData | Температурек: 25 |Так как регистр не соответствует, это свойство JSON является дополнительным и становится парой "ключ-значение" в словаре.|
|| Датесаваилабле:<br>  8/1/2019 12:00:00 AM-07:00<br>8/2/2019 12:00:00 AM-07:00 |Дополнительное свойство из JSON преобразуется в пару "ключ-значение" с массивом в качестве объекта значения.|
| |Суммаривордс:<br>Здорово<br>Ветрено<br>хумид |Дополнительное свойство из JSON преобразуется в пару "ключ-значение" с массивом в качестве объекта значения.|

При сериализации целевого объекта пары "ключ-значение" данных расширения становятся свойствами JSON так же, как и во входящем JSON:

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

Обратите внимание `ExtensionData` , что имя свойства не отображается в JSON. Такое поведение позволяет JSON выполнить цикл обработки без потери дополнительных данных, которые в противном случае не будут десериализованы.

## <a name="use-utf8jsonwriter-directly"></a>Использование Utf8JsonWriter напрямую

В следующем примере показано, <xref:System.Text.Json.Utf8JsonWriter> как использовать класс напрямую.

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

## <a name="use-utf8jsonreader-directly"></a>Использование Utf8JsonReader напрямую

В следующем примере показано, <xref:System.Text.Json.Utf8JsonReader> как использовать класс напрямую. В коде предполагается, `jsonUtf8` что переменная является массивом байтов, который содержит допустимый код JSON, закодированный как UTF-8.

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

## <a name="additional-resources"></a>Дополнительные ресурсы

* [Общие сведения о System. Text. JSON](system-text-json-overview.md)
* [Справочник по API System. Text. JSON](xref:System.Text.Json)
* [Поддержка DateTime и DateTimeOffset в System. Text. JSON](../datetime/system-text-json-support.md)
