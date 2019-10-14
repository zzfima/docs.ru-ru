---
ms.openlocfilehash: db1d09c8c9e606b5327a42977a74a74703282d84
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2019
ms.locfileid: "72237447"
---
### <a name="net-core-30-follows-unicode-best-practices-when-replacing-ill-formed-utf-8-byte-sequences"></a><span data-ttu-id="48cb1-101">В .NET Core 3.0 применяются рекомендации по Юникоду при замене некорректных последовательностей байтов UTF-8</span><span class="sxs-lookup"><span data-stu-id="48cb1-101">.NET Core 3.0 follows Unicode best practices when replacing ill-formed UTF-8 byte sequences</span></span>

<span data-ttu-id="48cb1-102">Когда класс <xref:System.Text.UTF8Encoding> обнаруживает некорректную последовательность байтов в кодировке UTF-8 при перекодировании байт в символы, он заменяет эту последовательность символом "�" (символ замены U+FFFD) в выходной строке.</span><span class="sxs-lookup"><span data-stu-id="48cb1-102">When the <xref:System.Text.UTF8Encoding> class encounters an ill-formed UTF-8 byte sequence during a byte-to-character transcoding operation, it will replace that sequence with a '�' (U+FFFD REPLACEMENT CHARACTER) character in the output string.</span></span> <span data-ttu-id="48cb1-103">В .NET Core 3.0, в отличие от предыдущих версий .NET Core и .NET Framework, применяются рекомендации по Юникоду для таких замен при операциях перекодирования.</span><span class="sxs-lookup"><span data-stu-id="48cb1-103">.NET Core 3.0 differs from previous versions of .NET Core and the .NET Framework by following the Unicode best practice for performing this replacement during the transcoding operation.</span></span>

<span data-ttu-id="48cb1-104">Это лишь часть больших усилий улучшить обработку данных в формате UTF-8 в .NET, включая новые типы <xref:System.Text.Unicode.Utf8?displayProperty=nameWithType> и <xref:System.Text.Rune?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="48cb1-104">This is part of a larger effort to improve UTF-8 handling throughout .NET, including by the new <xref:System.Text.Unicode.Utf8?displayProperty=nameWithType> and <xref:System.Text.Rune?displayProperty=nameWithType> types.</span></span> <span data-ttu-id="48cb1-105">Для типа <xref:System.Text.UTF8Encoding> предоставлен улучшенный механизм обработки ошибок, чтобы его выходные данные соответствовали новым типам.</span><span class="sxs-lookup"><span data-stu-id="48cb1-105">The <xref:System.Text.UTF8Encoding> type was given improved error handling mechanics so that it produces output consistent with the newly introduced types.</span></span>

#### <a name="change-description"></a><span data-ttu-id="48cb1-106">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="48cb1-106">Change description</span></span>

<span data-ttu-id="48cb1-107">Начиная с .NET Core 3.0, при перекодировании байтов в символы класс <xref:System.Text.UTF8Encoding> выполняет подстановку символов на основе рекомендаций по Юникоду.</span><span class="sxs-lookup"><span data-stu-id="48cb1-107">Starting with .NET Core 3.0, when transcoding bytes to characters, the <xref:System.Text.UTF8Encoding> class performs character substitution based on Unicode best practices.</span></span> <span data-ttu-id="48cb1-108">Используемый механизм подстановки описан в [документе по стандарту "Юникод" версии 12.0, раздел 3.9 (PDF)](https://www.unicode.org/versions/Unicode12.0.0/ch03.pdf) с заголовком _U+FFFD Substitution of Maximal Subparts_ (Замена наибольшей части неправильной последовательности символом U+FFFD).</span><span class="sxs-lookup"><span data-stu-id="48cb1-108">The substitution mechanism used is described by [The Unicode Standard, Version 12.0, Sec. 3.9 (PDF)](https://www.unicode.org/versions/Unicode12.0.0/ch03.pdf) in the heading titled _U+FFFD Substitution of Maximal Subparts_.</span></span>

<span data-ttu-id="48cb1-109">Такой подход _применяется_ только в том случае, если входная последовательность байтов содержит некорректные данные в кодировке UTF-8.</span><span class="sxs-lookup"><span data-stu-id="48cb1-109">This behavior _only_ applies when the input byte sequence contains ill-formed UTF-8 data.</span></span> <span data-ttu-id="48cb1-110">Кроме того, если экземпляр <xref:System.Text.UTF8Encoding> был создан с помощью `throwOnInvalidBytes: true` (см. [документацию по конструктору UTF8Encoding](<xref:System.Text.UTF8Encoding.%23ctor(System.Boolean,System.Boolean)>, экземпляр `UTF8Encoding` будет и дальше выдавать исключение при недопустимых входных данных, а не выполнять замену символом U+FFFD.</span><span class="sxs-lookup"><span data-stu-id="48cb1-110">Additionally, if the <xref:System.Text.UTF8Encoding> instance has been constructed with `throwOnInvalidBytes: true` (see the [UTF8Encoding constructor documentation](<xref:System.Text.UTF8Encoding.%23ctor(System.Boolean,System.Boolean)>, the `UTF8Encoding` instance will continue to throw on invalid input rather than perform U+FFFD replacement.</span></span>

<span data-ttu-id="48cb1-111">Ниже показано влияние этого изменения на примере недопустимых 3-байтовых входных данных:</span><span class="sxs-lookup"><span data-stu-id="48cb1-111">The following illustrates the impact of this change with an invalid 3-byte input:</span></span>

|<span data-ttu-id="48cb1-112">Некорректно сформированные 3-байтовые входные данные</span><span class="sxs-lookup"><span data-stu-id="48cb1-112">Ill-formed 3-byte input</span></span>|<span data-ttu-id="48cb1-113">Выходные данные в версиях до .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="48cb1-113">Output before .NET Core 3.0</span></span>|<span data-ttu-id="48cb1-114">Выходные данные в .NET Core 3.0 и более поздних версиях</span><span class="sxs-lookup"><span data-stu-id="48cb1-114">Output starting with .NET Core 3.0</span></span>|
|---|---|---|
| `[ ED A0 90 ]` | <span data-ttu-id="48cb1-115">`[ FFFD FFFD ]` (выходные данные в виде двухзначного кода)</span><span class="sxs-lookup"><span data-stu-id="48cb1-115">`[ FFFD FFFD ]` (2-character output)</span></span>| <span data-ttu-id="48cb1-116">`[ FFFD FFFD FFFD ]` (выходные данные в виде трехзначного кода)</span><span class="sxs-lookup"><span data-stu-id="48cb1-116">`[ FFFD FFFD FFFD ]` (3-character output)</span></span>|

<span data-ttu-id="48cb1-117">Согласно _таблице 3-9_ из PDF-документа по Юникоду, ссылка на который приведена выше, предпочтительным является вариант с выходными данными в виде трехзначного кода.</span><span class="sxs-lookup"><span data-stu-id="48cb1-117">This 3-char output is the preferred output, according to _Table 3-9_ of the previously linked Unicode Standard PDF.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="48cb1-118">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="48cb1-118">Version introduced</span></span>

<span data-ttu-id="48cb1-119">3.0</span><span class="sxs-lookup"><span data-stu-id="48cb1-119">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="48cb1-120">Рекомендуемое действие</span><span class="sxs-lookup"><span data-stu-id="48cb1-120">Recommended action</span></span>

<span data-ttu-id="48cb1-121">От разработчика не требуется никаких действий.</span><span class="sxs-lookup"><span data-stu-id="48cb1-121">No action is required on the part of the developer.</span></span>

#### <a name="category"></a><span data-ttu-id="48cb1-122">Категория</span><span class="sxs-lookup"><span data-stu-id="48cb1-122">Category</span></span>

<span data-ttu-id="48cb1-123">CoreFX</span><span class="sxs-lookup"><span data-stu-id="48cb1-123">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="48cb1-124">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="48cb1-124">Affected APIs</span></span>

- <xref:System.Text.UTF8Encoding.GetCharCount%2A?displayProperty=nameWithType>
- <xref:System.Text.UTF8Encoding.GetChars%2A?displayProperty=nameWithType>
- <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=nameWithType>

<!--

### Affected APIs

- `Overload:System.Text.UTF8Encoding.GetCharCount`
- `Overload:System.Text.UTF8Encoding.GetChars`
- `M:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)`

-->
