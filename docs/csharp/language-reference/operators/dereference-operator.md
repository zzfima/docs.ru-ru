---
title: Оператор -&gt; (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- ->_CSharpKeyword
helpviewer_keywords:
- member access operator (->) [C#]
- -> operator [C#]
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
ms.openlocfilehash: fb95e508ce1339868723bcc3178851e8c1355c1f
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44271251"
---
# <a name="-gt-operator-c-reference"></a><span data-ttu-id="a2ce7-102">Оператор -&gt; (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="a2ce7-102">-&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="a2ce7-103">Оператор `->` объединяет операции разыменования указателя и доступа к члену.</span><span class="sxs-lookup"><span data-stu-id="a2ce7-103">The `->` operator combines pointer dereferencing and member access.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2ce7-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="a2ce7-104">Remarks</span></span>  
 <span data-ttu-id="a2ce7-105">Выражение в формате</span><span class="sxs-lookup"><span data-stu-id="a2ce7-105">An expression of the form,</span></span>  
  
```csharp  
x->y  
```  
  
 <span data-ttu-id="a2ce7-106">(где `x` — это указатель типа `T*` и `y` — это член `T`) эквивалентно</span><span class="sxs-lookup"><span data-stu-id="a2ce7-106">(where `x` is a pointer of type `T*` and `y` is a member of `T`) is equivalent to,</span></span>  
  
```csharp  
(*x).y  
```  
  
 <span data-ttu-id="a2ce7-107">Оператор `->` можно использовать только в коде, который помечен как [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="a2ce7-107">The `->` operator can be used only in code that is marked as [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span></span>  
  
 <span data-ttu-id="a2ce7-108">Оператор `->` перегрузить нельзя.</span><span class="sxs-lookup"><span data-stu-id="a2ce7-108">The `->` operator cannot be overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2ce7-109">Пример</span><span class="sxs-lookup"><span data-stu-id="a2ce7-109">Example</span></span>  
 [!code-csharp[csRefOperators#15](../../../csharp/language-reference/operators/codesnippet/CSharp/dereference-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="a2ce7-110">См. также</span><span class="sxs-lookup"><span data-stu-id="a2ce7-110">See Also</span></span>

- [<span data-ttu-id="a2ce7-111">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="a2ce7-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="a2ce7-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a2ce7-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="a2ce7-113">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="a2ce7-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
