---
title: Выведение типа Nullable не поддерживается в данном контексте
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 42bde0b1843e52bbc16118bb056ade791591904e
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249504"
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a><span data-ttu-id="9c218-102">Выведение типа Nullable не поддерживается в данном контексте</span><span class="sxs-lookup"><span data-stu-id="9c218-102">Nullable type inference is not supported in this context</span></span>
<span data-ttu-id="9c218-103">Типы значений и структуры могут быть признаны недействительными.</span><span class="sxs-lookup"><span data-stu-id="9c218-103">Value types and structures can be declared nullable.</span></span>  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 <span data-ttu-id="9c218-104">Однако вы не можете использовать необдательную декларацию в сочетании с выводом типа.</span><span class="sxs-lookup"><span data-stu-id="9c218-104">However, you cannot use the nullable declaration in combination with type inference.</span></span> <span data-ttu-id="9c218-105">Следующие примеры вызывают эту ошибку.</span><span class="sxs-lookup"><span data-stu-id="9c218-105">The following examples cause this error.</span></span>  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 <span data-ttu-id="9c218-106">**Идентификатор ошибки:** BC36629</span><span class="sxs-lookup"><span data-stu-id="9c218-106">**Error ID:** BC36629</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9c218-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="9c218-107">To correct this error</span></span>  
  
- <span data-ttu-id="9c218-108">Используйте `As` оговорку, чтобы объявить переменную в качестве необобнажаемого типа значения.</span><span class="sxs-lookup"><span data-stu-id="9c218-108">Use an `As` clause to declare the variable as a nullable value type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c218-109">См. также</span><span class="sxs-lookup"><span data-stu-id="9c218-109">See also</span></span>

- [<span data-ttu-id="9c218-110">Типы значений, допускающие значение NULL</span><span class="sxs-lookup"><span data-stu-id="9c218-110">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="9c218-111">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="9c218-111">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
