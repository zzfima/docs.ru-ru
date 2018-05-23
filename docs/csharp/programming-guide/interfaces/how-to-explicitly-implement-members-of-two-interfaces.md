---
title: Практическое руководство. Явная реализация членов двух интерфейсов (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [C#], explicitly implementing interface members
- interfaces [C#], explicitly implementing with inheritance
ms.assetid: 8b402ddc-dff9-4869-89cb-d718c764e68e
ms.openlocfilehash: c73089fdbf1350c1aff68ac3e8e78be00e21b931
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-explicitly-implement-members-of-two-interfaces-c-programming-guide"></a><span data-ttu-id="ac64a-102">Практическое руководство. Явная реализация членов двух интерфейсов (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="ac64a-102">How to: Explicitly Implement Members of Two Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="ac64a-103">Явная реализация [интерфейсов](../../../csharp/language-reference/keywords/interface.md) позволяет разработчику реализовать два интерфейса с одинаковыми именами членов и создать отдельные реализации каждого члена интерфейса.</span><span class="sxs-lookup"><span data-stu-id="ac64a-103">Explicit [interface](../../../csharp/language-reference/keywords/interface.md) implementation also allows the programmer to implement two interfaces that have the same member names and give each interface member a separate implementation.</span></span> <span data-ttu-id="ac64a-104">В этом примере размеры поля выводятся в метрической и английской системе мер.</span><span class="sxs-lookup"><span data-stu-id="ac64a-104">This example displays the dimensions of a box in both metric and English units.</span></span> <span data-ttu-id="ac64a-105">[Класс](../../../csharp/language-reference/keywords/class.md) Box реализует два интерфейса (IEnglishDimensions и IMetricDimensions), представляющие соответствующие системы мер.</span><span class="sxs-lookup"><span data-stu-id="ac64a-105">The Box [class](../../../csharp/language-reference/keywords/class.md) implements two interfaces IEnglishDimensions and IMetricDimensions, which represent the different measurement systems.</span></span> <span data-ttu-id="ac64a-106">В обоих интерфейсах представлены члены с одинаковыми именами: Length и Width.</span><span class="sxs-lookup"><span data-stu-id="ac64a-106">Both interfaces have identical member names, Length and Width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac64a-107">Пример</span><span class="sxs-lookup"><span data-stu-id="ac64a-107">Example</span></span>  
 [!code-csharp[csProgGuideInheritance#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_1.cs)]  
  
## <a name="robust-programming"></a><span data-ttu-id="ac64a-108">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="ac64a-108">Robust Programming</span></span>  
 <span data-ttu-id="ac64a-109">Если требуется использовать единицы английской системы мер по умолчанию, реализуйте методы Length и Width обычным способом, после чего явно реализуйте методы Length и Width из интерфейса IMetricDimensions:</span><span class="sxs-lookup"><span data-stu-id="ac64a-109">If you want to make the default measurements in English units, implement the methods Length and Width normally, and explicitly implement the Length and Width methods from the IMetricDimensions interface:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_2.cs)]  
  
 <span data-ttu-id="ac64a-110">В этом случае единицы английской системы мер будут доступны из экземпляра класса, а метрические единицы — из экземпляра интерфейса:</span><span class="sxs-lookup"><span data-stu-id="ac64a-110">In this case, you can access the English units from the class instance and access the metric units from the interface instance:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_3.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="ac64a-111">См. также</span><span class="sxs-lookup"><span data-stu-id="ac64a-111">See Also</span></span>  
 [<span data-ttu-id="ac64a-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ac64a-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ac64a-113">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="ac64a-113">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="ac64a-114">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="ac64a-114">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)  
 [<span data-ttu-id="ac64a-115">Практическое руководство. Явная реализация членов интерфейса</span><span class="sxs-lookup"><span data-stu-id="ac64a-115">How to: Explicitly Implement Interface Members</span></span>](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-interface-members.md)
