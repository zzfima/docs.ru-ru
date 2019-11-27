---
title: Тип данных String
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
ms.openlocfilehash: c2c6f9632646c432abb7b6da8887253e526cc994
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343910"
---
# <a name="string-data-type-visual-basic"></a><span data-ttu-id="f0f13-102">Тип данных String (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0f13-102">String Data Type (Visual Basic)</span></span>

<span data-ttu-id="f0f13-103">Содержит последовательности 16-разрядных (2-байтовых) кодовых точек без знака, которые находятся в диапазоне от 0 до 65535.</span><span class="sxs-lookup"><span data-stu-id="f0f13-103">Holds sequences of unsigned 16-bit (2-byte) code points that range in value from 0 through 65535.</span></span> <span data-ttu-id="f0f13-104">Каждая кодовая *точка*, или код символа, представляет один символ Юникода.</span><span class="sxs-lookup"><span data-stu-id="f0f13-104">Each *code point*, or character code, represents a single Unicode character.</span></span> <span data-ttu-id="f0f13-105">Строка может содержать от 0 до приблизительно 2 000 000 000 (2 ^ 31) символов Юникода.</span><span class="sxs-lookup"><span data-stu-id="f0f13-105">A string can contain from 0 to approximately two billion (2 ^ 31) Unicode characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0f13-106">Заметки</span><span class="sxs-lookup"><span data-stu-id="f0f13-106">Remarks</span></span>  

 <span data-ttu-id="f0f13-107">Используйте `String` тип данных для хранения нескольких символов без дополнительных затрат на Управление массивом `Char()`, массива элементов `Char`.</span><span class="sxs-lookup"><span data-stu-id="f0f13-107">Use the `String` data type to hold multiple characters without the array management overhead of `Char()`, an array of `Char` elements.</span></span>  
  
 <span data-ttu-id="f0f13-108">Значение `String` по умолчанию — `Nothing` (пустая ссылка).</span><span class="sxs-lookup"><span data-stu-id="f0f13-108">The default value of `String` is `Nothing` (a null reference).</span></span> <span data-ttu-id="f0f13-109">Обратите внимание, что это не то же самое, что пустая строка (значение `""`).</span><span class="sxs-lookup"><span data-stu-id="f0f13-109">Note that this is not the same as the empty string (value `""`).</span></span>  
  
## <a name="unicode-characters"></a><span data-ttu-id="f0f13-110">Символы Юникода</span><span class="sxs-lookup"><span data-stu-id="f0f13-110">Unicode Characters</span></span>  

 <span data-ttu-id="f0f13-111">Первая 128 кодовых позиций (0 – 127) Юникода соответствует буквам и символам стандартной клавиатуры США.</span><span class="sxs-lookup"><span data-stu-id="f0f13-111">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span></span> <span data-ttu-id="f0f13-112">Первые 128 кодовые точки те же, что и кодировка ASCII.</span><span class="sxs-lookup"><span data-stu-id="f0f13-112">These first 128 code points are the same as those the ASCII character set defines.</span></span> <span data-ttu-id="f0f13-113">Вторая 128 кодовых позиций (128 – 255) представляет специальные символы, такие как буквы латинского алфавита, диакритические знаки, символы валют и дроби.</span><span class="sxs-lookup"><span data-stu-id="f0f13-113">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span></span> <span data-ttu-id="f0f13-114">В Юникоде используются оставшиеся кодовые точки (256-65535) для широкого спектра символов.</span><span class="sxs-lookup"><span data-stu-id="f0f13-114">Unicode uses the remaining code points (256-65535) for a wide variety of symbols.</span></span> <span data-ttu-id="f0f13-115">Это включает в себя международные текстовые символы, диакритические знаки, математические и технические символы.</span><span class="sxs-lookup"><span data-stu-id="f0f13-115">This includes worldwide textual characters, diacritics, and mathematical and technical symbols.</span></span>  
  
 <span data-ttu-id="f0f13-116">Для определения своей классификации Юникода можно использовать такие методы, как <xref:System.Char.IsDigit%2A> и <xref:System.Char.IsPunctuation%2A> на отдельный символ в `String` переменной.</span><span class="sxs-lookup"><span data-stu-id="f0f13-116">You can use methods such as <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on an individual character in a `String` variable to determine its Unicode classification.</span></span>  
  
## <a name="format-requirements"></a><span data-ttu-id="f0f13-117">Требования к формату</span><span class="sxs-lookup"><span data-stu-id="f0f13-117">Format Requirements</span></span>  

 <span data-ttu-id="f0f13-118">`String` литерал необходимо заключить в кавычки (`" "`).</span><span class="sxs-lookup"><span data-stu-id="f0f13-118">You must enclose a `String` literal within quotation marks (`" "`).</span></span> <span data-ttu-id="f0f13-119">Если необходимо включить кавычки в качестве одного из символов в строке, используются две смежные кавычки (`""`).</span><span class="sxs-lookup"><span data-stu-id="f0f13-119">If you must include a quotation mark as one of the characters in the string, you use two contiguous quotation marks (`""`).</span></span> <span data-ttu-id="f0f13-120">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f0f13-120">The following example illustrates this.</span></span>  
  
```vb  
Dim j As String = "Joe said ""Hello"" to me."  
Dim h As String = "Hello"  
' The following messages all display the same thing:  
' "Joe said "Hello" to me."  
MsgBox(j)  
MsgBox("Joe said " & """" & h & """" & " to me.")  
MsgBox("Joe said """ & h & """ to me.")  
```  
  
 <span data-ttu-id="f0f13-121">Обратите внимание, что смежные кавычки, представляющие кавычки в строке, не зависят от кавычек, начинающихся и заканчивая литералом `String`.</span><span class="sxs-lookup"><span data-stu-id="f0f13-121">Note that the contiguous quotation marks that represent a quotation mark in the string are independent of the quotation marks that begin and end the `String` literal.</span></span>  
  
## <a name="string-manipulations"></a><span data-ttu-id="f0f13-122">Манипуляции со строками</span><span class="sxs-lookup"><span data-stu-id="f0f13-122">String Manipulations</span></span>  

 <span data-ttu-id="f0f13-123">После присвоения строки переменной `String` эта строка является *неизменяемой*, что означает, что изменить ее длину или содержимое нельзя.</span><span class="sxs-lookup"><span data-stu-id="f0f13-123">Once you assign a string to a `String` variable, that string is *immutable*, which means you cannot change its length or contents.</span></span> <span data-ttu-id="f0f13-124">При изменении строки каким-либо образом Visual Basic создает новую строку и задействует предыдущую.</span><span class="sxs-lookup"><span data-stu-id="f0f13-124">When you alter a string in any way, Visual Basic creates a new string and abandons the previous one.</span></span> <span data-ttu-id="f0f13-125">Переменная `String` указывает на новую строку.</span><span class="sxs-lookup"><span data-stu-id="f0f13-125">The `String` variable then points to the new string.</span></span>  
  
 <span data-ttu-id="f0f13-126">Вы можете манипулировать содержимым `String` переменной с помощью различных строковых функций.</span><span class="sxs-lookup"><span data-stu-id="f0f13-126">You can manipulate the contents of a `String` variable by using a variety of string functions.</span></span> <span data-ttu-id="f0f13-127">В следующем примере показана функция <xref:Microsoft.VisualBasic.Strings.Left%2A></span><span class="sxs-lookup"><span data-stu-id="f0f13-127">The following example illustrates the <xref:Microsoft.VisualBasic.Strings.Left%2A> function</span></span>  
  
```vb  
Dim S As String = "Database"  
' The following statement sets S to a new string containing "Data".  
S = Microsoft.VisualBasic.Left(S, 4)  
```  
  
 <span data-ttu-id="f0f13-128">Строка, созданная другим компонентом, может быть дополнена начальными или конечными пробелами.</span><span class="sxs-lookup"><span data-stu-id="f0f13-128">A string created by another component might be padded with leading or trailing spaces.</span></span> <span data-ttu-id="f0f13-129">Если вы получаете такую строку, для удаления этих пробелов можно использовать функции <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>и <xref:Microsoft.VisualBasic.Strings.RTrim%2A>.</span><span class="sxs-lookup"><span data-stu-id="f0f13-129">If you receive such a string, you can use the <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, and <xref:Microsoft.VisualBasic.Strings.RTrim%2A> functions to remove these spaces.</span></span>  
  
 <span data-ttu-id="f0f13-130">Дополнительные сведения об операциях со строками см. в разделе [строки](../../../visual-basic/programming-guide/language-features/strings/index.md).</span><span class="sxs-lookup"><span data-stu-id="f0f13-130">For more information about string manipulations, see [Strings](../../../visual-basic/programming-guide/language-features/strings/index.md).</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="f0f13-131">Советы по программированию</span><span class="sxs-lookup"><span data-stu-id="f0f13-131">Programming Tips</span></span>  
  
- <span data-ttu-id="f0f13-132">**Отрицательные числа.**</span><span class="sxs-lookup"><span data-stu-id="f0f13-132">**Negative Numbers.**</span></span> <span data-ttu-id="f0f13-133">Помните, что символы, удерживаемые `String`, не являются знаками и не могут представлять отрицательные значения.</span><span class="sxs-lookup"><span data-stu-id="f0f13-133">Remember that the characters held by `String` are unsigned and cannot represent negative values.</span></span> <span data-ttu-id="f0f13-134">В любом случае не следует использовать `String` для хранения числовых значений.</span><span class="sxs-lookup"><span data-stu-id="f0f13-134">In any case, you should not use `String` to hold numeric values.</span></span>  
  
- <span data-ttu-id="f0f13-135">**Вопросы взаимодействия.**</span><span class="sxs-lookup"><span data-stu-id="f0f13-135">**Interop Considerations.**</span></span> <span data-ttu-id="f0f13-136">Если вы взаимодействуете с компонентами, которые не написаны для .NET Framework, например автоматизации или COM-объекты, помните, что в других средах символы строки имеют разную ширину данных (8 бит).</span><span class="sxs-lookup"><span data-stu-id="f0f13-136">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that string characters have a different data width (8 bits) in other environments.</span></span> <span data-ttu-id="f0f13-137">При передаче строкового аргумента из 8-разрядных символов в такой компонент объявите его как `Byte()`, массив `Byte`ных элементов, а не `String` в новом коде Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f0f13-137">If you are passing a string argument of 8-bit characters to such a component, declare it as `Byte()`, an array of `Byte` elements, instead of `String` in your new Visual Basic code.</span></span>  
  
- <span data-ttu-id="f0f13-138">**Символы типа.**</span><span class="sxs-lookup"><span data-stu-id="f0f13-138">**Type Characters.**</span></span> <span data-ttu-id="f0f13-139">Добавление символа типа идентификатора `$` к любому идентификатору приводит к тому, что он применяет его к `String` типу данных.</span><span class="sxs-lookup"><span data-stu-id="f0f13-139">Appending the identifier type character `$` to any identifier forces it to the `String` data type.</span></span> <span data-ttu-id="f0f13-140">`String` не имеет символа типа литерала.</span><span class="sxs-lookup"><span data-stu-id="f0f13-140">`String` has no literal type character.</span></span> <span data-ttu-id="f0f13-141">Однако компилятор обрабатывает литералы, заключенные в кавычки (`" "`), как `String`.</span><span class="sxs-lookup"><span data-stu-id="f0f13-141">However, the compiler treats literals enclosed in quotation marks (`" "`) as `String`.</span></span>  
  
- <span data-ttu-id="f0f13-142">**Тип платформы.**</span><span class="sxs-lookup"><span data-stu-id="f0f13-142">**Framework Type.**</span></span> <span data-ttu-id="f0f13-143">Соответствующий тип в .NET Framework является классом <xref:System.String?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f0f13-143">The corresponding type in the .NET Framework is the <xref:System.String?displayProperty=nameWithType> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0f13-144">См. также</span><span class="sxs-lookup"><span data-stu-id="f0f13-144">See also</span></span>

- <xref:System.String?displayProperty=nameWithType>
- [<span data-ttu-id="f0f13-145">Типы данных</span><span class="sxs-lookup"><span data-stu-id="f0f13-145">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="f0f13-146">Тип данных Char</span><span class="sxs-lookup"><span data-stu-id="f0f13-146">Char Data Type</span></span>](../../../visual-basic/language-reference/data-types/char-data-type.md)
- [<span data-ttu-id="f0f13-147">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="f0f13-147">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="f0f13-148">Сводка по преобразованию</span><span class="sxs-lookup"><span data-stu-id="f0f13-148">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="f0f13-149">Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа</span><span class="sxs-lookup"><span data-stu-id="f0f13-149">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="f0f13-150">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="f0f13-150">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
