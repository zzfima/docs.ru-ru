---
title: "Использование переменной итератора в лямбда-выражение может иметь непредвиденные результаты | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42324
- bc42324
dev_langs:
- VB
helpviewer_keywords:
- BC42324
ms.assetid: b5c2c4bd-3b2a-4a73-aaeb-55728eb03b68
caps.latest.revision: 8
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
ms.openlocfilehash: 1c2e0e322ff46b9e215a169cd4cf3805c7dc3943
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="using-the-iteration-variable-in-a-lambda-expression-may-have-unexpected-results"></a><span data-ttu-id="e1ea0-102">Использование переменной итератора в лямбда-выражении может привести к неожиданным результатам</span><span class="sxs-lookup"><span data-stu-id="e1ea0-102">Using the iteration variable in a lambda expression may have unexpected results</span></span>
<span data-ttu-id="e1ea0-103">Использование переменной итерации в лямбда-выражении может привести к непредусмотренным результатам.</span><span class="sxs-lookup"><span data-stu-id="e1ea0-103">Using the iteration variable in a lambda expression may have unexpected results.</span></span> <span data-ttu-id="e1ea0-104">Вместо этого создайте локальную переменную в цикле и присвойте ей значение переменной итерации.</span><span class="sxs-lookup"><span data-stu-id="e1ea0-104">Instead, create a local variable within the loop and assign it the value of the iteration variable.</span></span>  
  
 <span data-ttu-id="e1ea0-105">Это предупреждение появляется при использовании переменной итерации цикла в лямбда-выражение, объявленная внутри цикла.</span><span class="sxs-lookup"><span data-stu-id="e1ea0-105">This warning appears when you use a loop iteration variable in a lambda expression that is declared inside the loop.</span></span> <span data-ttu-id="e1ea0-106">Например приведенный ниже приводят к выводу предупреждения.</span><span class="sxs-lookup"><span data-stu-id="e1ea0-106">For example, the following example causes the warning to appear.</span></span>  
  
```vb  
For i As Integer = 1 To 10  
    ' The warning is given for the use of i.  
    Dim exampleFunc As Func(Of Integer) = Function() i  
Next  
```  
  
 <span data-ttu-id="e1ea0-107">В следующем примере показано непредвиденные результаты, которые могут возникнуть.</span><span class="sxs-lookup"><span data-stu-id="e1ea0-107">The following example shows the unexpected results that might occur.</span></span>  
  
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
  
 <span data-ttu-id="e1ea0-108">`For` Цикла создает массив лямбда-выражений, каждое из которых возвращает значение переменной итерации цикла `i`.</span><span class="sxs-lookup"><span data-stu-id="e1ea0-108">The `For` loop creates an array of lambda expressions, each of which returns the value of the loop iteration variable `i`.</span></span> <span data-ttu-id="e1ea0-109">Когда лямбда-выражения вычисляются в `For Each` цикла может ожидать появления 0, 1, 2, 3 и 4, последовательных значений `i` в `For` цикла.</span><span class="sxs-lookup"><span data-stu-id="e1ea0-109">When the lambda expressions are evaluated in the `For Each` loop, you might expect to see 0, 1, 2, 3, and 4 displayed, the successive values of `i` in the `For` loop.</span></span> <span data-ttu-id="e1ea0-110">Вместо этого, вы увидите итоговое значение `i` отображается пять раз:</span><span class="sxs-lookup"><span data-stu-id="e1ea0-110">Instead, you see the final value of `i` displayed five times:</span></span>  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 <span data-ttu-id="e1ea0-111">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="e1ea0-111">By default, this message is a warning.</span></span> <span data-ttu-id="e1ea0-112">Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [в Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="e1ea0-112">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="e1ea0-113">**Идентификатор ошибки:** BC42324</span><span class="sxs-lookup"><span data-stu-id="e1ea0-113">**Error ID:** BC42324</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e1ea0-114">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="e1ea0-114">To correct this error</span></span>  
  
-   <span data-ttu-id="e1ea0-115">Присвойте значение переменной итерации локальной переменной и используйте локальную переменную в лямбда-выражение.</span><span class="sxs-lookup"><span data-stu-id="e1ea0-115">Assign the value of the iteration variable to a local variable, and use the local variable in the lambda expression.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e1ea0-116">См. также</span><span class="sxs-lookup"><span data-stu-id="e1ea0-116">See Also</span></span>  
 [<span data-ttu-id="e1ea0-117">Лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="e1ea0-117">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
