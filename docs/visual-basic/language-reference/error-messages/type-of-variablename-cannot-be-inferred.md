---
title: Тип <variablename> не может быть выведен, поскольку для границ цикла и переменной шага нет расширяющего преобразования к одному типу
ms.date: 07/20/2015
f1_keywords:
- bc30982
- vbc30982
helpviewer_keywords:
- BC30982
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
ms.openlocfilehash: e90e881546c12df2c8b19ff03a4d4c7304c4596c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58815879"
---
# <a name="type-of-variablename-cannot-be-inferred-because-the-loop-bounds-and-the-step-variable-do-not-widen-to-the-same-type"></a><span data-ttu-id="11bfe-102">Тип "\<имя_переменной >" не могут быть получены, так как границы цикла и переменной шага нет расширяющего преобразования к одному типу</span><span class="sxs-lookup"><span data-stu-id="11bfe-102">Type of '\<variablename>' cannot be inferred because the loop bounds and the step variable do not widen to the same type</span></span>
<span data-ttu-id="11bfe-103">Вы написали `For...Next` цикл, в котором компилятор не может вывести тип данных для управляющей переменной цикла, потому, что выполняются следующие условия:</span><span class="sxs-lookup"><span data-stu-id="11bfe-103">You have written a `For...Next` loop in which the compiler cannot infer a data type for the loop control variable because the following conditions are true:</span></span>  
  
-   <span data-ttu-id="11bfe-104">Тип данных управляющей переменной цикла не указан с помощью выражения `As` .</span><span class="sxs-lookup"><span data-stu-id="11bfe-104">The data type of the loop control variable is not specified with an `As` clause.</span></span>  
  
-   <span data-ttu-id="11bfe-105">Границы цикла и переменная шага содержат по крайней мере два типа данных.</span><span class="sxs-lookup"><span data-stu-id="11bfe-105">The loop bounds and step variable contain at least two data types.</span></span>  
  
-   <span data-ttu-id="11bfe-106">Нет стандартных преобразований между типами данных.</span><span class="sxs-lookup"><span data-stu-id="11bfe-106">No standard conversions exist between the data types.</span></span>  
  
 <span data-ttu-id="11bfe-107">Таким образом компилятор не может вывести тип данных управляющей переменной цикла.</span><span class="sxs-lookup"><span data-stu-id="11bfe-107">Therefore, the compiler cannot infer the data type of a loop's control variable.</span></span>  
  
 <span data-ttu-id="11bfe-108">В следующем примере переменной шага является символом и границы цикла — оба целые числа.</span><span class="sxs-lookup"><span data-stu-id="11bfe-108">In the following example, the step variable is a character and the loop bounds are both integers.</span></span> <span data-ttu-id="11bfe-109">Так как стандартные преобразования между символами и целых чисел, не существует, возникает следующая ошибка.</span><span class="sxs-lookup"><span data-stu-id="11bfe-109">Because there is no standard conversion between characters and integers, this error is reported.</span></span>  
  
```vb  
Dim stepVar = "1"c  
Dim m = 0  
Dim n = 20  
  
' Not valid.  
' For i = 1 To 10 Step stepVar  
    ' Loop processing  
' Next  
```  
  
 <span data-ttu-id="11bfe-110">**Идентификатор ошибки:** BC30982</span><span class="sxs-lookup"><span data-stu-id="11bfe-110">**Error ID:** BC30982</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="11bfe-111">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="11bfe-111">To correct this error</span></span>  
  
-   <span data-ttu-id="11bfe-112">Измените типы границ цикла и переменной шага, чтобы по крайней мере один из них — это тип, остальные расширяющего преобразования к.</span><span class="sxs-lookup"><span data-stu-id="11bfe-112">Change the types of the loop bounds and step variable as necessary so that at least one of them is a type that the others widen to.</span></span> <span data-ttu-id="11bfe-113">В предыдущем примере, измените тип `stepVar` для `Integer`.</span><span class="sxs-lookup"><span data-stu-id="11bfe-113">In the preceding example, change the type of `stepVar` to `Integer`.</span></span>  
  
    ```  
    Dim stepVar = 1  
    ```  
  
     <span data-ttu-id="11bfe-114">—или—</span><span class="sxs-lookup"><span data-stu-id="11bfe-114">—or—</span></span>  
  
    ```  
    Dim stepVar As Integer = 1  
    ```  
  
-   <span data-ttu-id="11bfe-115">Используйте функции явного преобразования для преобразования границ цикла и переменной шага в соответствующие типы.</span><span class="sxs-lookup"><span data-stu-id="11bfe-115">Use explicit conversion functions to convert the loop bounds and step variable to the appropriate types.</span></span> <span data-ttu-id="11bfe-116">В приведенном выше примере применяются `Val` функция `stepVar`.</span><span class="sxs-lookup"><span data-stu-id="11bfe-116">In the preceding example, apply the `Val` function to `stepVar`.</span></span>  
  
    ```  
    For i = 1 To 10 Step Val(stepVar)  
        ' Loop processing  
    Next  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="11bfe-117">См. также</span><span class="sxs-lookup"><span data-stu-id="11bfe-117">See also</span></span>

- <xref:Microsoft.VisualBasic.Conversion.Val%2A>
- [<span data-ttu-id="11bfe-118">Оператор For...Next</span><span class="sxs-lookup"><span data-stu-id="11bfe-118">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="11bfe-119">Явные и неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="11bfe-119">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="11bfe-120">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="11bfe-120">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="11bfe-121">Оператор Option Infer</span><span class="sxs-lookup"><span data-stu-id="11bfe-121">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="11bfe-122">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="11bfe-122">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="11bfe-123">Расширяющие и сужающие преобразования</span><span class="sxs-lookup"><span data-stu-id="11bfe-123">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
