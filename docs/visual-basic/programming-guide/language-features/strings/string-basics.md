---
title: Основы работы со строками
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Like operator
- strings [Visual Basic], Visual Basic
- strings [Visual Basic], regular expressions
ms.assetid: 5674418d-f00d-4f72-9f98-d15897793350
ms.openlocfilehash: 7141966e3c8a8cbce42111c56a85a00709e8fe1a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344282"
---
# <a name="string-basics-in-visual-basic"></a><span data-ttu-id="f59f3-102">Основы работы со строками в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f59f3-102">String Basics in Visual Basic</span></span>
<span data-ttu-id="f59f3-103">Тип данных `String` представляет последовательность символов (каждый из которых, в свою очередь, представляет экземпляр типа данных `Char`).</span><span class="sxs-lookup"><span data-stu-id="f59f3-103">The `String` data type represents a series of characters (each representing in turn an instance of the `Char` data type).</span></span> <span data-ttu-id="f59f3-104">This topic introduces the basic concepts of strings in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f59f3-104">This topic introduces the basic concepts of strings in Visual Basic.</span></span>  
  
## <a name="string-variables"></a><span data-ttu-id="f59f3-105">Строковые переменные</span><span class="sxs-lookup"><span data-stu-id="f59f3-105">String Variables</span></span>  
 <span data-ttu-id="f59f3-106">Экземпляру строки можно назначить литеральное значение, которое представляет ряд символов.</span><span class="sxs-lookup"><span data-stu-id="f59f3-106">An instance of a string can be assigned a literal value that represents a series of characters.</span></span> <span data-ttu-id="f59f3-107">Пример:</span><span class="sxs-lookup"><span data-stu-id="f59f3-107">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#63)]  
  
 <span data-ttu-id="f59f3-108">Переменная `String` также может принимать любое выражение, результатом которого является строка.</span><span class="sxs-lookup"><span data-stu-id="f59f3-108">A `String` variable can also accept any expression that evaluates to a string.</span></span> <span data-ttu-id="f59f3-109">Ниже приведены примеры.</span><span class="sxs-lookup"><span data-stu-id="f59f3-109">Examples are shown below:</span></span>  
  
 [!code-vb[VbVbalrStrings#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#64)]  
  
 <span data-ttu-id="f59f3-110">Любой литерал, который присваивается переменной `String`, должен быть заключен в кавычки ("").</span><span class="sxs-lookup"><span data-stu-id="f59f3-110">Any literal that is assigned to a `String` variable must be enclosed in quotation marks ("").</span></span> <span data-ttu-id="f59f3-111">Это означает, что кавычки в пределах строки не могут быть представлены кавычкой.</span><span class="sxs-lookup"><span data-stu-id="f59f3-111">This means that a quotation mark within a string cannot be represented by a quotation mark.</span></span> <span data-ttu-id="f59f3-112">Например, следующий код вызовет ошибку компиляции:</span><span class="sxs-lookup"><span data-stu-id="f59f3-112">For example, the following code causes a compiler error:</span></span>  
  
 [!code-vb[VbVbalrStrings#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#65)]  
  
 <span data-ttu-id="f59f3-113">Этот код вызывает ошибку, так как компилятор завершает строку после второй пары кавычек, а остаток строки интерпретируется как код.</span><span class="sxs-lookup"><span data-stu-id="f59f3-113">This code causes an error because the compiler terminates the string after the second quotation mark, and the remainder of the string is interpreted as code.</span></span> <span data-ttu-id="f59f3-114">To solve this problem, Visual Basic interprets two quotation marks in a string literal as one quotation mark in the string.</span><span class="sxs-lookup"><span data-stu-id="f59f3-114">To solve this problem, Visual Basic interprets two quotation marks in a string literal as one quotation mark in the string.</span></span> <span data-ttu-id="f59f3-115">В следующем примере показан правильный способ указания кавычек в строке:</span><span class="sxs-lookup"><span data-stu-id="f59f3-115">The following example demonstrates the correct way to include a quotation mark in a string:</span></span>  
  
 [!code-vb[VbVbalrStrings#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#66)]  
  
 <span data-ttu-id="f59f3-116">В предыдущем примере два символа кавычек перед словом `Look` становятся одним символом кавычек в строке.</span><span class="sxs-lookup"><span data-stu-id="f59f3-116">In the preceding example, the two quotation marks preceding the word `Look` become one quotation mark in the string.</span></span> <span data-ttu-id="f59f3-117">Три символа кавычек в конце строки представляют один символ кавычек в строке и конечный символ строки.</span><span class="sxs-lookup"><span data-stu-id="f59f3-117">The three quotation marks at the end of the line represent one quotation mark in the string and the string termination character.</span></span>  
  
 <span data-ttu-id="f59f3-118">Строковые литералы могут содержать несколько строк:</span><span class="sxs-lookup"><span data-stu-id="f59f3-118">String literals can contain multiple lines:</span></span>  
  
```vb  
Dim x = "hello  
world"  
```  
  
 <span data-ttu-id="f59f3-119">Результирующая строка содержит последовательности новых строк, используемых в строковом литерале (vbcr, vbcrlf и т. д.).</span><span class="sxs-lookup"><span data-stu-id="f59f3-119">The resulting string contains newline sequences that you used in your string literal (vbcr, vbcrlf, etc.).</span></span>  <span data-ttu-id="f59f3-120">Вам больше не требуется использовать старое решение:</span><span class="sxs-lookup"><span data-stu-id="f59f3-120">You no longer need to use the old workaround:</span></span>  
  
```vb  
Dim x = <xml><![CDATA[Hello  
World]]></xml>.Value  
```  
  
## <a name="characters-in-strings"></a><span data-ttu-id="f59f3-121">Символы в строках</span><span class="sxs-lookup"><span data-stu-id="f59f3-121">Characters in Strings</span></span>  
 <span data-ttu-id="f59f3-122">Строку можно представить как последовательность значений `Char`. При этом тип `String` имеет встроенные функции, которые позволяют работать со строками, как с массивами.</span><span class="sxs-lookup"><span data-stu-id="f59f3-122">A string can be thought of as a series of `Char` values, and the `String` type has built-in functions that allow you to perform many manipulations on a string that resemble the manipulations allowed by arrays.</span></span> <span data-ttu-id="f59f3-123">Like all array in .NET Framework, these are zero-based arrays.</span><span class="sxs-lookup"><span data-stu-id="f59f3-123">Like all array in .NET Framework, these are zero-based arrays.</span></span> <span data-ttu-id="f59f3-124">К определенному символу в строке можно обратиться с помощью свойства `Chars`, которое предоставляет механизм доступа к символу по позиции, в которой он отображается в строке.</span><span class="sxs-lookup"><span data-stu-id="f59f3-124">You may refer to a specific character in a string through the `Chars` property, which provides a way to access a character by the position in which it appears in the string.</span></span> <span data-ttu-id="f59f3-125">Пример:</span><span class="sxs-lookup"><span data-stu-id="f59f3-125">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#67)]  
  
 <span data-ttu-id="f59f3-126">В приведенном выше примере свойство `Chars` строки возвращает четвертый символ в строке, `D`, и присваивает его `myChar`.</span><span class="sxs-lookup"><span data-stu-id="f59f3-126">In the above example, the `Chars` property of the string returns the fourth character in the string, which is `D`, and assigns it to `myChar`.</span></span> <span data-ttu-id="f59f3-127">Вы также можете получить длину определенной строки с помощью свойства `Length`.</span><span class="sxs-lookup"><span data-stu-id="f59f3-127">You can also get the length of a particular string through the `Length` property.</span></span> <span data-ttu-id="f59f3-128">Если вам требуется выполнить несколько манипуляций со строкой, можно преобразовать ее в массив экземпляров `Char` с помощью функции `ToCharArray` строки.</span><span class="sxs-lookup"><span data-stu-id="f59f3-128">If you need to perform multiple array-type manipulations on a string, you can convert it to an array of `Char` instances using the `ToCharArray` function of the string.</span></span> <span data-ttu-id="f59f3-129">Пример:</span><span class="sxs-lookup"><span data-stu-id="f59f3-129">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#68)]  
  
 <span data-ttu-id="f59f3-130">Переменная `myArray` теперь содержит массив значений `Char`, каждое из которых представляет символ из `myString`.</span><span class="sxs-lookup"><span data-stu-id="f59f3-130">The variable `myArray` now contains an array of `Char` values, each representing a character from `myString`.</span></span>  
  
## <a name="the-immutability-of-strings"></a><span data-ttu-id="f59f3-131">Неизменность строк</span><span class="sxs-lookup"><span data-stu-id="f59f3-131">The Immutability of Strings</span></span>  
 <span data-ttu-id="f59f3-132">A string is *immutable*, which means its value cannot be changed once it has been created.</span><span class="sxs-lookup"><span data-stu-id="f59f3-132">A string is *immutable*, which means its value cannot be changed once it has been created.</span></span> <span data-ttu-id="f59f3-133">Однако это не мешает назначить строковой переменной более одного значения.</span><span class="sxs-lookup"><span data-stu-id="f59f3-133">However, this does not prevent you from assigning more than one value to a string variable.</span></span> <span data-ttu-id="f59f3-134">Рассмотрим следующий пример.</span><span class="sxs-lookup"><span data-stu-id="f59f3-134">Consider the following example:</span></span>  
  
 [!code-vb[VbVbalrStrings#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#69)]  
  
 <span data-ttu-id="f59f3-135">Здесь строковая переменная создается, получает значение, которое затем изменяется.</span><span class="sxs-lookup"><span data-stu-id="f59f3-135">Here, a string variable is created, given a value, and then its value is changed.</span></span>  
  
 <span data-ttu-id="f59f3-136">В частности, в первой строке создается экземпляр типа `String`, которому присваивается значение `This string is immutable`.</span><span class="sxs-lookup"><span data-stu-id="f59f3-136">More specifically, in the first line, an instance of type `String` is created and given the value `This string is immutable`.</span></span> <span data-ttu-id="f59f3-137">Во второй строке примера создается новый экземпляр, которому присваивается значение `Or is it?`. При этом строковая переменная удаляет ссылку на первый экземпляр и сохраняет ссылку на новый экземпляр.</span><span class="sxs-lookup"><span data-stu-id="f59f3-137">In the second line of the example, a new instance is created and given the value `Or is it?`, and the string variable discards its reference to the first instance and stores a reference to the new instance.</span></span>  
  
 <span data-ttu-id="f59f3-138">В отличие от других встроенных типов данных `String` — это ссылочный тип.</span><span class="sxs-lookup"><span data-stu-id="f59f3-138">Unlike other intrinsic data types, `String` is a reference type.</span></span> <span data-ttu-id="f59f3-139">Если переменная ссылочного типа передается в качестве аргумента функции или подпрограмме, вместо фактического значения строки передается ссылка на адрес в памяти, где хранятся данные.</span><span class="sxs-lookup"><span data-stu-id="f59f3-139">When a variable of reference type is passed as an argument to a function or subroutine, a reference to the memory address where the data is stored is passed instead of the actual value of the string.</span></span> <span data-ttu-id="f59f3-140">Поэтому в предыдущем примере имя переменной остается таким же, но оно указывает на другой экземпляр класса `String`, который содержит новое значение.</span><span class="sxs-lookup"><span data-stu-id="f59f3-140">So in the previous example, the name of the variable remains the same, but it points to a new and different instance of the `String` class, which holds the new value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f59f3-141">См. также</span><span class="sxs-lookup"><span data-stu-id="f59f3-141">See also</span></span>

- [<span data-ttu-id="f59f3-142">Знакомство со строками в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f59f3-142">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
- [<span data-ttu-id="f59f3-143">Тип данных String</span><span class="sxs-lookup"><span data-stu-id="f59f3-143">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)
- [<span data-ttu-id="f59f3-144">Тип данных Char</span><span class="sxs-lookup"><span data-stu-id="f59f3-144">Char Data Type</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)
- [<span data-ttu-id="f59f3-145">Базовые операции со строками в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f59f3-145">Basic String Operations</span></span>](../../../../standard/base-types/basic-string-operations.md)
