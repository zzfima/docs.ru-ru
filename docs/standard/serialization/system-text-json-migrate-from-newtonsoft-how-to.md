---
title: Мигрировать из Newtonsoft.Json - System.Text.Json .NET
author: tdykstra
ms.author: tdykstra
no-loc:
- System.Text.Json
- Newtonsoft.Json
ms.date: 01/10/2020
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 957bafcdf69d5792702962db6598458a0c8ec974
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291572"
---
# <a name="how-to-migrate-from-newtonsoftjson-to-systemtextjson"></a>Переход с Newtonsoft.Json на System.Text.Json

В этой статье показано, как мигрировать <xref:System.Text.Json>из [Newtonsoft.Json](https://www.newtonsoft.com/json) в .

В `System.Text.Json` пространстве имен предусмотрена функциональность для сериализации и десеризации из нотации объектов JavaScript (JSON). Библиотека `System.Text.Json` включена в общую платформу [.NET Core 3.0.](https://aka.ms/netcore3download) Для других целевых инфраструктур установите пакет [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet. Пакет поддерживает:

* .NET Стандарт 2.0 и более поздние версии
* .NET Framework 4.7.2 и более поздние версии
* .NET Core 2.0, 2.1 и 2.2

`System.Text.Json`основное внимание уделяется производительности, безопасности и соблюдению стандартов. Он имеет некоторые ключевые различия в поведении по умолчанию и не стремится иметь паритет функций с `Newtonsoft.Json`. Для некоторых `System.Text.Json` сценариев нет встроенной функциональности, но есть рекомендуемые обходные пути. Для других сценариев обходные пути непрактичны. Если ваша заявка зависит от отсутствующих функций, подумайте о [подаче проблемы,](https://github.com/dotnet/runtime/issues/new) чтобы узнать, можно ли добавить поддержку для вашего сценария.

<!-- For information about which features might be added in future releases, see the [Roadmap](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md). [Restore this when the roadmap is updated.]-->

Большая часть этой статьи <xref:System.Text.Json.JsonSerializer> посвящена использованию API, но она <xref:System.Text.Json.JsonDocument> также содержит рекомендации по <xref:System.Text.Json.Utf8JsonReader>использованию <xref:System.Text.Json.Utf8JsonWriter> (представляющей модель объекта документа или DOM) и типов.

## <a name="table-of-differences-between-newtonsoftjson-and-systemtextjson"></a>Таблица различий между Newtonsoft.Json и System.Text.Json

В следующей `Newtonsoft.Json` таблице `System.Text.Json` перечислены объекты и эквиваленты. Эквиваленты подпадают под следующие категории:

* Поддерживается встроенной функциональностью. Получение аналогичного `System.Text.Json` поведения от может потребовать использования атрибута или глобального варианта.
* Не поддерживается, обходной путь возможен. Обходные пути являются [пользовательскими преобразователями,](system-text-json-converters-how-to.md)которые не могут обеспечить полный паритет с `Newtonsoft.Json` функциональностью. Для некоторых из них примеры приводится пример кода. Если вы полагаетесь на эти `Newtonsoft.Json` функции, миграция потребует внесения изменений в модели объектов .NET или других изменений кода.
* Не поддерживается, обходнее не является практическим или возможным. Если вы полагаетесь на эти `Newtonsoft.Json` функции, миграция невозможна без существенных изменений.

| Функция Newtonsoft.Json                               | Эквивалент System.Text.Json |
|-------------------------------------------------------|-----------------------------|
| Десериализация без чувственных случаев по умолчанию           | ✔️ [PropertyNameCaseНечувствительные глобальные настройки](#case-insensitive-deserialization) |
| Имена свойств верблюжьего дела                             | ✔️ [PropertyNamingPolicy глобальная настройка](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) |
| Минимальный характер побега                            | ✔️ [Строгий характер побега, настраиваемый](#minimal-character-escaping) |
| `NullValueHandling.Ignore`глобальная настройка             | ✔️ [игнорироватьНуллюлваки глобальный вариант](system-text-json-how-to.md#exclude-all-null-value-properties) |
| Разрешить комментарии                                        | ✔️ [ReadCommentHandling глобальная настройка](#comments) |
| Разрешить замгой                                 | ✔️ [AllowTrailingCommas глобальная настройка](#trailing-commas) |
| Пользовательская регистрация конвертера                         | ✔️ [Порядок приоритета отличается](#converter-registration-precedence) |
| Нет максимальной глубины по умолчанию                           | ✔️ [максимальная глубина 64, настраиваемая](#maximum-depth) |
| Поддержка широкого спектра типов                    | ⚠️[Некоторые типы требуют пользовательских преобразователей](#types-without-built-in-support) |
| Десериализация строк как числа                        | ⚠️[Не поддерживается, обходной путь, образец](#quoted-numbers) |
| Десериализация `Dictionary` с неструнным ключом          | ⚠️[Не поддерживается, обходной путь, образец](#dictionary-with-non-string-key) |
| Полиморфная сериализация                             | ⚠️[Не поддерживается, обходной путь, образец](#polymorphic-serialization) |
| Полиморфная десериализация                           | ⚠️[Не поддерживается, обходной путь, образец](#polymorphic-deserialization) |
| Десеризировать выведенный тип `object` к свойствам      | ⚠️[Не поддерживается, обходной путь, образец](#deserialization-of-object-properties) |
| Десеризировать JSON `null` в буквальном смысле к ненеобнутивным типам значений | ⚠️[Не поддерживается, обходной путь, образец](#deserialize-null-to-non-nullable-type) |
| Десериализизировать неизменяемые классы и структуры          | ⚠️[Не поддерживается, обходной путь, образец](#deserialize-to-immutable-classes-and-structs) |
| Атрибут `[JsonConstructor]`                         | ⚠️[Не поддерживается, обходной путь, образец](#specify-constructor-to-use) |
| `Required`настройка `[JsonProperty]` атрибута        | ⚠️[Не поддерживается, обходной путь, образец](#required-properties) |
| `NullValueHandling`настройка `[JsonProperty]` атрибута | ⚠️[Не поддерживается, обходной путь, образец](#conditionally-ignore-a-property)  |
| `DefaultValueHandling`настройка `[JsonProperty]` атрибута | ⚠️[Не поддерживается, обходной путь, образец](#conditionally-ignore-a-property)  |
| `DefaultValueHandling`глобальная настройка                 | ⚠️[Не поддерживается, обходной путь, образец](#conditionally-ignore-a-property) |
| `DefaultContractResolver`исключать свойства       | ⚠️[Не поддерживается, обходной путь, образец](#conditionally-ignore-a-property) |
| `DateTimeZoneHandling`, `DateFormatString` настройки   | ⚠️[Не поддерживается, обходной путь, образец](#specify-date-format) |
| Обратные вызовы                                             | ⚠️[Не поддерживается, обходной путь, образец](#callbacks) |
| Поддержка публичных и непубличных областей              | ⚠️[Не поддерживается, обходной путь](#public-and-non-public-fields) |
| Поддержка внутренних и частных собственников и геттеров | ⚠️[Не поддерживается, обходной путь](#internal-and-private-property-setters-and-getters) |
| Метод`JsonConvert.PopulateObject`                   | ⚠️[Не поддерживается, обходной путь](#populate-existing-objects) |
| `ObjectCreationHandling`глобальная настройка               | ⚠️[Не поддерживается, обходной путь](#reuse-rather-than-replace-properties) |
| Добавление в коллекции без сеттеров                    | ⚠️[Не поддерживается, обходной путь](#add-to-collections-without-setters) |
| `PreserveReferencesHandling`глобальная настройка           | ❌[Не поддерживается](#preserve-object-references-and-handle-loops) |
| `ReferenceLoopHandling`глобальная настройка                | ❌[Не поддерживается](#preserve-object-references-and-handle-loops) |
| Поддержка `System.Runtime.Serialization` атрибутов | ❌[Не поддерживается](#systemruntimeserialization-attributes) |
| `MissingMemberHandling`глобальная настройка                | ❌[Не поддерживается](#missingmemberhandling) |
| Разрешить имена свойств без кавычек                   | ❌[Не поддерживается](#json-strings-property-names-and-string-values) |
| Разрешить отдельные кавычки вокруг значений строки              | ❌[Не поддерживается](#json-strings-property-names-and-string-values) |
| Разрешить значения, не связанные с строкой JSON, для свойств строк    | ❌[Не поддерживается](#non-string-values-for-string-properties) |

Это не исчерпывающий `Newtonsoft.Json` список функций. Список включает в себя многие сценарии, которые были запрошены в [вопросах GitHub](https://github.com/dotnet/runtime/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) или [столбах StackOverflow.](https://stackoverflow.com/questions/tagged/system.text.json) Если вы реализуете обходной путь для одного из перечисленных здесь сценариев, который в настоящее время не имеет примерного кода, и если вы хотите поделиться своим решением, выберите **эту страницу** в [разделе Обратная связь](/dotnet/standard/serialization/system-text-json-migrate-from-newtonsoft-how-to#feedback) на этой странице. Это создает проблему GitHub и перечисляет ее в нижней части этой страницы.

## <a name="differences-in-default-jsonserializer-behavior-compared-to-newtonsoftjson"></a>Различия в поведении JsonSerializer по умолчанию по сравнению с Newtonsoft.Json

<xref:System.Text.Json>является строгим по умолчанию и избегает каких-либо угадываний или интерпретации от имени вызывающего абонента, подчеркивая детерминированное поведение. Библиотека намеренно спроектирована таким образом для производительности и безопасности. `Newtonsoft.Json`гибкая по умолчанию. Это фундаментальное различие в дизайне за многие из следующих конкретных различий в поведении по умолчанию.

### <a name="case-insensitive-deserialization"></a>Десериализация без чувствительного к случаю

Во время десериализации `Newtonsoft.Json` по умолчанию сопоставляет нечувствительное имя свойства. По <xref:System.Text.Json> умолчанию является случай чувствительным, что дает лучшую производительность, поскольку он делает точное соответствие. Для получения информации о том, как [Case-insensitive property matching](system-text-json-how-to.md#case-insensitive-property-matching)делать нечувствительное сопоставление, см.

Если вы используете `System.Text.Json` косвенно, используя ASP.NET Core, вам не нужно ничего делать, чтобы получить поведение, как `Newtonsoft.Json`. ASP.NET Core определяет настройки [для имен свойств верблюда и](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) нечувствительных к `System.Text.Json`случаям соответствия при использовании.

### <a name="minimal-character-escaping"></a>Минимальный характер побега

Во время `Newtonsoft.Json` сериализации, является относительно вседозволенным о позволяя символов через, не избегая их. То есть, он не заменяет их на `\uxxxx` то, где `xxxx` находится кодовая точка персонажа. Там, где он избегает их, он `\` делает это, испуская до символа (например, `"` становится `\"`). <xref:System.Text.Json>избегает большего количества символов по умолчанию, чтобы обеспечить защиту от кросс-сайт сценариев (XSS) или раскрытия информации атак и делает это с помощью шести символов последовательности. `System.Text.Json`избегает всех не-ASCII символов по умолчанию, так что вам не `StringEscapeHandling.EscapeNonAscii` `Newtonsoft.Json`нужно ничего делать, если вы используете в . `System.Text.Json`также избегает HTML-чувствительных символов, по умолчанию. Для получения информации о `System.Text.Json` том, как переопределить поведение по умолчанию, см. [Customize character encoding](system-text-json-how-to.md#customize-character-encoding)

### <a name="comments"></a>Комментарии

Во время десериализации, `Newtonsoft.Json` игнорирует комментарии в JSON по умолчанию. По <xref:System.Text.Json> умолчанию, чтобы бросить исключения для комментариев, потому что спецификация [RFC 8259](https://tools.ietf.org/html/rfc8259) не включает их. Для получения информации о том, как разрешить комментарии, см [Разрешить комментарии и задние запятые](system-text-json-how-to.md#allow-comments-and-trailing-commas).

### <a name="trailing-commas"></a>Трейлинг запятые

Во время десериализации, `Newtonsoft.Json` игнорирует запоздающейся запятые по умолчанию. Он также игнорирует несколько запоздалых запятых (например, `[{"Color":"Red"},{"Color":"Green"},,]`). По <xref:System.Text.Json> умолчанию, чтобы бросить исключения для запятых, потому что спецификация [RFC 8259](https://tools.ietf.org/html/rfc8259) не позволяет им. Для получения информации `System.Text.Json` о том, как сделать принять их, см [Разрешить комментарии и задние запятые](system-text-json-how-to.md#allow-comments-and-trailing-commas). Там нет способа, чтобы несколько запоздалых запятых.

### <a name="converter-registration-precedence"></a>Преображительная регистрация приоритета

Приоритет `Newtonsoft.Json` регистрации пользовательских преобразователей заключается в следующем:

* Атрибут на имущество
* Атрибут по типу
* Коллекция [преобразователей](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonSerializerSettings_Converters.htm)

Этот порядок означает, что `Converters` пользовательский конвертер в коллекции переопределяется конвертером, который регистрируется, применяя атрибут на уровне типа. Обе эти регистрации переопределены атрибутом на уровне собственности.

Приоритет <xref:System.Text.Json> регистрации пользовательских преобразователей отличается:

* Атрибут на имущество
* <xref:System.Text.Json.JsonSerializerOptions.Converters>Коллекции
* Атрибут по типу

Разница в том, что пользовательский `Converters` конвертер в коллекции переопределяет атрибут на уровне типа. Намерение этого порядка приоритета заключается в том, чтобы сделать время выполнения изменения переопределить выбор времени проектирования. Нет никакого способа изменить приоритет.

Для получения дополнительной информации о пользовательской регистрации конвертера, [см.](system-text-json-converters-how-to.md#register-a-custom-converter)

### <a name="maximum-depth"></a>Максимальная глубина

`Newtonsoft.Json`не имеет максимального предела глубины по умолчанию. Ибо <xref:System.Text.Json> есть предел по умолчанию 64, и это <xref:System.Text.Json.JsonSerializerOptions.MaxDepth?displayProperty=nameWithType>настраивается при настройке.

### <a name="json-strings-property-names-and-string-values"></a>Строки JSON (имена свойств и значения строки)

Во время десериализации, `Newtonsoft.Json` принимает имена свойств, окруженные двойными котировками, отдельными котировками или без котировок. Он принимает значения строки, окруженные двойными кавычками или отдельными кавычками. Например, `Newtonsoft.Json` принимает следующее JSON:

```json
{
  "name1": "value",
  'name2': "value",
  name3: 'value'
}
```

`System.Text.Json`принимает имена свойств и значения строк в двойных котировках, потому что этот формат требуется спецификацией [RFC 8259](https://tools.ietf.org/html/rfc8259) и является единственным форматом, который считается действительным JSON.

Значение, заключенное в отдельные кавычки, приводит к [JsonException](xref:System.Text.Json.JsonException) со следующим сообщением:

```
''' is an invalid start of a value.
```

### <a name="non-string-values-for-string-properties"></a>Значения нестроки для свойств строк

`Newtonsoft.Json`принимает значения, не связанные с строкой, такие `true` `false`как число или буквальные значения и, для десериализации к свойствам строки типа. Вот пример JSON, который `Newtonsoft.Json` успешно десериализируется до следующего класса:

```json
{
  "String1": 1,
  "String2": true,
  "String3": false
}
```

```csharp
public class ExampleClass
{
    public string String1 { get; set; }
    public string String2 { get; set; }
    public string String3 { get; set; }
}
```

`System.Text.Json`не десериализирует значения, не связанные строкой, на свойства строки. Нестроковое значение, полученное для поля строки, приводит к [JsonException](xref:System.Text.Json.JsonException) со следующим сообщением:

```
The JSON value could not be converted to System.String.
```

## <a name="scenarios-using-jsonserializer-that-require-workarounds"></a>Сценарии с использованием JsonSerializer, требующие обходных ведомостей

Следующие сценарии не поддерживаются встроенной функциональностью, но возможны обходные пути. Обходные пути являются [пользовательскими преобразователями,](system-text-json-converters-how-to.md)которые не могут обеспечить полный паритет с `Newtonsoft.Json` функциональностью. Для некоторых из них примеры приводится пример кода. Если вы полагаетесь на эти `Newtonsoft.Json` функции, миграция потребует внесения изменений в модели объектов .NET или других изменений кода.

### <a name="types-without-built-in-support"></a>Типы без встроенной поддержки

<xref:System.Text.Json>не обеспечивает встроенную поддержку для следующих типов:

* <xref:System.Data.DataTable>и связанные с ними типы
* Типы F-типов, таких как [дискриминируемые союзы,](../../fsharp/language-reference/discriminated-unions.md) [типы записей](../../fsharp/language-reference/records.md)и [анонимные типы записей.](../../fsharp/language-reference/anonymous-records.md)
* <xref:System.Dynamic.ExpandoObject>
* <xref:System.TimeZoneInfo>
* <xref:System.Numerics.BigInteger>
* <xref:System.TimeSpan>
* <xref:System.DBNull>
* <xref:System.Type>
* <xref:System.ValueTuple>и связанные с ним общие типы

Пользовательские преобразователи могут быть реализованы для типов, которые не имеют встроенной поддержки.

### <a name="quoted-numbers"></a>Цитируемые цифры

`Newtonsoft.Json`может сериализировать или десериализировать номера, представленные строками JSON (окруженные кавычками). Например, он может `{"DegreesCelsius":"23"}` принять: вместо `{"DegreesCelsius":23}`. Для этого можно <xref:System.Text.Json>включить такое поведение в, реализуйте пользовательский конвертер, как следующий пример. Преобразователь обрабатывает `long`свойства, определяемые как:

* Он сериализирует их как строки JSON.
* Он принимает номера и цифры JSON в кавычках при десериализации.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/LongToStringConverter.cs)]

Зарегистрируйте этот [пользовательский](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) преобразователь, используя атрибут на отдельных `long` свойствах или [добавив преобразователь](system-text-json-converters-how-to.md#registration-sample---converters-collection) в коллекцию. <xref:System.Text.Json.JsonSerializerOptions.Converters>

### <a name="dictionary-with-non-string-key"></a>Словарь с ключом без строк

`Newtonsoft.Json`поддерживает коллекции `Dictionary<TKey, TValue>`типа . Встроенная поддержка словарных коллекций <xref:System.Text.Json> в `Dictionary<string, TValue>`. То есть ключ должен быть строкой.

Чтобы поддержать словарь целым рядом или какой-либо другой тип ключа, создайте конвертер, как пример в [Как писать пользовательские преобразователи.](system-text-json-converters-how-to.md#support-dictionary-with-non-string-key)

### <a name="polymorphic-serialization"></a>Полиморфная сериализация

`Newtonsoft.Json`автоматически делает полиморфную сериализацию. Для получения информации об ограниченных <xref:System.Text.Json>возможностях полиморфной сериализации, [см.](system-text-json-how-to.md#serialize-properties-of-derived-classes)

Описано решение свойств, которые могут содержать производные классы как тип. `object` Если это невозможно, другой вариант заключается в создании `Write` преобразователя с методом для всей иерархии типа наследования, как пример в [Как написать пользовательские преобразователи.](system-text-json-converters-how-to.md#support-polymorphic-deserialization)

### <a name="polymorphic-deserialization"></a>Полиморфная десериализация

`Newtonsoft.Json`имеет `TypeNameHandling` параметр, который добавляет метаданные имени типа в JSON во время сериализации. Он использует метаданные при десериализации, чтобы сделать полиморфную десериализацию. <xref:System.Text.Json>может сделать ограниченный диапазон [полиморфной сериализации,](system-text-json-how-to.md#serialize-properties-of-derived-classes) но не полиморфной десериализации.

Для поддержки полиморфной десериализации создайте конвертер, как в примере в [Как писать пользовательские преобразователи.](system-text-json-converters-how-to.md#support-polymorphic-deserialization)

### <a name="deserialization-of-object-properties"></a>Десериализация свойств объектов

Когда `Newtonsoft.Json` deserializes <xref:System.Object>к, оно:

* Выводы типа примитивных значений в полезной `null`нагрузке JSON `string` `long`(кроме) и возвращает сохраненные , `double`, `boolean`, или `DateTime` в качестве коробочный объект. *Примитивные значения* представляют собой отдельные значения JSON, `false`такие `null`как число JSON, `true`строка, или .
* Возвращает `JObject` или `JArray` для сложных значений в полезной нагрузке JSON. *Сложные значения* представляют коллекции пар ключевых значений`{}`JSON в скобках ()`[]`или списках значений в скобках (). Свойства и значения в скобках или скобках могут иметь дополнительные свойства или значения.
* Возвращает нулевую ссылку, `null` когда полезная нагрузка имеет буквальный JSON.

<xref:System.Text.Json>хранит коробку `JsonElement` для примитивных и сложных <xref:System.Object>значений всякий раз, когда десериализации, например:

* Свойство `object`.
* Значение `object` словаря.
* Значение `object` массива.
* Корень `object`.

Тем `System.Text.Json` не `null` менее, `Newtonsoft.Json` относится так же, как и `null` возвращает нулевую ссылку, когда полезная нагрузка имеет JSON буквально в нем.

Чтобы реализовать вывод типа `object` для свойств, создайте преобразователь, как пример в [Как написать пользовательские преобразователи.](system-text-json-converters-how-to.md#deserialize-inferred-types-to-object-properties)

### <a name="deserialize-null-to-non-nullable-type"></a>Десериализация null к не-недействительному типу

`Newtonsoft.Json`не делает исключение в следующем сценарии:

* `NullValueHandling`установлен на, `Ignore`и
* Во время десериализации JSON содержит нулевую величину для типа значения, не являемого необнуженой.

В том же <xref:System.Text.Json> сценарии, делает бросить исключение. (Соответствующий параметр <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType>нулевой обработки .)

Если у вас есть целевой тип, лучшим обходным решением является сделать свойство в вопросе недействительным (например, изменить `int` на). `int?`

Другой обходной путь заключается в том, чтобы сделать преобразователь `DateTimeOffset` для типа, например, следующий пример, который обрабатывает нулевые значения для типов:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DateTimeOffsetNullHandlingConverter.cs)]

Зарегистрируйте этот [пользовательский](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) преобразователь, используя атрибут <xref:System.Text.Json.JsonSerializerOptions.Converters> на свойстве или [добавив преобразователь](system-text-json-converters-how-to.md#registration-sample---converters-collection) в коллекцию.

**Примечание:** Предыдущий преобразователь **обрабатывает нулевые значения иначе,** чем `Newtonsoft.Json` для POPO, которые указывают значения по умолчанию. Например, предположим, что следующий код представляет ваш целевой объект:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

И предположим, что следующий JSON десериализован с помощью предыдущего преобразователя:

```json
{
  "Date": null,
  "TemperatureCelsius": 25,
  "Summary": null
}
```

После `Date` десериализации, свойство имеет 1/1/0001 (`default(DateTimeOffset)`), то есть значение, установленное в конструкторе перезаписано. Учитывая те же POCO `Newtonsoft.Json` и JSON, десериализация оставит 1/1/2001 в собственности. `Date`

### <a name="deserialize-to-immutable-classes-and-structs"></a>Десериализизировать неизменяемые классы и структуры

`Newtonsoft.Json`может десериализироваться до неизменяемых классов и структур, поскольку он может использовать конструкторы, которые имеют параметры. <xref:System.Text.Json>поддерживает только общественные безпараметры конструкторов. В качестве обходного пути можно вызвать конструктора с параметрами в пользовательском конвертере.

Вот неизменяемая структура с несколькими параметрами конструктора:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ImmutablePoint.cs#ImmutablePoint)]

А вот конвертер, который сериализирует и десериализирует эту структуру:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ImmutablePointConverter.cs)]

Зарегистрируйте этот пользовательский конвертер, <xref:System.Text.Json.JsonSerializerOptions.Converters> [добавив преобразователь](system-text-json-converters-how-to.md#registration-sample---converters-collection) в коллекцию.

Например, аналогичный преобразователь, который обрабатывает открытые общие свойства, [см. встроенный преобразователь для пар с ключевыми значениями.](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/JsonValueConverterKeyValuePair.cs)

### <a name="specify-constructor-to-use"></a>Указать конструктор для использования

Атрибут `Newtonsoft.Json` `[JsonConstructor]` позволяет указать, какой конструктор вызывать при десериализации в POCO. <xref:System.Text.Json>поддерживает только безпараметрики. Как обходной путь, вы можете вызвать какой конструктор вам нужно в пользовательском преобразователе. Смотрите пример [для Deserialize для неизменяемых классов и структур .](#deserialize-to-immutable-classes-and-structs)

### <a name="required-properties"></a>Обязательные свойства

В `Newtonsoft.Json`, вы указываете, что `Required` свойство требуется, установив на атрибут. `[JsonProperty]` `Newtonsoft.Json`выбрасывает исключение, если в JSON не получено значение для свойства, отмеченного по мере необходимости.

<xref:System.Text.Json>не выбрасывает исключение, если для одного из свойств целевого типа не получено значение. Например, если у `WeatherForecast` вас есть класс:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

Следующие JSON десериализован без ошибок:

```json
{
    "TemperatureCelsius": 25,
    "Summary": "Hot"
}
```

Чтобы сбой десериализации, если в JSON нет `Date` свойства, реализуйте пользовательский конвертер. Следующий код преобразователя образца бросает исключение, если `Date` свойство не установлено после завершения десериализации:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecastRequiredPropertyConverter.cs)]

Зарегистрируйте этот пользовательский преобразователь, используя атрибут на <xref:System.Text.Json.JsonSerializerOptions.Converters> классе [POCO](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) или добавив [преобразователь](system-text-json-converters-how-to.md#registration-sample---converters-collection) в коллекцию.

Если вы следуете этому шаблону, не проходите в объекте опций при повторном вызове <xref:System.Text.Json.JsonSerializer.Serialize%2A> или <xref:System.Text.Json.JsonSerializer.Deserialize%2A>. Объект опций <xref:System.Text.Json.JsonSerializerOptions.Converters%2A> содержит коллекцию. Если вы передаете `Serialize` `Deserialize`его в или , пользовательский преобразователь вызывает в себя, что делает бесконечный цикл, что приводит к исключению переполнения стека. Если параметры по умолчанию невозможны, создайте новый экземпляр параметров с необходимыми настройками. Этот подход будет медленным, так как каждый новый экземпляр кэша самостоятельно.

Предыдущий код конвертера является упрощенным примером. Дополнительная логика потребуется, если вам нужно обрабатывать атрибуты (например, [«JsonIgnore»](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) или различные параметры (например, пользовательские кодеры). Кроме того, пример кода не обрабатывает свойства, для которых значение по умолчанию устанавливается в конструкторе. И этот подход не делает различий между следующими сценариями:

* Свойство отсутствует в JSON.
* Свойство для ненеобнутивного типа присутствует в JSON, но значение является значением `int`по умолчанию для типа, например, ноль для .
* Свойство для несолужиевого типа значения присутствует в JSON, но значение недействительно.

### <a name="conditionally-ignore-a-property"></a>Условно игнорировать свойство

`Newtonsoft.Json`имеет несколько способов условно проигнорировать свойство по сериализации или десериализации:

* `DefaultContractResolver`позволяет выбрать свойства для включения или исключения, на основе произвольных критериев.
* В `NullValueHandling` `DefaultValueHandling` настройках `JsonSerializerSettings` и настройках позволяет указать, что все свойства нулевой стоимости или значения по умолчанию должны быть проигнорированы.
* `DefaultValueHandling` `[JsonProperty]` Параметры `NullValueHandling` атрибута позволяют указывать отдельные свойства, которые следует игнорировать при установлении значения, установленном на нулевую или значение по умолчанию.

<xref:System.Text.Json>предоставляет следующие способы опустить свойства при сериализации:

* Атрибут [«JsonIgnore»](system-text-json-how-to.md#exclude-individual-properties) на свойстве приводит к тому, что свойство будет опущено из JSON во время сериализации.
* Глобальный [опцион IgnoreNullValues](system-text-json-how-to.md#exclude-all-null-value-properties) позволяет исключить все свойства нулевой стоимости.
* Глобальный [опцион IgnoreReadOnlyProperties](system-text-json-how-to.md#exclude-all-read-only-properties) позволяет исключить все свойства только для чтения.

Эти опции **не** позволяют:

* Игнорировать все свойства, которые имеют значение по умолчанию для типа.
* Игнорировать выбранные свойства, которые имеют значение по умолчанию для типа.
* Игнорировать выбранные свойства, если их значение является нулевым.
* Игнорировать выбранные свойства на основе произвольных критериев, оцениваемых во время выполнения.

Для этой функциональности можно написать пользовательский конвертер. Вот пример POCO и пользовательский конвертер для него, который иллюстрирует этот подход:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecastRuntimeIgnoreConverter.cs)]

Преобразователь `Summary` приводит к тому, что свойство будет исключено из сериализации, если его значение является нулевым, пустой строкой или "N/A".

Зарегистрируйте этот [пользовательский конвертер, используя атрибут в классе](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) или добавив [преобразователь](system-text-json-converters-how-to.md#registration-sample---converters-collection) в коллекцию. <xref:System.Text.Json.JsonSerializerOptions.Converters>

Этот подход требует дополнительной логики, если:

* POCO включает в себя сложные свойства.
* Необходимо обрабатывать такие атрибуты, как `[JsonIgnore]` или такие параметры, как пользовательские кодора.

### <a name="specify-date-format"></a>Указать формат даты

`Newtonsoft.Json`предоставляет несколько способов `DateTime` контроля `DateTimeOffset` за тем, как сериализируются и десериализируются свойства и типы:

* Настройка `DateTimeZoneHandling` может быть использована `DateTime` для сериализации всех значений как дат UTC.
* Настройка `DateFormatString` `DateTime` и преобразователи могут быть использованы для настройки формата строк даты.

В <xref:System.Text.Json>, единственный формат, который имеет встроенную поддержку ISO 8601-1:2019, поскольку он широко принят, однозначный, и делает поездки в тур точно. Чтобы использовать любой другой формат, создайте пользовательский конвертер. Для получения дополнительной информации смотрите [службу поддержки DateTime и DateTimeOffset в System.Text.Json](../datetime/system-text-json-support.md).

### <a name="callbacks"></a>Обратные вызовы

`Newtonsoft.Json`позволяет выполнять пользовательский код в нескольких точках процесса сериализации или десериализации:

* OnDeserializing (при начале десеризации объекта)
* OnDeserialized (при завершении десериализации объекта)
* OnSerializing (при начале сериализации объекта)
* OnSerialized (при завершении сериализации объекта)

В <xref:System.Text.Json>, вы можете имитировать обратные вызовы, написав пользовательский конвертер. В следующем примере показан пользовательский конвертер для POCO. Преобразователь включает в себя код, который отображает `Newtonsoft.Json` сообщение в каждой точке, которая соответствует обратному отлику.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecastCallbacksConverter.cs)]

Зарегистрируйте этот [пользовательский конвертер, используя атрибут в классе](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) или добавив [преобразователь](system-text-json-converters-how-to.md#registration-sample---converters-collection) в коллекцию. <xref:System.Text.Json.JsonSerializerOptions.Converters>

Если вы используете пользовательский преобразователь, который следует за предыдущим образцом:

* Код `OnDeserializing` не имеет доступа к новому экземпляру POCO. Чтобы манипулировать новым экземпляром POCO в начале десериализации, поместите этот код в конструктор POCO.
* Не проходят в объекте опций, когда `Serialize` `Deserialize`рекурсивно вызова или . Объект опций `Converters` содержит коллекцию. Если вы передаете `Serialize` `Deserialize`его в или, преобразователь будет использоваться, что делает бесконечный цикл, что приводит к исключению переполнения стека.

### <a name="public-and-non-public-fields"></a>Публичные и непубличные поля

`Newtonsoft.Json`может сериализовать и десериализировать поля, а также свойства. <xref:System.Text.Json>работает только с общественной собственностью. Пользовательские преобразователи могут предоставить эту функциональность.

### <a name="internal-and-private-property-setters-and-getters"></a>Внутренние и частные собственности сеттеров и getters

`Newtonsoft.Json`могут использовать частные и внутренние установки `JsonProperty` свойств и getters через атрибут. <xref:System.Text.Json>поддерживает только публичные сеттеры. Пользовательские преобразователи могут предоставить эту функциональность.

### <a name="populate-existing-objects"></a>Заполнить существующие объекты

Метод `JsonConvert.PopulateObject` десериализации `Newtonsoft.Json` документа JSON до существующего экземпляра класса вместо создания нового экземпляра. <xref:System.Text.Json>всегда создает новый экземпляр целевого типа, используя безпараметр по умолчанию. Пользовательские преобразователи могут десериализироваться до существующего экземпляра.

### <a name="reuse-rather-than-replace-properties"></a>Повторное использование, а не замена свойств

Настройка `Newtonsoft.Json` `ObjectCreationHandling` позволяет указать, что объекты в свойствах должны быть повторно использованы, а не заменены во время десериализации. <xref:System.Text.Json>всегда заменяет объекты в свойствах.  Пользовательские преобразователи могут предоставить эту функциональность.

### <a name="add-to-collections-without-setters"></a>Добавление в коллекции без сеттеров

Во время десериализации добавляет объекты в коллекцию, `Newtonsoft.Json` даже если в свойстве нет сеттера. <xref:System.Text.Json>игнорирует свойства, которые не имеют сеттеров. Пользовательские преобразователи могут предоставить эту функциональность.

## <a name="scenarios-that-jsonserializer-currently-doesnt-support"></a>Сценарии, которые JsonSerializer в настоящее время не поддерживает

Для следующих сценариев обходные пути не являются практичными или возможными. Если вы полагаетесь на эти `Newtonsoft.Json` функции, миграция невозможна без существенных изменений.

### <a name="preserve-object-references-and-handle-loops"></a>Сохранение ссылок объектов и циклов обработки

По умолчанию `Newtonsoft.Json` сериализируется по стоимости. Например, если объект содержит два свойства, содержащие `Person` ссылку на один `Person` и тот же объект, значения свойств этого объекта дублируются в JSON.

`Newtonsoft.Json`имеет `PreserveReferencesHandling` настройки, `JsonSerializerSettings` что позволяет сериализировать по ссылке:

* Метаданные идентификатора добавляются в `Person` JSON, созданные для первого объекта.
* Созданный для второго `Person` объекта JSON содержит ссылку на этот идентификатор вместо значений свойств.

`Newtonsoft.Json`также имеет `ReferenceLoopHandling` параметр, который позволяет игнорировать круговые ссылки, а не бросать исключение.

<xref:System.Text.Json>только поддерживает сериализацию по значениям и бросает исключение для круговых ссылок.

### <a name="systemruntimeserialization-attributes"></a>Атрибуты System.Runtime.Serialization

<xref:System.Text.Json>не поддерживает атрибуты из `System.Runtime.Serialization` пространства имен, `DataMemberAttribute` `IgnoreDataMemberAttribute`такие как и .

### <a name="octal-numbers"></a>Октальные числа

`Newtonsoft.Json`рассматривает числа с ведущим нулем в качестве октальных чисел. <xref:System.Text.Json>не позволяет вести нули, потому что спецификация [RFC 8259](https://tools.ietf.org/html/rfc8259) не позволяет их.

### <a name="missingmemberhandling"></a>MissingMemberHandling

`Newtonsoft.Json`может быть настроен для того, чтобы выбросить исключения во время десериализации, если JSON включает свойства, которые отсутствуют в целевом типе. <xref:System.Text.Json>игнорирует дополнительные свойства в JSON, за исключением случаев использования [атрибута «JsonExtensionData».](system-text-json-how-to.md#handle-overflow-json) Нет обходного пути для отсутствующих функций участника.

### <a name="tracewriter"></a>TraceWriter

`Newtonsoft.Json`позволяет отладить `TraceWriter` с помощью для просмотра журналов, которые генерируются путем сериализации или десериализации. <xref:System.Text.Json>не делает лесозаготовки.

## <a name="jsondocument-and-jsonelement-compared-to-jtoken-like-jobject-jarray"></a>JsonDocument и JsonElement по сравнению с JToken (например, JObject, JArray)

<xref:System.Text.Json.JsonDocument?displayProperty=fullName>обеспечивает возможность анализировать и создавать модель объекта для **чтения только** (DOM) из существующих полезных нагрузок JSON. DOM обеспечивает случайный доступ к данным в полезной нагрузке JSON. Элементы JSON, которые составляют полезную нагрузку, могут быть доступны через <xref:System.Text.Json.JsonElement> тип. Тип `JsonElement` предоставляет AI для преобразования текста JSON в общие типы .NET. `JsonDocument`разоблачает свойство. <xref:System.Text.Json.JsonDocument.RootElement>

### <a name="jsondocument-is-idisposable"></a>JsonДокумент является IDisposable

`JsonDocument`создает представление данных в памяти в объединенный буфер. Таким образом, `JArray` `Newtonsoft.Json`в `JsonDocument` отличие от `IDisposable` `JObject` или от , тип реализует и должен быть использован внутри использующего блока.

Только вернуть `JsonDocument` из вашего API, если вы хотите передать пожизненное владение и распоряжаться ответственностью с абонента. В большинстве сценариев это не обязательно. Если абоненту необходимо работать со всем документом <xref:System.Text.Json.JsonElement.Clone%2A> JSON, верните <xref:System.Text.Json.JsonDocument.RootElement%2A> <xref:System.Text.Json.JsonElement>, который является . Если вызывающему необходимо работать с определенным элементом в <xref:System.Text.Json.JsonElement.Clone%2A> документе JSON, верните этот <xref:System.Text.Json.JsonElement>элемент. Если вы `RootElement` вернете или субэлемент `Clone`непосредственно без принятия, абонент не сможет `JsonElement` получить `JsonDocument` доступ к возвращенным после того, что владеет он удаляется.

Вот пример, который требует, чтобы `Clone`вы сделали:

```csharp
public JsonElement LookAndLoad(JsonElement source)
{
    string json = File.ReadAllText(source.GetProperty("fileName").GetString());

    using (JsonDocument doc = JsonDocument.Parse(json))
    {
        return doc.RootElement.Clone();
    }
}
```

Предыдущий код `JsonElement` предполагает свойство. `fileName` Он открывает файл JSON `JsonDocument`и создает . Метод предполагает, что абонент хочет работать со всем документом, `Clone` поэтому `RootElement`он возвращает .

Если вы `JsonElement` получаете и возвращаете подэлемент, нет `Clone` необходимости возвращать часть подэлемента. Звонящее несет ответственность `JsonDocument` за сохранение того, к кому `JsonElement` принадлежит сдавливая. Пример:

```csharp
public JsonElement ReturnFileName(JsonElement source)
{
   return source.GetProperty("fileName");
}
```

### <a name="jsondocument-is-read-only"></a>JsonDocument читается только

DOM <xref:System.Text.Json> не может добавлять, удалять или изменять элементы JSON. Он разработан таким образом для производительности и сокращения ассигнований на разбор общих размеров полезной нагрузки JSON (т.е. < 1 МБ). Если в сценарии в настоящее время используется модифицируемый DOM, может быть осуществим один из следующих обходных пути:

* `JsonDocument` Чтобы построить с нуля (то есть, не проходя `Parse` в существующих JSON полезной `Utf8JsonWriter` нагрузки на метод), написать текст `JsonDocument`JSON с помощью и разобрать выход из этого, чтобы сделать новый .
* Чтобы изменить `JsonDocument`существующий, используйте его для записи текста JSON, внося изменения во `JsonDocument`время записи, и разбирайте выход из этого, чтобы сделать новый .
* Чтобы объединить существующие документы `JObject.Merge` JSON, эквивалентные или `JContainer.Merge` AIS от `Newtonsoft.Json`, см. [this GitHub issue](https://github.com/dotnet/corefx/issues/42466#issuecomment-570475853)

### <a name="jsonelement-is-a-union-struct"></a>JsonElement является союзструктури

`JsonDocument`предоставляет `RootElement` как свойство типа <xref:System.Text.Json.JsonElement>, который является союзом, структурировать тип, который включает в себя любой элемент JSON. `Newtonsoft.Json`использует выделенные иерархические`JArray` `JToken`типы, такие как `JObject`, , и так далее. `JsonElement`это то, что вы можете искать и перечислять, и вы можете использовать `JsonElement` для материализации элементов JSON в типах .NET.

### <a name="how-to-search-a-jsondocument-and-jsonelement-for-sub-elements"></a>Как найти JsonDocument и JsonElement для субэлементов

Поиски токенов JSON `JArray` `Newtonsoft.Json` с использованием `JObject` или от, как правило, относительно быстро, потому что они поиск в некоторых словаре. Для сравнения, `JsonElement` поиск по требуют последовательного поиска свойств и, следовательно, является `TryGetProperty`относительно медленным (например, при использовании ). <xref:System.Text.Json>предназначен для минимизации первоначального времени разбора, а не времени поиска. Поэтому используйте следующие подходы для `JsonDocument` оптимизации производительности при поиске через объект:

* Используйте встроенные регистраторы (и)<xref:System.Text.Json.JsonElement.EnumerateArray%2A> <xref:System.Text.Json.JsonElement.EnumerateObject%2A>вместо того, чтобы делать свой собственный индексирования или циклов.
* Не делайте последовательный поиск в целом `JsonDocument` через каждое `RootElement`свойство с помощью . Вместо этого поиск вложенных объектов JSON основан на известной структуре данных JSON. Например, если вы ищете `Grade` свойство `Student` в объектах, цикл через `Student` объекты и получить значение `Grade` для каждого, а не поиск через все `JsonElement` объекты, `Grade` ищущие свойства. Выполнение последнего приведет к ненужным передачам по тем же данным.

Для примера кода [см.](system-text-json-how-to.md#use-jsondocument-for-access-to-data)

## <a name="utf8jsonreader-compared-to-jsontextreader"></a>Utf8JsonReader по сравнению с JsonTextReader

<xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName>является высокопроизводительным, низким распределением, вперед только читатель для UTF-8 закодирован ный текст JSON, читать с [readOnlySpan\<байт>](xref:System.ReadOnlySpan%601) или [\<ReadOnlySequence байт>](xref:System.Buffers.ReadOnlySequence%601). Это `Utf8JsonReader` низкоуровневый тип, который может быть использован для создания пользовательских парзеров и десериализаторов.

В следующих разделах разъясняются рекомендуемые шаблоны программирования для использования `Utf8JsonReader`.

### <a name="utf8jsonreader-is-a-ref-struct"></a>Utf8JsonReader является рефери struct

Поскольку `Utf8JsonReader` тип является *реф-структурой,* он имеет [определенные ограничения.](../../csharp/language-reference/keywords/ref.md#ref-struct-types) Например, он не может храниться в виде поля на классе или структурировать, кроме структуры рефа. Для достижения высокой производительности, `ref struct` этот тип должен быть, так как он должен кэшировать входный [байт,>,\< ](xref:System.ReadOnlySpan%601)который сам по себе является реф struct. Кроме того, этот тип является изменяемым, так как он содержит состояние. Таким образом, **передать его по рефери,** а не по стоимости. Передача его по значению приведет к структурной копии и изменения состояния не будут видны вызывающего абонента. Это отличается `Newtonsoft.Json` от `Newtonsoft.Json` `JsonTextReader` так как это класс. Для получения дополнительной информации о том, как использовать реф-структуры, [см.](../../csharp/write-safe-efficient-code.md)

### <a name="read-utf-8-text"></a>Читать текст UTF-8

Для достижения наилучшей производительности `Utf8JsonReader`при использовании, прочитайте jSON полезные нагрузки, уже закодированные как utF-8 текст, а не как UTF-16 строк. Для примера кода см. [Данные фильтра с помощью Utf8JsonReader.](system-text-json-how-to.md#filter-data-using-utf8jsonreader)

### <a name="read-with-a-stream-or-pipereader"></a>Читать с помощью потока или PipeReader

Поддерживает `Utf8JsonReader` чтение из UTF-8 закодированы [ReadOnlySpan\<байт>](xref:System.ReadOnlySpan%601) или [\<ReadOnlySequence байт>](xref:System.Buffers.ReadOnlySequence%601) (который является результатом чтения <xref:System.IO.Pipelines.PipeReader>с).

Для синхронного чтения, вы можете прочитать jSON полезной нагрузки до конца потока в байт массив и передать, что в читателя. Для чтения из строки (которая кодируется как UTF-16), позвоните <xref:System.Text.Encoding.UTF8>.<xref:System.Text.Encoding.GetBytes%2A> сначала транскодировать строку в закодированный массив байт UTF-8. Затем передайте, `Utf8JsonReader`что в .

`Utf8JsonReader` Поскольку входный вход считается текстом JSON, знак заказа UTF-8 байт (BOM) считается недействительным JSON. Вызывающий абонент должен отфильтровать это перед передачей данных читателю.

Примеры кода можно найти [в примере Utf8JsonReader.](system-text-json-how-to.md#use-utf8jsonreader)

### <a name="read-with-multi-segment-readonlysequence"></a>Читать с многосегментной ReadOnlySequence

Если ваш ввод JSON является [байтом\<ReadOnlySpan>, ](xref:System.ReadOnlySpan%601)каждый `ValueSpan` элемент JSON может быть доступен из свойства на читателе, как вы идете через цикл чтения. Однако, если ваш ввод является [накидкой ReadOnlySequence\<>](xref:System.Buffers.ReadOnlySequence%601) (который является результатом чтения с a), <xref:System.IO.Pipelines.PipeReader>некоторые элементы JSON могут пересекать несколько сегментов `ReadOnlySequence<byte>` объекта. Эти элементы не <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> будут доступны из смежного блока памяти. Вместо этого, всякий раз, `ReadOnlySequence<byte>` когда у вас <xref:System.Text.Json.Utf8JsonReader.HasValueSequence%2A> есть многосегментвный в качестве ввода, опрос собственности на читателя, чтобы выяснить, как получить доступ к текущему элементу JSON. Вот рекомендуемый шаблон:

```csharp
while (reader.Read())
{
    switch (reader.TokenType)
    {
        // ...
        ReadOnlySpan<byte> jsonElement = reader.HasValueSequence ?
            reader.ValueSequence.ToArray() :
            reader.ValueSpan;
        // ...
    }
}
```

### <a name="use-valuetextequals-for-property-name-lookups"></a>Используйте ValueTextEquals для поиска имен свойств

Не используйте <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> для сравнения байт-байт, вызывая <xref:System.MemoryExtensions.SequenceEqual%2A> поиск имени свойства. Позвоните <xref:System.Text.Json.Utf8JsonReader.ValueTextEquals%2A> вместо этого, потому что этот метод отсылает любые символы, которые бежали в JSON. Вот пример, который показывает, как искать свойство, которое называется "имя":

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ValueTextEqualsExample.cs?name=SnippetDefineUtf8Var)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ValueTextEqualsExample.cs?name=SnippetUseUtf8Var&highlight=11)]

### <a name="read-null-values-into-nullable-value-types"></a>Чтение нулевых значений в недействительные типы значений

`Newtonsoft.Json`предоставляет AIS, <xref:System.Nullable%601>которые `ReadAsBoolean`возвращаются, такие `Null` `TokenType` как , `bool?`который обрабатывает для вас, вернувшись . Встроенные `System.Text.Json` AIS возвращают только необнудаемые типы значений. Например, <xref:System.Text.Json.Utf8JsonReader.GetBoolean%2A?displayProperty=nameWithType> возвращает `bool`. Оно бросает исключение если `Null` оно находит в JSON. Следующие примеры показывают два способа обработки нулей, один, вернув необыдаемый тип значения, и один, вернув значение по умолчанию:

```csharp
public bool? ReadAsNullableBoolean()
{
    _reader.Read();
    if (_reader.TokenType == JsonTokenType.Null)
    {
        return null;
    }
    if (_reader.TokenType != JsonTokenType.True && _reader.TokenType != JsonTokenType.False)
    {
        throw new JsonException();
    }
    return _reader.GetBoolean();
}
```

```csharp
public bool ReadAsBoolean(bool defaultValue)
{
    _reader.Read();
    if (_reader.TokenType == JsonTokenType.Null)
    {
        return defaultValue;
    }
    if (_reader.TokenType != JsonTokenType.True && _reader.TokenType != JsonTokenType.False)
    {
        throw new JsonException();
    }
    return _reader.GetBoolean();
}
```

### <a name="multi-targeting"></a>Настройка для различных версий

Если необходимо продолжать использовать `Newtonsoft.Json` определенные целевые фреймворки, можно многоцелевых и иметь две реализации. Однако это не тривиально и потребует некоторого `#ifdefs` дублирования источников. Один из способов поделиться как можно `ref struct` больше `Utf8JsonReader` кода, как это возможно, чтобы создать обертку вокруг и `Newtonsoft.Json` `JsonTextReader`. Эта обертка унифицирует область публичной поверхности при изоляции поведенческих различий. Это позволяет изолировать изменения в основном к конструкции типа, наряду с передачей нового типа вокруг по ссылке. Это шаблон, который [microsoft.Extensions.DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) библиотека следующим образом:

* [UnifiedJsonReader.JsonTextReader.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.JsonTextReader.cs)
* [UnifiedJsonReader.Utf8JsonReader.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.Utf8JsonReader.cs)

## <a name="utf8jsonwriter-compared-to-jsontextwriter"></a>Utf8JsonWriter по сравнению с JsonTextWriter

<xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName>является высокопроизводительным способом написания UTF-8 закодированного текста `String`JSON из общих типов .NET, таких как , `Int32`и `DateTime`. Автор — это низкоуровневый тип, который можно использовать для создания пользовательских сериализаторов.

В следующих разделах разъясняются рекомендуемые шаблоны программирования для использования `Utf8JsonWriter`.

### <a name="write-with-utf-8-text"></a>Пишите текстом UTF-8

Для достижения наилучшей производительности `Utf8JsonWriter`при использовании, написать JSON полезных нагрузок уже закодированы как UTF-8 текст, а не как UTF-16 строк. Используйте <xref:System.Text.Json.JsonEncodedText> для кэша и предварительного кодирования известных имен свойств строк и значений в качестве статики, и передавать их писателю, а не с помощью строки UTF-16 буквальных. Это быстрее, чем кэширование и использование байт-массивов UTF-8.

Этот подход также работает, если вам нужно сделать пользовательские побега. `System.Text.Json`не позволяет отключить побег при написании строки. Тем не менее, вы <xref:System.Text.Encodings.Web.JavaScriptEncoder> можете передать в свой собственный `JsonEncodedText` обычай `JavascriptEncoder` в качестве опции для писателя, или создать свой собственный, который использует ваш, чтобы сделать побег, а затем написать `JsonEncodedText` вместо строки. Для получения дополнительной информации [см.](system-text-json-how-to.md#customize-character-encoding)

### <a name="write-raw-values"></a>Написать необработанные значения

Метод `Newtonsoft.Json` `WriteRawValue` записывает сырой JSON, где значение ожидается. <xref:System.Text.Json>не имеет прямого эквивалента, но вот обходной путь, который гарантирует, что только действительный JSON написан:

```csharp
using JsonDocument doc = JsonDocument.Parse(string);
doc.WriteTo(writer);
```

### <a name="customize-character-escaping"></a>Настраивать символ побега

Настройка `JsonTextWriter` [StringEscapeHandling](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_StringEscapeHandling.htm) предлагает варианты, чтобы избежать всех не-ASCII символов **или** HTML символов. По умолчанию, `Utf8JsonWriter` избегает всех не-ASCII **и** HTML символов. Этот побег делается по соображениям безопасности. Чтобы указать другую политику <xref:System.Text.Encodings.Web.JavaScriptEncoder> побега, создайте и установите <xref:System.Text.Json.JsonWriterOptions.Encoder?displayProperty=nameWithType>. Для получения дополнительной информации [см.](system-text-json-how-to.md#customize-character-encoding)

### <a name="customize-json-format"></a>Настройка формата JSON

`JsonTextWriter`включает в себя следующие `Utf8JsonWriter` настройки, для которых не имеет эквивалента:

* [Отступ](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_Indentation.htm) - Определяет, сколько символов отступ. `Utf8JsonWriter`всегда делает отступы 2-символа.
* [IndentChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_IndentChar.htm) - определяет символ для использования для отступов.  `Utf8JsonWriter`всегда использует белое пространство.
* [QuoteChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteChar.htm) - определяет символ для использования для окружания значений строки.  `Utf8JsonWriter`всегда использует двойные котировки.
* [Цитата -](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteName.htm) Определяет, следует ли окружать имена собственности цитатами.  `Utf8JsonWriter`всегда окружает их цитатами.

Есть нет обходных путей, которые позволили бы `Utf8JsonWriter` вам настроить JSON производства таким образом.

### <a name="write-null-values"></a>Написать нулевую стоимость

Чтобы написать нулевые значения с помощью, `Utf8JsonWriter`позвоните:

* <xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A>написать пару с нулевым значением.
* <xref:System.Text.Json.Utf8JsonWriter.WriteNullValue%2A>писать null как элемент массива JSON.

Для свойства строки, если строка <xref:System.Text.Json.Utf8JsonWriter.WriteString%2A> нулевая, и <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A> эквивалентны `WriteNull` и `WriteNullValue`.

### <a name="write-timespan-uri-or-char-values"></a>Напишите значения Timespan, Uri или char

`JsonTextWriter`предоставляет `WriteValue` методы для [TimeSpan](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_18.htm), [Uri](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_22.htm), и [символ](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_3.htm) значения. `Utf8JsonWriter`не имеет эквивалентных методов. Вместо этого, форматировать эти значения `ToString()`в виде строк <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A>(например, вызывая, например) и вызова .

### <a name="multi-targeting"></a>Настройка для различных версий

Если необходимо продолжать использовать `Newtonsoft.Json` определенные целевые фреймворки, можно многоцелевых и иметь две реализации. Однако это не тривиально и потребует некоторого `#ifdefs` дублирования источников. Один из способов поделиться как можно больше `Utf8JsonWriter` кода, как это возможно, чтобы создать обертку вокруг и `Newtonsoft` `JsonTextWriter`. Эта обертка унифицирует область публичной поверхности при изоляции поведенческих различий. Это позволяет изолировать изменения в основном к конструкции типа. [Библиотека Microsoft.Extensions.DependencyModel:](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/)

* [UnifiedJsonWriter.JsonTextWriter.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.JsonTextWriter.cs)
* [UnifiedJsonWriter.Utf8JsonWriter.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.Utf8JsonWriter.cs)

## <a name="additional-resources"></a>Дополнительные ресурсы

<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)[Restore this when the roadmap is updated.]-->
* [System.Text.JsonОбзор](system-text-json-overview.md)
* [Как использоватьSystem.Text.Json](system-text-json-how-to.md)
* [Практическое руководство. Написание настраиваемых преобразователей](system-text-json-converters-how-to.md)
* [Поддержка DateTime и DateTimeOffset вSystem.Text.Json](../datetime/system-text-json-support.md)
* [System.Text.JsonСсылка на API](xref:System.Text.Json)
* [System.Text.Json. Ссылка на API сериализации](xref:System.Text.Json.Serialization)
