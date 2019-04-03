---
title: Основы работы со строками в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Like operator
- strings [Visual Basic], Visual Basic
- strings [Visual Basic], regular expressions
ms.assetid: 5674418d-f00d-4f72-9f98-d15897793350
ms.openlocfilehash: 9d2d3c82f5512bc1e37e3b05086fbd364ee12298
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58820897"
---
# <a name="string-basics-in-visual-basic"></a><span data-ttu-id="8fc11-102">Основы работы со строками в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8fc11-102">String Basics in Visual Basic</span></span>
<span data-ttu-id="8fc11-103">Тип данных `String` представляет последовательность символов (каждый из которых, в свою очередь, представляет экземпляр типа данных `Char`).</span><span class="sxs-lookup"><span data-stu-id="8fc11-103">The `String` data type represents a series of characters (each representing in turn an instance of the `Char` data type).</span></span> <span data-ttu-id="8fc11-104">В этом разделе представлены основные понятия строк в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8fc11-104">This topic introduces the basic concepts of strings in Visual Basic.</span></span>  
  
## <a name="string-variables"></a><span data-ttu-id="8fc11-105">Строковые переменные</span><span class="sxs-lookup"><span data-stu-id="8fc11-105">String Variables</span></span>  
 <span data-ttu-id="8fc11-106">Экземпляру строки можно назначить литеральное значение, которое представляет ряд символов.</span><span class="sxs-lookup"><span data-stu-id="8fc11-106">An instance of a string can be assigned a literal value that represents a series of characters.</span></span> <span data-ttu-id="8fc11-107">Пример:</span><span class="sxs-lookup"><span data-stu-id="8fc11-107">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#63)]  
  
 <span data-ttu-id="8fc11-108">Переменная `String` также может принимать любое выражение, результатом которого является строка.</span><span class="sxs-lookup"><span data-stu-id="8fc11-108">A `String` variable can also accept any expression that evaluates to a string.</span></span> <span data-ttu-id="8fc11-109">Ниже приведены примеры.</span><span class="sxs-lookup"><span data-stu-id="8fc11-109">Examples are shown below:</span></span>  
  
 [!code-vb[VbVbalrStrings#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#64)]  
  
 <span data-ttu-id="8fc11-110">Любой литерал, который присваивается переменной `String`, должен быть заключен в кавычки ("").</span><span class="sxs-lookup"><span data-stu-id="8fc11-110">Any literal that is assigned to a `String` variable must be enclosed in quotation marks ("").</span></span> <span data-ttu-id="8fc11-111">Это означает, что кавычки в пределах строки не могут быть представлены кавычкой.</span><span class="sxs-lookup"><span data-stu-id="8fc11-111">This means that a quotation mark within a string cannot be represented by a quotation mark.</span></span> <span data-ttu-id="8fc11-112">Например, следующий код вызовет ошибку компиляции:</span><span class="sxs-lookup"><span data-stu-id="8fc11-112">For example, the following code causes a compiler error:</span></span>  
  
 [!code-vb[VbVbalrStrings#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#65)]  
  
 <span data-ttu-id="8fc11-113">Этот код вызывает ошибку, так как компилятор завершает строку после второй пары кавычек, а остаток строки интерпретируется как код.</span><span class="sxs-lookup"><span data-stu-id="8fc11-113">This code causes an error because the compiler terminates the string after the second quotation mark, and the remainder of the string is interpreted as code.</span></span> <span data-ttu-id="8fc11-114">Чтобы решить эту проблему, Visual Basic интерпретирует две кавычки в строковом литерале как один символ кавычек в строке.</span><span class="sxs-lookup"><span data-stu-id="8fc11-114">To solve this problem, Visual Basic interprets two quotation marks in a string literal as one quotation mark in the string.</span></span> <span data-ttu-id="8fc11-115">В следующем примере показан правильный способ указания кавычек в строке:</span><span class="sxs-lookup"><span data-stu-id="8fc11-115">The following example demonstrates the correct way to include a quotation mark in a string:</span></span>  
  
 [!code-vb[VbVbalrStrings#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#66)]  
  
 <span data-ttu-id="8fc11-116">В предыдущем примере два символа кавычек перед словом `Look` становятся одним символом кавычек в строке.</span><span class="sxs-lookup"><span data-stu-id="8fc11-116">In the preceding example, the two quotation marks preceding the word `Look` become one quotation mark in the string.</span></span> <span data-ttu-id="8fc11-117">Три символа кавычек в конце строки представляют один символ кавычек в строке и конечный символ строки.</span><span class="sxs-lookup"><span data-stu-id="8fc11-117">The three quotation marks at the end of the line represent one quotation mark in the string and the string termination character.</span></span>  
  
 <span data-ttu-id="8fc11-118">Строковые литералы могут содержать несколько строк:</span><span class="sxs-lookup"><span data-stu-id="8fc11-118">String literals can contain multiple lines:</span></span>  
  
```vb  
Dim x = "hello  
world"  
```  
  
 <span data-ttu-id="8fc11-119">Результирующая строка содержит последовательности новых строк, используемых в строковом литерале (vbcr, vbcrlf и т. д.).</span><span class="sxs-lookup"><span data-stu-id="8fc11-119">The resulting string contains newline sequences that you used in your string literal (vbcr, vbcrlf, etc.).</span></span>  <span data-ttu-id="8fc11-120">Вам больше не требуется использовать старое решение:</span><span class="sxs-lookup"><span data-stu-id="8fc11-120">You no longer need to use the old workaround:</span></span>  
  
```vb  
Dim x = <xml><![CDATA[Hello  
World]]></xml>.Value  
```  
  
## <a name="characters-in-strings"></a><span data-ttu-id="8fc11-121">Символы в строках</span><span class="sxs-lookup"><span data-stu-id="8fc11-121">Characters in Strings</span></span>  
 <span data-ttu-id="8fc11-122">Строку можно представить как последовательность значений `Char`. При этом тип `String` имеет встроенные функции, которые позволяют работать со строками, как с массивами.</span><span class="sxs-lookup"><span data-stu-id="8fc11-122">A string can be thought of as a series of `Char` values, and the `String` type has built-in functions that allow you to perform many manipulations on a string that resemble the manipulations allowed by arrays.</span></span> <span data-ttu-id="8fc11-123">Как и все массивы в [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], строки — это массивы с индексацией с нуля.</span><span class="sxs-lookup"><span data-stu-id="8fc11-123">Like all array in [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], these are zero-based arrays.</span></span> <span data-ttu-id="8fc11-124">К определенному символу в строке можно обратиться с помощью свойства `Chars`, которое предоставляет механизм доступа к символу по позиции, в которой он отображается в строке.</span><span class="sxs-lookup"><span data-stu-id="8fc11-124">You may refer to a specific character in a string through the `Chars` property, which provides a way to access a character by the position in which it appears in the string.</span></span> <span data-ttu-id="8fc11-125">Пример:</span><span class="sxs-lookup"><span data-stu-id="8fc11-125">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#67)]  
  
 <span data-ttu-id="8fc11-126">В приведенном выше примере свойство `Chars` строки возвращает четвертый символ в строке, `D`, и присваивает его `myChar`.</span><span class="sxs-lookup"><span data-stu-id="8fc11-126">In the above example, the `Chars` property of the string returns the fourth character in the string, which is `D`, and assigns it to `myChar`.</span></span> <span data-ttu-id="8fc11-127">Вы также можете получить длину определенной строки с помощью свойства `Length`.</span><span class="sxs-lookup"><span data-stu-id="8fc11-127">You can also get the length of a particular string through the `Length` property.</span></span> <span data-ttu-id="8fc11-128">Если вам требуется выполнить несколько манипуляций со строкой, можно преобразовать ее в массив экземпляров `Char` с помощью функции `ToCharArray` строки.</span><span class="sxs-lookup"><span data-stu-id="8fc11-128">If you need to perform multiple array-type manipulations on a string, you can convert it to an array of `Char` instances using the `ToCharArray` function of the string.</span></span> <span data-ttu-id="8fc11-129">Пример:</span><span class="sxs-lookup"><span data-stu-id="8fc11-129">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#68)]  
  
 <span data-ttu-id="8fc11-130">Переменная `myArray` теперь содержит массив значений `Char`, каждое из которых представляет символ из `myString`.</span><span class="sxs-lookup"><span data-stu-id="8fc11-130">The variable `myArray` now contains an array of `Char` values, each representing a character from `myString`.</span></span>  
  
## <a name="the-immutability-of-strings"></a><span data-ttu-id="8fc11-131">Неизменность строк</span><span class="sxs-lookup"><span data-stu-id="8fc11-131">The Immutability of Strings</span></span>  
 <span data-ttu-id="8fc11-132">Строка, такая *неизменяемый*, значит, его значение нельзя изменить после ее создания.</span><span class="sxs-lookup"><span data-stu-id="8fc11-132">A string is *immutable*, which means its value cannot be changed once it has been created.</span></span> <span data-ttu-id="8fc11-133">Однако это не мешает назначить строковой переменной более одного значения.</span><span class="sxs-lookup"><span data-stu-id="8fc11-133">However, this does not prevent you from assigning more than one value to a string variable.</span></span> <span data-ttu-id="8fc11-134">Рассмотрим следующий пример.</span><span class="sxs-lookup"><span data-stu-id="8fc11-134">Consider the following example:</span></span>  
  
 [!code-vb[VbVbalrStrings#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#69)]  
  
 <span data-ttu-id="8fc11-135">Здесь строковая переменная создается, получает значение, которое затем изменяется.</span><span class="sxs-lookup"><span data-stu-id="8fc11-135">Here, a string variable is created, given a value, and then its value is changed.</span></span>  
  
 <span data-ttu-id="8fc11-136">В частности, в первой строке создается экземпляр типа `String`, которому присваивается значение `This string is immutable`.</span><span class="sxs-lookup"><span data-stu-id="8fc11-136">More specifically, in the first line, an instance of type `String` is created and given the value `This string is immutable`.</span></span> <span data-ttu-id="8fc11-137">Во второй строке примера создается новый экземпляр, которому присваивается значение `Or is it?`. При этом строковая переменная удаляет ссылку на первый экземпляр и сохраняет ссылку на новый экземпляр.</span><span class="sxs-lookup"><span data-stu-id="8fc11-137">In the second line of the example, a new instance is created and given the value `Or is it?`, and the string variable discards its reference to the first instance and stores a reference to the new instance.</span></span>  
  
 <span data-ttu-id="8fc11-138">В отличие от других встроенных типов данных `String` — это ссылочный тип.</span><span class="sxs-lookup"><span data-stu-id="8fc11-138">Unlike other intrinsic data types, `String` is a reference type.</span></span> <span data-ttu-id="8fc11-139">Если переменная ссылочного типа передается в качестве аргумента функции или подпрограмме, вместо фактического значения строки передается ссылка на адрес в памяти, где хранятся данные.</span><span class="sxs-lookup"><span data-stu-id="8fc11-139">When a variable of reference type is passed as an argument to a function or subroutine, a reference to the memory address where the data is stored is passed instead of the actual value of the string.</span></span> <span data-ttu-id="8fc11-140">Поэтому в предыдущем примере имя переменной остается таким же, но оно указывает на другой экземпляр класса `String`, который содержит новое значение.</span><span class="sxs-lookup"><span data-stu-id="8fc11-140">So in the previous example, the name of the variable remains the same, but it points to a new and different instance of the `String` class, which holds the new value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fc11-141">См. также</span><span class="sxs-lookup"><span data-stu-id="8fc11-141">See also</span></span>

- [<span data-ttu-id="8fc11-142">Знакомство со строками в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8fc11-142">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
- [<span data-ttu-id="8fc11-143">Тип данных String</span><span class="sxs-lookup"><span data-stu-id="8fc11-143">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)
- [<span data-ttu-id="8fc11-144">Тип данных Char</span><span class="sxs-lookup"><span data-stu-id="8fc11-144">Char Data Type</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)
- [<span data-ttu-id="8fc11-145">Базовые операции со строками в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8fc11-145">Basic String Operations</span></span>](../../../../standard/base-types/basic-string-operations.md)
