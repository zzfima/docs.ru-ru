---
title: Практическое руководство. сделать объект Freezable доступным только для чтения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
ms.openlocfilehash: be3abd74a71fc711cd9f4bf6796b7d55017355ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543436"
---
# <a name="how-to-make-a-freezable-read-only"></a><span data-ttu-id="79d37-102">Практическое руководство. сделать объект Freezable доступным только для чтения</span><span class="sxs-lookup"><span data-stu-id="79d37-102">How to: Make a Freezable Read-Only</span></span>
<span data-ttu-id="79d37-103">В этом примере показано, как сделать <xref:System.Windows.Freezable> только для чтения, вызвав его <xref:System.Windows.Freezable.Freeze%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="79d37-103">This example shows how to make a <xref:System.Windows.Freezable> read-only by calling its <xref:System.Windows.Freezable.Freeze%2A> method.</span></span>  
  
 <span data-ttu-id="79d37-104">Невозможно закрепить <xref:System.Windows.Freezable> объекта, если выполнено одно из следующих условий является `true` об объекте:</span><span class="sxs-lookup"><span data-stu-id="79d37-104">You cannot freeze a <xref:System.Windows.Freezable> object if any one of the following conditions is `true` about the object:</span></span>  
  
-   <span data-ttu-id="79d37-105">Объект имеет анимированные или свойства с привязкой к данным.</span><span class="sxs-lookup"><span data-stu-id="79d37-105">It has animated or data bound properties.</span></span>  
  
-   <span data-ttu-id="79d37-106">Он имеет свойства, которые задаются динамический ресурс.</span><span class="sxs-lookup"><span data-stu-id="79d37-106">It has properties that are set by a dynamic resource.</span></span> <span data-ttu-id="79d37-107">Дополнительные сведения о динамических ресурсах см. в разделе [ресурсов XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span><span class="sxs-lookup"><span data-stu-id="79d37-107">For more information about dynamic resources, see the [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
-   <span data-ttu-id="79d37-108">Он содержит <xref:System.Windows.Freezable> подчиненных объектах, которые нельзя зафиксировать.</span><span class="sxs-lookup"><span data-stu-id="79d37-108">It contains <xref:System.Windows.Freezable> sub-objects that cannot be frozen.</span></span>  
  
 <span data-ttu-id="79d37-109">Если эти условия выполняются `false` для вашей <xref:System.Windows.Freezable> объекта и вы не собираетесь изменять, можно зафиксировать, чтобы получить выигрыш в производительности.</span><span class="sxs-lookup"><span data-stu-id="79d37-109">If these conditions are `false` for your <xref:System.Windows.Freezable> object and you do not intend to modify it, consider freezing it to gain performance benefits.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79d37-110">Пример</span><span class="sxs-lookup"><span data-stu-id="79d37-110">Example</span></span>  
 <span data-ttu-id="79d37-111">В следующем примере фиксируется <xref:System.Windows.Media.SolidColorBrush>, который является типом <xref:System.Windows.Freezable> объекта.</span><span class="sxs-lookup"><span data-stu-id="79d37-111">The following example freezes a <xref:System.Windows.Media.SolidColorBrush>, which is a type of <xref:System.Windows.Freezable> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 <span data-ttu-id="79d37-112">Дополнительные сведения о <xref:System.Windows.Freezable> объектов, в разделе [Freezable Общие сведения об объектах](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="79d37-112">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79d37-113">См. также</span><span class="sxs-lookup"><span data-stu-id="79d37-113">See Also</span></span>  
 <xref:System.Windows.Freezable>  
 <xref:System.Windows.Freezable.CanFreeze%2A>  
 <xref:System.Windows.Freezable.Freeze%2A>  
 [<span data-ttu-id="79d37-114">Общие сведения об объектах класса Freezable</span><span class="sxs-lookup"><span data-stu-id="79d37-114">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="79d37-115">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="79d37-115">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
