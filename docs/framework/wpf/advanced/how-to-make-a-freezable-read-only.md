---
title: Как выполнить Задание объекта Freezable как доступного только для чтения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
ms.openlocfilehash: e0cc5d73f9b9f15fc02bf20a70c84da1a7c535c9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54671672"
---
# <a name="how-to-make-a-freezable-read-only"></a><span data-ttu-id="e7288-102">Как выполнить Задание объекта Freezable как доступного только для чтения</span><span class="sxs-lookup"><span data-stu-id="e7288-102">How to: Make a Freezable Read-Only</span></span>
<span data-ttu-id="e7288-103">В этом примере показано, как сделать <xref:System.Windows.Freezable> только для чтения, вызвав его <xref:System.Windows.Freezable.Freeze%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="e7288-103">This example shows how to make a <xref:System.Windows.Freezable> read-only by calling its <xref:System.Windows.Freezable.Freeze%2A> method.</span></span>  
  
 <span data-ttu-id="e7288-104">Невозможно закрепить <xref:System.Windows.Freezable> объекта, если одно из следующих условий не `true` об объекте:</span><span class="sxs-lookup"><span data-stu-id="e7288-104">You cannot freeze a <xref:System.Windows.Freezable> object if any one of the following conditions is `true` about the object:</span></span>  
  
-   <span data-ttu-id="e7288-105">Объект имеет анимированные или свойства с привязкой к данным.</span><span class="sxs-lookup"><span data-stu-id="e7288-105">It has animated or data bound properties.</span></span>  
  
-   <span data-ttu-id="e7288-106">Он имеет свойства, которые задаются динамический ресурс.</span><span class="sxs-lookup"><span data-stu-id="e7288-106">It has properties that are set by a dynamic resource.</span></span> <span data-ttu-id="e7288-107">Дополнительные сведения о динамических ресурсов, см. в разделе [ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span><span class="sxs-lookup"><span data-stu-id="e7288-107">For more information about dynamic resources, see the [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
-   <span data-ttu-id="e7288-108">Он содержит <xref:System.Windows.Freezable> вложенные объекты, которые нельзя зафиксировать.</span><span class="sxs-lookup"><span data-stu-id="e7288-108">It contains <xref:System.Windows.Freezable> sub-objects that cannot be frozen.</span></span>  
  
 <span data-ttu-id="e7288-109">Если эти условия выполняются `false` для вашей <xref:System.Windows.Freezable> объекта и вы не собираетесь изменять, можно зафиксировать, чтобы получить выигрыш в производительности.</span><span class="sxs-lookup"><span data-stu-id="e7288-109">If these conditions are `false` for your <xref:System.Windows.Freezable> object and you do not intend to modify it, consider freezing it to gain performance benefits.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7288-110">Пример</span><span class="sxs-lookup"><span data-stu-id="e7288-110">Example</span></span>  
 <span data-ttu-id="e7288-111">В следующем примере фиксируется <xref:System.Windows.Media.SolidColorBrush>, который представляет собой разновидность <xref:System.Windows.Freezable> объекта.</span><span class="sxs-lookup"><span data-stu-id="e7288-111">The following example freezes a <xref:System.Windows.Media.SolidColorBrush>, which is a type of <xref:System.Windows.Freezable> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 <span data-ttu-id="e7288-112">Дополнительные сведения о <xref:System.Windows.Freezable> объектов, см. в разделе [Freezable Общие сведения об объектах](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e7288-112">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7288-113">См. также</span><span class="sxs-lookup"><span data-stu-id="e7288-113">See also</span></span>
- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CanFreeze%2A>
- <xref:System.Windows.Freezable.Freeze%2A>
- [<span data-ttu-id="e7288-114">Общие сведения об объектах класса Freezable</span><span class="sxs-lookup"><span data-stu-id="e7288-114">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)
- [<span data-ttu-id="e7288-115">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="e7288-115">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
