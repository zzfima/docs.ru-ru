---
title: Практическое руководство. Определение фиксации объекта Freezable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], determining if frozen
ms.assetid: 92e58baa-ee12-4a9e-ac3a-ca458807a8b2
ms.openlocfilehash: 6a63862d35f2c40289ea6445eb3dab8a2abe4a61
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776237"
---
# <a name="how-to-determine-whether-a-freezable-is-frozen"></a><span data-ttu-id="ea0c6-102">Практическое руководство. Определение фиксации объекта Freezable</span><span class="sxs-lookup"><span data-stu-id="ea0c6-102">How to: Determine Whether a Freezable Is Frozen</span></span>
<span data-ttu-id="ea0c6-103">В этом примере показано, как определить, является ли <xref:System.Windows.Freezable> объект заморожен.</span><span class="sxs-lookup"><span data-stu-id="ea0c6-103">This example shows how to determine whether a <xref:System.Windows.Freezable> object is frozen.</span></span> <span data-ttu-id="ea0c6-104">Если попытаться изменить зафиксированный <xref:System.Windows.Freezable> объекта, он выдает <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="ea0c6-104">If you try to modify a frozen <xref:System.Windows.Freezable> object, it throws an <xref:System.InvalidOperationException>.</span></span> <span data-ttu-id="ea0c6-105">Чтобы избежать возникновения этого исключения, используйте <xref:System.Windows.Freezable.IsFrozen%2A> свойство <xref:System.Windows.Freezable> объектом, чтобы определить, зафиксирован ли он.</span><span class="sxs-lookup"><span data-stu-id="ea0c6-105">To avoid throwing this exception, use the <xref:System.Windows.Freezable.IsFrozen%2A> property of the <xref:System.Windows.Freezable> object to determine whether it is frozen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea0c6-106">Пример</span><span class="sxs-lookup"><span data-stu-id="ea0c6-106">Example</span></span>  
 <span data-ttu-id="ea0c6-107">В следующем примере фиксируется <xref:System.Windows.Media.SolidColorBrush> и затем проверяется с помощью <xref:System.Windows.Freezable.IsFrozen%2A> свойства, чтобы определить, зафиксирован ли он.</span><span class="sxs-lookup"><span data-stu-id="ea0c6-107">The following example freezes a <xref:System.Windows.Media.SolidColorBrush> and then tests it by using the <xref:System.Windows.Freezable.IsFrozen%2A> property to determine whether it is frozen.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 <span data-ttu-id="ea0c6-108">Дополнительные сведения о <xref:System.Windows.Freezable> объектов, см. в разделе [Freezable Общие сведения об объектах](freezable-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ea0c6-108">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea0c6-109">См. также</span><span class="sxs-lookup"><span data-stu-id="ea0c6-109">See also</span></span>

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.IsFrozen%2A>
- [<span data-ttu-id="ea0c6-110">Общие сведения об объектах класса Freezable</span><span class="sxs-lookup"><span data-stu-id="ea0c6-110">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="ea0c6-111">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="ea0c6-111">How-to Topics</span></span>](base-elements-how-to-topics.md)
