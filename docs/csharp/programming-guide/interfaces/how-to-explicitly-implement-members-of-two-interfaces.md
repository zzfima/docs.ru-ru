---
title: Руководство по программированию на C#. Явная реализация элементов двух интерфейсов
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [C#], explicitly implementing interface members
- interfaces [C#], explicitly implementing with inheritance
ms.assetid: 8b402ddc-dff9-4869-89cb-d718c764e68e
ms.openlocfilehash: c7adc08f62a7f8a14b8e10f8b5ecdd6e37db811d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75701242"
---
# <a name="how-to-explicitly-implement-members-of-two-interfaces-c-programming-guide"></a><span data-ttu-id="e8a25-102">Руководство по программированию на C#. Явная реализация элементов двух интерфейсов</span><span class="sxs-lookup"><span data-stu-id="e8a25-102">How to explicitly implement members of two interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="e8a25-103">Явная реализация [интерфейсов](../../language-reference/keywords/interface.md) позволяет разработчику реализовать два интерфейса с одинаковыми именами членов и создать отдельные реализации каждого члена интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e8a25-103">Explicit [interface](../../language-reference/keywords/interface.md) implementation also allows the programmer to implement two interfaces that have the same member names and give each interface member a separate implementation.</span></span> <span data-ttu-id="e8a25-104">В этом примере размеры поля выводятся в метрической и английской системе мер.</span><span class="sxs-lookup"><span data-stu-id="e8a25-104">This example displays the dimensions of a box in both metric and English units.</span></span> <span data-ttu-id="e8a25-105">[Класс](../../language-reference/keywords/class.md) Box реализует два интерфейса (IEnglishDimensions и IMetricDimensions), представляющие соответствующие системы мер.</span><span class="sxs-lookup"><span data-stu-id="e8a25-105">The Box [class](../../language-reference/keywords/class.md) implements two interfaces IEnglishDimensions and IMetricDimensions, which represent the different measurement systems.</span></span> <span data-ttu-id="e8a25-106">В обоих интерфейсах представлены члены с одинаковыми именами: Length и Width.</span><span class="sxs-lookup"><span data-stu-id="e8a25-106">Both interfaces have identical member names, Length and Width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8a25-107">Пример</span><span class="sxs-lookup"><span data-stu-id="e8a25-107">Example</span></span>  
 [!code-csharp[csProgGuideInheritance#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#9)]  
  
## <a name="robust-programming"></a><span data-ttu-id="e8a25-108">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="e8a25-108">Robust Programming</span></span>  
 <span data-ttu-id="e8a25-109">Если требуется использовать единицы английской системы мер по умолчанию, реализуйте методы Length и Width обычным способом, после чего явно реализуйте методы Length и Width из интерфейса IMetricDimensions:</span><span class="sxs-lookup"><span data-stu-id="e8a25-109">If you want to make the default measurements in English units, implement the methods Length and Width normally, and explicitly implement the Length and Width methods from the IMetricDimensions interface:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#10)]  
  
 <span data-ttu-id="e8a25-110">В этом случае единицы английской системы мер будут доступны из экземпляра класса, а метрические единицы — из экземпляра интерфейса:</span><span class="sxs-lookup"><span data-stu-id="e8a25-110">In this case, you can access the English units from the class instance and access the metric units from the interface instance:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="e8a25-111">См. также</span><span class="sxs-lookup"><span data-stu-id="e8a25-111">See also</span></span>

- [<span data-ttu-id="e8a25-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="e8a25-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="e8a25-113">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="e8a25-113">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="e8a25-114">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="e8a25-114">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="e8a25-115">Практическое руководство. Явная реализация членов интерфейса</span><span class="sxs-lookup"><span data-stu-id="e8a25-115">How to explicitly implement interface members</span></span>](./how-to-explicitly-implement-interface-members.md)
