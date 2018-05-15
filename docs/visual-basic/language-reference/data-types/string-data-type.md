---
title: Тип данных String (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.String
helpviewer_keywords:
- strings [Visual Basic], character
- strings [Visual Basic], fixed-length
- string keyword [Visual Basic]
- fixed-length strings [Visual Basic], string data type
- literals [Visual Basic], string
- text [Visual Basic], String data type
- $ identifier type character
- String data type
- fixed-length strings
- string literals [Visual Basic]
- data types [Visual Basic], assigning
- String literals [Visual Basic]
- identifier type characters [Visual Basic], $
ms.assetid: 15ac03f5-cabd-42cc-a754-1df3893c25d9
ms.openlocfilehash: 894638bbe50dad2cae1f74a2f7b7fe006f029d1b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="string-data-type-visual-basic"></a><span data-ttu-id="88934-102">Тип данных String (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="88934-102">String Data Type (Visual Basic)</span></span>
<span data-ttu-id="88934-103">Содержит последовательности точек неподписанный код 16-разрядное (2-байтовые) этого диапазона, в диапазоне от 0 до 65535.</span><span class="sxs-lookup"><span data-stu-id="88934-103">Holds sequences of unsigned 16-bit (2-byte) code points that range in value from 0 through 65535.</span></span> <span data-ttu-id="88934-104">Каждый *кодовой*, или код символа, представляет один знак Юникода.</span><span class="sxs-lookup"><span data-stu-id="88934-104">Each *code point*, or character code, represents a single Unicode character.</span></span> <span data-ttu-id="88934-105">Строка может содержать от нуля до двух миллиардов (2 ^ 31) знаков Юникода.</span><span class="sxs-lookup"><span data-stu-id="88934-105">A string can contain from 0 to approximately two billion (2 ^ 31) Unicode characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="88934-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="88934-106">Remarks</span></span>  
 <span data-ttu-id="88934-107">Используйте `String` тип данных для хранения нескольких символов, одновременно снижая издержки управления массивом `Char()`, массив `Char` элементов.</span><span class="sxs-lookup"><span data-stu-id="88934-107">Use the `String` data type to hold multiple characters without the array management overhead of `Char()`, an array of `Char` elements.</span></span>  
  
 <span data-ttu-id="88934-108">Значение по умолчанию `String` — `Nothing` (ссылка null).</span><span class="sxs-lookup"><span data-stu-id="88934-108">The default value of `String` is `Nothing` (a null reference).</span></span> <span data-ttu-id="88934-109">Обратите внимание, что это не то же, что пустая строка (значение `""`).</span><span class="sxs-lookup"><span data-stu-id="88934-109">Note that this is not the same as the empty string (value `""`).</span></span>  
  
## <a name="unicode-characters"></a><span data-ttu-id="88934-110">Символы Юникода</span><span class="sxs-lookup"><span data-stu-id="88934-110">Unicode Characters</span></span>  
 <span data-ttu-id="88934-111">Первые 128 кодовых точек (от 0 до 127) Юникода соответствуют буквы и символы на стандартной клавиатуре США.</span><span class="sxs-lookup"><span data-stu-id="88934-111">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span></span> <span data-ttu-id="88934-112">Эти первые 128 кодовых точек являются такие же, как определяет набор символов ASCII.</span><span class="sxs-lookup"><span data-stu-id="88934-112">These first 128 code points are the same as those the ASCII character set defines.</span></span> <span data-ttu-id="88934-113">128 кодовых точек (от 128 до 255) представляют специальные символы, такие как буквы латинского алфавита, диакритические знаки, символы валют и дроби.</span><span class="sxs-lookup"><span data-stu-id="88934-113">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span></span> <span data-ttu-id="88934-114">Юникод использует остальные кодовые точки (от 256 до 65535) для широкого набора символов.</span><span class="sxs-lookup"><span data-stu-id="88934-114">Unicode uses the remaining code points (256-65535) for a wide variety of symbols.</span></span> <span data-ttu-id="88934-115">Сюда входят международные текстовые знаки, диакритические знаки и математические и технические символы.</span><span class="sxs-lookup"><span data-stu-id="88934-115">This includes worldwide textual characters, diacritics, and mathematical and technical symbols.</span></span>  
  
 <span data-ttu-id="88934-116">Можно использовать методы, такие как <xref:System.Char.IsDigit%2A> и <xref:System.Char.IsPunctuation%2A> на отдельный символ в `String` переменную для определения ее классификации Юникода.</span><span class="sxs-lookup"><span data-stu-id="88934-116">You can use methods such as <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on an individual character in a `String` variable to determine its Unicode classification.</span></span>  
  
## <a name="format-requirements"></a><span data-ttu-id="88934-117">Требования к формату</span><span class="sxs-lookup"><span data-stu-id="88934-117">Format Requirements</span></span>  
 <span data-ttu-id="88934-118">Необходимо заключить `String` литерал в кавычках (`" "`).</span><span class="sxs-lookup"><span data-stu-id="88934-118">You must enclose a `String` literal within quotation marks (`" "`).</span></span> <span data-ttu-id="88934-119">Если необходимо включить знак кавычек, как один из символов в строке, используется два смежных кавычки (`""`).</span><span class="sxs-lookup"><span data-stu-id="88934-119">If you must include a quotation mark as one of the characters in the string, you use two contiguous quotation marks (`""`).</span></span> <span data-ttu-id="88934-120">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="88934-120">The following example illustrates this.</span></span>  
  
```  
Dim j As String = "Joe said ""Hello"" to me."  
Dim h As String = "Hello"  
' The following messages all display the same thing:  
' "Joe said "Hello" to me."  
MsgBox(j)  
MsgBox("Joe said " & """" & h & """" & " to me.")  
MsgBox("Joe said """ & h & """ to me.")  
```  
  
 <span data-ttu-id="88934-121">Обратите внимание, что парные кавычки, знак кавычки в строке зависят от кавычки в начале и конце `String` литерала.</span><span class="sxs-lookup"><span data-stu-id="88934-121">Note that the contiguous quotation marks that represent a quotation mark in the string are independent of the quotation marks that begin and end the `String` literal.</span></span>  
  
## <a name="string-manipulations"></a><span data-ttu-id="88934-122">Со строками</span><span class="sxs-lookup"><span data-stu-id="88934-122">String Manipulations</span></span>  
 <span data-ttu-id="88934-123">После того как строка, `String` переменных, эта строка является *неизменяемый*, это означает, что вы не может изменить его длину или содержимое.</span><span class="sxs-lookup"><span data-stu-id="88934-123">Once you assign a string to a `String` variable, that string is *immutable*, which means you cannot change its length or contents.</span></span> <span data-ttu-id="88934-124">При изменении строки каким-либо образом Visual Basic создает новую строку и закрывает предыдущую.</span><span class="sxs-lookup"><span data-stu-id="88934-124">When you alter a string in any way, Visual Basic creates a new string and abandons the previous one.</span></span> <span data-ttu-id="88934-125">`String` Переменная указывает новую строку.</span><span class="sxs-lookup"><span data-stu-id="88934-125">The `String` variable then points to the new string.</span></span>  
  
 <span data-ttu-id="88934-126">Можно управлять содержимым `String` переменной с помощью различных строковых функций.</span><span class="sxs-lookup"><span data-stu-id="88934-126">You can manipulate the contents of a `String` variable by using a variety of string functions.</span></span> <span data-ttu-id="88934-127">В следующем примере демонстрируется <xref:Microsoft.VisualBasic.Strings.Left%2A> функции</span><span class="sxs-lookup"><span data-stu-id="88934-127">The following example illustrates the <xref:Microsoft.VisualBasic.Strings.Left%2A> function</span></span>  
  
```  
Dim S As String = "Database"  
' The following statement sets S to a new string containing "Data".  
S = Microsoft.VisualBasic.Left(S, 4)  
```  
  
 <span data-ttu-id="88934-128">Строка, созданная другим компонентом может быть заполняются начальные или конечные пробелы.</span><span class="sxs-lookup"><span data-stu-id="88934-128">A string created by another component might be padded with leading or trailing spaces.</span></span> <span data-ttu-id="88934-129">Получив такой строки, можно использовать <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, и <xref:Microsoft.VisualBasic.Strings.RTrim%2A> функции для удаления этих пробелов.</span><span class="sxs-lookup"><span data-stu-id="88934-129">If you receive such a string, you can use the <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, and <xref:Microsoft.VisualBasic.Strings.RTrim%2A> functions to remove these spaces.</span></span>  
  
 <span data-ttu-id="88934-130">Дополнительные сведения о со строками в разделе [строки](../../../visual-basic/programming-guide/language-features/strings/index.md).</span><span class="sxs-lookup"><span data-stu-id="88934-130">For more information about string manipulations, see [Strings](../../../visual-basic/programming-guide/language-features/strings/index.md).</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="88934-131">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="88934-131">Programming Tips</span></span>  
  
-   <span data-ttu-id="88934-132">**Отрицательные числа.**</span><span class="sxs-lookup"><span data-stu-id="88934-132">**Negative Numbers.**</span></span> <span data-ttu-id="88934-133">Помните, что символы удерживаемые `String` без знака и не может представлять отрицательные значения.</span><span class="sxs-lookup"><span data-stu-id="88934-133">Remember that the characters held by `String` are unsigned and cannot represent negative values.</span></span> <span data-ttu-id="88934-134">В любом случае не следует использовать `String` для хранения числовых значений.</span><span class="sxs-lookup"><span data-stu-id="88934-134">In any case, you should not use `String` to hold numeric values.</span></span>  
  
-   <span data-ttu-id="88934-135">**Вопросы взаимодействия.**</span><span class="sxs-lookup"><span data-stu-id="88934-135">**Interop Considerations.**</span></span> <span data-ttu-id="88934-136">При взаимодействии с компонентами, которые не написаны для платформы .NET Framework, например, автоматизация или COM-объекты, помните, что строка символов быть другой размер (8 бит) в других средах.</span><span class="sxs-lookup"><span data-stu-id="88934-136">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that string characters have a different data width (8 bits) in other environments.</span></span> <span data-ttu-id="88934-137">Если вы передаете 8-битовых символов строкового аргумента такому компоненту, объявите его как `Byte()`, массив `Byte` элементов, а не `String` в новом коде Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="88934-137">If you are passing a string argument of 8-bit characters to such a component, declare it as `Byte()`, an array of `Byte` elements, instead of `String` in your new Visual Basic code.</span></span>  
  
-   <span data-ttu-id="88934-138">**Символы типов.**</span><span class="sxs-lookup"><span data-stu-id="88934-138">**Type Characters.**</span></span> <span data-ttu-id="88934-139">Добавление знак типа идентификатора `$` к любому идентификатору производится принудительное для `String` тип данных.</span><span class="sxs-lookup"><span data-stu-id="88934-139">Appending the identifier type character `$` to any identifier forces it to the `String` data type.</span></span> <span data-ttu-id="88934-140">`String` не имеет типа литерала символа.</span><span class="sxs-lookup"><span data-stu-id="88934-140">`String` has no literal type character.</span></span> <span data-ttu-id="88934-141">Однако компилятор обрабатывает литералы, заключенные в кавычки (`" "`) как `String`.</span><span class="sxs-lookup"><span data-stu-id="88934-141">However, the compiler treats literals enclosed in quotation marks (`" "`) as `String`.</span></span>  
  
-   <span data-ttu-id="88934-142">**Тип Framework.**</span><span class="sxs-lookup"><span data-stu-id="88934-142">**Framework Type.**</span></span> <span data-ttu-id="88934-143">Соответствующий тип в .NET Framework — <xref:System.String?displayProperty=nameWithType> класса.</span><span class="sxs-lookup"><span data-stu-id="88934-143">The corresponding type in the .NET Framework is the <xref:System.String?displayProperty=nameWithType> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88934-144">См. также</span><span class="sxs-lookup"><span data-stu-id="88934-144">See Also</span></span>  
 <xref:System.String?displayProperty=nameWithType>  
 [<span data-ttu-id="88934-145">Типы данных</span><span class="sxs-lookup"><span data-stu-id="88934-145">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="88934-146">Тип данных Char</span><span class="sxs-lookup"><span data-stu-id="88934-146">Char Data Type</span></span>](../../../visual-basic/language-reference/data-types/char-data-type.md)  
 [<span data-ttu-id="88934-147">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="88934-147">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="88934-148">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="88934-148">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="88934-149">Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа</span><span class="sxs-lookup"><span data-stu-id="88934-149">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [<span data-ttu-id="88934-150">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="88934-150">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
