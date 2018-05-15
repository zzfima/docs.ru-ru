---
title: Вложенная функция не имеет сигнатуры, совместимой с делегатом &#39; &lt;имя_делегата&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: 94c53d30ad9aea9386fbb1be3e65fa31719f7a2f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-39ltdelegatenamegt39"></a><span data-ttu-id="124f9-102">Вложенная функция не имеет сигнатуры, совместимой с делегатом &#39; &lt;имя_делегата&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="124f9-102">Nested function does not have a signature that is compatible with delegate &#39;&lt;delegatename&gt;&#39;</span></span>
<span data-ttu-id="124f9-103">Лямбда-выражение для делегата, имеющего несовместимая сигнатура назначено.</span><span class="sxs-lookup"><span data-stu-id="124f9-103">A lambda expression has been assigned to a delegate that has an incompatible signature.</span></span> <span data-ttu-id="124f9-104">Например, в следующем коде делегат `Del` имеет два параметра целого типа.</span><span class="sxs-lookup"><span data-stu-id="124f9-104">For example, in the following code, delegate `Del` has two integer parameters.</span></span>  
  
```vb  
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer  
```  
  
 <span data-ttu-id="124f9-105">Эта ошибка возникает, если лямбда-выражение с одним аргументом объявляется как тип `Del`:</span><span class="sxs-lookup"><span data-stu-id="124f9-105">The error is raised if a lambda expression with one argument is declared as type `Del`:</span></span>  
  
```vb  
' Neither of these is valid.   
' Dim lambda1 As Del = Function(n As Integer) n + 1  
' Dim lambda2 As Del = Function(n) n + 1  
```  
  
 <span data-ttu-id="124f9-106">**Идентификатор ошибки:** BC36532</span><span class="sxs-lookup"><span data-stu-id="124f9-106">**Error ID:** BC36532</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="124f9-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="124f9-107">To correct this error</span></span>  
  
-   <span data-ttu-id="124f9-108">Измените определение делегата или назначенного лямбда-выражения, чтобы сигнатуры были совместимы.</span><span class="sxs-lookup"><span data-stu-id="124f9-108">Adjust either the delegate definition or the assigned lambda expression so that the signatures are compatible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="124f9-109">См. также</span><span class="sxs-lookup"><span data-stu-id="124f9-109">See Also</span></span>  
 [<span data-ttu-id="124f9-110">Неявное преобразование делегата</span><span class="sxs-lookup"><span data-stu-id="124f9-110">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)  
 [<span data-ttu-id="124f9-111">Лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="124f9-111">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
