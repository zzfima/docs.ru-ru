---
title: "Типы данных констант и литералов (Visual Basic) | Документы Microsoft"
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
- declaring constants, literal data types
- data types [Visual Basic], declaring
- constants, declaring
- explicit declarations
- literals, coercing data type
- declarations, data types
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
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
ms.openlocfilehash: 29a997ee0dd847e8505d1a5c24cacfdfdb0a42cc
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="constant-and-literal-data-types-visual-basic"></a><span data-ttu-id="b4cf4-102">Типы данных констант и литералов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b4cf4-102">Constant and Literal Data Types (Visual Basic)</span></span>
<span data-ttu-id="b4cf4-103">Литерал — это значение, выраженное самостоятельно, а не как значение переменной или результата выражения, например число 3 или строка «Hello».</span><span class="sxs-lookup"><span data-stu-id="b4cf4-103">A literal is a value that is expressed as itself rather than as a variable's value or the result of an expression, such as the number 3 or the string "Hello".</span></span> <span data-ttu-id="b4cf4-104">Константа представляет собой значимое имя, занимает место литерал и сохраняет этот же значение на протяжении всей программы, в отличие от переменной, значение которого может измениться.</span><span class="sxs-lookup"><span data-stu-id="b4cf4-104">A constant is a meaningful name that takes the place of a literal and retains this same value throughout the program, as opposed to a variable, whose value may change.</span></span>  
  
 <span data-ttu-id="b4cf4-105">Когда [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) — `Off` и [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) — `On`, можно явно объявить все константы с типом данных.</span><span class="sxs-lookup"><span data-stu-id="b4cf4-105">When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare all constants explicitly with a data type.</span></span> <span data-ttu-id="b4cf4-106">В следующем примере тип данных `MyByte` явно объявляется как тип данных `Byte`:</span><span class="sxs-lookup"><span data-stu-id="b4cf4-106">In the following example, the data type of `MyByte` is explicitly declared as data type `Byte`:</span></span>  
  
 <span data-ttu-id="b4cf4-107">[!code-vb[VbVbalrConstants&#1;](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="b4cf4-107">[!code-vb[VbVbalrConstants#1](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_1.vb)]</span></span>  
  
 <span data-ttu-id="b4cf4-108">Когда `Option Infer` — `On` или `Option Strict` — `Off`, можно объявить константу без указания типа данных с `As` предложения.</span><span class="sxs-lookup"><span data-stu-id="b4cf4-108">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="b4cf4-109">Компилятор определяет тип константы из типа выражения.</span><span class="sxs-lookup"><span data-stu-id="b4cf4-109">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="b4cf4-110">Целочисленный литерал приведен по умолчанию для `Integer` тип данных.</span><span class="sxs-lookup"><span data-stu-id="b4cf4-110">A numeric integer literal is cast by default to the `Integer` data type.</span></span> <span data-ttu-id="b4cf4-111">Тип данных по умолчанию для чисел с плавающей запятой — `Double`и ключевые слова `True` и `False` укажите `Boolean` константой.</span><span class="sxs-lookup"><span data-stu-id="b4cf4-111">The default data type for floating-point numbers is `Double`, and the keywords `True` and `False` specify a `Boolean` constant.</span></span>  
  
## <a name="literals-and-type-coercion"></a><span data-ttu-id="b4cf4-112">Литералы и приведение типов</span><span class="sxs-lookup"><span data-stu-id="b4cf4-112">Literals and Type Coercion</span></span>  
 <span data-ttu-id="b4cf4-113">В некоторых случаях может потребоваться принудительно литерала к определенному типу данных. Например, при назначении особенно большого целочисленного значения литерала переменной типа `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="b4cf4-113">In some cases, you might want to force a literal to a particular data type; for example, when assigning a particularly large integral literal value to a variable of type `Decimal`.</span></span> <span data-ttu-id="b4cf4-114">Следующий пример приводит к ошибке:</span><span class="sxs-lookup"><span data-stu-id="b4cf4-114">The following example produces an error:</span></span>  
  
```  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 <span data-ttu-id="b4cf4-115">Эта ошибка возникает из представления литерала.</span><span class="sxs-lookup"><span data-stu-id="b4cf4-115">The error results from the representation of the literal.</span></span> <span data-ttu-id="b4cf4-116">`Decimal` Тип данных может содержать значение такой величины, но литерал неявно представлен как `Long`, который невозможно.</span><span class="sxs-lookup"><span data-stu-id="b4cf4-116">The `Decimal` data type can hold a value this large, but the literal is implicitly represented as a `Long`, which cannot.</span></span>  
  
 <span data-ttu-id="b4cf4-117">Приведение литерала к определенному типу данных двумя способами: путем добавления к литералу символа типа либо путем заключения его между окружающими символами.</span><span class="sxs-lookup"><span data-stu-id="b4cf4-117">You can coerce a literal to a particular data type in two ways: by appending a type character to it, or by placing it within enclosing characters.</span></span> <span data-ttu-id="b4cf4-118">Символ типа или окружающие символы должны непосредственно предшествовать и/или выполните литерал без промежуточных пробелов или знаков любого типа.</span><span class="sxs-lookup"><span data-stu-id="b4cf4-118">A type character or enclosing characters must immediately precede and/or follow the literal, with no intervening space or characters of any kind.</span></span>  
  
 <span data-ttu-id="b4cf4-119">Чтобы предыдущий пример работал, добавьте `D` введите знак в литерал, вследствие чего он представлен как `Decimal`:</span><span class="sxs-lookup"><span data-stu-id="b4cf4-119">To make the previous example work, you can append the `D` type character to the literal, which causes it to be represented as a `Decimal`:</span></span>  
  
 <span data-ttu-id="b4cf4-120">[!code-vb[VbVbalrConstants&#2;](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="b4cf4-120">[!code-vb[VbVbalrConstants#2](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_2.vb)]</span></span>  
  
 <span data-ttu-id="b4cf4-121">В следующем примере показано правильное использование символов типа и окружающих символов:</span><span class="sxs-lookup"><span data-stu-id="b4cf4-121">The following example demonstrates correct usage of type characters and enclosing characters:</span></span>  
  
 <span data-ttu-id="b4cf4-122">[!code-vb[VbVbalrConstants&#3;](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="b4cf4-122">[!code-vb[VbVbalrConstants#3](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_3.vb)]</span></span>  
  
 <span data-ttu-id="b4cf4-123">В следующей таблице показаны окружающие символы и тип символов, доступных в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4cf4-123">The following table shows the enclosing characters and type characters available in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
|<span data-ttu-id="b4cf4-124">Тип данных</span><span class="sxs-lookup"><span data-stu-id="b4cf4-124">Data type</span></span>|<span data-ttu-id="b4cf4-125">Окружающий символ</span><span class="sxs-lookup"><span data-stu-id="b4cf4-125">Enclosing character</span></span>|<span data-ttu-id="b4cf4-126">Добавленный символ типа</span><span class="sxs-lookup"><span data-stu-id="b4cf4-126">Appended type character</span></span>|  
|---|---|---|  
|`Boolean`|<span data-ttu-id="b4cf4-127">(нет)</span><span class="sxs-lookup"><span data-stu-id="b4cf4-127">(none)</span></span>|<span data-ttu-id="b4cf4-128">(нет)</span><span class="sxs-lookup"><span data-stu-id="b4cf4-128">(none)</span></span>|  
|`Byte`|<span data-ttu-id="b4cf4-129">(нет)</span><span class="sxs-lookup"><span data-stu-id="b4cf4-129">(none)</span></span>|<span data-ttu-id="b4cf4-130">(нет)</span><span class="sxs-lookup"><span data-stu-id="b4cf4-130">(none)</span></span>|  
|`Char`|<span data-ttu-id="b4cf4-131">"</span><span class="sxs-lookup"><span data-stu-id="b4cf4-131">"</span></span>|<span data-ttu-id="b4cf4-132">C</span><span class="sxs-lookup"><span data-stu-id="b4cf4-132">C</span></span>|  
|`Date`|#|<span data-ttu-id="b4cf4-133">(нет)</span><span class="sxs-lookup"><span data-stu-id="b4cf4-133">(none)</span></span>|  
|`Decimal`|<span data-ttu-id="b4cf4-134">(нет)</span><span class="sxs-lookup"><span data-stu-id="b4cf4-134">(none)</span></span>|<span data-ttu-id="b4cf4-135">D или @</span><span class="sxs-lookup"><span data-stu-id="b4cf4-135">D or @</span></span>|  
|`Double`|<span data-ttu-id="b4cf4-136">(нет)</span><span class="sxs-lookup"><span data-stu-id="b4cf4-136">(none)</span></span>|<span data-ttu-id="b4cf4-137">R или</span><span class="sxs-lookup"><span data-stu-id="b4cf4-137">R or</span></span> #|  
|`Integer`|<span data-ttu-id="b4cf4-138">(нет)</span><span class="sxs-lookup"><span data-stu-id="b4cf4-138">(none)</span></span>|<span data-ttu-id="b4cf4-139">I или %</span><span class="sxs-lookup"><span data-stu-id="b4cf4-139">I or %</span></span>|  
|`Long`|<span data-ttu-id="b4cf4-140">(нет)</span><span class="sxs-lookup"><span data-stu-id="b4cf4-140">(none)</span></span>|<span data-ttu-id="b4cf4-141">L или &</span><span class="sxs-lookup"><span data-stu-id="b4cf4-141">L or &</span></span>|  
|`Short`|<span data-ttu-id="b4cf4-142">(нет)</span><span class="sxs-lookup"><span data-stu-id="b4cf4-142">(none)</span></span>|<span data-ttu-id="b4cf4-143">S</span><span class="sxs-lookup"><span data-stu-id="b4cf4-143">S</span></span>|  
|`Single`|<span data-ttu-id="b4cf4-144">(нет)</span><span class="sxs-lookup"><span data-stu-id="b4cf4-144">(none)</span></span>|<span data-ttu-id="b4cf4-145">F или!</span><span class="sxs-lookup"><span data-stu-id="b4cf4-145">F or !</span></span>|  
|`String`|<span data-ttu-id="b4cf4-146">"</span><span class="sxs-lookup"><span data-stu-id="b4cf4-146">"</span></span>|<span data-ttu-id="b4cf4-147">(нет)</span><span class="sxs-lookup"><span data-stu-id="b4cf4-147">(none)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b4cf4-148">См. также</span><span class="sxs-lookup"><span data-stu-id="b4cf4-148">See Also</span></span>  
 <span data-ttu-id="b4cf4-149">[Константы, определенные пользователем](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md) </span><span class="sxs-lookup"><span data-stu-id="b4cf4-149">[User-Defined Constants](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md) </span></span>  
<span data-ttu-id="b4cf4-150"> [Практическое руководство: объявление константы](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md) </span><span class="sxs-lookup"><span data-stu-id="b4cf4-150"> [How to: Declare A Constant](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md) </span></span>  
<span data-ttu-id="b4cf4-151"> [Общие сведения о константах](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md) </span><span class="sxs-lookup"><span data-stu-id="b4cf4-151"> [Constants Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md) </span></span>  
<span data-ttu-id="b4cf4-152"> [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="b4cf4-152"> [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
<span data-ttu-id="b4cf4-153"> [Оператор Option Explicit](../../../../visual-basic/language-reference/statements/option-explicit-statement.md) </span><span class="sxs-lookup"><span data-stu-id="b4cf4-153"> [Option Explicit Statement](../../../../visual-basic/language-reference/statements/option-explicit-statement.md) </span></span>  
<span data-ttu-id="b4cf4-154"> [Общие сведения о перечислениях](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md) </span><span class="sxs-lookup"><span data-stu-id="b4cf4-154"> [Enumerations Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md) </span></span>  
<span data-ttu-id="b4cf4-155"> [Практическое руководство: объявление перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md) </span><span class="sxs-lookup"><span data-stu-id="b4cf4-155"> [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md) </span></span>  
<span data-ttu-id="b4cf4-156"> [Перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span><span class="sxs-lookup"><span data-stu-id="b4cf4-156"> [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span></span>  
<span data-ttu-id="b4cf4-157"> [Типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span><span class="sxs-lookup"><span data-stu-id="b4cf4-157"> [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span></span>  
<span data-ttu-id="b4cf4-158"> [Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span><span class="sxs-lookup"><span data-stu-id="b4cf4-158"> [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span></span>
