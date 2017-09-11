---
title: "Универсальные методы и массивы (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], arrays
- arrays [C#], generics
ms.assetid: 7d956536-3851-41b5-94ad-3e7c0a5fe485
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 46cea2733504e56aec5e65a4c9a8b655bc9431cf
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="generics-and-arrays-c-programming-guide"></a><span data-ttu-id="850c5-102">Универсальные методы и массивы (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="850c5-102">Generics and Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="850c5-103">В C# 2.0 и более поздних версиях одномерные массивы с нулевой нижней границей автоматически реализуют <xref:System.Collections.Generic.IList%601>.</span><span class="sxs-lookup"><span data-stu-id="850c5-103">In C# 2.0 and later, single-dimensional arrays that have a lower bound of zero automatically implement <xref:System.Collections.Generic.IList%601>.</span></span> <span data-ttu-id="850c5-104">Это позволяет создавать универсальные методы, которые могут использовать один и тот же код для выполнения итераций в массивах и других типах коллекций.</span><span class="sxs-lookup"><span data-stu-id="850c5-104">This enables you to create generic methods that can use the same code to iterate through arrays and other collection types.</span></span> <span data-ttu-id="850c5-105">Этот способ используется преимущественно для чтения данных в коллекциях.</span><span class="sxs-lookup"><span data-stu-id="850c5-105">This technique is primarily useful for reading data in collections.</span></span> <span data-ttu-id="850c5-106">Интерфейс <xref:System.Collections.Generic.IList%601> нельзя использовать для добавления или удаления элементов массива.</span><span class="sxs-lookup"><span data-stu-id="850c5-106">The <xref:System.Collections.Generic.IList%601> interface cannot be used to add or remove elements from an array.</span></span> <span data-ttu-id="850c5-107">При попытке вызвать метод <xref:System.Collections.Generic.IList%601>, например <xref:System.Collections.Generic.IList%601.RemoveAt%2A>, для массива в этом контексте возникнет исключение.</span><span class="sxs-lookup"><span data-stu-id="850c5-107">An exception will be thrown if you try to call an <xref:System.Collections.Generic.IList%601> method such as <xref:System.Collections.Generic.IList%601.RemoveAt%2A> on an array in this context.</span></span>  
  
 <span data-ttu-id="850c5-108">В следующем примере кода показано, как отдельный универсальный метод, принимающий входной параметр <xref:System.Collections.Generic.IList%601>, можно использовать для выполнения итераций в списке и массиве (в данном случае в массиве целых чисел).</span><span class="sxs-lookup"><span data-stu-id="850c5-108">The following code example demonstrates how a single generic method that takes an <xref:System.Collections.Generic.IList%601> input parameter can iterate through both a list and an array, in this case an array of integers.</span></span>  
  
 <span data-ttu-id="850c5-109">[!code-cs[csProgGuideGenerics#35](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-arrays_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="850c5-109">[!code-cs[csProgGuideGenerics#35](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-arrays_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="850c5-110">См. также</span><span class="sxs-lookup"><span data-stu-id="850c5-110">See Also</span></span>  
 <span data-ttu-id="850c5-111"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="850c5-111"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="850c5-112">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="850c5-112">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="850c5-113">[Универсальные шаблоны](../../../csharp/programming-guide/generics/index.md) </span><span class="sxs-lookup"><span data-stu-id="850c5-113">[Generics](../../../csharp/programming-guide/generics/index.md) </span></span>  
 <span data-ttu-id="850c5-114">[Массивы](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="850c5-114">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 [<span data-ttu-id="850c5-115">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="850c5-115">Generics</span></span>](~/docs/standard/generics/index.md)

