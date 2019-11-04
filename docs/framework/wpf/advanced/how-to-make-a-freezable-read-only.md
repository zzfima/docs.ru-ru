---
title: Практическое руководство. сделать объект Freezable доступным только для чтения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
ms.openlocfilehash: 4185966d864be425bc631953461f6f27ab983bee
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460069"
---
# <a name="how-to-make-a-freezable-read-only"></a><span data-ttu-id="ff84f-102">Практическое руководство. сделать объект Freezable доступным только для чтения</span><span class="sxs-lookup"><span data-stu-id="ff84f-102">How to: Make a Freezable Read-Only</span></span>
<span data-ttu-id="ff84f-103">В этом примере показано, как сделать <xref:System.Windows.Freezable> только для чтения, вызвав его метод <xref:System.Windows.Freezable.Freeze%2A>.</span><span class="sxs-lookup"><span data-stu-id="ff84f-103">This example shows how to make a <xref:System.Windows.Freezable> read-only by calling its <xref:System.Windows.Freezable.Freeze%2A> method.</span></span>  
  
 <span data-ttu-id="ff84f-104">Нельзя зафиксировать объект <xref:System.Windows.Freezable>, если одно из следующих условий `true` об объекте:</span><span class="sxs-lookup"><span data-stu-id="ff84f-104">You cannot freeze a <xref:System.Windows.Freezable> object if any one of the following conditions is `true` about the object:</span></span>  
  
- <span data-ttu-id="ff84f-105">Он имеет анимированные или привязанные к данным свойства.</span><span class="sxs-lookup"><span data-stu-id="ff84f-105">It has animated or data bound properties.</span></span>  
  
- <span data-ttu-id="ff84f-106">Он имеет свойства, заданные динамическим ресурсом.</span><span class="sxs-lookup"><span data-stu-id="ff84f-106">It has properties that are set by a dynamic resource.</span></span> <span data-ttu-id="ff84f-107">Дополнительные сведения о динамических ресурсах см. в разделе [ресурсы XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span><span class="sxs-lookup"><span data-stu-id="ff84f-107">For more information about dynamic resources, see the [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span></span>  
  
- <span data-ttu-id="ff84f-108">Он содержит <xref:System.Windows.Freezable> подобъекты, которые не могут быть заморожены.</span><span class="sxs-lookup"><span data-stu-id="ff84f-108">It contains <xref:System.Windows.Freezable> sub-objects that cannot be frozen.</span></span>  
  
 <span data-ttu-id="ff84f-109">Если эти условия `false` для объекта <xref:System.Windows.Freezable> и вы не собираетесь его изменять, попробуйте заморозить его, чтобы получить выигрыш в производительности.</span><span class="sxs-lookup"><span data-stu-id="ff84f-109">If these conditions are `false` for your <xref:System.Windows.Freezable> object and you do not intend to modify it, consider freezing it to gain performance benefits.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff84f-110">Пример</span><span class="sxs-lookup"><span data-stu-id="ff84f-110">Example</span></span>  
 <span data-ttu-id="ff84f-111">В следующем примере закрепляется <xref:System.Windows.Media.SolidColorBrush>, который является типом объекта <xref:System.Windows.Freezable>.</span><span class="sxs-lookup"><span data-stu-id="ff84f-111">The following example freezes a <xref:System.Windows.Media.SolidColorBrush>, which is a type of <xref:System.Windows.Freezable> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 <span data-ttu-id="ff84f-112">Дополнительные сведения о <xref:System.Windows.Freezable> объектах см. в разделе [Общие сведения об объектах Freezable](freezable-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ff84f-112">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff84f-113">См. также</span><span class="sxs-lookup"><span data-stu-id="ff84f-113">See also</span></span>

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CanFreeze%2A>
- <xref:System.Windows.Freezable.Freeze%2A>
- [<span data-ttu-id="ff84f-114">Общие сведения об объектах класса Freezable</span><span class="sxs-lookup"><span data-stu-id="ff84f-114">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="ff84f-115">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="ff84f-115">How-to Topics</span></span>](base-elements-how-to-topics.md)
