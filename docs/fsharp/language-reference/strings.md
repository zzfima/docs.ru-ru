---
title: строк
description: Узнайте, как F# тип "String" представляет неизменяемый текст как последовательность символов Юникода.
ms.date: 07/05/2019
ms.openlocfilehash: 002de464d09a49b6161608db6e46c619369f5ceb
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452822"
---
# <a name="strings"></a><span data-ttu-id="b8506-103">строк</span><span class="sxs-lookup"><span data-stu-id="b8506-103">Strings</span></span>

> [!NOTE]
> <span data-ttu-id="b8506-104">Ссылки на справочник по API в этой статье ведут на сайт MSDN.</span><span class="sxs-lookup"><span data-stu-id="b8506-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="b8506-105">Работа над справочником по API docs.microsoft.com не завершена.</span><span class="sxs-lookup"><span data-stu-id="b8506-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="b8506-106">Тип `string` представляет неизменяемый текст как последовательность символов Юникода.</span><span class="sxs-lookup"><span data-stu-id="b8506-106">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="b8506-107">`string` — это псевдоним для `System.String` в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b8506-107">`string` is an alias for `System.String` in the .NET Framework.</span></span>

## <a name="remarks"></a><span data-ttu-id="b8506-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="b8506-108">Remarks</span></span>

<span data-ttu-id="b8506-109">Строковые литералы разделяются символом кавычки (").</span><span class="sxs-lookup"><span data-stu-id="b8506-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="b8506-110">Символ обратной косой черты (\\) используется для кодирования определенных специальных символов.</span><span class="sxs-lookup"><span data-stu-id="b8506-110">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="b8506-111">Обратная косая черта и следующий символ вместе называются *escape-последовательностью*.</span><span class="sxs-lookup"><span data-stu-id="b8506-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="b8506-112">В следующей таблице показаны F# escape-последовательности, поддерживаемые в строковых литералах.</span><span class="sxs-lookup"><span data-stu-id="b8506-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="b8506-113">Символ</span><span class="sxs-lookup"><span data-stu-id="b8506-113">Character</span></span>|<span data-ttu-id="b8506-114">Escape-последовательность</span><span class="sxs-lookup"><span data-stu-id="b8506-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="b8506-115">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="b8506-115">Alert</span></span>|`\a`|
|<span data-ttu-id="b8506-116">Отмена</span><span class="sxs-lookup"><span data-stu-id="b8506-116">Backspace</span></span>|`\b`|
|<span data-ttu-id="b8506-117">Подача страницы</span><span class="sxs-lookup"><span data-stu-id="b8506-117">Form feed</span></span>|`\f`|
|<span data-ttu-id="b8506-118">Новая строка</span><span class="sxs-lookup"><span data-stu-id="b8506-118">Newline</span></span>|`\n`|
|<span data-ttu-id="b8506-119">Возврат каретки</span><span class="sxs-lookup"><span data-stu-id="b8506-119">Carriage return</span></span>|`\r`|
|<span data-ttu-id="b8506-120">Вкладка</span><span class="sxs-lookup"><span data-stu-id="b8506-120">Tab</span></span>|`\t`|
|<span data-ttu-id="b8506-121">Вертикальная табуляция</span><span class="sxs-lookup"><span data-stu-id="b8506-121">Vertical tab</span></span>|`\v`|
|<span data-ttu-id="b8506-122">Обратная косая черта</span><span class="sxs-lookup"><span data-stu-id="b8506-122">Backslash</span></span>|`\\`|
|<span data-ttu-id="b8506-123">Знак кавычек</span><span class="sxs-lookup"><span data-stu-id="b8506-123">Quotation mark</span></span>|`\"`|
|<span data-ttu-id="b8506-124">Заменяет</span><span class="sxs-lookup"><span data-stu-id="b8506-124">Apostrophe</span></span>|`\'`|
|<span data-ttu-id="b8506-125">символьный формат Юникода</span><span class="sxs-lookup"><span data-stu-id="b8506-125">Unicode character</span></span>|<span data-ttu-id="b8506-126">`\DDD` (где `D` обозначает десятичную цифру, диапазон 000-255, например, `\231` = "c")</span><span class="sxs-lookup"><span data-stu-id="b8506-126">`\DDD` (where `D` indicates a decimal digit; range of 000 - 255; for example, `\231` = "ç")</span></span>|
|<span data-ttu-id="b8506-127">символьный формат Юникода</span><span class="sxs-lookup"><span data-stu-id="b8506-127">Unicode character</span></span>|<span data-ttu-id="b8506-128">`\xHH` (где `H` обозначает шестнадцатеричную цифру, диапазон 00 – FF; например, `\xE7` = "c")</span><span class="sxs-lookup"><span data-stu-id="b8506-128">`\xHH` (where `H` indicates a hexadecimal digit; range of 00 - FF; for example, `\xE7` = "ç")</span></span>|
|<span data-ttu-id="b8506-129">символьный формат Юникода</span><span class="sxs-lookup"><span data-stu-id="b8506-129">Unicode character</span></span>|<span data-ttu-id="b8506-130">`\uHHHH` (UTF-16) (где `H` обозначает шестнадцатеричную цифру, диапазон — 0000-FFFF;  Например, `\u00E7` = "c")</span><span class="sxs-lookup"><span data-stu-id="b8506-130">`\uHHHH` (UTF-16) (where `H` indicates a hexadecimal digit; range of 0000 - FFFF;  for example, `\u00E7` = "ç")</span></span>|
|<span data-ttu-id="b8506-131">символьный формат Юникода</span><span class="sxs-lookup"><span data-stu-id="b8506-131">Unicode character</span></span>|<span data-ttu-id="b8506-132">`\U00HHHHHH` (UTF-32) (где `H` обозначает шестнадцатеричную цифру, диапазон 000000-10FFFF;  Например, `\U0001F47D` = "👽").</span><span class="sxs-lookup"><span data-stu-id="b8506-132">`\U00HHHHHH` (UTF-32) (where `H` indicates a hexadecimal digit; range of 000000 - 10FFFF;  for example, `\U0001F47D` = "👽")</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="b8506-133">Escape-последовательность `\DDD` — десятичная нотация, а не восьмеричная нотация, как в большинстве других языков.</span><span class="sxs-lookup"><span data-stu-id="b8506-133">The `\DDD` escape sequence is decimal notation, not octal notation like in most other languages.</span></span> <span data-ttu-id="b8506-134">Таким образом, цифры `8` и `9` допустимы, а последовательность `\032` представляет пробел (U + 0020), а та же кодовая точка в восьмеричной нотации будет `\040`.</span><span class="sxs-lookup"><span data-stu-id="b8506-134">Therefore, digits `8` and `9` are valid, and a sequence of `\032` represents a space (U+0020), whereas that same code point in octal notation would be `\040`.</span></span>

> [!NOTE]
> <span data-ttu-id="b8506-135">Если ограничиться диапазоном 0-255 (0xFF), то escape-последовательности `\DDD` и `\x` фактически являются набором символов [ISO – 8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) , так как они соответствуют первой 256 кодовых позиций Юникода.</span><span class="sxs-lookup"><span data-stu-id="b8506-135">Being constrained to a range of 0 - 255 (0xFF), the `\DDD` and `\x` escape sequences are effectively the [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) character set, since that matches the first 256 Unicode code points.</span></span>

## <a name="verbatim-strings"></a><span data-ttu-id="b8506-136">Буквальные строки</span><span class="sxs-lookup"><span data-stu-id="b8506-136">Verbatim Strings</span></span>

<span data-ttu-id="b8506-137">Если предшествует символ @, литерал является буквальной строкой.</span><span class="sxs-lookup"><span data-stu-id="b8506-137">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="b8506-138">Это означает, что все escape-последовательности игнорируются, за исключением того, что две кавычки считаются символом одной кавычки.</span><span class="sxs-lookup"><span data-stu-id="b8506-138">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

## <a name="triple-quoted-strings"></a><span data-ttu-id="b8506-139">Строки с тройным заключенным в кавычки</span><span class="sxs-lookup"><span data-stu-id="b8506-139">Triple Quoted Strings</span></span>

<span data-ttu-id="b8506-140">Кроме того, строка может быть заключена в тройные кавычки.</span><span class="sxs-lookup"><span data-stu-id="b8506-140">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="b8506-141">В этом случае все escape-последовательности игнорируются, включая двойные кавычки.</span><span class="sxs-lookup"><span data-stu-id="b8506-141">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="b8506-142">Чтобы указать строку, содержащую внедренную строку в кавычках, можно использовать буквальную строку или строку с тройными кавычками.</span><span class="sxs-lookup"><span data-stu-id="b8506-142">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="b8506-143">При использовании буквальной строки необходимо указать две кавычки, чтобы указать символ одинарной кавычки.</span><span class="sxs-lookup"><span data-stu-id="b8506-143">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="b8506-144">При использовании строки, заключенной в тройные кавычки, можно использовать символы одинарной кавычки без синтаксического анализа в качестве конца строки.</span><span class="sxs-lookup"><span data-stu-id="b8506-144">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="b8506-145">Этот метод может быть полезен при работе с XML или с другими структурами, включающими в себя внедренные кавычки.</span><span class="sxs-lookup"><span data-stu-id="b8506-145">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="b8506-146">В коде строки, имеющие разрывы строк, принимаются, а разрывы строк интерпретируется как символы новой строки, если только символ обратной косой черты не является последним символом перед разрывом строки.</span><span class="sxs-lookup"><span data-stu-id="b8506-146">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="b8506-147">Начальные пробелы в следующей строке игнорируются при использовании символа обратной косой черты.</span><span class="sxs-lookup"><span data-stu-id="b8506-147">Leading white space on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="b8506-148">Следующий код создает строку `str1` со значением `"abc\ndef"` и строкой `str2` со значением `"abcdef"`.</span><span class="sxs-lookup"><span data-stu-id="b8506-148">The following code produces a string `str1` that has value `"abc\ndef"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

## <a name="string-indexing-and-slicing"></a><span data-ttu-id="b8506-149">Индексирование строк и создание срезов</span><span class="sxs-lookup"><span data-stu-id="b8506-149">String Indexing and Slicing</span></span>

<span data-ttu-id="b8506-150">Получить доступ к отдельным символам в строке можно с помощью синтаксиса, подобного массиву, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="b8506-150">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="b8506-151">В результате получается `b`.</span><span class="sxs-lookup"><span data-stu-id="b8506-151">The output is `b`.</span></span>

<span data-ttu-id="b8506-152">Кроме того, можно извлечь подстроки с помощью синтаксиса среза массива, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="b8506-152">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="b8506-153">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="b8506-153">The output is as follows.</span></span>

```console
abc
def
```

<span data-ttu-id="b8506-154">Строки ASCII можно представлять массивами беззнаковых байтов типа `byte[]`.</span><span class="sxs-lookup"><span data-stu-id="b8506-154">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="b8506-155">Добавьте суффикс `B` в строковый литерал, чтобы указать, что это строка ASCII.</span><span class="sxs-lookup"><span data-stu-id="b8506-155">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="b8506-156">Строковые литералы ASCII, используемые с массивами байтов, поддерживают те же escape-последовательности, что и строки в Юникоде, за исключением escape-последовательностей Юникода.</span><span class="sxs-lookup"><span data-stu-id="b8506-156">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a><span data-ttu-id="b8506-157">Строковые операторы</span><span class="sxs-lookup"><span data-stu-id="b8506-157">String Operators</span></span>

<span data-ttu-id="b8506-158">Существует два способа сцепления строк: с помощью оператора `+` или с помощью оператора `^`.</span><span class="sxs-lookup"><span data-stu-id="b8506-158">There are two ways to concatenate strings: by using the `+` operator or by using the `^` operator.</span></span> <span data-ttu-id="b8506-159">Оператор `+` поддерживает совместимость с функциями обработки строк .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b8506-159">The `+` operator maintains compatibility with the .NET Framework string handling features.</span></span>

<span data-ttu-id="b8506-160">В следующем примере показано объединение строк.</span><span class="sxs-lookup"><span data-stu-id="b8506-160">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a><span data-ttu-id="b8506-161">Класс String</span><span class="sxs-lookup"><span data-stu-id="b8506-161">String Class</span></span>

<span data-ttu-id="b8506-162">Так как тип строки в F# фактически является .NET Framework типом `System.String`, доступны все элементы `System.String`.</span><span class="sxs-lookup"><span data-stu-id="b8506-162">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="b8506-163">Сюда входит оператор `+`, который используется для сцепления строк, свойства `Length` и свойства `Chars`, которые возвращают строку в виде массива символов Юникода.</span><span class="sxs-lookup"><span data-stu-id="b8506-163">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="b8506-164">Дополнительные сведения о строках см. в разделе `System.String`.</span><span class="sxs-lookup"><span data-stu-id="b8506-164">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="b8506-165">Используя свойство `Chars` `System.String`, можно получить доступ к отдельным символам в строке, указав индекс, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="b8506-165">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a><span data-ttu-id="b8506-166">Строковый модуль</span><span class="sxs-lookup"><span data-stu-id="b8506-166">String Module</span></span>

<span data-ttu-id="b8506-167">Дополнительные функции обработки строк входят в модуль `String` в пространстве имен `FSharp.Core`.</span><span class="sxs-lookup"><span data-stu-id="b8506-167">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="b8506-168">Дополнительные сведения см. в разделе [Модуль Core. String](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="b8506-168">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="b8506-169">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b8506-169">See also</span></span>

- [<span data-ttu-id="b8506-170">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="b8506-170">F# Language Reference</span></span>](index.md)
