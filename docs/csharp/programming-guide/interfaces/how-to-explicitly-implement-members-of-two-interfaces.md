---
title: Как выполнить Руководство по программированию на C#. Явная реализация членов двух интерфейсов
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [C#], explicitly implementing interface members
- interfaces [C#], explicitly implementing with inheritance
ms.assetid: 8b402ddc-dff9-4869-89cb-d718c764e68e
ms.openlocfilehash: b0725d63f77fbe0b9f3151c0b742777667e93311
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54701252"
---
# <a name="how-to-explicitly-implement-members-of-two-interfaces-c-programming-guide"></a><span data-ttu-id="af763-102">Как выполнить Руководство по программированию на C#. Явная реализация членов двух интерфейсов</span><span class="sxs-lookup"><span data-stu-id="af763-102">How to: Explicitly Implement Members of Two Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="af763-103">Явная реализация [интерфейсов](../../../csharp/language-reference/keywords/interface.md) позволяет разработчику реализовать два интерфейса с одинаковыми именами членов и создать отдельные реализации каждого члена интерфейса.</span><span class="sxs-lookup"><span data-stu-id="af763-103">Explicit [interface](../../../csharp/language-reference/keywords/interface.md) implementation also allows the programmer to implement two interfaces that have the same member names and give each interface member a separate implementation.</span></span> <span data-ttu-id="af763-104">В этом примере размеры поля выводятся в метрической и английской системе мер.</span><span class="sxs-lookup"><span data-stu-id="af763-104">This example displays the dimensions of a box in both metric and English units.</span></span> <span data-ttu-id="af763-105">[Класс](../../../csharp/language-reference/keywords/class.md) Box реализует два интерфейса (IEnglishDimensions и IMetricDimensions), представляющие соответствующие системы мер.</span><span class="sxs-lookup"><span data-stu-id="af763-105">The Box [class](../../../csharp/language-reference/keywords/class.md) implements two interfaces IEnglishDimensions and IMetricDimensions, which represent the different measurement systems.</span></span> <span data-ttu-id="af763-106">В обоих интерфейсах представлены члены с одинаковыми именами: Length и Width.</span><span class="sxs-lookup"><span data-stu-id="af763-106">Both interfaces have identical member names, Length and Width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af763-107">Пример</span><span class="sxs-lookup"><span data-stu-id="af763-107">Example</span></span>  
 [!code-csharp[csProgGuideInheritance#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_1.cs)]  
  
## <a name="robust-programming"></a><span data-ttu-id="af763-108">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="af763-108">Robust Programming</span></span>  
 <span data-ttu-id="af763-109">Если требуется использовать единицы английской системы мер по умолчанию, реализуйте методы Length и Width обычным способом, после чего явно реализуйте методы Length и Width из интерфейса IMetricDimensions:</span><span class="sxs-lookup"><span data-stu-id="af763-109">If you want to make the default measurements in English units, implement the methods Length and Width normally, and explicitly implement the Length and Width methods from the IMetricDimensions interface:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_2.cs)]  
  
 <span data-ttu-id="af763-110">В этом случае единицы английской системы мер будут доступны из экземпляра класса, а метрические единицы — из экземпляра интерфейса:</span><span class="sxs-lookup"><span data-stu-id="af763-110">In this case, you can access the English units from the class instance and access the metric units from the interface instance:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_3.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="af763-111">См. также</span><span class="sxs-lookup"><span data-stu-id="af763-111">See also</span></span>

- [<span data-ttu-id="af763-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="af763-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="af763-113">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="af763-113">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
- [<span data-ttu-id="af763-114">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="af763-114">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)
- [<span data-ttu-id="af763-115">Практическое руководство. Явная реализация элементов интерфейса</span><span class="sxs-lookup"><span data-stu-id="af763-115">How to: Explicitly Implement Interface Members</span></span>](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-interface-members.md)
