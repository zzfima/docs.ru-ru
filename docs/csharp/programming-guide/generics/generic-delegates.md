---
title: "Универсальные делегаты. (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], delegates
- delegates [C#], generic
ms.assetid: bdea509c-44c1-4309-aaa9-15c7aee009df
caps.latest.revision: 16
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
ms.openlocfilehash: be067e2a2e2a192da8ccc92b60af81f0999c449a
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="generic-delegates-c-programming-guide"></a><span data-ttu-id="25054-102">Универсальные делегаты. (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="25054-102">Generic Delegates (C# Programming Guide)</span></span>
<span data-ttu-id="25054-103">[Делегат](../../../csharp/language-reference/keywords/delegate.md) может определять собственные параметры типа.</span><span class="sxs-lookup"><span data-stu-id="25054-103">A [delegate](../../../csharp/language-reference/keywords/delegate.md) can define its own type parameters.</span></span> <span data-ttu-id="25054-104">В коде, который ссылается на универсальный делегат, можно указать аргумент типа для создания закрытого сконструированного типа. Это будет аналогично созданию экземпляра универсального класса или вызову универсального метода, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="25054-104">Code that references the generic delegate can specify the type argument to create a closed constructed type, just like when instantiating a generic class or calling a generic method, as shown in the following example:</span></span>  
  
 <span data-ttu-id="25054-105">[!code-cs[csProgGuideGenerics#36](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="25054-105">[!code-cs[csProgGuideGenerics#36](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_1.cs)]</span></span>  
  
 <span data-ttu-id="25054-106">В C# версии 2.0 представлена новая функция группового преобразования методов, которая применяется как к конкретным, так и к универсальным типам делегатов, и позволяет записать приведенную выше строку с использованием упрощенного синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="25054-106">C# version 2.0 has a new feature called method group conversion, which applies to concrete as well as generic delegate types, and enables you to write the previous line with this simplified syntax:</span></span>  
  
 <span data-ttu-id="25054-107">[!code-cs[csProgGuideGenerics#37](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="25054-107">[!code-cs[csProgGuideGenerics#37](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_2.cs)]</span></span>  
  
 <span data-ttu-id="25054-108">Делегаты, определенные в универсальном классе, могут использовать параметры класса универсального типа таким же образом, как это делают методы класса.</span><span class="sxs-lookup"><span data-stu-id="25054-108">Delegates defined within a generic class can use the generic class type parameters in the same way that class methods do.</span></span>  
  
 <span data-ttu-id="25054-109">[!code-cs[csProgGuideGenerics#38](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="25054-109">[!code-cs[csProgGuideGenerics#38](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_3.cs)]</span></span>  
  
 <span data-ttu-id="25054-110">В коде, который ссылается на делегат, необходимо указать аргумент типа содержащего класса, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="25054-110">Code that references the delegate must specify the type argument of the containing class, as follows:</span></span>  
  
 <span data-ttu-id="25054-111">[!code-cs[csProgGuideGenerics#39](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="25054-111">[!code-cs[csProgGuideGenerics#39](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_4.cs)]</span></span>  
  
 <span data-ttu-id="25054-112">Универсальные делегаты особенно полезны при определении событий, основанных на типовых шаблонах разработки, поскольку аргумент отправителя может быть строго типизирован и больше не требует приведения к <xref:System.Object> и из него.</span><span class="sxs-lookup"><span data-stu-id="25054-112">Generic delegates are especially useful in defining events based on the typical design pattern because the sender argument can be strongly typed and no longer has to be cast to and from <xref:System.Object>.</span></span>  
  
 <span data-ttu-id="25054-113">[!code-cs[csProgGuideGenerics#40](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="25054-113">[!code-cs[csProgGuideGenerics#40](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_5.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25054-114">См. также</span><span class="sxs-lookup"><span data-stu-id="25054-114">See Also</span></span>  
 <span data-ttu-id="25054-115"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="25054-115"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="25054-116">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="25054-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="25054-117">[Введение в универсальные шаблоны](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span><span class="sxs-lookup"><span data-stu-id="25054-117">[Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span></span>  
 <span data-ttu-id="25054-118">[Универсальные методы](../../../csharp/programming-guide/generics/generic-methods.md) </span><span class="sxs-lookup"><span data-stu-id="25054-118">[Generic Methods](../../../csharp/programming-guide/generics/generic-methods.md) </span></span>  
 <span data-ttu-id="25054-119">[Универсальные классы](../../../csharp/programming-guide/generics/generic-classes.md) </span><span class="sxs-lookup"><span data-stu-id="25054-119">[Generic Classes](../../../csharp/programming-guide/generics/generic-classes.md) </span></span>  
 <span data-ttu-id="25054-120">[Универсальные интерфейсы](../../../csharp/programming-guide/generics/generic-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="25054-120">[Generic Interfaces](../../../csharp/programming-guide/generics/generic-interfaces.md) </span></span>  
 <span data-ttu-id="25054-121">[Делегаты](../../../csharp/programming-guide/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="25054-121">[Delegates](../../../csharp/programming-guide/delegates/index.md) </span></span>  
 [<span data-ttu-id="25054-122">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="25054-122">Generics</span></span>](~/docs/standard/generics/index.md)

