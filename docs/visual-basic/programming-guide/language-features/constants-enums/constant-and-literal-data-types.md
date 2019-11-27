---
title: Типы данных констант и литералов
ms.date: 07/20/2015
helpviewer_keywords:
- declaring constants [Visual Basic], literal data types
- data types [Visual Basic], declaring
- constants [Visual Basic], declaring
- explicit declarations
- literals [Visual Basic], coercing data type
- declarations [Visual Basic], data types
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
ms.openlocfilehash: 8ebecddfab0724023c269e92c1fc5534f096bf1c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333731"
---
# <a name="constant-and-literal-data-types-visual-basic"></a><span data-ttu-id="8bbee-102">Типы данных констант и литералов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8bbee-102">Constant and Literal Data Types (Visual Basic)</span></span>
<span data-ttu-id="8bbee-103">Литерал — это значение, которое выражено как само по себе, а не как значение переменной или результат выражения, например число 3 или строка "Hello".</span><span class="sxs-lookup"><span data-stu-id="8bbee-103">A literal is a value that is expressed as itself rather than as a variable's value or the result of an expression, such as the number 3 or the string "Hello".</span></span> <span data-ttu-id="8bbee-104">Константа — это понятное имя, которое принимает место литерала и сохраняется в программе в отличие от переменной, значение которой может измениться.</span><span class="sxs-lookup"><span data-stu-id="8bbee-104">A constant is a meaningful name that takes the place of a literal and retains this same value throughout the program, as opposed to a variable, whose value may change.</span></span>  
  
 <span data-ttu-id="8bbee-105">Если [параметр Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) имеет значение `Off` и [Option строго](../../../../visual-basic/language-reference/statements/option-strict-statement.md) `On`, необходимо явно объявить все константы с типом данных.</span><span class="sxs-lookup"><span data-stu-id="8bbee-105">When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare all constants explicitly with a data type.</span></span> <span data-ttu-id="8bbee-106">В следующем примере тип данных `MyByte` явно объявлен как тип данных `Byte`:</span><span class="sxs-lookup"><span data-stu-id="8bbee-106">In the following example, the data type of `MyByte` is explicitly declared as data type `Byte`:</span></span>  
  
 [!code-vb[VbVbalrConstants#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#1)]  
  
 <span data-ttu-id="8bbee-107">Если `Option Infer` имеет `On` или `Option Strict` `Off`, можно объявить константу без указания типа данных с помощью предложения `As`.</span><span class="sxs-lookup"><span data-stu-id="8bbee-107">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="8bbee-108">Компилятор определяет тип константы на основе типа выражения.</span><span class="sxs-lookup"><span data-stu-id="8bbee-108">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="8bbee-109">Числовой целочисленный литерал по умолчанию приводится к типу данных `Integer`.</span><span class="sxs-lookup"><span data-stu-id="8bbee-109">A numeric integer literal is cast by default to the `Integer` data type.</span></span> <span data-ttu-id="8bbee-110">Типом данных по умолчанию для чисел с плавающей запятой является `Double`, а ключевые слова `True` и `False` указать константу `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="8bbee-110">The default data type for floating-point numbers is `Double`, and the keywords `True` and `False` specify a `Boolean` constant.</span></span>  
  
## <a name="literals-and-type-coercion"></a><span data-ttu-id="8bbee-111">Литералы и приведение типов</span><span class="sxs-lookup"><span data-stu-id="8bbee-111">Literals and Type Coercion</span></span>  
 <span data-ttu-id="8bbee-112">В некоторых случаях может потребоваться принудительно применить литерал к конкретному типу данных. Например, при присваивании особо большого целочисленного значения литерала переменной типа `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="8bbee-112">In some cases, you might want to force a literal to a particular data type; for example, when assigning a particularly large integral literal value to a variable of type `Decimal`.</span></span> <span data-ttu-id="8bbee-113">Следующий пример приводит к ошибке:</span><span class="sxs-lookup"><span data-stu-id="8bbee-113">The following example produces an error:</span></span>  
  
```vb  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 <span data-ttu-id="8bbee-114">Эта ошибка возникает из представления литерала.</span><span class="sxs-lookup"><span data-stu-id="8bbee-114">The error results from the representation of the literal.</span></span> <span data-ttu-id="8bbee-115">Тип данных `Decimal` может содержать это большое значение, но литерал неявно представляется как `Long`, что не может.</span><span class="sxs-lookup"><span data-stu-id="8bbee-115">The `Decimal` data type can hold a value this large, but the literal is implicitly represented as a `Long`, which cannot.</span></span>  
  
 <span data-ttu-id="8bbee-116">Можно привести литерал к определенному типу данных двумя способами: путем добавления к нему символа типа или путем помещения его в окружающие символы.</span><span class="sxs-lookup"><span data-stu-id="8bbee-116">You can coerce a literal to a particular data type in two ways: by appending a type character to it, or by placing it within enclosing characters.</span></span> <span data-ttu-id="8bbee-117">Символ типа или заключенные в него символы должны находиться непосредственно перед и/или следовать за литералом без промежуточного пробела или символов какого-либо типа.</span><span class="sxs-lookup"><span data-stu-id="8bbee-117">A type character or enclosing characters must immediately precede and/or follow the literal, with no intervening space or characters of any kind.</span></span>  
  
 <span data-ttu-id="8bbee-118">Чтобы предыдущий пример работал, можно добавить к литералу символ типа `D`, что приводит к его представлению в виде `Decimal`:</span><span class="sxs-lookup"><span data-stu-id="8bbee-118">To make the previous example work, you can append the `D` type character to the literal, which causes it to be represented as a `Decimal`:</span></span>  
  
 [!code-vb[VbVbalrConstants#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#2)]  
  
 <span data-ttu-id="8bbee-119">В следующем примере показано правильное использование символов типа и окружающих символов:</span><span class="sxs-lookup"><span data-stu-id="8bbee-119">The following example demonstrates correct usage of type characters and enclosing characters:</span></span>  
  
 [!code-vb[VbVbalrConstants#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#3)]  
  
 <span data-ttu-id="8bbee-120">В следующей таблице показаны окружающие символы и символы типа, доступные в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8bbee-120">The following table shows the enclosing characters and type characters available in Visual Basic.</span></span>  
  
|<span data-ttu-id="8bbee-121">Тип данных</span><span class="sxs-lookup"><span data-stu-id="8bbee-121">Data type</span></span>|<span data-ttu-id="8bbee-122">Вложенный символ</span><span class="sxs-lookup"><span data-stu-id="8bbee-122">Enclosing character</span></span>|<span data-ttu-id="8bbee-123">Символ добавленного типа</span><span class="sxs-lookup"><span data-stu-id="8bbee-123">Appended type character</span></span>|  
|---|---|---|  
|`Boolean`|<span data-ttu-id="8bbee-124">(нет)</span><span class="sxs-lookup"><span data-stu-id="8bbee-124">(none)</span></span>|<span data-ttu-id="8bbee-125">(нет)</span><span class="sxs-lookup"><span data-stu-id="8bbee-125">(none)</span></span>|  
|`Byte`|<span data-ttu-id="8bbee-126">(нет)</span><span class="sxs-lookup"><span data-stu-id="8bbee-126">(none)</span></span>|<span data-ttu-id="8bbee-127">(нет)</span><span class="sxs-lookup"><span data-stu-id="8bbee-127">(none)</span></span>|  
|`Char`|<span data-ttu-id="8bbee-128">"</span><span class="sxs-lookup"><span data-stu-id="8bbee-128">"</span></span>|<span data-ttu-id="8bbee-129">C</span><span class="sxs-lookup"><span data-stu-id="8bbee-129">C</span></span>|  
|`Date`|#|<span data-ttu-id="8bbee-130">(нет)</span><span class="sxs-lookup"><span data-stu-id="8bbee-130">(none)</span></span>|  
|`Decimal`|<span data-ttu-id="8bbee-131">(нет)</span><span class="sxs-lookup"><span data-stu-id="8bbee-131">(none)</span></span>|<span data-ttu-id="8bbee-132">D или @</span><span class="sxs-lookup"><span data-stu-id="8bbee-132">D or @</span></span>|  
|`Double`|<span data-ttu-id="8bbee-133">(нет)</span><span class="sxs-lookup"><span data-stu-id="8bbee-133">(none)</span></span>|<span data-ttu-id="8bbee-134">R или #</span><span class="sxs-lookup"><span data-stu-id="8bbee-134">R or #</span></span>|  
|`Integer`|<span data-ttu-id="8bbee-135">(нет)</span><span class="sxs-lookup"><span data-stu-id="8bbee-135">(none)</span></span>|<span data-ttu-id="8bbee-136">I или%</span><span class="sxs-lookup"><span data-stu-id="8bbee-136">I or %</span></span>|  
|`Long`|<span data-ttu-id="8bbee-137">(нет)</span><span class="sxs-lookup"><span data-stu-id="8bbee-137">(none)</span></span>|<span data-ttu-id="8bbee-138">L или &</span><span class="sxs-lookup"><span data-stu-id="8bbee-138">L or &</span></span>|  
|`Short`|<span data-ttu-id="8bbee-139">(нет)</span><span class="sxs-lookup"><span data-stu-id="8bbee-139">(none)</span></span>|<span data-ttu-id="8bbee-140">S</span><span class="sxs-lookup"><span data-stu-id="8bbee-140">S</span></span>|  
|`Single`|<span data-ttu-id="8bbee-141">(нет)</span><span class="sxs-lookup"><span data-stu-id="8bbee-141">(none)</span></span>|<span data-ttu-id="8bbee-142">F или!</span><span class="sxs-lookup"><span data-stu-id="8bbee-142">F or !</span></span>|  
|`String`|<span data-ttu-id="8bbee-143">"</span><span class="sxs-lookup"><span data-stu-id="8bbee-143">"</span></span>|<span data-ttu-id="8bbee-144">(нет)</span><span class="sxs-lookup"><span data-stu-id="8bbee-144">(none)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8bbee-145">См. также</span><span class="sxs-lookup"><span data-stu-id="8bbee-145">See also</span></span>

- [<span data-ttu-id="8bbee-146">Константы, определенные пользователем</span><span class="sxs-lookup"><span data-stu-id="8bbee-146">User-Defined Constants</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)
- [<span data-ttu-id="8bbee-147">Практическое руководство. Объявление константы</span><span class="sxs-lookup"><span data-stu-id="8bbee-147">How to: Declare A Constant</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)
- [<span data-ttu-id="8bbee-148">Общие сведения о константах</span><span class="sxs-lookup"><span data-stu-id="8bbee-148">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [<span data-ttu-id="8bbee-149">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="8bbee-149">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="8bbee-150">Оператор Option Explicit</span><span class="sxs-lookup"><span data-stu-id="8bbee-150">Option Explicit Statement</span></span>](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="8bbee-151">Общие сведения о перечислениях</span><span class="sxs-lookup"><span data-stu-id="8bbee-151">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [<span data-ttu-id="8bbee-152">Инструкции. Объявление перечисления</span><span class="sxs-lookup"><span data-stu-id="8bbee-152">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="8bbee-153">Перечисления и уточнение имен</span><span class="sxs-lookup"><span data-stu-id="8bbee-153">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="8bbee-154">Типы данных</span><span class="sxs-lookup"><span data-stu-id="8bbee-154">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="8bbee-155">Константы и перечисления</span><span class="sxs-lookup"><span data-stu-id="8bbee-155">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
