---
title: Выведение типа Nullable не поддерживается в данном контексте
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 3ab8028062402e33b787a5a8649d93d975918393
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665705"
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a><span data-ttu-id="20925-102">Выведение типа Nullable не поддерживается в данном контексте</span><span class="sxs-lookup"><span data-stu-id="20925-102">Nullable type inference is not supported in this context</span></span>
<span data-ttu-id="20925-103">Типы значений и структуры могут объявляться допускает значения NULL.</span><span class="sxs-lookup"><span data-stu-id="20925-103">Value types and structures can be declared nullable.</span></span>  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 <span data-ttu-id="20925-104">Тем не менее нельзя использовать объявление nullable в сочетании с определением типа.</span><span class="sxs-lookup"><span data-stu-id="20925-104">However, you cannot use the nullable declaration in combination with type inference.</span></span> <span data-ttu-id="20925-105">Следующие примеры вызывать эту ошибку.</span><span class="sxs-lookup"><span data-stu-id="20925-105">The following examples cause this error.</span></span>  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 <span data-ttu-id="20925-106">**Идентификатор ошибки:** BC36629</span><span class="sxs-lookup"><span data-stu-id="20925-106">**Error ID:** BC36629</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="20925-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="20925-107">To correct this error</span></span>  
  
- <span data-ttu-id="20925-108">Используйте `As` предложение, чтобы объявить переменную как допускающие значение NULL.</span><span class="sxs-lookup"><span data-stu-id="20925-108">Use an `As` clause to declare the variable as nullable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20925-109">См. также</span><span class="sxs-lookup"><span data-stu-id="20925-109">See also</span></span>

- [<span data-ttu-id="20925-110">Типы значений, допускающие значение NULL</span><span class="sxs-lookup"><span data-stu-id="20925-110">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="20925-111">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="20925-111">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
