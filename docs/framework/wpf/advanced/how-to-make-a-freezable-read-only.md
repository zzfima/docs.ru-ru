---
title: Практическое руководство. Определение объекта Freezable как доступного только для чтения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
ms.openlocfilehash: 9b7102db4de0df7183355e50e3b372eac30d81b3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771024"
---
# <a name="how-to-make-a-freezable-read-only"></a><span data-ttu-id="f0844-102">Практическое руководство. Определение объекта Freezable как доступного только для чтения</span><span class="sxs-lookup"><span data-stu-id="f0844-102">How to: Make a Freezable Read-Only</span></span>
<span data-ttu-id="f0844-103">В этом примере показано, как сделать <xref:System.Windows.Freezable> только для чтения, вызвав его <xref:System.Windows.Freezable.Freeze%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="f0844-103">This example shows how to make a <xref:System.Windows.Freezable> read-only by calling its <xref:System.Windows.Freezable.Freeze%2A> method.</span></span>  
  
 <span data-ttu-id="f0844-104">Невозможно закрепить <xref:System.Windows.Freezable> объекта, если одно из следующих условий не `true` об объекте:</span><span class="sxs-lookup"><span data-stu-id="f0844-104">You cannot freeze a <xref:System.Windows.Freezable> object if any one of the following conditions is `true` about the object:</span></span>  
  
- <span data-ttu-id="f0844-105">Объект имеет анимированные или свойства с привязкой к данным.</span><span class="sxs-lookup"><span data-stu-id="f0844-105">It has animated or data bound properties.</span></span>  
  
- <span data-ttu-id="f0844-106">Он имеет свойства, которые задаются динамический ресурс.</span><span class="sxs-lookup"><span data-stu-id="f0844-106">It has properties that are set by a dynamic resource.</span></span> <span data-ttu-id="f0844-107">Дополнительные сведения о динамических ресурсов, см. в разделе [ресурсы XAML](xaml-resources.md).</span><span class="sxs-lookup"><span data-stu-id="f0844-107">For more information about dynamic resources, see the [XAML Resources](xaml-resources.md).</span></span>  
  
- <span data-ttu-id="f0844-108">Он содержит <xref:System.Windows.Freezable> вложенные объекты, которые нельзя зафиксировать.</span><span class="sxs-lookup"><span data-stu-id="f0844-108">It contains <xref:System.Windows.Freezable> sub-objects that cannot be frozen.</span></span>  
  
 <span data-ttu-id="f0844-109">Если эти условия выполняются `false` для вашей <xref:System.Windows.Freezable> объекта и вы не собираетесь изменять, можно зафиксировать, чтобы получить выигрыш в производительности.</span><span class="sxs-lookup"><span data-stu-id="f0844-109">If these conditions are `false` for your <xref:System.Windows.Freezable> object and you do not intend to modify it, consider freezing it to gain performance benefits.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0844-110">Пример</span><span class="sxs-lookup"><span data-stu-id="f0844-110">Example</span></span>  
 <span data-ttu-id="f0844-111">В следующем примере фиксируется <xref:System.Windows.Media.SolidColorBrush>, который представляет собой разновидность <xref:System.Windows.Freezable> объекта.</span><span class="sxs-lookup"><span data-stu-id="f0844-111">The following example freezes a <xref:System.Windows.Media.SolidColorBrush>, which is a type of <xref:System.Windows.Freezable> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 <span data-ttu-id="f0844-112">Дополнительные сведения о <xref:System.Windows.Freezable> объектов, см. в разделе [Freezable Общие сведения об объектах](freezable-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f0844-112">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0844-113">См. также</span><span class="sxs-lookup"><span data-stu-id="f0844-113">See also</span></span>

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CanFreeze%2A>
- <xref:System.Windows.Freezable.Freeze%2A>
- [<span data-ttu-id="f0844-114">Общие сведения об объектах класса Freezable</span><span class="sxs-lookup"><span data-stu-id="f0844-114">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="f0844-115">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="f0844-115">How-to Topics</span></span>](base-elements-how-to-topics.md)
