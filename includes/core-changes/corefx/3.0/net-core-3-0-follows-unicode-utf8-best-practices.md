---
ms.openlocfilehash: db1d09c8c9e606b5327a42977a74a74703282d84
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568118"
---
### <a name="net-core-30-follows-unicode-best-practices-when-replacing-ill-formed-utf-8-byte-sequences"></a>В .NET Core 3.0 применяются рекомендации по Юникоду при замене некорректных последовательностей байтов UTF-8

Когда класс <xref:System.Text.UTF8Encoding> обнаруживает некорректную последовательность байтов в кодировке UTF-8 при перекодировании байт в символы, он заменяет эту последовательность символом "�" (символ замены U+FFFD) в выходной строке. В .NET Core 3.0, в отличие от предыдущих версий .NET Core и .NET Framework, применяются рекомендации по Юникоду для таких замен при операциях перекодирования.

Это лишь часть больших усилий улучшить обработку данных в формате UTF-8 в .NET, включая новые типы <xref:System.Text.Unicode.Utf8?displayProperty=nameWithType> и <xref:System.Text.Rune?displayProperty=nameWithType>. Для типа <xref:System.Text.UTF8Encoding> предоставлен улучшенный механизм обработки ошибок, чтобы его выходные данные соответствовали новым типам.

#### <a name="change-description"></a>Описание изменений

Начиная с .NET Core 3.0, при перекодировании байтов в символы класс <xref:System.Text.UTF8Encoding> выполняет подстановку символов на основе рекомендаций по Юникоду. Используемый механизм подстановки описан в [документе по стандарту "Юникод" версии 12.0, раздел 3.9 (PDF)](https://www.unicode.org/versions/Unicode12.0.0/ch03.pdf) с заголовком _U+FFFD Substitution of Maximal Subparts_ (Замена наибольшей части неправильной последовательности символом U+FFFD).

Такой подход _применяется_ только в том случае, если входная последовательность байтов содержит некорректные данные в кодировке UTF-8. Кроме того, если экземпляр <xref:System.Text.UTF8Encoding> был создан с помощью `throwOnInvalidBytes: true` (см. [документацию по конструктору UTF8Encoding](<xref:System.Text.UTF8Encoding.%23ctor(System.Boolean,System.Boolean)>, экземпляр `UTF8Encoding` будет и дальше выдавать исключение при недопустимых входных данных, а не выполнять замену символом U+FFFD.

Ниже показано влияние этого изменения на примере недопустимых 3-байтовых входных данных:

|Некорректно сформированные 3-байтовые входные данные|Выходные данные в версиях до .NET Core 3.0|Выходные данные в .NET Core 3.0 и более поздних версиях|
|---|---|---|
| `[ ED A0 90 ]` | `[ FFFD FFFD ]` (выходные данные в виде двухзначного кода)| `[ FFFD FFFD FFFD ]` (выходные данные в виде трехзначного кода)|

Согласно _таблице 3-9_ из PDF-документа по Юникоду, ссылка на который приведена выше, предпочтительным является вариант с выходными данными в виде трехзначного кода.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="recommended-action"></a>Рекомендуемое действие

От разработчика не требуется никаких действий.

#### <a name="category"></a>Категория

CoreFX

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Text.UTF8Encoding.GetCharCount%2A?displayProperty=nameWithType>
- <xref:System.Text.UTF8Encoding.GetChars%2A?displayProperty=nameWithType>
- <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=nameWithType>

<!--

### Affected APIs

- `Overload:System.Text.UTF8Encoding.GetCharCount`
- `Overload:System.Text.UTF8Encoding.GetChars`
- `M:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)`

-->
