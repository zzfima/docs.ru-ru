---
title: Тип <variablename> не может быть выведен, поскольку для границ цикла и переменной шага нет расширяющего преобразования к одному типу
ms.date: 07/20/2015
f1_keywords:
- bc30982
- vbc30982
helpviewer_keywords:
- BC30982
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
ms.openlocfilehash: c3086f79fb71693810bc8f14e8c0f493aa1e6515
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512710"
---
# <a name="type-of-variablename-cannot-be-inferred-because-the-loop-bounds-and-the-step-variable-do-not-widen-to-the-same-type"></a><span data-ttu-id="1d6b7-102">Тип "\<variablename >" не может быть определен, так как границы цикла и переменная шага не расширяются до того же типа.</span><span class="sxs-lookup"><span data-stu-id="1d6b7-102">Type of '\<variablename>' cannot be inferred because the loop bounds and the step variable do not widen to the same type</span></span>

<span data-ttu-id="1d6b7-103">Вы написали `For...Next` цикл, в котором компилятор не может определить тип данных для управляющей переменной цикла, так как выполняются следующие условия.</span><span class="sxs-lookup"><span data-stu-id="1d6b7-103">You have written a `For...Next` loop in which the compiler cannot infer a data type for the loop control variable because the following conditions are true:</span></span>

- <span data-ttu-id="1d6b7-104">Тип данных управляющей переменной цикла не указан с помощью выражения `As` .</span><span class="sxs-lookup"><span data-stu-id="1d6b7-104">The data type of the loop control variable is not specified with an `As` clause.</span></span>

- <span data-ttu-id="1d6b7-105">Границы цикла и переменная шага содержат по крайней мере два типа данных.</span><span class="sxs-lookup"><span data-stu-id="1d6b7-105">The loop bounds and step variable contain at least two data types.</span></span>

- <span data-ttu-id="1d6b7-106">Между типами данных не существует стандартных преобразований.</span><span class="sxs-lookup"><span data-stu-id="1d6b7-106">No standard conversions exist between the data types.</span></span>

 <span data-ttu-id="1d6b7-107">Таким образом, компилятор не может определить тип данных управляющей переменной цикла.</span><span class="sxs-lookup"><span data-stu-id="1d6b7-107">Therefore, the compiler cannot infer the data type of a loop's control variable.</span></span>

 <span data-ttu-id="1d6b7-108">В следующем примере переменная шага является символом, а границы цикла — обоими целыми числами.</span><span class="sxs-lookup"><span data-stu-id="1d6b7-108">In the following example, the step variable is a character and the loop bounds are both integers.</span></span> <span data-ttu-id="1d6b7-109">Так как нет стандартного преобразования между символами и целыми числами, возникает эта ошибка.</span><span class="sxs-lookup"><span data-stu-id="1d6b7-109">Because there is no standard conversion between characters and integers, this error is reported.</span></span>

```vb
Dim stepVar = "1"c
Dim m = 0
Dim n = 20

' Not valid.
' For i = 1 To 10 Step stepVar
    ' Loop processing
' Next
```

<span data-ttu-id="1d6b7-110">**Идентификатор ошибки:** BC30982</span><span class="sxs-lookup"><span data-stu-id="1d6b7-110">**Error ID:** BC30982</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="1d6b7-111">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="1d6b7-111">To correct this error</span></span>

- <span data-ttu-id="1d6b7-112">При необходимости измените типы границ цикла и переменной шага, чтобы по крайней мере один из них был типом, расширяющимся в.</span><span class="sxs-lookup"><span data-stu-id="1d6b7-112">Change the types of the loop bounds and step variable as necessary so that at least one of them is a type that the others widen to.</span></span> <span data-ttu-id="1d6b7-113">В предыдущем примере измените тип `stepVar` на. `Integer`</span><span class="sxs-lookup"><span data-stu-id="1d6b7-113">In the preceding example, change the type of `stepVar` to `Integer`.</span></span>

  ```vb
  Dim stepVar = 1
  ```

  <span data-ttu-id="1d6b7-114">-или-</span><span class="sxs-lookup"><span data-stu-id="1d6b7-114">-or-</span></span>

  ```vb
  Dim stepVar As Integer = 1
  ```

- <span data-ttu-id="1d6b7-115">Используйте явные функции преобразования для преобразования границ цикла и переменной Step в соответствующие типы.</span><span class="sxs-lookup"><span data-stu-id="1d6b7-115">Use explicit conversion functions to convert the loop bounds and step variable to the appropriate types.</span></span> <span data-ttu-id="1d6b7-116">В предыдущем примере примените `Val` функцию к. `stepVar`</span><span class="sxs-lookup"><span data-stu-id="1d6b7-116">In the preceding example, apply the `Val` function to `stepVar`.</span></span>

  ```vb
  For i = 1 To 10 Step Val(stepVar)
      ' Loop processing
  Next
  ```

## <a name="see-also"></a><span data-ttu-id="1d6b7-117">См. также</span><span class="sxs-lookup"><span data-stu-id="1d6b7-117">See also</span></span>

- <xref:Microsoft.VisualBasic.Conversion.Val%2A>
- [<span data-ttu-id="1d6b7-118">Оператор For...Next</span><span class="sxs-lookup"><span data-stu-id="1d6b7-118">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="1d6b7-119">Явные и неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="1d6b7-119">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="1d6b7-120">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="1d6b7-120">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="1d6b7-121">Оператор Option Infer</span><span class="sxs-lookup"><span data-stu-id="1d6b7-121">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="1d6b7-122">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="1d6b7-122">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="1d6b7-123">Расширяющие и сужающие преобразования</span><span class="sxs-lookup"><span data-stu-id="1d6b7-123">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
