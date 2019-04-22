---
title: Использование переменной итератора в лямбда-выражении может привести к неожиданным результатам
ms.date: 07/20/2015
f1_keywords:
- vbc42324
- bc42324
helpviewer_keywords:
- BC42324
ms.assetid: b5c2c4bd-3b2a-4a73-aaeb-55728eb03b68
ms.openlocfilehash: 618fc88a2ca92ec911a3fbd82de580403d924430
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58841104"
---
# <a name="using-the-iteration-variable-in-a-lambda-expression-may-have-unexpected-results"></a><span data-ttu-id="e10e2-102">Использование переменной итератора в лямбда-выражении может привести к неожиданным результатам</span><span class="sxs-lookup"><span data-stu-id="e10e2-102">Using the iteration variable in a lambda expression may have unexpected results</span></span>
<span data-ttu-id="e10e2-103">Использование переменной итерации в лямбда-выражение может иметь непредвиденные результаты.</span><span class="sxs-lookup"><span data-stu-id="e10e2-103">Using the iteration variable in a lambda expression may have unexpected results.</span></span> <span data-ttu-id="e10e2-104">Вместо этого создайте локальную переменную в цикле и присвойте ей значение переменной итерации.</span><span class="sxs-lookup"><span data-stu-id="e10e2-104">Instead, create a local variable within the loop and assign it the value of the iteration variable.</span></span>  
  
 <span data-ttu-id="e10e2-105">Это предупреждение появляется при использовании переменной итерации цикла, объявленная внутри цикла лямбда-выражение.</span><span class="sxs-lookup"><span data-stu-id="e10e2-105">This warning appears when you use a loop iteration variable in a lambda expression that is declared inside the loop.</span></span> <span data-ttu-id="e10e2-106">Например следующий пример вызывает предупреждение выводится.</span><span class="sxs-lookup"><span data-stu-id="e10e2-106">For example, the following example causes the warning to appear.</span></span>  
  
```vb  
For i As Integer = 1 To 10  
    ' The warning is given for the use of i.  
    Dim exampleFunc As Func(Of Integer) = Function() i  
Next  
```  
  
 <span data-ttu-id="e10e2-107">В следующем примере непредвиденные результаты, которые могут возникнуть.</span><span class="sxs-lookup"><span data-stu-id="e10e2-107">The following example shows the unexpected results that might occur.</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        Dim array1 As Func(Of Integer)() = New Func(Of Integer)(4) {}  
  
        For i As Integer = 0 To 4  
            array1(i) = Function() i  
        Next  
  
        For Each funcElement In array1  
            System.Console.WriteLine(funcElement())  
        Next  
  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="e10e2-108">`For` Создает массив лямбда-выражений, каждый из которых возвращает значение переменной итерации цикла, цикл `i`.</span><span class="sxs-lookup"><span data-stu-id="e10e2-108">The `For` loop creates an array of lambda expressions, each of which returns the value of the loop iteration variable `i`.</span></span> <span data-ttu-id="e10e2-109">При вычислении лямбда-выражения в `For Each` цикл, могут ожидать см. в разделе 0, 1, 2, 3 и 4, последовательных значений `i` в `For` цикла.</span><span class="sxs-lookup"><span data-stu-id="e10e2-109">When the lambda expressions are evaluated in the `For Each` loop, you might expect to see 0, 1, 2, 3, and 4 displayed, the successive values of `i` in the `For` loop.</span></span> <span data-ttu-id="e10e2-110">Вместо этого отображается конечное значение `i` отображаются пять раз:</span><span class="sxs-lookup"><span data-stu-id="e10e2-110">Instead, you see the final value of `i` displayed five times:</span></span>  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 <span data-ttu-id="e10e2-111">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="e10e2-111">By default, this message is a warning.</span></span> <span data-ttu-id="e10e2-112">Дополнительные сведения о сокрытии предупреждений и обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="e10e2-112">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="e10e2-113">**Идентификатор ошибки:** BC42324</span><span class="sxs-lookup"><span data-stu-id="e10e2-113">**Error ID:** BC42324</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e10e2-114">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="e10e2-114">To correct this error</span></span>  
  
-   <span data-ttu-id="e10e2-115">Назначьте переменной итерации в локальной переменной и используйте локальную переменную в лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="e10e2-115">Assign the value of the iteration variable to a local variable, and use the local variable in the lambda expression.</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        Dim array1 As Func(Of Integer)() = New Func(Of Integer)(4) {}  
  
        For i As Integer = 0 To 4  
            Dim j = i  
            array1(i) = Function() j  
        Next  
  
        For Each funcElement In array1  
            System.Console.WriteLine(funcElement())  
        Next  
  
    End Sub  
End Module  
```  
  
## <a name="see-also"></a><span data-ttu-id="e10e2-116">См. также</span><span class="sxs-lookup"><span data-stu-id="e10e2-116">See also</span></span>

- [<span data-ttu-id="e10e2-117">Лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="e10e2-117">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
