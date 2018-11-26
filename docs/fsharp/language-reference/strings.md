---
title: Строки (F#)
description: Узнайте, как F# типа «строка» представляет неизменяемый текст как последовательность символов Юникода.
ms.date: 05/16/2016
ms.openlocfilehash: 158e30224fe50c2324e40d550b75e6abaf843597
ms.sourcegitcommit: 35316b768394e56087483cde93f854ba607b63bc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2018
ms.locfileid: "52296795"
---
# <a name="strings"></a><span data-ttu-id="f2f2f-103">Строки</span><span class="sxs-lookup"><span data-stu-id="f2f2f-103">Strings</span></span>

> [!NOTE]
> <span data-ttu-id="f2f2f-104">Ссылки на справочник по API в этой статье ведут на сайт MSDN.</span><span class="sxs-lookup"><span data-stu-id="f2f2f-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="f2f2f-105">Работа над справочником по API docs.microsoft.com не завершена.</span><span class="sxs-lookup"><span data-stu-id="f2f2f-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="f2f2f-106">`string` Тип представляет неизменяемый текст как последовательность символов Юникода.</span><span class="sxs-lookup"><span data-stu-id="f2f2f-106">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="f2f2f-107">`string` — это псевдоним для `System.String` в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f2f2f-107">`string` is an alias for `System.String` in the .NET Framework.</span></span>

## <a name="remarks"></a><span data-ttu-id="f2f2f-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="f2f2f-108">Remarks</span></span>

<span data-ttu-id="f2f2f-109">Строковые литералы разделяются знаком кавычки ("").</span><span class="sxs-lookup"><span data-stu-id="f2f2f-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="f2f2f-110">Символ обратной косой черты ( \\ ) используется для кодирования некоторых специальных знаков.</span><span class="sxs-lookup"><span data-stu-id="f2f2f-110">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="f2f2f-111">Обратная косая черта и следующий знак вместе называются *escape-последовательности*.</span><span class="sxs-lookup"><span data-stu-id="f2f2f-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="f2f2f-112">Escape-последовательности, поддерживаемые в F# строковые литералы, показаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="f2f2f-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="f2f2f-113">Знак</span><span class="sxs-lookup"><span data-stu-id="f2f2f-113">Character</span></span>|<span data-ttu-id="f2f2f-114">Escape-последовательность</span><span class="sxs-lookup"><span data-stu-id="f2f2f-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="f2f2f-115">Backspace</span><span class="sxs-lookup"><span data-stu-id="f2f2f-115">Backspace</span></span>|`\b`|
|<span data-ttu-id="f2f2f-116">Новая строка</span><span class="sxs-lookup"><span data-stu-id="f2f2f-116">Newline</span></span>|`\n`|
|<span data-ttu-id="f2f2f-117">Возврат каретки</span><span class="sxs-lookup"><span data-stu-id="f2f2f-117">Carriage return</span></span>|`\r`|
|<span data-ttu-id="f2f2f-118">Tab</span><span class="sxs-lookup"><span data-stu-id="f2f2f-118">Tab</span></span>|`\t`|
|<span data-ttu-id="f2f2f-119">Обратная косая черта</span><span class="sxs-lookup"><span data-stu-id="f2f2f-119">Backslash</span></span>|`\\`|
|<span data-ttu-id="f2f2f-120">Знак кавычек</span><span class="sxs-lookup"><span data-stu-id="f2f2f-120">Quotation mark</span></span>|`\"`|
|<span data-ttu-id="f2f2f-121">Апостроф</span><span class="sxs-lookup"><span data-stu-id="f2f2f-121">Apostrophe</span></span>|`\'`|
|<span data-ttu-id="f2f2f-122">символ Юникода</span><span class="sxs-lookup"><span data-stu-id="f2f2f-122">Unicode character</span></span>|<span data-ttu-id="f2f2f-123">`\uXXXX` или `\UXXXX` (где `X` указывает шестнадцатеричная цифра)</span><span class="sxs-lookup"><span data-stu-id="f2f2f-123">`\uXXXX` or `\UXXXX` (where `X` indicates a hexadecimal digit)</span></span>|

<span data-ttu-id="f2f2f-124">Если предшествует символ @, литерал является буквальная строка.</span><span class="sxs-lookup"><span data-stu-id="f2f2f-124">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="f2f2f-125">Это означает, что все escape-последовательности игнорируются, за исключением того, что два символа кавычки, интерпретируются как один знак кавычки.</span><span class="sxs-lookup"><span data-stu-id="f2f2f-125">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

<span data-ttu-id="f2f2f-126">Кроме того строки могут быть заключены в кавычки тройной.</span><span class="sxs-lookup"><span data-stu-id="f2f2f-126">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="f2f2f-127">В этом случае все escape-последовательности игнорируются, включая символы двойных кавычек.</span><span class="sxs-lookup"><span data-stu-id="f2f2f-127">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="f2f2f-128">Чтобы указать строку, которая содержит внедренную строку в кавычках, можно использовать либо буквальная строка или строку в тройных кавычках.</span><span class="sxs-lookup"><span data-stu-id="f2f2f-128">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="f2f2f-129">Если вы используете буквальная строка, необходимо указать двух знаков кавычек, чтобы указать символ одинарной кавычки.</span><span class="sxs-lookup"><span data-stu-id="f2f2f-129">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="f2f2f-130">Если вы используете строку в тройных кавычках, можно использовать символов одинарных кавычек без них, проанализированных в качестве конца строки.</span><span class="sxs-lookup"><span data-stu-id="f2f2f-130">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="f2f2f-131">Этот метод можно использовать при работе с XML-индекс или другие структуры, которые включают внедренные кавычки.</span><span class="sxs-lookup"><span data-stu-id="f2f2f-131">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="f2f2f-132">В коде допустимы строки, содержащие разрывы и разрывы строки интерпретируются буквально как символы новой строки, если обратная косая черта является последним символом перед разрывом строки.</span><span class="sxs-lookup"><span data-stu-id="f2f2f-132">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="f2f2f-133">Начальные пробелы в следующей строке учитывается, если используется обратная косая черта.</span><span class="sxs-lookup"><span data-stu-id="f2f2f-133">Leading white space on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="f2f2f-134">Следующий код создает строку `str1` значением `"abc\ndef"` и строка `str2` значением `"abcdef"`.</span><span class="sxs-lookup"><span data-stu-id="f2f2f-134">The following code produces a string `str1` that has value `"abc\ndef"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

<span data-ttu-id="f2f2f-135">Можно получить доступ к отдельных символов в строке, используя синтаксис, подобный массиву, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="f2f2f-135">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="f2f2f-136">В результате получается `b`.</span><span class="sxs-lookup"><span data-stu-id="f2f2f-136">The output is `b`.</span></span>

<span data-ttu-id="f2f2f-137">Или можно извлечь подстроки, используя синтаксис срез массива, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="f2f2f-137">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="f2f2f-138">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="f2f2f-138">The output is as follows.</span></span>

```
abc
def
```

<span data-ttu-id="f2f2f-139">Строки ASCII могут быть представлены массивы байтов без знака, тип `byte[]`.</span><span class="sxs-lookup"><span data-stu-id="f2f2f-139">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="f2f2f-140">Добавьте суффикс `B` в строковый литерал, он является строкой ASCII.</span><span class="sxs-lookup"><span data-stu-id="f2f2f-140">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="f2f2f-141">Строковые литералы ASCII, используемые с байтовыми массивами поддерживает же escape-последовательности, как строки в Юникоде, за исключением escape-последовательности Юникода.</span><span class="sxs-lookup"><span data-stu-id="f2f2f-141">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a><span data-ttu-id="f2f2f-142">Строковые операторы</span><span class="sxs-lookup"><span data-stu-id="f2f2f-142">String Operators</span></span>

<span data-ttu-id="f2f2f-143">Существует два способа для сцепления строк: с помощью `+` оператор или с помощью `^` оператор.</span><span class="sxs-lookup"><span data-stu-id="f2f2f-143">There are two ways to concatenate strings: by using the `+` operator or by using the `^` operator.</span></span> <span data-ttu-id="f2f2f-144">`+` Оператор, обеспечена совместимость с функциями обработки строк платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f2f2f-144">The `+` operator maintains compatibility with the .NET Framework string handling features.</span></span>

<span data-ttu-id="f2f2f-145">В следующем примере показано объединение строк.</span><span class="sxs-lookup"><span data-stu-id="f2f2f-145">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a><span data-ttu-id="f2f2f-146">Класс String</span><span class="sxs-lookup"><span data-stu-id="f2f2f-146">String Class</span></span>

<span data-ttu-id="f2f2f-147">Так как тип строки в F# является фактически .NET Framework `System.String` введите все `System.String` элементы доступны.</span><span class="sxs-lookup"><span data-stu-id="f2f2f-147">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="f2f2f-148">Сюда входят `+` оператор, который используется для объединения строк, `Length` свойство и `Chars` свойство, которое возвращает строку в виде массива знаков Юникода.</span><span class="sxs-lookup"><span data-stu-id="f2f2f-148">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="f2f2f-149">Дополнительные сведения о строках см. в разделе `System.String`.</span><span class="sxs-lookup"><span data-stu-id="f2f2f-149">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="f2f2f-150">С помощью `Chars` свойство `System.String`, доступ к отдельным символам в строке путем указания индекса, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="f2f2f-150">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a><span data-ttu-id="f2f2f-151">Модуль строки</span><span class="sxs-lookup"><span data-stu-id="f2f2f-151">String Module</span></span>

<span data-ttu-id="f2f2f-152">Дополнительные функции обработки строк включены в `String` модуля в `FSharp.Core` пространства имен.</span><span class="sxs-lookup"><span data-stu-id="f2f2f-152">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="f2f2f-153">Дополнительные сведения см. в разделе [модуль Core.String](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="f2f2f-153">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="f2f2f-154">См. также</span><span class="sxs-lookup"><span data-stu-id="f2f2f-154">See also</span></span>

- [<span data-ttu-id="f2f2f-155">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="f2f2f-155">F# Language Reference</span></span>](index.md)
