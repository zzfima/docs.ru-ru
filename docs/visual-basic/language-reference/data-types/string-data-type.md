---
title: "Строковый тип данных (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.String
dev_langs:
- VB
helpviewer_keywords:
- strings [Visual Basic], character
- strings [Visual Basic], fixed-length
- string keyword [Visual Basic]
- fixed-length strings, string data type
- literals, string
- text [Visual Basic], String data type
- $ identifier type character
- String data type
- fixed-length strings
- string literals
- data types [Visual Basic], assigning
- String literals
- identifier type characters, $
ms.assetid: 15ac03f5-cabd-42cc-a754-1df3893c25d9
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 5d7a4272169ae7b2749d038e1116818d2cfbad95
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="string-data-type-visual-basic"></a><span data-ttu-id="082ea-102">Тип данных String (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="082ea-102">String Data Type (Visual Basic)</span></span>
<span data-ttu-id="082ea-103">Содержит этот диапазон последовательности без знака 16-разрядные (2-байтовые) кодовые точки в диапазоне от 0 до 65535.</span><span class="sxs-lookup"><span data-stu-id="082ea-103">Holds sequences of unsigned 16-bit (2-byte) code points that range in value from 0 through 65535.</span></span> <span data-ttu-id="082ea-104">Каждый *кодовой*, или код знака, представляет один знак Юникода.</span><span class="sxs-lookup"><span data-stu-id="082ea-104">Each *code point*, or character code, represents a single Unicode character.</span></span> <span data-ttu-id="082ea-105">Строка может содержать от нуля до двух миллиардов (2 ^ 31) знаков Юникода.</span><span class="sxs-lookup"><span data-stu-id="082ea-105">A string can contain from 0 to approximately two billion (2 ^ 31) Unicode characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="082ea-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="082ea-106">Remarks</span></span>  
 <span data-ttu-id="082ea-107">Используйте `String` тип данных для хранения нескольких символов без использования управления массива `Char()`, массив `Char` элементы.</span><span class="sxs-lookup"><span data-stu-id="082ea-107">Use the `String` data type to hold multiple characters without the array management overhead of `Char()`, an array of `Char` elements.</span></span>  
  
 <span data-ttu-id="082ea-108">Значение по умолчанию `String` — `Nothing` (пустая ссылка).</span><span class="sxs-lookup"><span data-stu-id="082ea-108">The default value of `String` is `Nothing` (a null reference).</span></span> <span data-ttu-id="082ea-109">Обратите внимание, что это не совпадает с пустой строкой (значение `""`).</span><span class="sxs-lookup"><span data-stu-id="082ea-109">Note that this is not the same as the empty string (value `""`).</span></span>  
  
## <a name="unicode-characters"></a><span data-ttu-id="082ea-110">Символы Юникода</span><span class="sxs-lookup"><span data-stu-id="082ea-110">Unicode Characters</span></span>  
 <span data-ttu-id="082ea-111">Первые 128 кодовых точек (от 0 до 127) Юникода соответствуют буквам и символам стандартной американской клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="082ea-111">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span></span> <span data-ttu-id="082ea-112">Эти первые 128 кодовых точек являются такими же, как определяет набор символов ASCII.</span><span class="sxs-lookup"><span data-stu-id="082ea-112">These first 128 code points are the same as those the ASCII character set defines.</span></span> <span data-ttu-id="082ea-113">128 кодовых точек (128-255) представляют специальные символы, такие как буквы латинского алфавита, знаки ударения, символы валют и дроби.</span><span class="sxs-lookup"><span data-stu-id="082ea-113">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span></span> <span data-ttu-id="082ea-114">Юникод использует остальные кодовые точки (от&256; до&65535;) для широкого набора символов.</span><span class="sxs-lookup"><span data-stu-id="082ea-114">Unicode uses the remaining code points (256-65535) for a wide variety of symbols.</span></span> <span data-ttu-id="082ea-115">Это включает в себя международные текстовые знаки, математические и технические символы и диакритические знаки.</span><span class="sxs-lookup"><span data-stu-id="082ea-115">This includes worldwide textual characters, diacritics, and mathematical and technical symbols.</span></span>  
  
 <span data-ttu-id="082ea-116">Можно использовать методы, такие как <xref:System.Char.IsDigit%2A>и <xref:System.Char.IsPunctuation%2A>на отдельный символ в `String` переменную для определения ее классификации Юникода.</xref:System.Char.IsPunctuation%2A> </xref:System.Char.IsDigit%2A></span><span class="sxs-lookup"><span data-stu-id="082ea-116">You can use methods such as <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on an individual character in a `String` variable to determine its Unicode classification.</span></span>  
  
## <a name="format-requirements"></a><span data-ttu-id="082ea-117">Требования к формату</span><span class="sxs-lookup"><span data-stu-id="082ea-117">Format Requirements</span></span>  
 <span data-ttu-id="082ea-118">Необходимо заключить `String` литерал в кавычках (`" "`).</span><span class="sxs-lookup"><span data-stu-id="082ea-118">You must enclose a `String` literal within quotation marks (`" "`).</span></span> <span data-ttu-id="082ea-119">Если необходимо включить кавычки как один из символов в строке, используется два смежных кавычки (`""`).</span><span class="sxs-lookup"><span data-stu-id="082ea-119">If you must include a quotation mark as one of the characters in the string, you use two contiguous quotation marks (`""`).</span></span> <span data-ttu-id="082ea-120">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="082ea-120">The following example illustrates this.</span></span>  
  
```  
Dim j As String = "Joe said ""Hello"" to me."  
Dim h As String = "Hello"  
' The following messages all display the same thing:  
' "Joe said "Hello" to me."  
MsgBox(j)  
MsgBox("Joe said " & """" & h & """" & " to me.")  
MsgBox("Joe said """ & h & """ to me.")  
```  
  
 <span data-ttu-id="082ea-121">Обратите внимание, что парные кавычки, которые представляют кавычки в строке не зависят от кавычки, которые начинают и завершают `String` литерала.</span><span class="sxs-lookup"><span data-stu-id="082ea-121">Note that the contiguous quotation marks that represent a quotation mark in the string are independent of the quotation marks that begin and end the `String` literal.</span></span>  
  
## <a name="string-manipulations"></a><span data-ttu-id="082ea-122">Операции со строками</span><span class="sxs-lookup"><span data-stu-id="082ea-122">String Manipulations</span></span>  
 <span data-ttu-id="082ea-123">После того как строка, `String` переменной, что строка является *неизменяемый*, означает, что нельзя изменить её длину или содержимое.</span><span class="sxs-lookup"><span data-stu-id="082ea-123">Once you assign a string to a `String` variable, that string is *immutable*, which means you cannot change its length or contents.</span></span> <span data-ttu-id="082ea-124">При изменении строки каким-либо образом Visual Basic создает новую строку и закрывает предыдущую.</span><span class="sxs-lookup"><span data-stu-id="082ea-124">When you alter a string in any way, Visual Basic creates a new string and abandons the previous one.</span></span> <span data-ttu-id="082ea-125">`String` Переменная затем указывает на новую строку.</span><span class="sxs-lookup"><span data-stu-id="082ea-125">The `String` variable then points to the new string.</span></span>  
  
 <span data-ttu-id="082ea-126">Можно управлять содержимым `String` переменной с помощью различных строковых функций.</span><span class="sxs-lookup"><span data-stu-id="082ea-126">You can manipulate the contents of a `String` variable by using a variety of string functions.</span></span> <span data-ttu-id="082ea-127">В следующем примере <xref:Microsoft.VisualBasic.Strings.Left%2A>функция</xref:Microsoft.VisualBasic.Strings.Left%2A></span><span class="sxs-lookup"><span data-stu-id="082ea-127">The following example illustrates the <xref:Microsoft.VisualBasic.Strings.Left%2A> function</span></span>  
  
```  
Dim S As String = "Database"  
' The following statement sets S to a new string containing "Data".  
S = Microsoft.VisualBasic.Left(S, 4)  
```  
  
 <span data-ttu-id="082ea-128">Строка, созданная другим компонентом может быть заполняется начальные или конечные пробелы.</span><span class="sxs-lookup"><span data-stu-id="082ea-128">A string created by another component might be padded with leading or trailing spaces.</span></span> <span data-ttu-id="082ea-129">Если вы получаете такие строки, можно использовать <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, и <xref:Microsoft.VisualBasic.Strings.RTrim%2A>функции для удаления этих пробелов.</xref:Microsoft.VisualBasic.Strings.RTrim%2A> </xref:Microsoft.VisualBasic.Strings.LTrim%2A> </xref:Microsoft.VisualBasic.Strings.Trim%2A></span><span class="sxs-lookup"><span data-stu-id="082ea-129">If you receive such a string, you can use the <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, and <xref:Microsoft.VisualBasic.Strings.RTrim%2A> functions to remove these spaces.</span></span>  
  
 <span data-ttu-id="082ea-130">Дополнительные сведения об операции со строками см. в разделе [строки](../../../visual-basic/programming-guide/language-features/strings/index.md).</span><span class="sxs-lookup"><span data-stu-id="082ea-130">For more information about string manipulations, see [Strings](../../../visual-basic/programming-guide/language-features/strings/index.md).</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="082ea-131">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="082ea-131">Programming Tips</span></span>  
  
-   <span data-ttu-id="082ea-132">**Отрицательные числа.**</span><span class="sxs-lookup"><span data-stu-id="082ea-132">**Negative Numbers.**</span></span> <span data-ttu-id="082ea-133">Помните, что символы удерживаемые `String` без знака и не может представлять отрицательные значения.</span><span class="sxs-lookup"><span data-stu-id="082ea-133">Remember that the characters held by `String` are unsigned and cannot represent negative values.</span></span> <span data-ttu-id="082ea-134">В любом случае не следует использовать `String` для хранения числовых значений.</span><span class="sxs-lookup"><span data-stu-id="082ea-134">In any case, you should not use `String` to hold numeric values.</span></span>  
  
-   <span data-ttu-id="082ea-135">**Вопросы взаимодействия.**</span><span class="sxs-lookup"><span data-stu-id="082ea-135">**Interop Considerations.**</span></span> <span data-ttu-id="082ea-136">При взаимодействии с компонентами, написанными не для платформы .NET Framework, например автоматизации или COM-объектов, помните, что символы строки имеют другой размер (8 бит) в других средах.</span><span class="sxs-lookup"><span data-stu-id="082ea-136">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that string characters have a different data width (8 bits) in other environments.</span></span> <span data-ttu-id="082ea-137">Если такому компоненту передается строковый аргумент 8-разрядных символов, объявите ее в качестве `Byte()`, массив `Byte` элементов, а не `String` в новом коде Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="082ea-137">If you are passing a string argument of 8-bit characters to such a component, declare it as `Byte()`, an array of `Byte` elements, instead of `String` in your new Visual Basic code.</span></span>  
  
-   <span data-ttu-id="082ea-138">**Символы типов.**</span><span class="sxs-lookup"><span data-stu-id="082ea-138">**Type Characters.**</span></span> <span data-ttu-id="082ea-139">Добавление знак типа идентификатора `$` к любому идентификатору приводит к принудительному `String` тип данных.</span><span class="sxs-lookup"><span data-stu-id="082ea-139">Appending the identifier type character `$` to any identifier forces it to the `String` data type.</span></span> <span data-ttu-id="082ea-140">`String`не имеет буквенного символа.</span><span class="sxs-lookup"><span data-stu-id="082ea-140">`String` has no literal type character.</span></span> <span data-ttu-id="082ea-141">Однако компилятор обрабатывает литералы, заключенные в кавычки (`" "`) как `String`.</span><span class="sxs-lookup"><span data-stu-id="082ea-141">However, the compiler treats literals enclosed in quotation marks (`" "`) as `String`.</span></span>  
  
-   <span data-ttu-id="082ea-142">**Тип Framework.**</span><span class="sxs-lookup"><span data-stu-id="082ea-142">**Framework Type.**</span></span> <span data-ttu-id="082ea-143">Соответствующий тип в .NET Framework является <xref:System.String?displayProperty=fullName>класс.</xref:System.String?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="082ea-143">The corresponding type in the .NET Framework is the <xref:System.String?displayProperty=fullName> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="082ea-144">См. также</span><span class="sxs-lookup"><span data-stu-id="082ea-144">See Also</span></span>  
 <span data-ttu-id="082ea-145"><xref:System.String?displayProperty=fullName></xref:System.String?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="082ea-145"><xref:System.String?displayProperty=fullName></span></span>   
<span data-ttu-id="082ea-146"> [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md) </span><span class="sxs-lookup"><span data-stu-id="082ea-146"> [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md) </span></span>  
<span data-ttu-id="082ea-147"> [Тип данных char](../../../visual-basic/language-reference/data-types/char-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="082ea-147"> [Char Data Type](../../../visual-basic/language-reference/data-types/char-data-type.md) </span></span>  
<span data-ttu-id="082ea-148"> [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span><span class="sxs-lookup"><span data-stu-id="082ea-148"> [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span></span>  
<span data-ttu-id="082ea-149"> [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md) </span><span class="sxs-lookup"><span data-stu-id="082ea-149"> [Conversion Summary](../../../visual-basic/language-reference/keywords/conversion-summary.md) </span></span>  
<span data-ttu-id="082ea-150"> [Практическое руководство: вызов функции Windows, принимающей значение беззнакового типа](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md) </span><span class="sxs-lookup"><span data-stu-id="082ea-150"> [How to: Call a Windows Function that Takes Unsigned Types](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md) </span></span>  
<span data-ttu-id="082ea-151"> [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)</span><span class="sxs-lookup"><span data-stu-id="082ea-151"> [Efficient Use of Data Types](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)</span></span>

