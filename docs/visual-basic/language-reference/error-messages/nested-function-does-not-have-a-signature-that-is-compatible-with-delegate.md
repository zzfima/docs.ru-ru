---
title: Вложенная функция не имеет сигнатуры, совместимой с делегатом '<delegatename>'
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: 912962e2ab39c4811294ccc225814b230100e12a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64591999"
---
# <a name="nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-delegatename"></a><span data-ttu-id="60437-102">Вложенная функция не имеет сигнатуры, совместимой с делегатом '\<имя_делегата >'</span><span class="sxs-lookup"><span data-stu-id="60437-102">Nested function does not have a signature that is compatible with delegate '\<delegatename>'</span></span>
<span data-ttu-id="60437-103">Лямбда-выражение, явно назначенной делегат, который имеет несовместимую сигнатуру.</span><span class="sxs-lookup"><span data-stu-id="60437-103">A lambda expression has been assigned to a delegate that has an incompatible signature.</span></span> <span data-ttu-id="60437-104">Например, в следующем коде, делегировать `Del` имеет два целочисленных параметра.</span><span class="sxs-lookup"><span data-stu-id="60437-104">For example, in the following code, delegate `Del` has two integer parameters.</span></span>  
  
```vb  
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer  
```  
  
 <span data-ttu-id="60437-105">Ошибка возникает, если лямбда-выражение с одним аргументом объявлен как тип `Del`:</span><span class="sxs-lookup"><span data-stu-id="60437-105">The error is raised if a lambda expression with one argument is declared as type `Del`:</span></span>  
  
```vb  
' Neither of these is valid.   
' Dim lambda1 As Del = Function(n As Integer) n + 1  
' Dim lambda2 As Del = Function(n) n + 1  
```  
  
 <span data-ttu-id="60437-106">**Идентификатор ошибки:** BC36532</span><span class="sxs-lookup"><span data-stu-id="60437-106">**Error ID:** BC36532</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="60437-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="60437-107">To correct this error</span></span>  
  
- <span data-ttu-id="60437-108">Измените определения делегата или назначенного лямбда-выражения, таким образом, чтобы сигнатуры были совместимы.</span><span class="sxs-lookup"><span data-stu-id="60437-108">Adjust either the delegate definition or the assigned lambda expression so that the signatures are compatible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60437-109">См. также</span><span class="sxs-lookup"><span data-stu-id="60437-109">See also</span></span>

- [<span data-ttu-id="60437-110">Неявное преобразование делегата</span><span class="sxs-lookup"><span data-stu-id="60437-110">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [<span data-ttu-id="60437-111">Лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="60437-111">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
