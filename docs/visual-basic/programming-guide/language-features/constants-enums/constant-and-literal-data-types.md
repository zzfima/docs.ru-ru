---
title: Типы данных констант и литералов (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declaring constants [Visual Basic], literal data types
- data types [Visual Basic], declaring
- constants [Visual Basic], declaring
- explicit declarations
- literals [Visual Basic], coercing data type
- declarations [Visual Basic], data types
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
ms.openlocfilehash: 1d030f8058cd497212c20bca8f064f2bedc99fce
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2018
ms.locfileid: "42999931"
---
# <a name="constant-and-literal-data-types-visual-basic"></a><span data-ttu-id="2fa03-102">Типы данных констант и литералов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2fa03-102">Constant and Literal Data Types (Visual Basic)</span></span>
<span data-ttu-id="2fa03-103">Литерал — это значение, которое выражается само по себе, а не как значение переменной или результат выражения, например число 3 или строка «Hello».</span><span class="sxs-lookup"><span data-stu-id="2fa03-103">A literal is a value that is expressed as itself rather than as a variable's value or the result of an expression, such as the number 3 or the string "Hello".</span></span> <span data-ttu-id="2fa03-104">Константа представляет собой значимое имя, которое занимает место литерал и хранит это же значение для программы, в отличие от переменной, значения которых могут меняться.</span><span class="sxs-lookup"><span data-stu-id="2fa03-104">A constant is a meaningful name that takes the place of a literal and retains this same value throughout the program, as opposed to a variable, whose value may change.</span></span>  
  
 <span data-ttu-id="2fa03-105">Когда [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) — `Off` и [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) является `On`, необходимо объявить все константы явным образом с типом данных.</span><span class="sxs-lookup"><span data-stu-id="2fa03-105">When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare all constants explicitly with a data type.</span></span> <span data-ttu-id="2fa03-106">В следующем примере, тип данных `MyByte` явно объявлен как тип данных `Byte`:</span><span class="sxs-lookup"><span data-stu-id="2fa03-106">In the following example, the data type of `MyByte` is explicitly declared as data type `Byte`:</span></span>  
  
 [!code-vb[VbVbalrConstants#1](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_1.vb)]  
  
 <span data-ttu-id="2fa03-107">При `Option Infer` — `On` или `Option Strict` — `Off`, можно объявить без указания типа данных с константой `As` предложение.</span><span class="sxs-lookup"><span data-stu-id="2fa03-107">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="2fa03-108">Компилятор определяет тип константы из типа выражения.</span><span class="sxs-lookup"><span data-stu-id="2fa03-108">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="2fa03-109">По умолчанию для приводится целочисленный литерал `Integer` тип данных.</span><span class="sxs-lookup"><span data-stu-id="2fa03-109">A numeric integer literal is cast by default to the `Integer` data type.</span></span> <span data-ttu-id="2fa03-110">Тип данных по умолчанию для чисел с плавающей запятой — `Double`и ключевые слова `True` и `False` укажите `Boolean` константы.</span><span class="sxs-lookup"><span data-stu-id="2fa03-110">The default data type for floating-point numbers is `Double`, and the keywords `True` and `False` specify a `Boolean` constant.</span></span>  
  
## <a name="literals-and-type-coercion"></a><span data-ttu-id="2fa03-111">Литералы и приведение типов</span><span class="sxs-lookup"><span data-stu-id="2fa03-111">Literals and Type Coercion</span></span>  
 <span data-ttu-id="2fa03-112">В некоторых случаях может потребоваться принудительно литерала к определенному типу данных; Например, при назначении особенно большой целочисленный литерал переменной типа `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="2fa03-112">In some cases, you might want to force a literal to a particular data type; for example, when assigning a particularly large integral literal value to a variable of type `Decimal`.</span></span> <span data-ttu-id="2fa03-113">Следующий пример приводит к ошибке:</span><span class="sxs-lookup"><span data-stu-id="2fa03-113">The following example produces an error:</span></span>  
  
```  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 <span data-ttu-id="2fa03-114">Эта ошибка возникает из представления литерала.</span><span class="sxs-lookup"><span data-stu-id="2fa03-114">The error results from the representation of the literal.</span></span> <span data-ttu-id="2fa03-115">`Decimal` Тип данных может содержать значение такого размера, но литерал неявно представлен как `Long`, какие нельзя.</span><span class="sxs-lookup"><span data-stu-id="2fa03-115">The `Decimal` data type can hold a value this large, but the literal is implicitly represented as a `Long`, which cannot.</span></span>  
  
 <span data-ttu-id="2fa03-116">Приведение литерала к определенному типу данных двумя способами: путем добавления к литералу символа типа, или путем помещения его в окружающие символы.</span><span class="sxs-lookup"><span data-stu-id="2fa03-116">You can coerce a literal to a particular data type in two ways: by appending a type character to it, or by placing it within enclosing characters.</span></span> <span data-ttu-id="2fa03-117">Символ типа или окружающие символы необходимо сразу же перед и/или выполните литерала, без промежуточных пробелов или символов любого типа.</span><span class="sxs-lookup"><span data-stu-id="2fa03-117">A type character or enclosing characters must immediately precede and/or follow the literal, with no intervening space or characters of any kind.</span></span>  
  
 <span data-ttu-id="2fa03-118">Чтобы предыдущий пример работал, можно добавить `D` знак в литерал, что приводит к его в виде типа `Decimal`:</span><span class="sxs-lookup"><span data-stu-id="2fa03-118">To make the previous example work, you can append the `D` type character to the literal, which causes it to be represented as a `Decimal`:</span></span>  
  
 [!code-vb[VbVbalrConstants#2](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_2.vb)]  
  
 <span data-ttu-id="2fa03-119">В следующем примере показано правильное использование символов типа и окружающих символов:</span><span class="sxs-lookup"><span data-stu-id="2fa03-119">The following example demonstrates correct usage of type characters and enclosing characters:</span></span>  
  
 [!code-vb[VbVbalrConstants#3](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_3.vb)]  
  
 <span data-ttu-id="2fa03-120">Показано в следующей таблице окружающие символы и символы типов, доступные в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2fa03-120">The following table shows the enclosing characters and type characters available in Visual Basic.</span></span>  
  
|<span data-ttu-id="2fa03-121">Тип данных</span><span class="sxs-lookup"><span data-stu-id="2fa03-121">Data type</span></span>|<span data-ttu-id="2fa03-122">Заключения символа</span><span class="sxs-lookup"><span data-stu-id="2fa03-122">Enclosing character</span></span>|<span data-ttu-id="2fa03-123">Добавленный символ типа</span><span class="sxs-lookup"><span data-stu-id="2fa03-123">Appended type character</span></span>|  
|---|---|---|  
|`Boolean`|<span data-ttu-id="2fa03-124">(нет)</span><span class="sxs-lookup"><span data-stu-id="2fa03-124">(none)</span></span>|<span data-ttu-id="2fa03-125">(нет)</span><span class="sxs-lookup"><span data-stu-id="2fa03-125">(none)</span></span>|  
|`Byte`|<span data-ttu-id="2fa03-126">(нет)</span><span class="sxs-lookup"><span data-stu-id="2fa03-126">(none)</span></span>|<span data-ttu-id="2fa03-127">(нет)</span><span class="sxs-lookup"><span data-stu-id="2fa03-127">(none)</span></span>|  
|`Char`|<span data-ttu-id="2fa03-128">"</span><span class="sxs-lookup"><span data-stu-id="2fa03-128">"</span></span>|<span data-ttu-id="2fa03-129">В</span><span class="sxs-lookup"><span data-stu-id="2fa03-129">C</span></span>|  
|`Date`|#|<span data-ttu-id="2fa03-130">(нет)</span><span class="sxs-lookup"><span data-stu-id="2fa03-130">(none)</span></span>|  
|`Decimal`|<span data-ttu-id="2fa03-131">(нет)</span><span class="sxs-lookup"><span data-stu-id="2fa03-131">(none)</span></span>|<span data-ttu-id="2fa03-132">D или @</span><span class="sxs-lookup"><span data-stu-id="2fa03-132">D or @</span></span>|  
|`Double`|<span data-ttu-id="2fa03-133">(нет)</span><span class="sxs-lookup"><span data-stu-id="2fa03-133">(none)</span></span>|<span data-ttu-id="2fa03-134">R или #</span><span class="sxs-lookup"><span data-stu-id="2fa03-134">R or #</span></span>|  
|`Integer`|<span data-ttu-id="2fa03-135">(нет)</span><span class="sxs-lookup"><span data-stu-id="2fa03-135">(none)</span></span>|<span data-ttu-id="2fa03-136">Я или %</span><span class="sxs-lookup"><span data-stu-id="2fa03-136">I or %</span></span>|  
|`Long`|<span data-ttu-id="2fa03-137">(нет)</span><span class="sxs-lookup"><span data-stu-id="2fa03-137">(none)</span></span>|<span data-ttu-id="2fa03-138">L или &</span><span class="sxs-lookup"><span data-stu-id="2fa03-138">L or &</span></span>|  
|`Short`|<span data-ttu-id="2fa03-139">(нет)</span><span class="sxs-lookup"><span data-stu-id="2fa03-139">(none)</span></span>|<span data-ttu-id="2fa03-140">S</span><span class="sxs-lookup"><span data-stu-id="2fa03-140">S</span></span>|  
|`Single`|<span data-ttu-id="2fa03-141">(нет)</span><span class="sxs-lookup"><span data-stu-id="2fa03-141">(none)</span></span>|<span data-ttu-id="2fa03-142">F или!</span><span class="sxs-lookup"><span data-stu-id="2fa03-142">F or !</span></span>|  
|`String`|<span data-ttu-id="2fa03-143">"</span><span class="sxs-lookup"><span data-stu-id="2fa03-143">"</span></span>|<span data-ttu-id="2fa03-144">(нет)</span><span class="sxs-lookup"><span data-stu-id="2fa03-144">(none)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2fa03-145">См. также</span><span class="sxs-lookup"><span data-stu-id="2fa03-145">See Also</span></span>  
 [<span data-ttu-id="2fa03-146">Константы, определенные пользователем</span><span class="sxs-lookup"><span data-stu-id="2fa03-146">User-Defined Constants</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)  
 [<span data-ttu-id="2fa03-147">Практическое руководство. Объявление константы</span><span class="sxs-lookup"><span data-stu-id="2fa03-147">How to: Declare A Constant</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)  
 [<span data-ttu-id="2fa03-148">Общие сведения о константах</span><span class="sxs-lookup"><span data-stu-id="2fa03-148">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [<span data-ttu-id="2fa03-149">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="2fa03-149">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="2fa03-150">Оператор Option Explicit</span><span class="sxs-lookup"><span data-stu-id="2fa03-150">Option Explicit Statement</span></span>](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [<span data-ttu-id="2fa03-151">Общие сведения о перечислениях</span><span class="sxs-lookup"><span data-stu-id="2fa03-151">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [<span data-ttu-id="2fa03-152">Практическое: объявление перечисления</span><span class="sxs-lookup"><span data-stu-id="2fa03-152">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [<span data-ttu-id="2fa03-153">Перечисления и уточнение имен</span><span class="sxs-lookup"><span data-stu-id="2fa03-153">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [<span data-ttu-id="2fa03-154">Типы данных</span><span class="sxs-lookup"><span data-stu-id="2fa03-154">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)  
 [<span data-ttu-id="2fa03-155">Константы и перечисления</span><span class="sxs-lookup"><span data-stu-id="2fa03-155">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
