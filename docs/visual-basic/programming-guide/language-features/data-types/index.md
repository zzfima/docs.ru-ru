---
title: "Типы данных в Visual Basic"
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
- data types [Visual Basic], declaring
- typing
- data types [Visual Basic]
- Visual Basic code, data types
- data types [Visual Basic], improving speed with
ms.assetid: 5e1b9aaf-c7ca-4b29-9b22-0e82ed8e85e2
caps.latest.revision: 28
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8b90a5e58d135a3769761ca431fd0c05f79e045f
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="data-types-in-visual-basic"></a><span data-ttu-id="97145-102">Типы данных в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="97145-102">Data Types in Visual Basic</span></span>
<span data-ttu-id="97145-103">*Тип данных* программного элемента определяет данные, которые он может содержать, а также способ их хранения.</span><span class="sxs-lookup"><span data-stu-id="97145-103">The *data type* of a programming element refers to what kind of data it can hold and how it stores that data.</span></span> <span data-ttu-id="97145-104">Типы данных применяются ко всем значениям, которые могут храниться в памяти компьютера или участвовать в вычислении выражения.</span><span class="sxs-lookup"><span data-stu-id="97145-104">Data types apply to all values that can be stored in computer memory or participate in the evaluation of an expression.</span></span> <span data-ttu-id="97145-105">Все переменные, литералы, константы, перечисления, свойства, параметры и аргументы процедуры, а также возвращаемые значения процедуры относятся к определенному типу данных.</span><span class="sxs-lookup"><span data-stu-id="97145-105">Every variable, literal, constant, enumeration, property, procedure parameter, procedure argument, and procedure return value has a data type.</span></span>  
  
## <a name="declared-data-types"></a><span data-ttu-id="97145-106">Объявленные типы данных</span><span class="sxs-lookup"><span data-stu-id="97145-106">Declared Data Types</span></span>  
 <span data-ttu-id="97145-107">Программный элемент определяется с помощью оператора объявления, а его тип данных указывается с помощью предложения `As`.</span><span class="sxs-lookup"><span data-stu-id="97145-107">You define a programming element with a declaration statement, and you specify its data type with the `As` clause.</span></span> <span data-ttu-id="97145-108">В таблице ниже приведены инструкции, которые используются для объявления разных элементов.</span><span class="sxs-lookup"><span data-stu-id="97145-108">The following table shows the statements you use to declare various elements.</span></span>  
  
|<span data-ttu-id="97145-109">Программный элемент</span><span class="sxs-lookup"><span data-stu-id="97145-109">Programming element</span></span>|<span data-ttu-id="97145-110">Объявление типа данных</span><span class="sxs-lookup"><span data-stu-id="97145-110">Data type declaration</span></span>|  
|-------------------------|---------------------------|  
|<span data-ttu-id="97145-111">Переменная</span><span class="sxs-lookup"><span data-stu-id="97145-111">Variable</span></span>|<span data-ttu-id="97145-112">В [операторе Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="97145-112">In a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md)</span></span><br /><br /> <span data-ttu-id="97145-113">`Dim`   `amount As Double`</span><span class="sxs-lookup"><span data-stu-id="97145-113">`Dim`   `amount As Double`</span></span><br /><br /> <span data-ttu-id="97145-114">`Static`   `yourName As String`</span><span class="sxs-lookup"><span data-stu-id="97145-114">`Static`   `yourName As String`</span></span><br /><br /> <span data-ttu-id="97145-115">`Public`   `billsPaid As Decimal = 0`</span><span class="sxs-lookup"><span data-stu-id="97145-115">`Public`   `billsPaid As Decimal = 0`</span></span>|  
|<span data-ttu-id="97145-116">Литерал</span><span class="sxs-lookup"><span data-stu-id="97145-116">Literal</span></span>|<span data-ttu-id="97145-117">С помощью символа типа литерала; см. [символы типов](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)</span><span class="sxs-lookup"><span data-stu-id="97145-117">With a literal type character; see "Literal Type Characters" in [Type Characters](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)</span></span><br /><br /> <span data-ttu-id="97145-118">`Dim searchChar As Char = "."`  `C`</span><span class="sxs-lookup"><span data-stu-id="97145-118">`Dim searchChar As Char = "."`  `C`</span></span>|  
|<span data-ttu-id="97145-119">Константа</span><span class="sxs-lookup"><span data-stu-id="97145-119">Constant</span></span>|<span data-ttu-id="97145-120">В [операторе Const](../../../../visual-basic/language-reference/statements/const-statement.md)</span><span class="sxs-lookup"><span data-stu-id="97145-120">In a [Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md)</span></span><br /><br /> <span data-ttu-id="97145-121">`Const`   `modulus As Single = 4.17825F`</span><span class="sxs-lookup"><span data-stu-id="97145-121">`Const`   `modulus As Single = 4.17825F`</span></span>|  
|<span data-ttu-id="97145-122">Перечисление</span><span class="sxs-lookup"><span data-stu-id="97145-122">Enumeration</span></span>|<span data-ttu-id="97145-123">В [операторе Enum](../../../../visual-basic/language-reference/statements/enum-statement.md)</span><span class="sxs-lookup"><span data-stu-id="97145-123">In an [Enum Statement](../../../../visual-basic/language-reference/statements/enum-statement.md)</span></span><br /><br /> <span data-ttu-id="97145-124">`Public`   `Enum`   `colors`</span><span class="sxs-lookup"><span data-stu-id="97145-124">`Public`   `Enum`   `colors`</span></span>|  
|<span data-ttu-id="97145-125">Свойство</span><span class="sxs-lookup"><span data-stu-id="97145-125">Property</span></span>|<span data-ttu-id="97145-126">В [операторе Property](../../../../visual-basic/language-reference/statements/property-statement.md)</span><span class="sxs-lookup"><span data-stu-id="97145-126">In a [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md)</span></span><br /><br /> <span data-ttu-id="97145-127">`Property`   `region() As String`</span><span class="sxs-lookup"><span data-stu-id="97145-127">`Property`   `region() As String`</span></span>|  
|<span data-ttu-id="97145-128">Параметр процедуры</span><span class="sxs-lookup"><span data-stu-id="97145-128">Procedure parameter</span></span>|<span data-ttu-id="97145-129">В [операторе Sub](../../../../visual-basic/language-reference/statements/sub-statement.md), [инструкции Function](../../../../visual-basic/language-reference/statements/function-statement.md) или [инструкции Operator](../../../../visual-basic/language-reference/statements/operator-statement.md)</span><span class="sxs-lookup"><span data-stu-id="97145-129">In a [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md), [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md), or [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)</span></span><br /><br /> <span data-ttu-id="97145-130">`Sub addSale(ByVal`   `amount`   `As Double)`</span><span class="sxs-lookup"><span data-stu-id="97145-130">`Sub addSale(ByVal`   `amount`   `As Double)`</span></span>|  
|<span data-ttu-id="97145-131">Аргумент процедуры</span><span class="sxs-lookup"><span data-stu-id="97145-131">Procedure argument</span></span>|<span data-ttu-id="97145-132">В вызывающем коде; все аргументы являются уже объявленными элементами программирования или выражениями, содержащими объявленные элементы</span><span class="sxs-lookup"><span data-stu-id="97145-132">In the calling code; each argument is a programming element that has already been declared, or an expression containing declared elements</span></span><br /><br /> <span data-ttu-id="97145-133">`subString = Left(`  `inputString`  `,`   `5`  `)`</span><span class="sxs-lookup"><span data-stu-id="97145-133">`subString = Left(`  `inputString`  `,`   `5`  `)`</span></span>|  
|<span data-ttu-id="97145-134">Возвращаемое значение процедуры</span><span class="sxs-lookup"><span data-stu-id="97145-134">Procedure return value</span></span>|<span data-ttu-id="97145-135">В [инструкции Function](../../../../visual-basic/language-reference/statements/function-statement.md) или [инструкции Operator](../../../../visual-basic/language-reference/statements/operator-statement.md)</span><span class="sxs-lookup"><span data-stu-id="97145-135">In a [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md) or [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)</span></span><br /><br /> <span data-ttu-id="97145-136">`Function convert(ByVal b As Byte)`   `As String`</span><span class="sxs-lookup"><span data-stu-id="97145-136">`Function convert(ByVal b As Byte)`   `As String`</span></span>|  
  
 <span data-ttu-id="97145-137">См. список [типов данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md) Visual Basic</span><span class="sxs-lookup"><span data-stu-id="97145-137">For a list of Visual Basic data types, see [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97145-138">См. также</span><span class="sxs-lookup"><span data-stu-id="97145-138">See Also</span></span>  
 <span data-ttu-id="97145-139">[Символы типов](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md) </span><span class="sxs-lookup"><span data-stu-id="97145-139">[Type Characters](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md) </span></span>  
 <span data-ttu-id="97145-140">[Простые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="97145-140">[Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span></span>  
 <span data-ttu-id="97145-141">[Составные типы данных](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="97145-141">[Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) </span></span>  
 <span data-ttu-id="97145-142">[Универсальные типы в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span><span class="sxs-lookup"><span data-stu-id="97145-142">[Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span></span>  
 <span data-ttu-id="97145-143">[Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="97145-143">[Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span></span>  
 <span data-ttu-id="97145-144">[Преобразование типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="97145-144">[Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
 <span data-ttu-id="97145-145">[Структуры](../../../../visual-basic/programming-guide/language-features/data-types/structures.md) </span><span class="sxs-lookup"><span data-stu-id="97145-145">[Structures](../../../../visual-basic/programming-guide/language-features/data-types/structures.md) </span></span>  
 <span data-ttu-id="97145-146">[Кортежи](tuples.md)   </span><span class="sxs-lookup"><span data-stu-id="97145-146">[Tuples](tuples.md)   </span></span>  
 <span data-ttu-id="97145-147">[Устранение неполадок, связанных с типами данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="97145-147">[Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span></span>  
 <span data-ttu-id="97145-148">[Типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span><span class="sxs-lookup"><span data-stu-id="97145-148">[Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span></span>  
 [<span data-ttu-id="97145-149">Эффективное использование типов данных</span><span class="sxs-lookup"><span data-stu-id="97145-149">Efficient Use of Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)

