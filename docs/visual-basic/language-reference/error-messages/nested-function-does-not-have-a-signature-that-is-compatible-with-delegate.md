---
title: Вложенная функция не имеет сигнатуры, совместимой с делегатом &#39; &lt;имя_делегата&gt;&#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
caps.latest.revision: 5
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 60cf15343023110561da3e3fcf202bd00394127a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-39ltdelegatenamegt39"></a><span data-ttu-id="5f37f-102">Вложенная функция не имеет сигнатуры, совместимой с делегатом &#39; &lt;имя_делегата&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="5f37f-102">Nested function does not have a signature that is compatible with delegate &#39;&lt;delegatename&gt;&#39;</span></span>
<span data-ttu-id="5f37f-103">Лямбда-выражение для делегата, имеющего несовместимая сигнатура назначено.</span><span class="sxs-lookup"><span data-stu-id="5f37f-103">A lambda expression has been assigned to a delegate that has an incompatible signature.</span></span> <span data-ttu-id="5f37f-104">Например, в следующем коде делегат `Del` имеет два параметра целого типа.</span><span class="sxs-lookup"><span data-stu-id="5f37f-104">For example, in the following code, delegate `Del` has two integer parameters.</span></span>  
  
```vb  
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer  
```  
  
 <span data-ttu-id="5f37f-105">Эта ошибка возникает, если лямбда-выражение с одним аргументом объявляется как тип `Del`:</span><span class="sxs-lookup"><span data-stu-id="5f37f-105">The error is raised if a lambda expression with one argument is declared as type `Del`:</span></span>  
  
```vb  
' Neither of these is valid.   
' Dim lambda1 As Del = Function(n As Integer) n + 1  
' Dim lambda2 As Del = Function(n) n + 1  
```  
  
 <span data-ttu-id="5f37f-106">**Идентификатор ошибки:** BC36532</span><span class="sxs-lookup"><span data-stu-id="5f37f-106">**Error ID:** BC36532</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5f37f-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="5f37f-107">To correct this error</span></span>  
  
-   <span data-ttu-id="5f37f-108">Измените определение делегата или назначенного лямбда-выражения, чтобы сигнатуры были совместимы.</span><span class="sxs-lookup"><span data-stu-id="5f37f-108">Adjust either the delegate definition or the assigned lambda expression so that the signatures are compatible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f37f-109">См. также</span><span class="sxs-lookup"><span data-stu-id="5f37f-109">See Also</span></span>  
 [<span data-ttu-id="5f37f-110">Неявное преобразование делегата</span><span class="sxs-lookup"><span data-stu-id="5f37f-110">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)  
 [<span data-ttu-id="5f37f-111">Лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="5f37f-111">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
