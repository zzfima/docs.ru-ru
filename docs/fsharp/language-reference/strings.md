---
title: Строки
description: Узнайте, как F# типа «строка» представляет неизменяемый текст как последовательность символов Юникода.
ms.date: 07/05/2019
ms.openlocfilehash: ec895723cc6d21a701a27b5d70d053bb681ce2b3
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2019
ms.locfileid: "67660601"
---
# <a name="strings"></a><span data-ttu-id="bce97-103">Строки</span><span class="sxs-lookup"><span data-stu-id="bce97-103">Strings</span></span>

> [!NOTE]
> <span data-ttu-id="bce97-104">Ссылки на справочник по API в этой статье ведут на сайт MSDN.</span><span class="sxs-lookup"><span data-stu-id="bce97-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="bce97-105">Работа над справочником по API docs.microsoft.com не завершена.</span><span class="sxs-lookup"><span data-stu-id="bce97-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="bce97-106">`string` Тип представляет неизменяемый текст как последовательность символов Юникода.</span><span class="sxs-lookup"><span data-stu-id="bce97-106">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="bce97-107">`string` — это псевдоним для `System.String` в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bce97-107">`string` is an alias for `System.String` in the .NET Framework.</span></span>

## <a name="remarks"></a><span data-ttu-id="bce97-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="bce97-108">Remarks</span></span>

<span data-ttu-id="bce97-109">Строковые литералы разделяются знаком кавычки ("").</span><span class="sxs-lookup"><span data-stu-id="bce97-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="bce97-110">Символ обратной косой черты ( \\ ) используется для кодирования некоторых специальных знаков.</span><span class="sxs-lookup"><span data-stu-id="bce97-110">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="bce97-111">Обратная косая черта и следующий знак вместе называются *escape-последовательности*.</span><span class="sxs-lookup"><span data-stu-id="bce97-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="bce97-112">Escape-последовательности, поддерживаемые в F# строковые литералы, показаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="bce97-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="bce97-113">Знак</span><span class="sxs-lookup"><span data-stu-id="bce97-113">Character</span></span>|<span data-ttu-id="bce97-114">Escape-последовательность</span><span class="sxs-lookup"><span data-stu-id="bce97-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="bce97-115">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="bce97-115">Alert</span></span>|`\a`|
|<span data-ttu-id="bce97-116">Backspace</span><span class="sxs-lookup"><span data-stu-id="bce97-116">Backspace</span></span>|`\b`|
|<span data-ttu-id="bce97-117">Перевод страницы</span><span class="sxs-lookup"><span data-stu-id="bce97-117">Form feed</span></span>|`\f`|
|<span data-ttu-id="bce97-118">Новая строка</span><span class="sxs-lookup"><span data-stu-id="bce97-118">Newline</span></span>|`\n`|
|<span data-ttu-id="bce97-119">Возврат каретки</span><span class="sxs-lookup"><span data-stu-id="bce97-119">Carriage return</span></span>|`\r`|
|<span data-ttu-id="bce97-120">Tab</span><span class="sxs-lookup"><span data-stu-id="bce97-120">Tab</span></span>|`\t`|
|<span data-ttu-id="bce97-121">Вертикальная табуляция</span><span class="sxs-lookup"><span data-stu-id="bce97-121">Vertical tab</span></span>|`\v`|
|<span data-ttu-id="bce97-122">Обратная косая черта</span><span class="sxs-lookup"><span data-stu-id="bce97-122">Backslash</span></span>|`\\`|
|<span data-ttu-id="bce97-123">Знак кавычек</span><span class="sxs-lookup"><span data-stu-id="bce97-123">Quotation mark</span></span>|`\"`|
|<span data-ttu-id="bce97-124">Апостроф</span><span class="sxs-lookup"><span data-stu-id="bce97-124">Apostrophe</span></span>|`\'`|
|<span data-ttu-id="bce97-125">символ Юникода</span><span class="sxs-lookup"><span data-stu-id="bce97-125">Unicode character</span></span>|<span data-ttu-id="bce97-126">`\DDD` (где `D` Указывает десятичное число цифр; диапазон значений 000 - 255, например `\231` = «з»)</span><span class="sxs-lookup"><span data-stu-id="bce97-126">`\DDD` (where `D` indicates a decimal digit; range of 000 - 255; for example, `\231` = "ç")</span></span>|
|<span data-ttu-id="bce97-127">символ Юникода</span><span class="sxs-lookup"><span data-stu-id="bce97-127">Unicode character</span></span>|<span data-ttu-id="bce97-128">`\xHH` (где `H` указывает шестнадцатеричной цифрой; диапазон 00 - FF; например, `\xE7` = «з»)</span><span class="sxs-lookup"><span data-stu-id="bce97-128">`\xHH` (where `H` indicates a hexadecimal digit; range of 00 - FF; for example, `\xE7` = "ç")</span></span>|
|<span data-ttu-id="bce97-129">символ Юникода</span><span class="sxs-lookup"><span data-stu-id="bce97-129">Unicode character</span></span>|<span data-ttu-id="bce97-130">`\uHHHH` (UTF-16) (где `H` указывает шестнадцатеричной цифрой; в диапазоне 0000 - FFFF;  Например, `\u00E7` = «з»)</span><span class="sxs-lookup"><span data-stu-id="bce97-130">`\uHHHH` (UTF-16) (where `H` indicates a hexadecimal digit; range of 0000 - FFFF;  for example, `\u00E7` = "ç")</span></span>|
|<span data-ttu-id="bce97-131">символ Юникода</span><span class="sxs-lookup"><span data-stu-id="bce97-131">Unicode character</span></span>|<span data-ttu-id="bce97-132">`\U00HHHHHH` (UTF-32) (где `H` указывает шестнадцатеричной цифрой; диапазон 000000 - 10FFFF;  Например, `\U0001F47D` = "👽«)</span><span class="sxs-lookup"><span data-stu-id="bce97-132">`\U00HHHHHH` (UTF-32) (where `H` indicates a hexadecimal digit; range of 000000 - 10FFFF;  for example, `\U0001F47D` = "👽")</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="bce97-133">`\DDD` Escape-последовательность — десятичная нотация, не восьмеричной нотации, как и в большинстве других языков.</span><span class="sxs-lookup"><span data-stu-id="bce97-133">The `\DDD` escape sequence is decimal notation, not octal notation like in most other languages.</span></span> <span data-ttu-id="bce97-134">Таким образом, цифр `8` и `9` допустимы и последовательность `\032` представляет пробел (U + 0020), тогда как же кодовой точки в восьмеричной нотации бы `\040`.</span><span class="sxs-lookup"><span data-stu-id="bce97-134">Therefore, digits `8` and `9` are valid, and a sequence of `\032` represents a space (U+0020), whereas that same code point in octal notation would be `\040`.</span></span>

> [!NOTE]
> <span data-ttu-id="bce97-135">Ограничен до диапазона от 0 - 255 (0xFF) `\DDD` и `\x` escape-последовательности представляют собой [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) кодировку, поскольку, соответствующий первые 256 кодовых точек Юникода.</span><span class="sxs-lookup"><span data-stu-id="bce97-135">Being constrained to a range of 0 - 255 (0xFF), the `\DDD` and `\x` escape sequences are effectively the [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) character set, since that matches the first 256 Unicode code points.</span></span>

<span data-ttu-id="bce97-136">Если предшествует символ @, литерал является буквальная строка.</span><span class="sxs-lookup"><span data-stu-id="bce97-136">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="bce97-137">Это означает, что все escape-последовательности игнорируются, за исключением того, что два символа кавычки, интерпретируются как один знак кавычки.</span><span class="sxs-lookup"><span data-stu-id="bce97-137">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

<span data-ttu-id="bce97-138">Кроме того строки могут быть заключены в кавычки тройной.</span><span class="sxs-lookup"><span data-stu-id="bce97-138">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="bce97-139">В этом случае все escape-последовательности игнорируются, включая символы двойных кавычек.</span><span class="sxs-lookup"><span data-stu-id="bce97-139">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="bce97-140">Чтобы указать строку, которая содержит внедренную строку в кавычках, можно использовать либо буквальная строка или строку в тройных кавычках.</span><span class="sxs-lookup"><span data-stu-id="bce97-140">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="bce97-141">Если вы используете буквальная строка, необходимо указать двух знаков кавычек, чтобы указать символ одинарной кавычки.</span><span class="sxs-lookup"><span data-stu-id="bce97-141">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="bce97-142">Если вы используете строку в тройных кавычках, можно использовать символов одинарных кавычек без них, проанализированных в качестве конца строки.</span><span class="sxs-lookup"><span data-stu-id="bce97-142">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="bce97-143">Этот метод можно использовать при работе с XML-индекс или другие структуры, которые включают внедренные кавычки.</span><span class="sxs-lookup"><span data-stu-id="bce97-143">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="bce97-144">В коде допустимы строки, содержащие разрывы и разрывы строки интерпретируются буквально как символы новой строки, если обратная косая черта является последним символом перед разрывом строки.</span><span class="sxs-lookup"><span data-stu-id="bce97-144">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="bce97-145">Начальные пробелы в следующей строке учитывается, если используется обратная косая черта.</span><span class="sxs-lookup"><span data-stu-id="bce97-145">Leading white space on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="bce97-146">Следующий код создает строку `str1` значением `"abc\ndef"` и строка `str2` значением `"abcdef"`.</span><span class="sxs-lookup"><span data-stu-id="bce97-146">The following code produces a string `str1` that has value `"abc\ndef"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

<span data-ttu-id="bce97-147">Можно получить доступ к отдельных символов в строке, используя синтаксис, подобный массиву, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="bce97-147">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="bce97-148">В результате получается `b`.</span><span class="sxs-lookup"><span data-stu-id="bce97-148">The output is `b`.</span></span>

<span data-ttu-id="bce97-149">Или можно извлечь подстроки, используя синтаксис срез массива, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="bce97-149">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="bce97-150">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="bce97-150">The output is as follows.</span></span>

```
abc
def
```

<span data-ttu-id="bce97-151">Строки ASCII могут быть представлены массивы байтов без знака, тип `byte[]`.</span><span class="sxs-lookup"><span data-stu-id="bce97-151">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="bce97-152">Добавьте суффикс `B` в строковый литерал, он является строкой ASCII.</span><span class="sxs-lookup"><span data-stu-id="bce97-152">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="bce97-153">Строковые литералы ASCII, используемые с байтовыми массивами поддерживает же escape-последовательности, как строки в Юникоде, за исключением escape-последовательности Юникода.</span><span class="sxs-lookup"><span data-stu-id="bce97-153">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a><span data-ttu-id="bce97-154">Строковые операторы</span><span class="sxs-lookup"><span data-stu-id="bce97-154">String Operators</span></span>

<span data-ttu-id="bce97-155">Существует два способа для сцепления строк: с помощью `+` оператор или с помощью `^` оператор.</span><span class="sxs-lookup"><span data-stu-id="bce97-155">There are two ways to concatenate strings: by using the `+` operator or by using the `^` operator.</span></span> <span data-ttu-id="bce97-156">`+` Оператор, обеспечена совместимость с функциями обработки строк платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bce97-156">The `+` operator maintains compatibility with the .NET Framework string handling features.</span></span>

<span data-ttu-id="bce97-157">В следующем примере показано объединение строк.</span><span class="sxs-lookup"><span data-stu-id="bce97-157">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a><span data-ttu-id="bce97-158">Класс String</span><span class="sxs-lookup"><span data-stu-id="bce97-158">String Class</span></span>

<span data-ttu-id="bce97-159">Так как тип строки в F# является фактически .NET Framework `System.String` введите все `System.String` элементы доступны.</span><span class="sxs-lookup"><span data-stu-id="bce97-159">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="bce97-160">Сюда входят `+` оператор, который используется для объединения строк, `Length` свойство и `Chars` свойство, которое возвращает строку в виде массива знаков Юникода.</span><span class="sxs-lookup"><span data-stu-id="bce97-160">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="bce97-161">Дополнительные сведения о строках см. в разделе `System.String`.</span><span class="sxs-lookup"><span data-stu-id="bce97-161">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="bce97-162">С помощью `Chars` свойство `System.String`, доступ к отдельным символам в строке путем указания индекса, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="bce97-162">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a><span data-ttu-id="bce97-163">Модуль строки</span><span class="sxs-lookup"><span data-stu-id="bce97-163">String Module</span></span>

<span data-ttu-id="bce97-164">Дополнительные функции обработки строк включены в `String` модуля в `FSharp.Core` пространства имен.</span><span class="sxs-lookup"><span data-stu-id="bce97-164">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="bce97-165">Дополнительные сведения см. в разделе [модуль Core.String](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="bce97-165">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="bce97-166">См. также</span><span class="sxs-lookup"><span data-stu-id="bce97-166">See also</span></span>

- [<span data-ttu-id="bce97-167">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="bce97-167">F# Language Reference</span></span>](index.md)
