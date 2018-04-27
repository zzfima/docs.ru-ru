---
title: Типы данных констант и литералов (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declaring constants [Visual Basic], literal data types
- data types [Visual Basic], declaring
- constants [Visual Basic], declaring
- explicit declarations
- literals [Visual Basic], coercing data type
- declarations [Visual Basic], data types
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 58fa1e8c6c659c80cd7998a88d07849ea223750f
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="constant-and-literal-data-types-visual-basic"></a><span data-ttu-id="558e3-102">Типы данных констант и литералов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="558e3-102">Constant and Literal Data Types (Visual Basic)</span></span>
<span data-ttu-id="558e3-103">Литерал — это значение, выраженное самостоятельно, а не как значение переменной или результата выражения, например число 3 или строка «Hello».</span><span class="sxs-lookup"><span data-stu-id="558e3-103">A literal is a value that is expressed as itself rather than as a variable's value or the result of an expression, such as the number 3 or the string "Hello".</span></span> <span data-ttu-id="558e3-104">Константа — это понятное имя, которое занимает место литерал и сохраняет это же значение для программы, в отличие от переменной, значение которого может измениться.</span><span class="sxs-lookup"><span data-stu-id="558e3-104">A constant is a meaningful name that takes the place of a literal and retains this same value throughout the program, as opposed to a variable, whose value may change.</span></span>  
  
 <span data-ttu-id="558e3-105">Когда [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) — `Off` и [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) — `On`, вы должны явно объявить все константы с типом данных.</span><span class="sxs-lookup"><span data-stu-id="558e3-105">When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare all constants explicitly with a data type.</span></span> <span data-ttu-id="558e3-106">В следующем примере тип данных `MyByte` явно объявляется как тип данных `Byte`:</span><span class="sxs-lookup"><span data-stu-id="558e3-106">In the following example, the data type of `MyByte` is explicitly declared as data type `Byte`:</span></span>  
  
 [!code-vb[VbVbalrConstants#1](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_1.vb)]  
  
 <span data-ttu-id="558e3-107">Когда `Option Infer` — `On` или `Option Strict` — `Off`, можно объявить константу без указания типа данных с `As` предложения.</span><span class="sxs-lookup"><span data-stu-id="558e3-107">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="558e3-108">Компилятор определяет тип константы из типа выражения.</span><span class="sxs-lookup"><span data-stu-id="558e3-108">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="558e3-109">Целочисленный литерал приведен по умолчанию для `Integer` тип данных.</span><span class="sxs-lookup"><span data-stu-id="558e3-109">A numeric integer literal is cast by default to the `Integer` data type.</span></span> <span data-ttu-id="558e3-110">Для чисел с плавающей запятой имеет тип данных по умолчанию `Double`, а также ключевые слова `True` и `False` укажите `Boolean` константой.</span><span class="sxs-lookup"><span data-stu-id="558e3-110">The default data type for floating-point numbers is `Double`, and the keywords `True` and `False` specify a `Boolean` constant.</span></span>  
  
## <a name="literals-and-type-coercion"></a><span data-ttu-id="558e3-111">Литералы и приведение типов</span><span class="sxs-lookup"><span data-stu-id="558e3-111">Literals and Type Coercion</span></span>  
 <span data-ttu-id="558e3-112">В некоторых случаях может потребоваться принудительно литерала к определенному типу данных; Например, при назначении особенно большой целочисленное литеральное значение для переменной типа `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="558e3-112">In some cases, you might want to force a literal to a particular data type; for example, when assigning a particularly large integral literal value to a variable of type `Decimal`.</span></span> <span data-ttu-id="558e3-113">Следующий пример приводит к ошибке:</span><span class="sxs-lookup"><span data-stu-id="558e3-113">The following example produces an error:</span></span>  
  
```  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 <span data-ttu-id="558e3-114">Эта ошибка возникает из представления литерала.</span><span class="sxs-lookup"><span data-stu-id="558e3-114">The error results from the representation of the literal.</span></span> <span data-ttu-id="558e3-115">`Decimal` Тип данных может содержать значение такой величины, но литерал неявно представлен как `Long`, которые могут.</span><span class="sxs-lookup"><span data-stu-id="558e3-115">The `Decimal` data type can hold a value this large, but the literal is implicitly represented as a `Long`, which cannot.</span></span>  
  
 <span data-ttu-id="558e3-116">Приведение литерала к определенному типу данных двумя способами: путем добавления к литералу символа типа, или путем помещения его в пределах содержащего его символов.</span><span class="sxs-lookup"><span data-stu-id="558e3-116">You can coerce a literal to a particular data type in two ways: by appending a type character to it, or by placing it within enclosing characters.</span></span> <span data-ttu-id="558e3-117">Символ типа или окружающие символы должны непосредственно предшествовать и/или выполните литерал без промежуточных пробелов и символов любого типа.</span><span class="sxs-lookup"><span data-stu-id="558e3-117">A type character or enclosing characters must immediately precede and/or follow the literal, with no intervening space or characters of any kind.</span></span>  
  
 <span data-ttu-id="558e3-118">Чтобы предыдущий пример работал, можно добавить `D` знак в литерал, что приведет к представляется в виде типа `Decimal`:</span><span class="sxs-lookup"><span data-stu-id="558e3-118">To make the previous example work, you can append the `D` type character to the literal, which causes it to be represented as a `Decimal`:</span></span>  
  
 [!code-vb[VbVbalrConstants#2](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_2.vb)]  
  
 <span data-ttu-id="558e3-119">В следующем примере показано правильное использование символов типа и окружающих символов:</span><span class="sxs-lookup"><span data-stu-id="558e3-119">The following example demonstrates correct usage of type characters and enclosing characters:</span></span>  
  
 [!code-vb[VbVbalrConstants#3](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_3.vb)]  
  
 <span data-ttu-id="558e3-120">Следующей таблице показаны окружающие символы и символы типов, доступные в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="558e3-120">The following table shows the enclosing characters and type characters available in Visual Basic.</span></span>  
  
|<span data-ttu-id="558e3-121">Тип данных</span><span class="sxs-lookup"><span data-stu-id="558e3-121">Data type</span></span>|<span data-ttu-id="558e3-122">Внешний символ</span><span class="sxs-lookup"><span data-stu-id="558e3-122">Enclosing character</span></span>|<span data-ttu-id="558e3-123">Добавленный символ типа</span><span class="sxs-lookup"><span data-stu-id="558e3-123">Appended type character</span></span>|  
|---|---|---|  
|`Boolean`|<span data-ttu-id="558e3-124">(нет)</span><span class="sxs-lookup"><span data-stu-id="558e3-124">(none)</span></span>|<span data-ttu-id="558e3-125">(нет)</span><span class="sxs-lookup"><span data-stu-id="558e3-125">(none)</span></span>|  
|`Byte`|<span data-ttu-id="558e3-126">(нет)</span><span class="sxs-lookup"><span data-stu-id="558e3-126">(none)</span></span>|<span data-ttu-id="558e3-127">(нет)</span><span class="sxs-lookup"><span data-stu-id="558e3-127">(none)</span></span>|  
|`Char`|<span data-ttu-id="558e3-128">"</span><span class="sxs-lookup"><span data-stu-id="558e3-128">"</span></span>|<span data-ttu-id="558e3-129">В</span><span class="sxs-lookup"><span data-stu-id="558e3-129">C</span></span>|  
|`Date`|#|<span data-ttu-id="558e3-130">(нет)</span><span class="sxs-lookup"><span data-stu-id="558e3-130">(none)</span></span>|  
|`Decimal`|<span data-ttu-id="558e3-131">(нет)</span><span class="sxs-lookup"><span data-stu-id="558e3-131">(none)</span></span>|<span data-ttu-id="558e3-132">D или @</span><span class="sxs-lookup"><span data-stu-id="558e3-132">D or @</span></span>|  
|`Double`|<span data-ttu-id="558e3-133">(нет)</span><span class="sxs-lookup"><span data-stu-id="558e3-133">(none)</span></span>|<span data-ttu-id="558e3-134">R или #</span><span class="sxs-lookup"><span data-stu-id="558e3-134">R or #</span></span>|  
|`Integer`|<span data-ttu-id="558e3-135">(нет)</span><span class="sxs-lookup"><span data-stu-id="558e3-135">(none)</span></span>|<span data-ttu-id="558e3-136">I или %</span><span class="sxs-lookup"><span data-stu-id="558e3-136">I or %</span></span>|  
|`Long`|<span data-ttu-id="558e3-137">(нет)</span><span class="sxs-lookup"><span data-stu-id="558e3-137">(none)</span></span>|<span data-ttu-id="558e3-138">L или &</span><span class="sxs-lookup"><span data-stu-id="558e3-138">L or &</span></span>|  
|`Short`|<span data-ttu-id="558e3-139">(нет)</span><span class="sxs-lookup"><span data-stu-id="558e3-139">(none)</span></span>|<span data-ttu-id="558e3-140">S</span><span class="sxs-lookup"><span data-stu-id="558e3-140">S</span></span>|  
|`Single`|<span data-ttu-id="558e3-141">(нет)</span><span class="sxs-lookup"><span data-stu-id="558e3-141">(none)</span></span>|<span data-ttu-id="558e3-142">F или!</span><span class="sxs-lookup"><span data-stu-id="558e3-142">F or !</span></span>|  
|`String`|<span data-ttu-id="558e3-143">"</span><span class="sxs-lookup"><span data-stu-id="558e3-143">"</span></span>|<span data-ttu-id="558e3-144">(нет)</span><span class="sxs-lookup"><span data-stu-id="558e3-144">(none)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="558e3-145">См. также</span><span class="sxs-lookup"><span data-stu-id="558e3-145">See Also</span></span>  
 [<span data-ttu-id="558e3-146">Константы, определенные пользователем</span><span class="sxs-lookup"><span data-stu-id="558e3-146">User-Defined Constants</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)  
 [<span data-ttu-id="558e3-147">Практическое руководство. Объявление константы</span><span class="sxs-lookup"><span data-stu-id="558e3-147">How to: Declare A Constant</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)  
 [<span data-ttu-id="558e3-148">Общие сведения о константах</span><span class="sxs-lookup"><span data-stu-id="558e3-148">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [<span data-ttu-id="558e3-149">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="558e3-149">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="558e3-150">Оператор Option Explicit</span><span class="sxs-lookup"><span data-stu-id="558e3-150">Option Explicit Statement</span></span>](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [<span data-ttu-id="558e3-151">Общие сведения о перечислениях</span><span class="sxs-lookup"><span data-stu-id="558e3-151">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [<span data-ttu-id="558e3-152">Как: объявление перечисления</span><span class="sxs-lookup"><span data-stu-id="558e3-152">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [<span data-ttu-id="558e3-153">Перечисления и уточнение имен</span><span class="sxs-lookup"><span data-stu-id="558e3-153">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [<span data-ttu-id="558e3-154">Типы данных</span><span class="sxs-lookup"><span data-stu-id="558e3-154">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="558e3-155">Константы и перечисления</span><span class="sxs-lookup"><span data-stu-id="558e3-155">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
