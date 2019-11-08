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
# <a name="how-to-serialize-and-deserialize-json-in-net"></a>Как сериализовать и десериализовать JSON в .NET

> [!IMPORTANT]
> Документация по сериализации JSON находится в стадии разработки. В этой статье не рассматриваются все сценарии. Дополнительные сведения см. в описании [проблем с System. Text. JSON](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) в репозитории DotNet/Corefx в GitHub, особенно в [формате JSON-функциональность-doc](https://github.com/dotnet/corefx/labels/json-functionality-doc).

В этой статье показано, как использовать пространство имен <xref:System.Text.Json> для сериализации и десериализации в нотация объектов JavaScript (JSON) и обратно. В направлениях и образце кода библиотека используется напрямую, а не с помощью платформы, такой как [ASP.NET Core](/aspnet/core/).

## <a name="namespaces"></a>Пространства имен

Пространство имен <xref:System.Text.Json> содержит все точки входа и основные типы. Пространство имен <xref:System.Text.Json.Serialization> содержит атрибуты и интерфейсы API для сложных сценариев и настройки, характерные для сериализации и десериализации. В примерах кода, приведенных в этой статье, требуются директивы `using` для одного или обоих пространств имен:

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

Атрибуты из пространства имен <xref:System.Runtime.Serialization> в настоящее время не поддерживаются в `System.Text.Json`.

## <a name="how-to-write-net-objects-to-json-serialize"></a>Как записывать объекты .NET в JSON (сериализовать)

Чтобы записать JSON в строку или в файл, вызовите метод <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>.

В следующем примере показано создание JSON в виде строки:

```csharp
string json = JsonSerializer.Serialize(weatherForecast);
```

В следующем примере синхронный код используется для создания JSON-файла:

```csharp
File.WriteAllText(outputFileName, JsonSerializer.Serialize(weatherForecast));
```

В следующем примере асинхронный код используется для создания JSON-файла:

```csharp
using (FileStream fs = File.Create(outputFileName))
{
    await JsonSerializer.SerializeAsync(fs, weatherForecast);
}
```

В предыдущих примерах для сериализуемого типа используется определение типа. Перегрузка `Serialize()` принимает параметр универсального типа:

```csharp
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

### <a name="serialization-example"></a>Пример сериализации

Ниже приведен пример типа, который содержит коллекции и вложенные классы:

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

Выходные данные JSON из сериализации экземпляра предыдущего типа выглядят так, как показано в следующем примере. Выходные данные JSON по умолчанию минифицированные: 

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

### <a name="serialize-to-utf-8"></a>Сериализация в UTF-8

Чтобы выполнить сериализацию в UTF-8, вызовите метод <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>:

```csharp
byte[] jsonUtf8Bytes = JsonSerializer.SerializeToUtf8Bytes<WeatherForecast>(weatherForecast);
```

Также доступна перегрузка <xref:System.Text.Json.JsonSerializer.Serialize%2A>, которая принимает <xref:System.Text.Json.Utf8JsonWriter>.

Сериализация в UTF-8 происходит примерно на 5-10% быстрее, чем при использовании строковых методов. Разница заключается в том, что байты (как UTF-8) не нужно преобразовывать в строки (UTF-16).

## <a name="serialization-behavior"></a>Поведение сериализации

* По умолчанию все открытые свойства сериализуются. Можно [указать свойства для исключения](#exclude-properties-from-serialization).
* [Кодировщик по умолчанию](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) выводит символы, не входящие в набор ASCII, символы, УЧИТЫВАЮЩие HTML, в диапазоне ASCII и символы, которые должны быть экранированы в соответствии со [спецификацией JSON](https://tools.ietf.org/html/rfc8259#section-7).
* По умолчанию JSON — минифицированные. JSON можно [довольно просто распечатать](#serialize-to-formatted-json).
* По умолчанию регистр имен JSON соответствует именам .NET. Можно [настроить регистр имен JSON](#customize-json-names-and-values).
* Обнаружены циклические ссылки и создаются исключения. Дополнительные сведения см. в [статье о проблемах циклических ссылок](https://github.com/dotnet/corefx/issues/38579) в репозитории DotNet/Corefx в GitHub.
* В настоящее время поля исключаются.

Поддерживаемые типы:

* Примитивы .NET, которые сопоставляются с примитивами JavaScript, например числовыми типами, строками и логическими значениями.
* Определяемые пользователем [простые старые объекты CLR (POCO)](https://stackoverflow.com/questions/250001/poco-definition).
* Одномерное и зубчатые массивы (`ArrayName[][]`).
* `Dictionary<string,TValue>`, где `TValue` — `object`, `JsonElement`или POCO.
* Коллекции из следующих пространств имен. Дополнительные сведения см. в [статье о поддержке коллекций](https://github.com/dotnet/corefx/issues/36643) в репозитории DotNet/corefx на сайте GitHub.
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

Можно [реализовать пользовательские преобразователи](system-text-json-converters-how-to.md) для обработки дополнительных типов или предоставления функциональных возможностей, которые не поддерживаются встроенными преобразователями.

## <a name="how-to-read-json-into-net-objects-deserialize"></a>Чтение JSON в объектах .NET (десериализация)

Чтобы выполнить десериализацию из строки или файла, вызовите метод <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>.

В следующем примере показано чтение JSON из строки:

```csharp
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(jsonString);
```

Чтобы выполнить десериализацию из файла с помощью синхронного кода, считайте файл в строку, как показано в следующем примере:

```csharp
string jsonString = File.ReadAllText(inputFileName);
weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(jsonString);
```

Чтобы выполнить десериализацию из файла с помощью асинхронного кода, вызовите метод <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A>:

```csharp
using (FileStream fs = File.OpenRead(inputFileName))
{
    weatherForecast = await JsonSerializer.DeserializeAsync<WeatherForecast>(fs);
}
```

Пример типа и соответствующий JSON см. в разделе [Пример сериализации](#serialization-example) .

### <a name="deserialize-from-utf-8"></a>Десериализация из UTF-8

Для десериализации из UTF-8 вызовите перегрузку <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>, которая принимает `Utf8JsonReader` или `ReadOnlySpan<byte>`, как показано в следующих примерах. В примерах предполагается, что JSON находится в массиве байтов с именем jsonUtf8Bytes.

```csharp
var readOnlySpan = new ReadOnlySpan<byte>(jsonUtf8Bytes);
weatherForecast = JsonSerializer.Deserialize<WeatherForecastMin>(readOnlySpan);
```

```csharp
var utf8Reader = new Utf8JsonReader(jsonUtf8Bytes);
weatherForecast = JsonSerializer.Deserialize<WeatherForecastMin>(ref utf8Reader);
```

## <a name="deserialization-behavior"></a>Поведение десериализации

* По умолчанию при сопоставлении имен свойств учитывается регистр. Можно [указать нечувствительность к регистру](#case-insensitive-property-matching).
* Если JSON содержит значение для свойства, доступного только для чтения, значение игнорируется и исключение не создается.
* Десериализация в ссылочные типы без конструктора, не имеющего параметров, не поддерживается.
* Десериализация в неизменяемые объекты или свойства только для чтения не поддерживается. Дополнительные сведения см. в статье о [проблемах в службе поддержки неизменяемых объектов](https://github.com/dotnet/corefx/issues/38569) в GitHub и [о проблемах с поддержкой свойств только для чтения](https://github.com/dotnet/corefx/issues/38163) в репозитории DotNet/corefx в GitHub.
* По умолчанию перечисления поддерживаются в виде чисел. [Имена перечислений можно сериализовать как строки](#enums-as-strings).
* Поля не поддерживаются.
* По умолчанию комментарии или замыкающие запятые в JSON вызывают исключения. Можно [Разрешить комментарии и завершающие запятые](#allow-comments-and-trailing-commas).
* [Максимальная глубина по умолчанию](xref:System.Text.Json.JsonReaderOptions.MaxDepth) — 64.

Вы можете [реализовать пользовательские преобразователи](system-text-json-converters-how-to.md) для предоставления функциональных возможностей, которые не поддерживаются встроенными преобразователями.

## <a name="serialize-to-formatted-json"></a>Сериализовать в форматированный JSON

Чтобы довольно просто распечатать выходные данные JSON, задайте для <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> значение `true`.

```csharp
var options = new JsonSerializerOptions
{
    WriteIndented = true,
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

Ниже приведен пример типа для сериализации и печати выходных данных JSON:

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

## <a name="customize-json-names-and-values"></a>Настройка имен и значений JSON

По умолчанию имена и ключи словарей не изменяются в выходных данных JSON, включая регистр. Значения перечисления представлены в виде чисел. В этом разделе объясняется, как выполнять следующие задачи:

* Настройка отдельных имен свойств
* Преобразовать все имена свойств в неоднородный регистр
* Реализация политики именования пользовательских свойств
* Преобразовать ключи словаря в стиль Camel
* Преобразование перечислений в строки и Camel 

Для других сценариев, требующих специальной обработки имен и значений свойств JSON, можно [реализовать пользовательские преобразователи](system-text-json-converters-how-to.md).

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

Чтобы использовать прописные буквы для всех имен свойств JSON, задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> значение `JsonNamingPolicy.CamelCase`, как показано в следующем примере:

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

Политика именования свойств case:

* Применяется к сериализации и десериализации.
* Переопределяется атрибутами `[JsonPropertyName]`. Именно поэтому имя свойства JSON, `Wind` в примере, не является ни прописным.

### <a name="use-a-custom-json-property-naming-policy"></a>Использование настраиваемой политики именования свойств JSON

Чтобы использовать пользовательскую политику именования свойств JSON, создайте класс, производный от <xref:System.Text.Json.JsonNamingPolicy>, и переопределите метод <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A>, как показано в следующем примере:

```csharp
class UpperCaseNamingPolicy : JsonNamingPolicy
{
    public override string ConvertName(string name)
    {
        return name.ToUpper();
    }
}
```

Затем задайте для свойства <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> экземпляр класса политики именования:

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
* Переопределяется атрибутами `[JsonPropertyName]`. Именно поэтому имя свойства JSON `Wind` в примере — не верхний регистр.

### <a name="camel-case-dictionary-keys"></a>Ключи словаря символов в стиле Camel

Если свойство сериализуемого объекта имеет тип `Dictionary<string,TValue>`, `string` ключи можно преобразовать в стиль Camel. Для этого задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> значение `JsonNamingPolicy.CamelCase`, как показано в следующем примере:

```csharp
var options = new JsonSerializerOptions
{
    DictionaryKeyPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

Сериализация объекта с помощью словаря с именем `TemperatureRanges`, имеющего пары "ключ-значение" `"ColdMinTemp", 20` и `"HotMinTemp", 40` привести к выходным данным JSON, как в следующем примере:

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

Политика именования Camel для ключей словаря применяется только к сериализации. При десериализации словаря ключи будут соответствовать JSON-файлу, даже если для `DictionaryKeyPolicy`указан параметр `JsonNamingPolicy.CamelCase`.

### <a name="enums-as-strings"></a>Перечисление как строки

По умолчанию перечисления сериализуются как числа. Чтобы сериализовать имена перечислений как строки, используйте <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.

Например, предположим, что необходимо сериализовать следующий класс, имеющий перечисление:

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

Если сводка имеет `Hot`, по умолчанию сериализованный JSON имеет числовое значение 3:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": 3
}
```

Следующий пример кода сериализует имена перечислений и преобразует их в стиль Camel:

```csharp
options = new JsonSerializerOptions();
options.Converters.Add(new JsonStringEnumConverter(JsonNamingPolicy.CamelCase));
jsonWithEnumsAsStrings = JsonSerializer.Serialize(weatherForecastWithEnum, options);
```

Итоговый код JSON выглядит следующим образом:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "hot"
}
```

Поддержка перечислений в качестве строк также применяется к десериализации, как показано в следующем примере:

```csharp
options = new JsonSerializerOptions();
options.Converters.Add(new JsonStringEnumConverter(JsonNamingPolicy.CamelCase));
weatherForecastWithEnum = JsonSerializer.Deserialize<WeatherForecastWithEnum>(jsonWithEnumsAsStrings, options);
```

## <a name="exclude-properties-from-serialization"></a>Исключить свойства из сериализации

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

Свойство доступно только для чтения, если оно содержит открытый метод получения, но не является открытым методом задания. Чтобы исключить все свойства только для чтения, задайте для <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> значение `true`, как показано в следующем примере:

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

Этот параметр применяется только к сериализации. Во время десериализации свойства, доступные только для чтения, по умолчанию игнорируются.

### <a name="exclude-all-null-value-properties"></a>Исключить все свойства значений NULL

Чтобы исключить все свойства значений NULL, задайте для свойства <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> значение `true`, как показано в следующем примере:

```csharp
var options = new JsonSerializerOptions
{
    IgnoreNullValues = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

Ниже приведен пример объекта для сериализации и вывода JSON.

|свойство; |значения  |
|---------|---------|
| дата.    | 8/1/2019 12:00:00 AM-07:00|
| температурек| 25 |
| Сводка| null|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25
}
```

Этот параметр применяется к сериализации и десериализации. Сведения о том, как это влияет на десериализацию, см. в разделе [игнорирование значения NULL при десериализации](#ignore-null-when-deserializing).

## <a name="customize-character-encoding"></a>Настройка кодировки символов

По умолчанию сериализатор выполняет escape-последовательность символов, отличных от ASCII.  То есть он заменяет их `\uxxxx`, где `xxxxx` является кодом Юникода символа.  Например, если для свойства `Summary` задано значение кириллицы жарко, `WeatherForecast` объект сериализуется, как показано в следующем примере:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a>Сериализация наборов символов языка

Чтобы сериализовать наборы символов одного или нескольких языков, укажите [Диапазоны Юникода](xref:System.Text.Unicode.UnicodeRanges) при создании экземпляра <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, как показано в следующем примере:

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

Этот код выполняет сериализацию символов кириллицы и греческого языка. Символы кириллицы показаны в следующем примере:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "жарко",
}
```

Чтобы указать все языки, используйте <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.

### <a name="serialize-specific-characters"></a>Сериализация конкретных символов

Альтернативой является указание отдельных символов, которые нужно разрешить, без экранирования. В следующем примере сериализуются только первые два символа жарко:

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

Ниже приведен пример JSON, созданный с помощью приведенного выше кода.

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a>Сериализовать все символы

Чтобы избежать экранирования, можно использовать <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, как показано в следующем примере:

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
> В отличие от кодировщика по умолчанию, кодировщик `UnsafeRelaxedJsonEscaping`:
>
> * Не выполняет escape-символы с учетом HTML, например `<`, `>`, `&`и `'`.
> * Не предоставляет каких-либо дополнительных средств защиты от атак XSS или раскрытия информации, например, которые могут быть вызваны клиентом и сервером, который согласен с набором *символов*.
> * Является более разрешающей, чем кодировщик по умолчанию, для которого разрешено прохождение символов без экранирования.
>
> Используйте ненадежный кодировщик, только если известно, что клиент будет интерпретировать полученные полезные данные как JSON в кодировке UTF-8. Например, его можно использовать, если сервер отправляет заголовок ответа `Content-Type: application/json; charset=utf-8`. Никогда не разрешайте вывод необработанных `UnsafeRelaxedJsonEscaping` в HTML-страницу или элемент `<script>`.

## <a name="serialize-properties-of-derived-classes"></a>Сериализация свойств производных классов

Сериализация с помощью полиморфизма не поддерживается при указании во время компиляции типа для сериализации. Например, предположим, что у вас есть класс `WeatherForecast` и производный класс `WeatherForecastWithWind`:

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

И предположим, что аргумент типа метода `Serialize` во время компиляции `WeatherForecast`:

```csharp
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

В этом сценарии свойство `WindSpeed` не сериализуется, даже если объект `weatherForecast` фактически является `WeatherForecastWithWind`ным объектом. Сериализуются только свойства базового класса:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

Это поведение предназначено для предотвращения случайного раскрытия данных в производном от среды CLR типе.

Для сериализации свойств производного типа используйте один из следующих подходов:

* Вызовите перегрузку <xref:System.Text.Json.JsonSerializer.Serialize%2A>, которая позволяет указать тип во время выполнения:

  ```csharp
  json = JsonSerializer.Serialize(weatherForecast, weatherForecast.GetType());
  ```

* Объявите объект, который должен быть сериализован как `object`.

  ```csharp
  json = JsonSerializer.Serialize<object>(weatherForecast);
  ```

В предыдущем примере сценария оба подхода приводят к тому, что `WindSpeed` свойство включается в выходные данные JSON:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "WindSpeed": 35
}
```

Дополнительные сведения о полиморфизмной десериализации см. в разделе [Поддержка полиморфизма](system-text-json-converters-how-to.md#support-polymorphic-deserialization).

## <a name="allow-comments-and-trailing-commas"></a>Разрешить комментарии и завершающие запятые

По умолчанию в JSON не допускаются комментарии и конечные запятые. Чтобы разрешить комментарии в JSON, задайте для свойства <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> значение `JsonCommentHandling.Skip`. Чтобы разрешить замыкающие запятые, задайте для свойства <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> значение `true`. В следующем примере показано, как разрешить оба:

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

## <a name="case-insensitive-property-matching"></a>Сопоставление свойств без учета регистра

По умолчанию десериализация выполняет поиск совпадения имен свойств с учетом регистра между JSON и свойствами целевого объекта. Чтобы изменить это поведение, задайте для <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> значение `true`.

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

При десериализации JSON, показанного в указанном типе, свойства `DatesAvailable` и `SummaryWords` не будут переходятся и теряются. Чтобы записать дополнительные данные, такие как эти свойства, примените атрибут [жсонекстенсиондата](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) к свойству типа `Dictionary<string,object>` или `Dictionary<string,JsonElement>`:

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

При десериализации JSON, показанного ранее, в этот тип данных дополнительные данные становятся парами "ключ-значение" свойства `ExtensionData`:

|свойство; |значения  |Примечания  |
|---------|---------|---------|
| дата.    | 8/1/2019 12:00:00 AM-07:00||
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

Обратите внимание, что имя свойства `ExtensionData` не отображается в JSON. Такое поведение позволяет JSON выполнить цикл обработки без потери дополнительных данных, которые в противном случае не будут десериализованы.

## <a name="ignore-null-when-deserializing"></a>Игнорировать null при десериализации

По умолчанию, если свойство в JSON имеет значение null, соответствующему свойству в целевом объекте присваивается значение null. В некоторых сценариях свойство Target может иметь значение по умолчанию, и вы не хотите, чтобы значение NULL переопределяло по умолчанию.

Например, предположим, что целевой объект представляет следующий код:

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

Предположим, что десериализуется следующий JSON:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": null,
}
```

После десериализации свойство `Summary` объекта `WeatherForecastWithDefault` имеет значение null.

Чтобы изменить это поведение, задайте для параметра <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> значение `true`, как показано в следующем примере:

```csharp
var options = new JsonSerializerOptions
{
    IgnoreNullValues = true
};
weatherForecast = JsonSerializer.Deserialize<WeatherForecastWithDefault>(json, options);
```

При использовании этого параметра свойство `Summary` объекта `WeatherForecastWithDefault` является значением по умолчанию "нет сводки" после десериализации.

Значения NULL в JSON пропускаются только в том случае, если они являются допустимыми. Значения NULL для типов значений, не допускающих значения NULL, вызывают исключения. Дополнительные сведения см. в описании [проблемы с типами значений, не допускающими значения NULL](https://github.com/dotnet/corefx/issues/40922) , в репозитории DotNet/Corefx в GitHub.

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a>Utf8JsonReader, Utf8JsonWriter и Жсондокумент

<xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> — это однопроходный модуль чтения текста JSON в кодировке UTF-8 из `ReadOnlySpan<byte>` с высокой производительностью и низким уровнем распределения. `Utf8JsonReader` — это тип низкого уровня, который можно использовать для создания пользовательских средств синтаксического анализа и десериализаторов. Метод <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> использует `Utf8JsonReader`, как описано выше.

<xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> — это высокопроизводительный способ записи текста JSON в кодировке UTF-8 из распространенных типов .NET, таких как `String`, `Int32`и `DateTime`. Модуль записи — это тип низкого уровня, который можно использовать для создания пользовательских сериализаторов. Метод <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> использует `Utf8JsonWriter`, как описано выше.

<xref:System.Text.Json.JsonDocument?displayProperty=fullName> предоставляет возможность создания модель DOM (DOM) только для чтения с помощью `Utf8JsonReader`. Модель DOM предоставляет произвольный доступ к данным в полезных данных JSON. Доступ к элементам JSON, составляющим полезные данные, можно получить с помощью типа <xref:System.Text.Json.JsonElement>. `JsonElement` предоставляет перечислители массивов и объектов вместе с интерфейсами API для преобразования текста JSON в общие типы .NET. `JsonDocument` предоставляет свойство <xref:System.Text.Json.JsonDocument.RootElement>.

В следующих разделах показано, как использовать эти средства для чтения и записи данных JSON.

## <a name="use-jsondocument-for-access-to-data"></a>Использование Жсондокумент для доступа к данным

В следующем примере показано, как использовать класс <xref:System.Text.Json.JsonDocument> для произвольного доступа к данным:

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

Предыдущий код:

* Предполагается, что анализируемый JSON находится в строке с именем `jsonString`.
* Вычисляет среднее значение для объектов в массиве `Students`, имеющих свойство `Grade`. 
* Назначает значение по умолчанию 70 для учащихся, у которых нет категории.
* Подсчитывает число учащихся путем увеличения `count` переменной с каждой итерацией. Альтернативой является вызов <xref:System.Text.Json.JsonElement.GetArrayLength%2A>.

  ```csharp
  count = studentsElement.GetArrayLength();
  ```

Ниже приведен пример JSON, обрабатываемого этим кодом:

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

## <a name="use-jsondocument-to-write-json"></a>Использование Жсондокумент для записи JSON

В следующем примере показано, как записать JSON из <xref:System.Text.Json.JsonDocument>.

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

Предыдущий код:

* Считывает JSON-файл, загружает данные в `JsonDocument`и записывает форматированный (довольно печатный) JSON в файл.
* Использует <xref:System.Text.Json.JsonDocumentOptions>, чтобы указать, что комментарии во входном JSON разрешены, но игнорируются.
* По завершении вызывается <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> для модуля записи. В качестве альтернативы можно разрешить Автоочистку модуля записи при его удалении. 

Ниже приведен пример входных данных JSON для обработки в примере кода:

```json
{"Class Name": "Science","Teacher's Name": "Jane","Semester": "2019-01-01","Students": [{"Name": "John","Grade": 94.3},{"Name": "James","Grade": 81.0},{"Name": "Julia","Grade": 91.9},{"Name": "Jessica","Grade": 72.4},{"Name": "Johnathan"}],"Final": true}
```

В результате получается следующий качественный вывод JSON:

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

## <a name="use-utf8jsonwriter"></a>Использование Utf8JsonWriter

В следующем примере показано, как использовать класс <xref:System.Text.Json.Utf8JsonWriter>:

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

## <a name="use-utf8jsonreader"></a>Использование Utf8JsonReader

В следующем примере показано, как использовать класс <xref:System.Text.Json.Utf8JsonReader>:

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

В приведенном выше коде предполагается, что `jsonUtf8` переменной является массив байтов, который содержит допустимый формат JSON, закодированный как UTF-8.

### <a name="filter-data-using-utf8jsonreader"></a>Фильтрация данных с помощью Utf8JsonReader

В следующем примере показано, как синхронно прочитать файл и выполнить поиск значения:

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

Предыдущий код:

* Предполагается, что файл кодируется как UTF-16 и перекодируется в UTF-8. Файл, закодированный как UTF-8, можно прочитать непосредственно в `ReadOnlySpan<byte>`с помощью следующего кода:

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName); 
  ```

* Предполагается, что JSON содержит массив объектов, и каждый объект может содержать свойство "Name" типа String.
* Подсчитывает объекты и `name` значения свойств, заканчивающиеся на университет.

Ниже приведен пример JSON, который можно считать с помощью приведенного выше кода. Полученное итоговое сообщение "2 из 4 имеют имена, заканчивающиеся на" Университет ":

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

## <a name="additional-resources"></a>Дополнительные ресурсы

* [Общие сведения о System. Text. JSON](system-text-json-overview.md)
* [Справочник по API System. Text. JSON](xref:System.Text.Json)
* [Запись пользовательских преобразователей для System. Text. JSON](system-text-json-converters-how-to.md)
* [Поддержка DateTime и DateTimeOffset в System. Text. JSON](../datetime/system-text-json-support.md)
