---
title: Строки (F#)
description: 'Узнайте, как тип «строка» F # представляет постоянный текст как последовательность знаков Юникода.'
ms.date: 05/16/2016
ms.openlocfilehash: bdd1d1a542e70bcd95fce51e75d0c1ddffceb008
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564863"
---
# <a name="strings"></a><span data-ttu-id="c690b-103">Строки</span><span class="sxs-lookup"><span data-stu-id="c690b-103">Strings</span></span>

> [!NOTE]
<span data-ttu-id="c690b-104">Ссылки на справочник по API в этой статье ведут на сайт MSDN.</span><span class="sxs-lookup"><span data-stu-id="c690b-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="c690b-105">Работа над справочником по API docs.microsoft.com не завершена.</span><span class="sxs-lookup"><span data-stu-id="c690b-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="c690b-106">`string` Тип представляет постоянный текст как последовательность знаков Юникода.</span><span class="sxs-lookup"><span data-stu-id="c690b-106">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="c690b-107">`string` — это псевдоним для `System.String` в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c690b-107">`string` is an alias for `System.String` in the .NET Framework.</span></span>

## <a name="remarks"></a><span data-ttu-id="c690b-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="c690b-108">Remarks</span></span>
<span data-ttu-id="c690b-109">Строковые литералы разделяются знак кавычек ("").</span><span class="sxs-lookup"><span data-stu-id="c690b-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="c690b-110">Символ обратной косой черты (\) используется для кодирования некоторых специальных знаков.</span><span class="sxs-lookup"><span data-stu-id="c690b-110">The backslash character (\) is used to encode certain special characters.</span></span> <span data-ttu-id="c690b-111">Обратная косая черта и следующий знак вместе называются *escape-последовательность*.</span><span class="sxs-lookup"><span data-stu-id="c690b-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="c690b-112">Escape-последовательности, поддерживаемые в F # строки литералов показаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="c690b-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="c690b-113">Знак</span><span class="sxs-lookup"><span data-stu-id="c690b-113">Character</span></span>|<span data-ttu-id="c690b-114">Escape-последовательность</span><span class="sxs-lookup"><span data-stu-id="c690b-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="c690b-115">Backspace</span><span class="sxs-lookup"><span data-stu-id="c690b-115">Backspace</span></span>|<span data-ttu-id="c690b-116">\b</span><span class="sxs-lookup"><span data-stu-id="c690b-116">\b</span></span>|
|<span data-ttu-id="c690b-117">Новая строка</span><span class="sxs-lookup"><span data-stu-id="c690b-117">Newline</span></span>|<span data-ttu-id="c690b-118">\n</span><span class="sxs-lookup"><span data-stu-id="c690b-118">\n</span></span>|
|<span data-ttu-id="c690b-119">Возврат каретки</span><span class="sxs-lookup"><span data-stu-id="c690b-119">Carriage return</span></span>|<span data-ttu-id="c690b-120">\r</span><span class="sxs-lookup"><span data-stu-id="c690b-120">\r</span></span>|
|<span data-ttu-id="c690b-121">Tab</span><span class="sxs-lookup"><span data-stu-id="c690b-121">Tab</span></span>|<span data-ttu-id="c690b-122">\t</span><span class="sxs-lookup"><span data-stu-id="c690b-122">\t</span></span>|
|<span data-ttu-id="c690b-123">Обратная косая черта</span><span class="sxs-lookup"><span data-stu-id="c690b-123">Backslash</span></span>|\\|
|<span data-ttu-id="c690b-124">Знак кавычек</span><span class="sxs-lookup"><span data-stu-id="c690b-124">Quotation mark</span></span>|\"|
|<span data-ttu-id="c690b-125">Апостроф</span><span class="sxs-lookup"><span data-stu-id="c690b-125">Apostrophe</span></span>|\'|
|<span data-ttu-id="c690b-126">символ Юникода</span><span class="sxs-lookup"><span data-stu-id="c690b-126">Unicode character</span></span>|<span data-ttu-id="c690b-127">\u*XXXX* или \U*XXXXXXXX* (где *X* указывает шестнадцатеричная цифра)</span><span class="sxs-lookup"><span data-stu-id="c690b-127">\u*XXXX* or \U*XXXXXXXX* (where *X* indicates a hexadecimal digit)</span></span>|

<span data-ttu-id="c690b-128">Если предшествует символ @, литерал является буквальная строка.</span><span class="sxs-lookup"><span data-stu-id="c690b-128">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="c690b-129">Это означает, что все escape-последовательности игнорируются, за исключением того, что два символа кавычек, интерпретируются как один знак кавычки.</span><span class="sxs-lookup"><span data-stu-id="c690b-129">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

<span data-ttu-id="c690b-130">Кроме того строки могут быть заключены в кавычки тройной.</span><span class="sxs-lookup"><span data-stu-id="c690b-130">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="c690b-131">В этом случае все escape-последовательности игнорируются, включая символы двойных кавычек.</span><span class="sxs-lookup"><span data-stu-id="c690b-131">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="c690b-132">Чтобы указать строку, содержащую встроенный строкой в кавычках, можно использовать либо буквальная строка или строка тройных кавычках.</span><span class="sxs-lookup"><span data-stu-id="c690b-132">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="c690b-133">Если вы используете буквальная строка, необходимо указать двух знаков кавычек, чтобы указать символ одинарной кавычки.</span><span class="sxs-lookup"><span data-stu-id="c690b-133">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="c690b-134">Если используется строка тройных кавычках, можно использовать знаков кавычек без их во время синтаксического анализа как конец строки.</span><span class="sxs-lookup"><span data-stu-id="c690b-134">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="c690b-135">Этот метод может оказаться полезным при работе с XML или другие структуры, содержащие внедренные кавычки.</span><span class="sxs-lookup"><span data-stu-id="c690b-135">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="c690b-136">В коде строки, содержащие разрывы принимаются и разрывы строки интерпретируются буквально как символы новой строки, если знак обратной косой черты является последнего символа перед разрывом строки.</span><span class="sxs-lookup"><span data-stu-id="c690b-136">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="c690b-137">Начальные пробелы в следующей строке учитывается, если используется символ обратной косой черты.</span><span class="sxs-lookup"><span data-stu-id="c690b-137">Leading whitespace on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="c690b-138">В следующем коде создается строка `str1` значением `"abc\n     def"` и строку `str2` значением `"abcdef"`.</span><span class="sxs-lookup"><span data-stu-id="c690b-138">The following code produces a string `str1` that has value `"abc\n     def"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

<span data-ttu-id="c690b-139">Можно получить доступ к отдельных символов в строке, используя синтаксис, подобный массиву, следующим образом.</span><span class="sxs-lookup"><span data-stu-id="c690b-139">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="c690b-140">В результате получается `b`.</span><span class="sxs-lookup"><span data-stu-id="c690b-140">The output is `b`.</span></span>

<span data-ttu-id="c690b-141">Или можно извлекать подстроки, используя синтаксис диапазона массива, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="c690b-141">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="c690b-142">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="c690b-142">The output is as follows.</span></span>

```
abc
def
```

<span data-ttu-id="c690b-143">Строки ASCII могут быть представлены массивы байтов без знака, тип `byte[]`.</span><span class="sxs-lookup"><span data-stu-id="c690b-143">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="c690b-144">Добавьте суффикс `B` в строковый литерал, чтобы указать, что это строка ASCII.</span><span class="sxs-lookup"><span data-stu-id="c690b-144">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="c690b-145">Строковые литералы ASCII, используемые с байтовыми массивами поддерживает же escape-последовательности, как строки в Юникоде, за исключением escape-последовательности Юникода.</span><span class="sxs-lookup"><span data-stu-id="c690b-145">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]
    
## <a name="string-operators"></a><span data-ttu-id="c690b-146">Операторы строки</span><span class="sxs-lookup"><span data-stu-id="c690b-146">String Operators</span></span>
<span data-ttu-id="c690b-147">Существует два способа для сцепления строк: с помощью `+` оператор или с помощью `^` оператор.</span><span class="sxs-lookup"><span data-stu-id="c690b-147">There are two ways to concatenate strings: by using the `+` operator or by using the `^` operator.</span></span> <span data-ttu-id="c690b-148">`+` Оператор, обеспечена совместимость с функциями обработки строк платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c690b-148">The `+` operator maintains compatibility with the .NET Framework string handling features.</span></span>

<span data-ttu-id="c690b-149">В следующем примере показано объединение строк.</span><span class="sxs-lookup"><span data-stu-id="c690b-149">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]
    
## <a name="string-class"></a><span data-ttu-id="c690b-150">Класс String</span><span class="sxs-lookup"><span data-stu-id="c690b-150">String Class</span></span>
<span data-ttu-id="c690b-151">Так как тип string в языке F # — фактически .NET Framework `System.String` введите все `System.String` элементы доступны.</span><span class="sxs-lookup"><span data-stu-id="c690b-151">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="c690b-152">Сюда входят `+` оператор, который используется для объединения строк, `Length` свойство и `Chars` свойство, которое возвращает строку в виде массива знаков Юникода.</span><span class="sxs-lookup"><span data-stu-id="c690b-152">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="c690b-153">Дополнительные сведения о строках см. в разделе `System.String`.</span><span class="sxs-lookup"><span data-stu-id="c690b-153">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="c690b-154">С помощью `Chars` свойство `System.String`, доступ к отдельным символам в строку путем указания индекса, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="c690b-154">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]
    
## <a name="string-module"></a><span data-ttu-id="c690b-155">Строка модуля</span><span class="sxs-lookup"><span data-stu-id="c690b-155">String Module</span></span>
<span data-ttu-id="c690b-156">Дополнительные функции обработки строк включены в `String` модуля в `FSharp.Core` пространства имен.</span><span class="sxs-lookup"><span data-stu-id="c690b-156">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="c690b-157">Дополнительные сведения см. в разделе [модуль Core.String](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="c690b-157">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="c690b-158">См. также</span><span class="sxs-lookup"><span data-stu-id="c690b-158">See Also</span></span>
[<span data-ttu-id="c690b-159">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="c690b-159">F# Language Reference</span></span>](index.md)
