---
title: "Основы работы с Visual Basic строка | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- strings [Visual Basic], Like operator
- strings [Visual Basic], Visual Basic
- strings [Visual Basic], regular expressions
ms.assetid: 5674418d-f00d-4f72-9f98-d15897793350
caps.latest.revision: 14
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
ms.openlocfilehash: 98c2707ef8aabc77951b21cfe9f4edcd3a88c863
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="string-basics-in-visual-basic"></a><span data-ttu-id="bd2f2-102">Основы работы со строками в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bd2f2-102">String Basics in Visual Basic</span></span>
<span data-ttu-id="bd2f2-103">Тип данных `String` представляет последовательность символов (каждый из которых, в свою очередь, представляет экземпляр типа данных `Char`).</span><span class="sxs-lookup"><span data-stu-id="bd2f2-103">The `String` data type represents a series of characters (each representing in turn an instance of the `Char` data type).</span></span> <span data-ttu-id="bd2f2-104">В этом разделе рассмотрены базовые понятия строк в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd2f2-104">This topic introduces the basic concepts of strings in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
## <a name="string-variables"></a><span data-ttu-id="bd2f2-105">Строковые переменные</span><span class="sxs-lookup"><span data-stu-id="bd2f2-105">String Variables</span></span>  
 <span data-ttu-id="bd2f2-106">Экземпляру строки можно назначить литеральное значение, которое представляет ряд символов.</span><span class="sxs-lookup"><span data-stu-id="bd2f2-106">An instance of a string can be assigned a literal value that represents a series of characters.</span></span> <span data-ttu-id="bd2f2-107">Пример:</span><span class="sxs-lookup"><span data-stu-id="bd2f2-107">For example:</span></span>  
  
 <span data-ttu-id="bd2f2-108">[!code-vb[VbVbalrStrings&#63;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="bd2f2-108">[!code-vb[VbVbalrStrings#63](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_1.vb)]</span></span>  
  
 <span data-ttu-id="bd2f2-109">Переменная `String` также может принимать любое выражение, результатом которого является строка.</span><span class="sxs-lookup"><span data-stu-id="bd2f2-109">A `String` variable can also accept any expression that evaluates to a string.</span></span> <span data-ttu-id="bd2f2-110">Ниже приведены примеры.</span><span class="sxs-lookup"><span data-stu-id="bd2f2-110">Examples are shown below:</span></span>  
  
 <span data-ttu-id="bd2f2-111">[!code-vb[VbVbalrStrings&#64;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="bd2f2-111">[!code-vb[VbVbalrStrings#64](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_2.vb)]</span></span>  
  
 <span data-ttu-id="bd2f2-112">Любой литерал, который присваивается переменной `String`, должен быть заключен в кавычки ("").</span><span class="sxs-lookup"><span data-stu-id="bd2f2-112">Any literal that is assigned to a `String` variable must be enclosed in quotation marks ("").</span></span> <span data-ttu-id="bd2f2-113">Это означает, что кавычки в пределах строки не могут быть представлены кавычкой.</span><span class="sxs-lookup"><span data-stu-id="bd2f2-113">This means that a quotation mark within a string cannot be represented by a quotation mark.</span></span> <span data-ttu-id="bd2f2-114">Например, следующий код вызовет ошибку компиляции:</span><span class="sxs-lookup"><span data-stu-id="bd2f2-114">For example, the following code causes a compiler error:</span></span>  
  
 <span data-ttu-id="bd2f2-115">[!code-vb[VbVbalrStrings&#65;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="bd2f2-115">[!code-vb[VbVbalrStrings#65](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_3.vb)]</span></span>  
  
 <span data-ttu-id="bd2f2-116">Этот код вызывает ошибку, так как компилятор завершает строку после второй пары кавычек, а остаток строки интерпретируется как код.</span><span class="sxs-lookup"><span data-stu-id="bd2f2-116">This code causes an error because the compiler terminates the string after the second quotation mark, and the remainder of the string is interpreted as code.</span></span> <span data-ttu-id="bd2f2-117">Чтобы устранить эту проблему, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] интерпретирует два символа кавычек в строковом литерале как один символ кавычек в строке.</span><span class="sxs-lookup"><span data-stu-id="bd2f2-117">To solve this problem, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] interprets two quotation marks in a string literal as one quotation mark in the string.</span></span> <span data-ttu-id="bd2f2-118">В следующем примере показан правильный способ указания кавычек в строке:</span><span class="sxs-lookup"><span data-stu-id="bd2f2-118">The following example demonstrates the correct way to include a quotation mark in a string:</span></span>  
  
 <span data-ttu-id="bd2f2-119">[!code-vb[VbVbalrStrings&#66;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="bd2f2-119">[!code-vb[VbVbalrStrings#66](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_4.vb)]</span></span>  
  
 <span data-ttu-id="bd2f2-120">В предыдущем примере два символа кавычек перед словом `Look` становятся одним символом кавычек в строке.</span><span class="sxs-lookup"><span data-stu-id="bd2f2-120">In the preceding example, the two quotation marks preceding the word `Look` become one quotation mark in the string.</span></span> <span data-ttu-id="bd2f2-121">Три символа кавычек в конце строки представляют один символ кавычек в строке и конечный символ строки.</span><span class="sxs-lookup"><span data-stu-id="bd2f2-121">The three quotation marks at the end of the line represent one quotation mark in the string and the string termination character.</span></span>  
  
 <span data-ttu-id="bd2f2-122">Строковые литералы могут содержать несколько строк:</span><span class="sxs-lookup"><span data-stu-id="bd2f2-122">String literals can contain multiple lines:</span></span>  
  
```vb  
Dim x = "hello  
world"  
  
```  
  
 <span data-ttu-id="bd2f2-123">Результирующая строка содержит последовательности новых строк, используемых в строковом литерале (vbcr, vbcrlf и т. д.).</span><span class="sxs-lookup"><span data-stu-id="bd2f2-123">The resulting string contains newline sequences that you used in your string literal (vbcr, vbcrlf, etc.).</span></span>  <span data-ttu-id="bd2f2-124">Вам больше не требуется использовать старое решение:</span><span class="sxs-lookup"><span data-stu-id="bd2f2-124">You no longer need to use the old workaround:</span></span>  
  
```vb  
Dim x = <xml><![CDATA[Hello  
World]]></xml>.Value  
  
```  
  
## <a name="characters-in-strings"></a><span data-ttu-id="bd2f2-125">Символы в строках</span><span class="sxs-lookup"><span data-stu-id="bd2f2-125">Characters in Strings</span></span>  
 <span data-ttu-id="bd2f2-126">Строку можно представить как последовательность значений `Char`. При этом тип `String` имеет встроенные функции, которые позволяют работать со строками, как с массивами.</span><span class="sxs-lookup"><span data-stu-id="bd2f2-126">A string can be thought of as a series of `Char` values, and the `String` type has built-in functions that allow you to perform many manipulations on a string that resemble the manipulations allowed by arrays.</span></span> <span data-ttu-id="bd2f2-127">Как и все массивы в [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)], строки — это массивы с индексацией с нуля.</span><span class="sxs-lookup"><span data-stu-id="bd2f2-127">Like all array in [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)], these are zero-based arrays.</span></span> <span data-ttu-id="bd2f2-128">К определенному символу в строке можно обратиться с помощью свойства `Chars`, которое предоставляет механизм доступа к символу по позиции, в которой он отображается в строке.</span><span class="sxs-lookup"><span data-stu-id="bd2f2-128">You may refer to a specific character in a string through the `Chars` property, which provides a way to access a character by the position in which it appears in the string.</span></span> <span data-ttu-id="bd2f2-129">Пример:</span><span class="sxs-lookup"><span data-stu-id="bd2f2-129">For example:</span></span>  
  
 <span data-ttu-id="bd2f2-130">[!code-vb[VbVbalrStrings&#67;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="bd2f2-130">[!code-vb[VbVbalrStrings#67](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_5.vb)]</span></span>  
  
 <span data-ttu-id="bd2f2-131">В приведенном выше примере свойство `Chars` строки возвращает четвертый символ в строке, `D`, и присваивает его `myChar`.</span><span class="sxs-lookup"><span data-stu-id="bd2f2-131">In the above example, the `Chars` property of the string returns the fourth character in the string, which is `D`, and assigns it to `myChar`.</span></span> <span data-ttu-id="bd2f2-132">Вы также можете получить длину определенной строки с помощью свойства `Length`.</span><span class="sxs-lookup"><span data-stu-id="bd2f2-132">You can also get the length of a particular string through the `Length` property.</span></span> <span data-ttu-id="bd2f2-133">Если вам требуется выполнить несколько манипуляций со строкой, можно преобразовать ее в массив экземпляров `Char` с помощью функции `ToCharArray` строки.</span><span class="sxs-lookup"><span data-stu-id="bd2f2-133">If you need to perform multiple array-type manipulations on a string, you can convert it to an array of `Char` instances using the `ToCharArray` function of the string.</span></span> <span data-ttu-id="bd2f2-134">Пример:</span><span class="sxs-lookup"><span data-stu-id="bd2f2-134">For example:</span></span>  
  
 <span data-ttu-id="bd2f2-135">[!code-vb[VbVbalrStrings&#68;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="bd2f2-135">[!code-vb[VbVbalrStrings#68](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_6.vb)]</span></span>  
  
 <span data-ttu-id="bd2f2-136">Переменная `myArray` теперь содержит массив значений `Char`, каждое из которых представляет символ из `myString`.</span><span class="sxs-lookup"><span data-stu-id="bd2f2-136">The variable `myArray` now contains an array of `Char` values, each representing a character from `myString`.</span></span>  
  
## <a name="the-immutability-of-strings"></a><span data-ttu-id="bd2f2-137">Неизменность строк</span><span class="sxs-lookup"><span data-stu-id="bd2f2-137">The Immutability of Strings</span></span>  
 <span data-ttu-id="bd2f2-138">Строка *неизменяемый*, то есть, его значение невозможно изменить после его создания.</span><span class="sxs-lookup"><span data-stu-id="bd2f2-138">A string is *immutable*, which means its value cannot be changed once it has been created.</span></span> <span data-ttu-id="bd2f2-139">Однако это не мешает назначить строковой переменной более одного значения.</span><span class="sxs-lookup"><span data-stu-id="bd2f2-139">However, this does not prevent you from assigning more than one value to a string variable.</span></span> <span data-ttu-id="bd2f2-140">Рассмотрим следующий пример.</span><span class="sxs-lookup"><span data-stu-id="bd2f2-140">Consider the following example:</span></span>  
  
 <span data-ttu-id="bd2f2-141">[!code-vb[VbVbalrStrings&#69;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="bd2f2-141">[!code-vb[VbVbalrStrings#69](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_7.vb)]</span></span>  
  
 <span data-ttu-id="bd2f2-142">Здесь строковая переменная создается, получает значение, которое затем изменяется.</span><span class="sxs-lookup"><span data-stu-id="bd2f2-142">Here, a string variable is created, given a value, and then its value is changed.</span></span>  
  
 <span data-ttu-id="bd2f2-143">В частности, в первой строке создается экземпляр типа `String`, которому присваивается значение `This string is immutable`.</span><span class="sxs-lookup"><span data-stu-id="bd2f2-143">More specifically, in the first line, an instance of type `String` is created and given the value `This string is immutable`.</span></span> <span data-ttu-id="bd2f2-144">Во второй строке примера создается новый экземпляр, которому присваивается значение `Or is it?`. При этом строковая переменная удаляет ссылку на первый экземпляр и сохраняет ссылку на новый экземпляр.</span><span class="sxs-lookup"><span data-stu-id="bd2f2-144">In the second line of the example, a new instance is created and given the value `Or is it?`, and the string variable discards its reference to the first instance and stores a reference to the new instance.</span></span>  
  
 <span data-ttu-id="bd2f2-145">В отличие от других встроенных типов данных `String` — это ссылочный тип.</span><span class="sxs-lookup"><span data-stu-id="bd2f2-145">Unlike other intrinsic data types, `String` is a reference type.</span></span> <span data-ttu-id="bd2f2-146">Если переменная ссылочного типа передается в качестве аргумента функции или подпрограмме, вместо фактического значения строки передается ссылка на адрес в памяти, где хранятся данные.</span><span class="sxs-lookup"><span data-stu-id="bd2f2-146">When a variable of reference type is passed as an argument to a function or subroutine, a reference to the memory address where the data is stored is passed instead of the actual value of the string.</span></span> <span data-ttu-id="bd2f2-147">Поэтому в предыдущем примере имя переменной остается таким же, но оно указывает на другой экземпляр класса `String`, который содержит новое значение.</span><span class="sxs-lookup"><span data-stu-id="bd2f2-147">So in the previous example, the name of the variable remains the same, but it points to a new and different instance of the `String` class, which holds the new value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd2f2-148">См. также</span><span class="sxs-lookup"><span data-stu-id="bd2f2-148">See Also</span></span>  
 <span data-ttu-id="bd2f2-149">[Знакомство со строками в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md) </span><span class="sxs-lookup"><span data-stu-id="bd2f2-149">[Introduction to Strings in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md) </span></span>  
<span data-ttu-id="bd2f2-150"> [Тип данных String](../../../../visual-basic/language-reference/data-types/string-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="bd2f2-150"> [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md) </span></span>  
<span data-ttu-id="bd2f2-151"> [Тип данных char](../../../../visual-basic/language-reference/data-types/char-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="bd2f2-151"> [Char Data Type](../../../../visual-basic/language-reference/data-types/char-data-type.md) </span></span>  
<span data-ttu-id="bd2f2-152"> [Основные операции со строками](http://msdn.microsoft.com/library/8133d357-90b5-4b62-9927-43323d99b6b6)</span><span class="sxs-lookup"><span data-stu-id="bd2f2-152"> [Basic String Operations](http://msdn.microsoft.com/library/8133d357-90b5-4b62-9927-43323d99b6b6)</span></span>
