---
title: "Практическое руководство. Явная реализация членов двух интерфейсов (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- inheritance [C#], explicitly implementing interface members
- interfaces [C#], explicitly implementing with inheritance
ms.assetid: 8b402ddc-dff9-4869-89cb-d718c764e68e
caps.latest.revision: 15
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
ms.openlocfilehash: 1446233793e3fd61f09d7da99f4f68cb7b3eabb8
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-explicitly-implement-members-of-two-interfaces-c-programming-guide"></a><span data-ttu-id="f2eb1-102">Практическое руководство. Явная реализация членов двух интерфейсов (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="f2eb1-102">How to: Explicitly Implement Members of Two Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="f2eb1-103">Явная реализация [интерфейсов](../../../csharp/language-reference/keywords/interface.md) позволяет разработчику реализовать два интерфейса с одинаковыми именами членов и создать отдельные реализации каждого члена интерфейса.</span><span class="sxs-lookup"><span data-stu-id="f2eb1-103">Explicit [interface](../../../csharp/language-reference/keywords/interface.md) implementation also allows the programmer to implement two interfaces that have the same member names and give each interface member a separate implementation.</span></span> <span data-ttu-id="f2eb1-104">В этом примере размеры поля выводятся в метрической и английской системе мер.</span><span class="sxs-lookup"><span data-stu-id="f2eb1-104">This example displays the dimensions of a box in both metric and English units.</span></span> <span data-ttu-id="f2eb1-105">[Класс](../../../csharp/language-reference/keywords/class.md) Box реализует два интерфейса (IEnglishDimensions и IMetricDimensions), представляющие соответствующие системы мер.</span><span class="sxs-lookup"><span data-stu-id="f2eb1-105">The Box [class](../../../csharp/language-reference/keywords/class.md) implements two interfaces IEnglishDimensions and IMetricDimensions, which represent the different measurement systems.</span></span> <span data-ttu-id="f2eb1-106">В обоих интерфейсах представлены члены с одинаковыми именами: Length и Width.</span><span class="sxs-lookup"><span data-stu-id="f2eb1-106">Both interfaces have identical member names, Length and Width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2eb1-107">Пример</span><span class="sxs-lookup"><span data-stu-id="f2eb1-107">Example</span></span>  
 <span data-ttu-id="f2eb1-108">[!code-cs[csProgGuideInheritance#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f2eb1-108">[!code-cs[csProgGuideInheritance#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_1.cs)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="f2eb1-109">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="f2eb1-109">Robust Programming</span></span>  
 <span data-ttu-id="f2eb1-110">Если требуется использовать единицы английской системы мер по умолчанию, реализуйте методы Length и Width обычным способом, после чего явно реализуйте методы Length и Width из интерфейса IMetricDimensions:</span><span class="sxs-lookup"><span data-stu-id="f2eb1-110">If you want to make the default measurements in English units, implement the methods Length and Width normally, and explicitly implement the Length and Width methods from the IMetricDimensions interface:</span></span>  
  
 <span data-ttu-id="f2eb1-111">[!code-cs[csProgGuideInheritance#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="f2eb1-111">[!code-cs[csProgGuideInheritance#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_2.cs)]</span></span>  
  
 <span data-ttu-id="f2eb1-112">В этом случае единицы английской системы мер будут доступны из экземпляра класса, а метрические единицы — из экземпляра интерфейса:</span><span class="sxs-lookup"><span data-stu-id="f2eb1-112">In this case, you can access the English units from the class instance and access the metric units from the interface instance:</span></span>  
  
 <span data-ttu-id="f2eb1-113">[!code-cs[csProgGuideInheritance#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="f2eb1-113">[!code-cs[csProgGuideInheritance#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2eb1-114">См. также</span><span class="sxs-lookup"><span data-stu-id="f2eb1-114">See Also</span></span>  
 <span data-ttu-id="f2eb1-115">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f2eb1-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="f2eb1-116">[Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="f2eb1-116">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="f2eb1-117">[Интерфейсы](../../../csharp/programming-guide/interfaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="f2eb1-117">[Interfaces](../../../csharp/programming-guide/interfaces/index.md) </span></span>  
 [<span data-ttu-id="f2eb1-118">Практическое руководство. Явная реализация членов интерфейса</span><span class="sxs-lookup"><span data-stu-id="f2eb1-118">How to: Explicitly Implement Interface Members</span></span>](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-interface-members.md)

