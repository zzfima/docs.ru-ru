---
title: Миграция с Newtonsoft.Json на System.Text.Json — .NET
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
ms.openlocfilehash: d84b6d16d529914c87d42bf12ce17dc7093fe9ee
ms.sourcegitcommit: 09b4090b78f52fd09b0e430cd4b26576f1fdf96e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2020
ms.locfileid: "76211971"
---
# <a name="how-to-migrate-from-opno-locnewtonsoftjson-to-opno-locsystemtextjson"></a>Переход с Newtonsoft.Json на System.Text.Json

В этой статье показано, как выполнить миграцию с [Newtonsoft.Json](https://www.newtonsoft.com/json) на <xref:System.Text.Json>.

`System.Text.Json` фокусируется в первую очередь на производительность, безопасность и соответствие стандартам. Он имеет некоторые ключевые отличия в поведении по умолчанию и не имеет функции соответствия `Newtonsoft.Json`. В некоторых сценариях `System.Text.Json` не имеет встроенных функций, но рекомендуется использовать их. В других сценариях обходные пути нецелесообразны. Если приложение зависит от отсутствующей функции, попробуйте добавить [проблему](https://github.com/dotnet/runtime/issues/new) , чтобы узнать, можно ли добавлять поддержку для вашего сценария.

<!-- For information about which features might be added in future releases, see the [Roadmap](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md). [Restore this when the roadmap is updated.]-->

Большая часть этой статьи посвящена использованию <xref:System.Text.Json.JsonSerializer> API, но также содержит рекомендации по использованию <xref:System.Text.Json.JsonDocument> (который представляет модель DOM или модель DOM), <xref:System.Text.Json.Utf8JsonReader>и типы <xref:System.Text.Json.Utf8JsonWriter>.

## <a name="table-of-differences-between-opno-locnewtonsoftjson-and-opno-locsystemtextjson"></a>Таблица различий между Newtonsoft.Json и System.Text.Json

В следующей таблице перечислены `Newtonsoft.Json` функции и `System.Text.Json` эквиваленты. Эквиваленты делятся на следующие категории:

* Поддерживается встроенными функциональными возможностями. Для получения подобного поведения от `System.Text.Json` может потребоваться использование атрибута или глобального параметра.
* Не поддерживается, решение можно устранить. Обходные пути являются [пользовательскими преобразователями](system-text-json-converters-how-to.md), которые могут не обеспечивать полную четность с помощью функций `Newtonsoft.Json`. Некоторые из этих примеров кода приведены в качестве примеров. Если вы полагаетесь на эти `Newtonsoft.Json` функции, то миграция потребует внесения изменений в объектные модели .NET или другие изменения кода.
* Не поддерживается, обходной путь не является практичным и невозможным. Если вы полагаетесь на эти `Newtonsoft.Json` функции, миграция будет невозможна без существенных изменений.

| Функция в Newtonsoft.Json                               | эквивалент System.Text.Json |
|-------------------------------------------------------|-----------------------------|
| Десериализация без учета регистра по умолчанию           | [глобальный параметр ✔️ пропертинамекасеинсенситиве](#case-insensitive-deserialization) |
| Имена свойств в стиле Camel                             | [глобальный параметр ✔️ пропертинамингполици](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) |
| Минимальное экранирование символов                            | ✔️е [запрещенного экранирования символов, настраиваемого](#minimal-character-escaping) |
| Глобальный параметр `NullValueHandling.Ignore`             | ✔️ [глобальный параметр игноренуллвалуес](system-text-json-how-to.md#exclude-all-null-value-properties) |
| Разрешить комментарии                                        | [глобальный параметр ✔️ реадкомменсандлинг](#comments) |
| Разрешить конечные запятые                                 | [глобальный параметр ✔️ алловтраилингкоммас](#trailing-commas) |
| Регистрация пользовательского преобразователя                         | ✔️ [Порядок приоритета отличается](#converter-registration-precedence) |
| По умолчанию отсутствует максимальная глубина                           | [Максимальная глубина ✔️ по умолчанию 64, настраиваемая](#maximum-depth) |
| Поддержка широкого спектра типов                    | ⚠️ для [некоторых типов требуются пользовательские преобразователи](#types-without-built-in-support) |
| Десериализация строк как чисел                        | ⚠️ [не поддерживается, обходной путь, пример](#quoted-numbers) |
| Десериализация `Dictionary` с ключом, не являющимся строкой          | ⚠️ [не поддерживается, обходной путь, пример](#dictionary-with-non-string-key) |
| Пресериализация в полиморфизм                             | ⚠️ [не поддерживается, обходной путь, пример](#polymorphic-serialization) |
| Пресериализация в полиморфизм                           | ⚠️ [не поддерживается, обходной путь, пример](#polymorphic-deserialization) |
| Десериализация выводимого типа для `object` свойств      | ⚠️ [не поддерживается, обходной путь, пример](#deserialization-of-object-properties) |
| Десериализация JSON `null` литерала в типы, не допускающие значение null | ⚠️ [не поддерживается, обходной путь, пример](#deserialize-null-to-non-nullable-type) |
| Десериализация в неизменяемые классы и структуры          | ⚠️ [не поддерживается, обходной путь, пример](#deserialize-to-immutable-classes-and-structs) |
| Атрибут `[JsonConstructor]`                         | ⚠️ [не поддерживается, обходной путь, пример](#specify-constructor-to-use) |
| параметр `Required` для атрибута `[JsonProperty]`        | ⚠️ [не поддерживается, обходной путь, пример](#required-properties) |
| параметр `NullValueHandling` для атрибута `[JsonProperty]` | ⚠️ [не поддерживается, обходной путь, пример](#conditionally-ignore-a-property)  |
| параметр `DefaultValueHandling` для атрибута `[JsonProperty]` | ⚠️ [не поддерживается, обходной путь, пример](#conditionally-ignore-a-property)  |
| Глобальный параметр `DefaultValueHandling`                 | ⚠️ [не поддерживается, обходной путь, пример](#conditionally-ignore-a-property) |
| `DefaultContractResolver` для исключения свойств       | ⚠️ [не поддерживается, обходной путь, пример](#conditionally-ignore-a-property) |
| `DateTimeZoneHandling`, параметры `DateFormatString`   | ⚠️ [не поддерживается, обходной путь, пример](#specify-date-format) |
| Обратные вызовы                                             | ⚠️ [не поддерживается, обходной путь, пример](#callbacks) |
| Поддержка открытых и не открытых полей              | ⚠️ [не поддерживается, обходной путь](#public-and-non-public-fields) |
| Поддержка методов и методов доступа для внутренних и закрытых свойств | ⚠️ [не поддерживается, обходной путь](#internal-and-private-property-setters-and-getters) |
| Метод`JsonConvert.PopulateObject`                   | ⚠️ [не поддерживается, обходной путь](#populate-existing-objects) |
| Глобальный параметр `ObjectCreationHandling`               | ⚠️ [не поддерживается, обходной путь](#reuse-rather-than-replace-properties) |
| Добавить в коллекции без методов задания                    | ⚠️ [не поддерживается, обходной путь](#add-to-collections-without-setters) |
| Глобальный параметр `PreserveReferencesHandling`           | ❌ [не поддерживается](#preserve-object-references-and-handle-loops) |
| Глобальный параметр `ReferenceLoopHandling`                | ❌ [не поддерживается](#preserve-object-references-and-handle-loops) |
| Поддержка атрибутов `System.Runtime.Serialization` | ❌ [не поддерживается](#systemruntimeserialization-attributes) |
| Глобальный параметр `MissingMemberHandling`                | ❌ [не поддерживается](#missingmemberhandling) |
| Разрешить имена свойств без кавычек                   | ❌ [не поддерживается](#json-strings-property-names-and-string-values) |
| Разрешить одиночные кавычки вокруг строковых значений              | ❌ [не поддерживается](#json-strings-property-names-and-string-values) |
| Разрешить значения, отличные от строкового JSON, для строковых свойств    | ❌ [не поддерживается](#non-string-values-for-string-properties) |

Это не исчерпывающий список функций `Newtonsoft.Json`. Список включает многие сценарии, которые были запрошены в [проблемах GitHub](https://github.com/dotnet/runtime/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) или [StackOverflow](https://stackoverflow.com/questions/tagged/system.text.json) . Если вы реализуете обходной путь для одного из сценариев, перечисленных здесь без примера кода, и если вы хотите поделиться своим решением, нажмите кнопку "**Эта страница**" в нижней части страницы. Это создает ошибку GitHub и добавляет ее к проблемам, перечисленным в нижней части страницы.

## <a name="differences-in-default-jsonserializer-behavior-compared-to-opno-locnewtonsoftjson"></a>Различия в поведении JsonSerializer по умолчанию по сравнению с Newtonsoft.Json

<xref:System.Text.Json> по умолчанию является строгой и позволяет избежать подбора или интерпретации от имени вызывающего объекта, подчеркивая детерминированное поведение. Библиотека преднамеренно разработана таким образом для повышения производительности и безопасности. `Newtonsoft.Json` по умолчанию является гибкой. Это фундаментальное различие в проектировании – это за многие из следующих различий в поведении по умолчанию.

### <a name="case-insensitive-deserialization"></a>Десериализация без учета регистра 

Во время десериализации `Newtonsoft.Json` имя свойства, по умолчанию совпадающее с учетом регистра. <xref:System.Text.Json> умолчанию учитывается регистр, что обеспечивает лучшую производительность, поскольку выполняет точное соответствие. Сведения о том, как выполнять сопоставление без учета регистра, см. в разделе [сопоставление свойств без учета регистра](system-text-json-how-to.md#case-insensitive-property-matching).

Если вы используете `System.Text.Json` косвенно с помощью ASP.NET Core, вам не нужно ничего делать для получения такого поведения, как `Newtonsoft.Json`. ASP.NET Core задает параметры для [имен свойств в неоднородном регистре](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) и сопоставления без учета регистра при использовании `System.Text.Json`.

### <a name="minimal-character-escaping"></a>Минимальное экранирование символов

Во время сериализации `Newtonsoft.Json` имеет относительно недостаточное разрешение на использование символов без экранирования их. То есть он не заменяет их `\uxxxx`, где `xxxx` является кодовой точкой символа. Там они помещаются в escape-последовательность, выпуская `\` перед символом (например, `"` преобразуется в `\"`). по умолчанию <xref:System.Text.Json> содержит больше символов, чтобы обеспечить защиту от несанкционированного использования межсайтовых сценариев (XSS) или атак с раскрытием информации и делает это с помощью последовательности из шести символов. `System.Text.Json` отменяет все символы, отличные от ASCII, по умолчанию, поэтому вам не нужно ничего делать, если вы используете `StringEscapeHandling.EscapeNonAscii` в `Newtonsoft.Json`. `System.Text.Json` также по умолчанию обходит символы, зависящие от HTML. Сведения о том, как переопределить поведение `System.Text.Json` по умолчанию, см. в разделе [Настройка кодировки символов](system-text-json-how-to.md#customize-character-encoding).

### <a name="comments"></a>Comments

Во время десериализации `Newtonsoft.Json` по умолчанию игнорирует комментарии в JSON. <xref:System.Text.Json> по умолчанию — создавать исключения для комментариев, так как спецификация [RFC 8259](https://tools.ietf.org/html/rfc8259) не включает их. Сведения о том, как разрешить комментарии, см. в разделе [allow Comments and замыкающие запятые](system-text-json-how-to.md#allow-comments-and-trailing-commas).

### <a name="trailing-commas"></a>Конечные запятые

Во время десериализации `Newtonsoft.Json` по умолчанию игнорирует конечные запятые. Он также игнорирует несколько конечных запятых (например, `[{"Color":"Red"},{"Color":"Green"},,]`). <xref:System.Text.Json> по умолчанию — создавать исключения для конечных запятых, так как спецификация [RFC 8259](https://tools.ietf.org/html/rfc8259) не допускает их. Сведения о том, как сделать `System.Text.Json` допустимыми, см. в разделе [allow Comments and замыкающие запятые](system-text-json-how-to.md#allow-comments-and-trailing-commas). Невозможно разрешить несколько конечных запятых.

### <a name="converter-registration-precedence"></a>Приоритет регистрации преобразователя

Приоритет регистрации `Newtonsoft.Json` для пользовательских преобразователей выглядит следующим образом:

* Атрибут для свойства
* Атрибут для типа
* Коллекция [преобразователей](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonSerializerSettings_Converters.htm)

Этот порядок означает, что пользовательский преобразователь в коллекции `Converters` переопределяется преобразователем, зарегистрированным путем применения атрибута на уровне типа. Обе эти регистрации переопределяются атрибутом на уровне свойства.

Приоритет регистрации <xref:System.Text.Json> для пользовательских преобразователей отличается:

* Атрибут для свойства
* Коллекция <xref:System.Text.Json.JsonSerializerOptions.Converters>
* Атрибут для типа

Разница заключается в том, что пользовательский преобразователь в коллекции `Converters` переопределяет атрибут на уровне типа. Цель этого порядка приоритета заключается в том, чтобы изменения во время выполнения переопределяли варианты времени разработки. Изменить приоритет невозможно.

Дополнительные сведения о регистрации пользовательских преобразователей см. [в разделе Регистрация пользовательского преобразователя](system-text-json-converters-how-to.md#register-a-custom-converter).

### <a name="maximum-depth"></a>Максимальная глубина

значение по умолчанию для `Newtonsoft.Json` не равно максимальной глубины. Для <xref:System.Text.Json> существует ограничение по умолчанию 64, которое можно настроить, установив <xref:System.Text.Json.JsonSerializerOptions.MaxDepth?displayProperty=nameWithType>.

### <a name="json-strings-property-names-and-string-values"></a>Строки JSON (имена свойств и строковые значения)

Во время десериализации `Newtonsoft.Json` принимает имена свойств, заключенные в двойные кавычки, одинарные кавычки или без кавычек. Он принимает строковые значения, заключенные в двойные кавычки или одинарные кавычки. Например, `Newtonsoft.Json` принимает следующий код JSON:

```json
{
  "name1": "value",
  'name2': "value",
  name3: 'value'
}
```

`System.Text.Json` принимает только имена свойств и строковые значения в двойных кавычках, поскольку этот формат является обязательным для спецификации [RFC 8259](https://tools.ietf.org/html/rfc8259) и является единственным форматом, который считается допустимым JSON.

Значение, заключенное в одинарные кавычки, приводит к [жсонексцептион](xref:System.Text.Json.JsonException) со следующим сообщением:

```
''' is an invalid start of a value.
```

### <a name="non-string-values-for-string-properties"></a>Нестроковые значения для строковых свойств

`Newtonsoft.Json` принимает нестроковые значения, такие как число или литералы `true` и `false`, для десериализации свойств типа String. Ниже приведен пример JSON, который `Newtonsoft.Json` успешно десериализуется в следующий класс:

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

`System.Text.Json` не выполняет десериализацию нестроковых значений в свойства строк. Нестроковое значение, полученное для строкового поля, приводит к [жсонексцептион](xref:System.Text.Json.JsonException) со следующим сообщением:

```
The JSON value could not be converted to System.String.
```

## <a name="scenarios-using-jsonserializer-that-require-workarounds"></a>Сценарии с использованием JsonSerializer, для которых требуются обходные пути

Следующие сценарии не поддерживаются встроенными функциями, но возможны обходные пути. Обходные пути являются [пользовательскими преобразователями](system-text-json-converters-how-to.md), которые могут не обеспечивать полную четность с помощью функций `Newtonsoft.Json`. Некоторые из этих примеров кода приведены в качестве примеров. Если вы полагаетесь на эти `Newtonsoft.Json` функции, то миграция потребует внесения изменений в объектные модели .NET или другие изменения кода.

### <a name="types-without-built-in-support"></a>Типы без встроенной поддержки

<xref:System.Text.Json> не предоставляет встроенную поддержку для следующих типов:

* <xref:System.Data.DataTable> и связанные типы
* F#типы, такие как [Размеченные объединения](../../fsharp/language-reference/discriminated-unions.md), [типы записей](../../fsharp/language-reference/records.md)и [анонимные типы записей](../../fsharp/language-reference/anonymous-records.md).
* <xref:System.Dynamic.ExpandoObject>
* <xref:System.TimeZoneInfo>
* <xref:System.Numerics.BigInteger>
* <xref:System.TimeSpan>
* <xref:System.DBNull>
* <xref:System.Type>
* <xref:System.ValueTuple> и связанные с ними универсальные типы

Пользовательские преобразователи можно реализовать для типов, у которых нет встроенной поддержки.

### <a name="quoted-numbers"></a>Заключенные в кавычки числа

`Newtonsoft.Json` может сериализовать или десериализовать числа, представленные строками JSON (заключенные в кавычки). Например, он может принимать: `{"DegreesCelsius":"23"}` вместо `{"DegreesCelsius":23}`. Чтобы включить это поведение в <xref:System.Text.Json>, реализуйте пользовательский преобразователь, как показано в следующем примере. Преобразователь обрабатывает свойства, определенные как `long`:

* Он сериализует их как строки JSON. 
* Он принимает числа и числа JSON в кавычках при десериализации.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/LongToStringConverter.cs)]

Зарегистрируйте этот пользовательский преобразователь, [используя атрибут](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) для отдельных свойств `long` или [добавив преобразователь](system-text-json-converters-how-to.md#registration-sample---converters-collection) в коллекцию <xref:System.Text.Json.JsonSerializerOptions.Converters>.

### <a name="dictionary-with-non-string-key"></a>Словарь с ключом, не являющимся строкой

`Newtonsoft.Json` поддерживает коллекции типа `Dictionary<TKey, TValue>`. Встроенная поддержка коллекций словарей в <xref:System.Text.Json> ограничена `Dictionary<string, TValue>`. То есть ключ должен быть строкой.

Чтобы обеспечить поддержку словаря с целым числом или другим типом в качестве ключа, создайте такой преобразователь, как в примере, в котором [описывается написание пользовательских преобразователей](system-text-json-converters-how-to.md#support-dictionary-with-non-string-key).

### <a name="polymorphic-serialization"></a>Пресериализация в полиморфизм

`Newtonsoft.Json` автоматически выполняет сериализацию. Сведения о возможностях ограниченного преобразования полиморфизма <xref:System.Text.Json>см. в разделе [сериализация свойств производных классов](system-text-json-how-to.md#serialize-properties-of-derived-classes).

Описанный обходной путь состоит в определении свойств, которые могут содержать производные классы в качестве типа `object`. Если это невозможно, можно создать преобразователь с `Write`ным методом для всей иерархии типов наследования, как в примере [записи пользовательских преобразователей](system-text-json-converters-how-to.md#support-polymorphic-deserialization).

### <a name="polymorphic-deserialization"></a>Пресериализация в полиморфизм

`Newtonsoft.Json` имеет параметр `TypeNameHandling`, который добавляет метаданные имени типа в JSON во время сериализации. Он использует метаданные при десериализации для выполнения полиморфизма. <xref:System.Text.Json> может выполнять ограниченный диапазон [полиморфизма](system-text-json-how-to.md#serialize-properties-of-derived-classes) , но не является полиморфизмом.

Чтобы обеспечить поддержку полиморфизма, создайте такой же конвертер, как и в примере, в котором [описывается написание пользовательских преобразователей](system-text-json-converters-how-to.md#support-polymorphic-deserialization).

### <a name="deserialization-of-object-properties"></a>Десериализация свойств объекта

При `Newtonsoft.Json` десериализации для `object` свойств в POCO или в словарях типа `Dictionary<string, object>`это:

* Выводит типы примитивных значений в полезных данных JSON (кроме `null`) и возвращает хранимые `string`, `long`, `double`, `boolean`или `DateTime` в виде упакованного объекта. *Примитивные значения* — это одиночные значения JSON, такие как номер JSON, строка, `true`, `false`или `null`.
* Возвращает `JObject` или `JArray` для сложных значений в полезных данных JSON. *Сложные значения* — это коллекции пар "ключ-значение" JSON в фигурных скобках (`{}`) или списках значений в квадратных скобках (`[]`). Свойства и значения в фигурных скобках или квадратных скобках могут иметь дополнительные свойства или значения.
* Возвращает пустую ссылку, если полезная нагрузка содержит литерал `null` JSON.

<xref:System.Text.Json> сохраняет упакованную `JsonElement` как для простых, так и для сложных значений в свойстве `System.Object` или словаре. Однако он обрабатывает `null` так же, как `Newtonsoft.Json`, и возвращает пустую ссылку, если полезная нагрузка содержит `null` литерал JSON.

Чтобы реализовать определение типа для `object` свойств, создайте преобразователь, как в примере, в котором [описывается написание пользовательских преобразователей](system-text-json-converters-how-to.md#deserialize-inferred-types-to-object-properties).

### <a name="deserialize-null-to-non-nullable-type"></a>Десериализация значения NULL в тип, не допускающий значения NULL 

`Newtonsoft.Json` не создает исключение в следующем сценарии:

* для `NullValueHandling` задано значение `Ignore`, а
* Во время десериализации JSON содержит значение NULL для типа, не допускающего значения NULL.

В том же сценарии <xref:System.Text.Json> создает исключение. (Соответствующий параметр обработки значений NULL — <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType>.)

Если вы владеете типом целевого объекта, лучшим решением будет сделать свойство в вопросе null (например, изменить `int` на `int?`).

Еще один обходной путь — сделать преобразователь для типа, например следующий пример, который обрабатывает значения NULL для типов `DateTimeOffset`:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DateTimeOffsetNullHandlingConverter.cs)]

Зарегистрируйте этот пользовательский преобразователь с [помощью атрибута в свойстве](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) или путем [добавления преобразователя](system-text-json-converters-how-to.md#registration-sample---converters-collection) в коллекцию <xref:System.Text.Json.JsonSerializerOptions.Converters>.

**Примечание.** Предыдущий преобразователь **обрабатывает значения NULL иначе** , чем `Newtonsoft.Json` ВЫПОЛНЯЕТ для POCO, задающих значения по умолчанию. Например, предположим, что целевой объект представляет следующий код:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

Предположим, что следующий JSON десериализуется с помощью предыдущего конвертера:

```json
{
  "Date": null,
  "TemperatureCelsius": 25,
  "Summary": null
}
```

После десериализации свойство `Date` имеет 1/1/0001 (`default(DateTimeOffset)`), то есть значение, заданное в конструкторе, перезаписывается. При наличии одних и тех же POCO и JSON `Newtonsoft.Json` десериализация оставляет 1/1/2001 в свойстве `Date`.

### <a name="deserialize-to-immutable-classes-and-structs"></a>Десериализация в неизменяемые классы и структуры

`Newtonsoft.Json` можно десериализовать в неизменяемые классы и структуры, так как он может использовать конструкторы с параметрами. <xref:System.Text.Json> поддерживает только открытые конструкторы без параметров. В качестве обходного решения можно вызвать конструктор с параметрами в пользовательском преобразователе.

Ниже приведена неизменяемая структура с несколькими параметрами конструктора:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ImmutablePoint.cs#ImmutablePoint)]

А вот преобразователь, который сериализует и десериализует эту структуру:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ImmutablePointConverter.cs)]

Зарегистрируйте этот пользовательский преобразователь, [добавив преобразователь](system-text-json-converters-how-to.md#registration-sample---converters-collection) в коллекцию <xref:System.Text.Json.JsonSerializerOptions.Converters>.

Пример подобного преобразователя, обрабатывающего открытые универсальные свойства, см. в разделе [встроенный преобразователь для пар "ключ-значение"](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/JsonValueConverterKeyValuePair.cs).

### <a name="specify-constructor-to-use"></a>Укажите используемый конструктор

Атрибут `Newtonsoft.Json` `[JsonConstructor]` позволяет указать, какой конструктор вызывать при десериализации POCO. <xref:System.Text.Json> поддерживает только конструкторы без параметров. В качестве обходного решения можно вызвать любой конструктор, необходимый в пользовательском преобразователе. См. пример для [десериализации неизменяемых классов и структур](#deserialize-to-immutable-classes-and-structs).

### <a name="required-properties"></a>Требуемые свойства

В `Newtonsoft.Json`указать, что свойство требуется, задав `Required` атрибута `[JsonProperty]`. `Newtonsoft.Json` создает исключение, если в JSON не получено значение для свойства, помеченного как обязательное.

<xref:System.Text.Json> не создает исключение, если для одного из свойств целевого типа не получено никакого значения. Например, если имеется класс `WeatherForecast`:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

Следующий JSON десериализуется без ошибки:

```json
{
    "TemperatureCelsius": 25,
    "Summary": "Hot"
}
```

Чтобы выполнить десериализацию не удалось, если в JSON нет `Date` свойства, реализуйте пользовательский преобразователь. Следующий пример кода преобразователя создает исключение, если после десериализации свойство `Date` не задано:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecastRequiredPropertyConverter.cs)]

Зарегистрируйте этот пользовательский преобразователь с [помощью атрибута в классе POCO](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) или путем [добавления преобразователя](system-text-json-converters-how-to.md#registration-sample---converters-collection) в коллекцию <xref:System.Text.Json.JsonSerializerOptions.Converters>.

Если следовать этому шаблону, не передавайте объект Options при рекурсивном вызове <xref:System.Text.Json.JsonSerializer.Serialize%2A> или <xref:System.Text.Json.JsonSerializer.Deserialize%2A>. Объект options содержит коллекцию <xref:System.Text.Json.JsonSerializerOptions.Converters%2A>. Если передать его в `Serialize` или `Deserialize`, Пользовательский преобразователь вызывает сам себя и делает бесконечный цикл, который приводит к возникновению исключения переполнения стека. Если параметры по умолчанию нецелесообразны, создайте новый экземпляр параметров с нужными параметрами. Этот подход будет замедляться, так как каждый новый экземпляр кэшируется независимо друг от друга.

Предыдущий код преобразователя является упрощенным примером. Если необходимо обрабатывать атрибуты (например, [[жсонигноре]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) или различные параметры (например, пользовательские кодировщики), потребуется дополнительная логика. Кроме того, пример кода не обрабатывает свойства, для которых в конструкторе задано значение по умолчанию. И этот подход не различает следующие сценарии:

* В JSON отсутствует свойство.
* Свойство для типа, не допускающего значения NULL, содержится в JSON, но значение является значением по умолчанию для типа, например нулевым для `int`.
* Свойство для типа, допускающего значение null, содержится в JSON, но значение равно null.

### <a name="conditionally-ignore-a-property"></a>Условно игнорировать свойство

`Newtonsoft.Json` имеет несколько способов условно игнорировать свойство при сериализации или десериализации:

* `DefaultContractResolver` позволяет выбрать свойства для включения или исключения на основе произвольных критериев. 
* Параметры `NullValueHandling` и `DefaultValueHandling` на `JsonSerializerSettings` позволяют указать, что все свойства со значением NULL или значениями по умолчанию должны игнорироваться.
* Параметры `NullValueHandling` и `DefaultValueHandling` атрибута `[JsonProperty]` позволяют указать отдельные свойства, которые должны игнорироваться при установке значения NULL или по умолчанию.

<xref:System.Text.Json> предоставляет следующие способы опустить свойства при сериализации:

* Атрибут [[жсонигноре]](system-text-json-how-to.md#exclude-individual-properties) в свойстве приводит к исключению свойства из JSON во время сериализации.
* Параметр [игноренуллвалуес](system-text-json-how-to.md#exclude-all-null-value-properties) Global позволяет исключить все свойства со значением NULL.
* Параметр [игноререадонлипропертиес](system-text-json-how-to.md#exclude-all-read-only-properties) Global позволяет исключить все свойства только для чтения.

Эти параметры **не** позволяют:

* Игнорировать все свойства, имеющие значение по умолчанию для типа.
* Игнорировать выбранные свойства, которые имеют значение по умолчанию для типа.
* Игнорировать выбранные свойства, если их значение равно null.
* Игнорировать выбранные свойства на основе произвольных критериев, вычисляемых во время выполнения. 

Для этой функции можно написать пользовательский преобразователь. Ниже приведен пример POCO и пользовательский конвертер, демонстрирующий этот подход:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecastRuntimeIgnoreConverter.cs)]

Преобразователь вызывает пропуск свойства `Summary` из сериализации, если его значение равно null, пустая строка или "н/д". 

Зарегистрируйте этот пользовательский преобразователь с [помощью атрибута в классе](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) или путем [добавления преобразователя](system-text-json-converters-how-to.md#registration-sample---converters-collection) в коллекцию <xref:System.Text.Json.JsonSerializerOptions.Converters>.

Этот подход требует дополнительной логики, если:

* POCO включает сложные свойства.
* Необходимо выполнять обработку таких атрибутов, как `[JsonIgnore]` или таких параметров, как пользовательские кодировщики.

### <a name="specify-date-format"></a>Укажите формат даты

`Newtonsoft.Json` предоставляет несколько способов управления сериализацией и десериализации свойств `DateTime` и типов `DateTimeOffset`:

* Параметр `DateTimeZoneHandling` можно использовать для сериализации всех значений `DateTime` как даты в формате UTC.
* Для настройки формата строк даты можно использовать параметры `DateFormatString` и `DateTime` преобразователей.

В <xref:System.Text.Json>единственным форматом, поддерживающим встроенную поддержку, является ISO 8601-1:2019, так как он широко используется, однозначно и делает круговые циклы. Чтобы использовать любой другой формат, создайте пользовательский преобразователь. Дополнительные сведения см. [в разделе Поддержка DateTime и DateTimeOffset в System.Text.Json](../datetime/system-text-json-support.md).

### <a name="callbacks"></a>Обратные вызовы

`Newtonsoft.Json` позволяет выполнять пользовательский код в нескольких точках процесса сериализации или десериализации:

* OnDeserializing (при начале десериализации объекта)
* Десериализация (после завершения десериализации объекта)
* Onserializing (при начале сериализации объекта)
* Onseriald (после завершения сериализации объекта)

В <xref:System.Text.Json>можно имитировать обратные вызовы, написав пользовательский преобразователь. В следующем примере показан пользовательский преобразователь для POCO. Этот преобразователь включает код, отображающий сообщение в каждой точке, которая соответствует обратному вызову `Newtonsoft.Json`.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecastCallbacksConverter.cs)]

Зарегистрируйте этот пользовательский преобразователь с [помощью атрибута в классе](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) или путем [добавления преобразователя](system-text-json-converters-how-to.md#registration-sample---converters-collection) в коллекцию <xref:System.Text.Json.JsonSerializerOptions.Converters>.

Если вы используете пользовательский преобразователь, следующий за предыдущим образцом:

* Код `OnDeserializing` не имеет доступа к новому экземпляру POCO. Чтобы управлять новым экземпляром POCO в начале десериализации, вставьте этот код в конструктор POCO.
* Не передавайте объект Options при рекурсивном вызове `Serialize` или `Deserialize`. Объект options содержит коллекцию `Converters`. Если передать его в `Serialize` или `Deserialize`, будет использоваться преобразователь, что приведет к возникновению исключения переполнения стека.

### <a name="public-and-non-public-fields"></a>Открытые и не являющиеся открытыми поля

`Newtonsoft.Json` могут сериализовать и десериализовать поля, а также свойства. <xref:System.Text.Json> работает только с общими свойствами. Эти функции могут быть предоставлены пользовательскими преобразователями.

### <a name="internal-and-private-property-setters-and-getters"></a>Методы и методы доступа для внутренних и закрытых свойств

`Newtonsoft.Json` может использовать частные и внутренние методы задания свойств и методы получения с помощью атрибута `JsonProperty`. <xref:System.Text.Json> поддерживает только открытые методы задания. Эти функции могут быть предоставлены пользовательскими преобразователями.

### <a name="populate-existing-objects"></a>Заполнение существующих объектов

Метод `JsonConvert.PopulateObject` в `Newtonsoft.Json` десериализует документ JSON в существующий экземпляр класса вместо создания нового экземпляра. <xref:System.Text.Json> всегда создает новый экземпляр целевого типа с помощью открытого конструктора без параметров по умолчанию. Пользовательские преобразователи можно десериализовать в существующий экземпляр.

### <a name="reuse-rather-than-replace-properties"></a>Повторное использование вместо замены свойств

Параметр `Newtonsoft.Json` `ObjectCreationHandling` позволяет указать, что объекты в свойствах следует использовать повторно, а не заменять во время десериализации. <xref:System.Text.Json> всегда заменяет объекты в свойствах.  Эти функции могут быть предоставлены пользовательскими преобразователями.

### <a name="add-to-collections-without-setters"></a>Добавить в коллекции без методов задания

Во время десериализации `Newtonsoft.Json` добавляет объекты в коллекцию, даже если свойство не имеет метода задания. <xref:System.Text.Json> не учитывает свойства, у которых нет методов задания. Эти функции могут быть предоставлены пользовательскими преобразователями.

## <a name="scenarios-that-jsonserializer-currently-doesnt-support"></a>Сценарии, JsonSerializer в настоящее время не поддерживают

В следующих сценариях обходные пути не являются практичными и невозможными. Если вы полагаетесь на эти `Newtonsoft.Json` функции, миграция будет невозможна без существенных изменений.

### <a name="preserve-object-references-and-handle-loops"></a>Сохранять ссылки на объекты и циклы обработки

По умолчанию `Newtonsoft.Json` сериализуется по значению. Например, если объект содержит два свойства, которые содержат ссылку на один и тот же объект `Person`, значения свойств этого объекта `Person` дублируются в JSON.

`Newtonsoft.Json` имеет параметр `PreserveReferencesHandling` на `JsonSerializerSettings`, который позволяет выполнять сериализацию по ссылке:

* Метаданные идентификатора добавляются в JSON, созданный для первого объекта `Person`.
* JSON, созданный для второго объекта `Person`, содержит ссылку на этот идентификатор вместо значений свойств.

`Newtonsoft.Json` также имеет параметр `ReferenceLoopHandling`, который позволяет игнорировать циклические ссылки, а не создавать исключение.

<xref:System.Text.Json> поддерживает только сериализацию по значению и создает исключение для циклических ссылок.

### <a name="systemruntimeserialization-attributes"></a>Атрибуты System. Runtime. Serialization

<xref:System.Text.Json> не поддерживает атрибуты из пространства имен `System.Runtime.Serialization`, например `DataMemberAttribute` и `IgnoreDataMemberAttribute`.

### <a name="octal-numbers"></a>Восьмеричные числа

`Newtonsoft.Json` обрабатывает числа с ведущим нулем в виде восьмеричных чисел. <xref:System.Text.Json> не допускают начальных нулей, так как спецификация [RFC 8259](https://tools.ietf.org/html/rfc8259) не разрешает их.

### <a name="missingmemberhandling"></a>миссингмемберхандлинг

`Newtonsoft.Json` можно настроить для создания исключений во время десериализации, если в JSON имеются свойства, отсутствующие в целевом типе. <xref:System.Text.Json> игнорирует дополнительные свойства в JSON, за исключением случаев, когда используется [атрибут [жсонекстенсиондата]](system-text-json-how-to.md#handle-overflow-json). Для функции отсутствующих членов не существует решения.

### <a name="tracewriter"></a>TraceWriter

`Newtonsoft.Json` позволяет выполнять отладку с помощью `TraceWriter` для просмотра журналов, созданных при сериализации или десериализации. <xref:System.Text.Json> не выполняет ведение журнала.

## <a name="jsondocument-and-jsonelement-compared-to-jtoken-like-jobject-jarray"></a>Жсондокумент и Жсонелемент по сравнению с JToken (например, JObject, Жаррай)

<xref:System.Text.Json.JsonDocument?displayProperty=fullName> предоставляет возможность выполнять синтаксический анализ и сборку модель DOM (DOM) **только для чтения** из существующих полезных данных JSON. Модель DOM предоставляет произвольный доступ к данным в полезных данных JSON. Доступ к элементам JSON, составляющим полезные данные, можно получить с помощью типа <xref:System.Text.Json.JsonElement>. Тип `JsonElement` предоставляет интерфейсы API для преобразования текста JSON в общие типы .NET. `JsonDocument` предоставляет свойство <xref:System.Text.Json.JsonDocument.RootElement>.

### <a name="jsondocument-is-idisposable"></a>Жсондокумент является IDisposable

`JsonDocument` создает в памяти представление данных в буфере в пуле. Таким образом, в отличие от `JObject` или `JArray` от `Newtonsoft.Json`тип `JsonDocument` реализует `IDisposable` и должен использоваться внутри блока using. 

Возвращать `JsonDocument` из API, если вы хотите передать владение временем существования и освободить ответственность вызывающему. В большинстве случаев это необязательно. Если вызывающему объекту необходимо работать с документом JSON целиком, возвращайте <xref:System.Text.Json.JsonElement.Clone%2A> <xref:System.Text.Json.JsonDocument.RootElement%2A>, то есть <xref:System.Text.Json.JsonElement>. Если вызывающему объекту необходимо работать с определенным элементом в документе JSON, возвращайте <xref:System.Text.Json.JsonElement.Clone%2A> этого <xref:System.Text.Json.JsonElement>. Если вы возвращаете `RootElement` или вложенный элемент напрямую, не выполняя `Clone`, вызывающий объект не сможет получить доступ к возвращаемому `JsonElement` после того, как `JsonDocument`, которому он принадлежит, будет удален.

Ниже приведен пример, в котором необходимо сделать `Clone`:

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

Приведенный выше код ждет `JsonElement`, содержащий свойство `fileName`. Он открывает JSON-файл и создает `JsonDocument`. Метод предполагает, что вызывающий объект хочет работать со всем документом, поэтому он возвращает `Clone` `RootElement`. 

Если вы получаете `JsonElement` и возвращаете вложенный элемент, нет необходимости возвращать `Clone` вложенного элемента. Вызывающий объект отвечает за поддержание активности `JsonDocument`, к которой принадлежит переданный `JsonElement`. Например:

```csharp
public JsonElement ReturnFileName(JsonElement source)
{
   return source.GetProperty("fileName");
}
```

### <a name="jsondocument-is-read-only"></a>Жсондокумент доступен только для чтения

<xref:System.Text.Json> DOM не удается добавить, удалить или изменить элементы JSON. Он разработан таким образом для повышения производительности и сокращения количества выделений для анализа общих размеров полезных данных JSON (то есть < 1 МБ). Если в вашем сценарии используется изменяемая модель DOM, возможны следующие обходные пути.

* Чтобы создать `JsonDocument` с нуля (то есть без передачи существующих полезных данных JSON в метод `Parse`), напишите текст JSON с помощью `Utf8JsonWriter` и Проанализируйте выходные данные, чтобы создать новый `JsonDocument`.
* Чтобы изменить существующий `JsonDocument`, используйте его для записи текста JSON, внесения изменений во время записи и синтаксического анализа выходных данных для создания нового `JsonDocument`.
* Сведения о слиянии существующих документов JSON, эквивалентных API `JObject.Merge` или `JContainer.Merge` из `Newtonsoft.Json`, см. в [этой статье о проблемах GitHub](https://github.com/dotnet/corefx/issues/42466#issuecomment-570475853).

### <a name="jsonelement-is-a-union-struct"></a>Жсонелемент является структурой объединения

`JsonDocument` предоставляет `RootElement` как свойство типа <xref:System.Text.Json.JsonElement>— объединение, тип структуры, охватывающий любой элемент JSON. `Newtonsoft.Json` использует выделенные иерархические типы, такие как `JObject`,`JArray`, `JToken`и т. д. `JsonElement` — это то, что можно искать и перечислять, и можно использовать `JsonElement` для материализации элементов JSON в типы .NET.

### <a name="how-to-search-a-jsondocument-and-jsonelement-for-sub-elements"></a>Поиск вложенных элементов в Жсондокумент и Жсонелемент

Выполняет поиск токенов JSON с помощью `JObject` или `JArray` от `Newtonsoft.Json`, как правило, выполняется относительно быстро, так как они уточняются в каком-либо словаре. По сравнению, поиск по `JsonElement` требует последовательного поиска свойств и, следовательно, довольно медленный (например, при использовании `TryGetProperty`). <xref:System.Text.Json> предназначено для снижения начального времени анализа, а не времени поиска. Поэтому используйте следующие подходы для оптимизации производительности при поиске по объекту `JsonDocument`.

* Используйте встроенные перечислители (<xref:System.Text.Json.JsonElement.EnumerateArray%2A> и <xref:System.Text.Json.JsonElement.EnumerateObject%2A>) вместо выполнения собственных индексов или циклов.
* Не выполняйте последовательный поиск по всему `JsonDocument` через каждое свойство с помощью `RootElement`. Вместо этого выполните поиск по вложенным объектам JSON на основе известной структуры данных JSON. Например, если вы ищете свойство `Grade` в `Student` объектов, пройдите по `Student`ным объектам и получите значение `Grade` для каждого из них, вместо того чтобы выполнять поиск по всем объектам `JsonElement`, которые ищут свойства `Grade`. Выполнение второго действия приведет к ненужным проходам по тем же данным.

Пример кода см. в разделе [Использование жсондокумент для доступа к данным](system-text-json-how-to.md#use-jsondocument-for-access-to-data).

## <a name="utf8jsonreader-compared-to-jsontextreader"></a>Utf8JsonReader по сравнению с Жсонтекстреадер

<xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> — это высокопроизводительное, медленное средство чтения, доступное только для прямого просмотра для текста JSON в кодировке UTF-8, чтение из [реадонлиспан\<байт >](xref:System.ReadOnlySpan%601) или [реадонлисекуенце\<байт >](xref:System.Buffers.ReadOnlySequence%601). `Utf8JsonReader` — это тип низкого уровня, который можно использовать для создания пользовательских средств синтаксического анализа и десериализаторов.

В следующих разделах описываются рекомендуемые шаблоны программирования для использования `Utf8JsonReader`.

### <a name="utf8jsonreader-is-a-ref-struct"></a>Utf8JsonReader является структурой ссылок

Поскольку тип `Utf8JsonReader` является *структурой ссылок*, он имеет [определенные ограничения](../../csharp/language-reference/keywords/ref.md#ref-struct-types). Например, он не может храниться как поле в классе или структуре, отличной от структуры ссылки. Для достижения высокой производительности этот тип должен быть `ref struct` так как он должен кэшировать входные [реадонлиспан\<byte >](xref:System.ReadOnlySpan%601), что является структурой ссылок. Кроме того, этот тип является изменяемым, так как он содержит состояние. Поэтому **передайте его по ссылке** , а не по значению. Передача его по значению приведет к копированию структуры, и изменения состояния не будут видны вызывающему объекту. Это отличается от `Newtonsoft.Json`, так как `Newtonsoft.Json` `JsonTextReader` является классом. Дополнительные сведения об использовании структур ref см. в разделе [написание безопасного и C# эффективного кода](../../csharp/write-safe-efficient-code.md).

### <a name="read-utf-8-text"></a>Чтение текста UTF-8

Для достижения наилучшей производительности при использовании `Utf8JsonReader`прочтите полезные данные JSON, уже закодированные как текст UTF-8, а не как строки UTF-16. Пример кода см. в разделе [Фильтрация данных с помощью Utf8JsonReader](system-text-json-how-to.md#filter-data-using-utf8jsonreader).

### <a name="read-with-a-stream-or-pipereader"></a>Чтение с помощью потока или Пипереадер

`Utf8JsonReader` поддерживает чтение из кодировки UTF-8 [реадонлиспан\<byte >](xref:System.ReadOnlySpan%601) или [реадонлисекуенце\<Byte >](xref:System.Buffers.ReadOnlySequence%601) (что является результатом чтения из <xref:System.IO.Pipelines.PipeReader>).

Для синхронного чтения можно считать полезные данные JSON до конца потока в массив байтов и передать его в модуль чтения. Для чтения из строки (которая кодируется в кодировке UTF-16) вызовите <xref:System.Text.Encoding.UTF8>.<xref:System.Text.Encoding.GetBytes%2A> Сначала перекодирует строку в массив байтов в кодировке UTF-8. Затем передайте его в `Utf8JsonReader`. 

Поскольку `Utf8JsonReader` считает входные данные текстом JSON, отметка порядка байтов UTF-8 (BOM) считается недопустимым JSON. Вызывающий объект должен отфильтровать это, прежде чем передавать данные в модуль чтения.

Примеры кода см. в разделе [use Utf8JsonReader](system-text-json-how-to.md#use-utf8jsonreader).

### <a name="read-with-multi-segment-readonlysequence"></a>Чтение с помощью Реадонлисекуенце нескольких сегментов

Если входные данные JSON являются [реадонлиспан\<](xref:System.ReadOnlySpan%601), к каждому элементу JSON можно получить доступ из свойства `ValueSpan` в модуле чтения по мере прохождения цикла чтения. Однако если входные данные являются [реадонлисекуенце\<](xref:System.Buffers.ReadOnlySequence%601) (что является результатом чтения из <xref:System.IO.Pipelines.PipeReader>), некоторые элементы JSON могут повлечь за собой несколько сегментов объекта `ReadOnlySequence<byte>`. Эти элементы не будут доступны из <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> в непрерывном блоке памяти. Вместо этого каждый раз, когда у вас есть несколько сегментов `ReadOnlySequence<byte>` в качестве входных данных, следует опросить свойство <xref:System.Text.Json.Utf8JsonReader.HasValueSequence%2A> в модуле чтения, чтобы выяснить, как получить доступ к текущему элементу JSON. Вот рекомендуемый шаблон:

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

### <a name="use-valuetextequals-for-property-name-lookups"></a>Использование Валуетекстекуалс для поиска имен свойств

Не используйте <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> для сравнения по байтам путем вызова <xref:System.MemoryExtensions.SequenceEqual%2A> для уточняющих запросов имени свойства. Вместо этого вызовите <xref:System.Text.Json.Utf8JsonReader.ValueTextEquals%2A>, так как этот метод преобразует все символы, которые экранированы в JSON. Ниже приведен пример, демонстрирующий Поиск свойства с именем Name.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ValueTextEqualsExample.cs?name=SnippetDefineUtf8Var)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ValueTextEqualsExample.cs?name=SnippetUseUtf8Var&highlight=11)]

### <a name="read-null-values-into-nullable-value-types"></a>Считывание значений NULL в типы значений, допускающие значения NULL

`Newtonsoft.Json` предоставляет интерфейсы API, которые возвращают <xref:System.Nullable%601>, такие как `ReadAsBoolean`, который обрабатывает `Null` `TokenType`, возвращая `bool?`. Встроенные API-интерфейсы `System.Text.Json` возвращают только типы значений, не допускающие значения NULL. Например, <xref:System.Text.Json.Utf8JsonReader.GetBoolean%2A?displayProperty=nameWithType> возвращает `bool`. Он вызывает исключение, если обнаруживает `Null` в JSON. В следующих примерах показаны два способа обработки значений NULL, один из которых возвращает тип значения, допускающего значение null, и один, возвращая значение по умолчанию:

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

Если необходимо продолжить использование `Newtonsoft.Json` для определенных целевых платформ, можно использовать несколько целевых версий и две реализации. Однако это нетривиальный, и потребуется некоторое `#ifdefs` и дублирование источника. Одним из способов совместного использования максимально возможного объема кода является создание `ref struct`ной оболочки для `Utf8JsonReader` и `Newtonsoft.Json` `JsonTextReader`. Эта оболочка будет объединять общедоступную контактную зону при изоляции различий в поведении. Это позволяет изолировать изменения в основном с созданием типа, а также передавать новый тип по ссылке. Это шаблон, который следует библиотеке [Microsoft. Extensions. депенденцимодел](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) :

* [UnifiedJsonReader.JsonTextReader.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.JsonTextReader.cs)
* [UnifiedJsonReader.Utf8JsonReader.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.Utf8JsonReader.cs)

## <a name="utf8jsonwriter-compared-to-jsontextwriter"></a>Utf8JsonWriter по сравнению с JsonTextWriter

<xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> — это высокопроизводительный способ записи текста JSON в кодировке UTF-8 из распространенных типов .NET, таких как `String`, `Int32`и `DateTime`. Модуль записи — это тип низкого уровня, который можно использовать для создания пользовательских сериализаторов.

В следующих разделах описываются рекомендуемые шаблоны программирования для использования `Utf8JsonWriter`.

### <a name="write-with-utf-8-text"></a>Запись с помощью текста UTF-8

Чтобы достичь максимальной производительности при использовании `Utf8JsonWriter`, напишите полезные данные JSON, уже закодированные как текст UTF-8, а не как строки UTF-16. Используйте <xref:System.Text.Json.JsonEncodedText> для кэширования и предварительно закодировать имена и значения именованных свойств строки как статические и передать их в модуль записи вместо использования строковых литералов UTF-16. Это быстрее, чем кэширование и использование байтовых массивов UTF-8.

Этот подход также работает, если необходимо выполнить пользовательское экранирование. `System.Text.Json` не позволяет отключить экранирование при записи строки. Однако можно передать собственный пользовательский <xref:System.Text.Encodings.Web.JavaScriptEncoder> в качестве параметра для модуля записи или создать собственную `JsonEncodedText`, которая использует `JavascriptEncoder` для выполнения экранирования, а затем написать `JsonEncodedText` вместо строки. Дополнительные сведения см. в разделе [Настройка кодировки символов](system-text-json-how-to.md#customize-character-encoding).

### <a name="write-raw-values"></a>Запись необработанных значений

Метод `Newtonsoft.Json` `WriteRawValue` записывает необработанный код JSON, где ожидается значение. <xref:System.Text.Json> не имеет прямого эквивалента, но ниже приведено решение, обеспечивающее написание только допустимого JSON:

```csharp
using JsonDocument doc = JsonDocument.Parse(string);
doc.WriteTo(writer);
```

### <a name="customize-character-escaping"></a>Настройка экранирования символов

Параметр [стринжескапехандлинг](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_StringEscapeHandling.htm) `JsonTextWriter` предлагает параметры для экранирования всех символов, не являющихся символами ASCII **, или** символов HTML. По умолчанию `Utf8JsonWriter` обходит все символы, отличные от ASCII **и** HTML. Такое экранирование выполняется в целях глубокой защиты. Чтобы указать другую политику экранирования, создайте <xref:System.Text.Encodings.Web.JavaScriptEncoder> и задайте <xref:System.Text.Json.JsonWriterOptions.Encoder?displayProperty=nameWithType>. Дополнительные сведения см. в разделе [Настройка кодировки символов](system-text-json-how-to.md#customize-character-encoding).

### <a name="customize-json-format"></a>Настройка формата JSON

`JsonTextWriter` включает следующие параметры, для которых `Utf8JsonWriter` не имеет эквивалента.

* [Отступ](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_Indentation.htm) — задает количество символов для отступа. `Utf8JsonWriter` всегда имеет 2-значный отступ.
* [Индентчар](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_IndentChar.htm) — указывает символ, используемый для отступа.  `Utf8JsonWriter` всегда использует пробелы.
* [QuoteChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteChar.htm) — указывает символ, используемый для окружить строковых значений.  `Utf8JsonWriter` всегда использует двойные кавычки.
* [QuoteName](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteName.htm) — указывает, следует ли заключать имена свойств в кавычки.  `Utf8JsonWriter` всегда заключаются в кавычки.

Не существует решений, которые позволяют настроить JSON, созданный `Utf8JsonWriter`.

### <a name="write-null-values"></a>Записать значения NULL

Чтобы записать значения NULL с помощью `Utf8JsonWriter`, вызовите:

* <xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A> записать пару "ключ-значение" со значением NULL в качестве значения.
* <xref:System.Text.Json.Utf8JsonWriter.WriteNullValue%2A> записать значение null как элемент массива JSON.

Для строкового свойства, если строка имеет значение null, <xref:System.Text.Json.Utf8JsonWriter.WriteString%2A> и <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A> эквивалентны `WriteNull` и `WriteNullValue`.

### <a name="write-timespan-uri-or-char-values"></a>Запись значений TimeSpan, URI или char

`JsonTextWriter` предоставляет методы `WriteValue` для значений [TimeSpan](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_18.htm), [URI](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_22.htm)и [char](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_3.htm) . `Utf8JsonWriter` не имеет эквивалентных методов. Вместо этого следует отформатировать эти значения как строки (например, вызвав `ToString()`) и вызвать <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A>.

### <a name="multi-targeting"></a>Настройка для различных версий

Если необходимо продолжить использование `Newtonsoft.Json` для определенных целевых платформ, можно использовать несколько целевых версий и две реализации. Однако это нетривиальный, и потребуется некоторое `#ifdefs` и дублирование источника. Одним из способов совместного использования максимально возможного объема кода является создание оболочки для `Utf8JsonWriter` и `Newtonsoft` `JsonTextWriter`. Эта оболочка будет объединять общедоступную контактную зону при изоляции различий в поведении. Это позволяет изолировать изменения в основном с созданием типа. Библиотека [Microsoft. Extensions. депенденцимодел](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) выглядит следующим образом:

* [UnifiedJsonWriter.JsonTextWriter.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.JsonTextWriter.cs)
* [UnifiedJsonWriter.Utf8JsonWriter.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.Utf8JsonWriter.cs)

## <a name="additional-resources"></a>Дополнительные ресурсы

<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)[Restore this when the roadmap is updated.]-->
* [Обзор System.Text.Json](system-text-json-overview.md)
* [Использование System.Text.Json](system-text-json-how-to.md)
* [Написание пользовательских преобразователей](system-text-json-converters-how-to.md)
* [Поддержка DateTime и DateTimeOffset в System.Text.Json](../datetime/system-text-json-support.md)
* [Справочник по System.Text.Json API](xref:System.Text.Json)
* [System.Text.Json. Справочник по API сериализации](xref:System.Text.Json.Serialization)
