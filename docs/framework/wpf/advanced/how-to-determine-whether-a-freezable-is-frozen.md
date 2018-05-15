---
title: Практическое руководство. Определение состояния объекта класса Freezable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], determining if frozen
ms.assetid: 92e58baa-ee12-4a9e-ac3a-ca458807a8b2
ms.openlocfilehash: f6d20025d59a702357b12da9f5dc0f5887968143
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-determine-whether-a-freezable-is-frozen"></a><span data-ttu-id="e57b9-102">Практическое руководство. Определение состояния объекта класса Freezable</span><span class="sxs-lookup"><span data-stu-id="e57b9-102">How to: Determine Whether a Freezable Is Frozen</span></span>
<span data-ttu-id="e57b9-103">В этом примере показано, как определить, является ли <xref:System.Windows.Freezable> объект заморожен.</span><span class="sxs-lookup"><span data-stu-id="e57b9-103">This example shows how to determine whether a <xref:System.Windows.Freezable> object is frozen.</span></span> <span data-ttu-id="e57b9-104">При попытке изменения зафиксированного <xref:System.Windows.Freezable> объекта, он вызывает <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="e57b9-104">If you try to modify a frozen <xref:System.Windows.Freezable> object, it throws an <xref:System.InvalidOperationException>.</span></span> <span data-ttu-id="e57b9-105">Чтобы избежать возникновения этого исключения, используйте <xref:System.Windows.Freezable.IsFrozen%2A> свойство <xref:System.Windows.Freezable> объекта, чтобы определить, зафиксирован ли он.</span><span class="sxs-lookup"><span data-stu-id="e57b9-105">To avoid throwing this exception, use the <xref:System.Windows.Freezable.IsFrozen%2A> property of the <xref:System.Windows.Freezable> object to determine whether it is frozen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e57b9-106">Пример</span><span class="sxs-lookup"><span data-stu-id="e57b9-106">Example</span></span>  
 <span data-ttu-id="e57b9-107">В следующем примере фиксируется <xref:System.Windows.Media.SolidColorBrush> и затем проверяется с помощью <xref:System.Windows.Freezable.IsFrozen%2A> свойства, чтобы определить, зафиксирован ли он.</span><span class="sxs-lookup"><span data-stu-id="e57b9-107">The following example freezes a <xref:System.Windows.Media.SolidColorBrush> and then tests it by using the <xref:System.Windows.Freezable.IsFrozen%2A> property to determine whether it is frozen.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 <span data-ttu-id="e57b9-108">Дополнительные сведения о <xref:System.Windows.Freezable> объектов, в разделе [Freezable Общие сведения об объектах](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e57b9-108">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e57b9-109">См. также</span><span class="sxs-lookup"><span data-stu-id="e57b9-109">See Also</span></span>  
 <xref:System.Windows.Freezable>  
 <xref:System.Windows.Freezable.IsFrozen%2A>  
 [<span data-ttu-id="e57b9-110">Общие сведения об объектах класса Freezable</span><span class="sxs-lookup"><span data-stu-id="e57b9-110">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="e57b9-111">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="e57b9-111">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
