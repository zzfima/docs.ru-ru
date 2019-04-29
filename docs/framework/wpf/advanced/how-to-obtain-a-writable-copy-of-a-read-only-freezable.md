---
title: Практическое руководство. Получение копии с возможностью записи объекта Freezable только для чтения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cloning Freezable objects [WPF]
- Freezable objects [WPF], modifiable clones
ms.assetid: d028de61-bbe9-4d62-b656-8fe3b1b2ca24
ms.openlocfilehash: 910c5dada6ca82f68992722e4df6b35f9f7497c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942796"
---
# <a name="how-to-obtain-a-writable-copy-of-a-read-only-freezable"></a><span data-ttu-id="ec990-102">Практическое руководство. Получение копии с возможностью записи объекта Freezable только для чтения</span><span class="sxs-lookup"><span data-stu-id="ec990-102">How to: Obtain a Writable Copy of a Read-Only Freezable</span></span>
<span data-ttu-id="ec990-103">В этом примере показано, как использовать <xref:System.Windows.Freezable.Clone%2A> метод, чтобы создать копию только для чтения <xref:System.Windows.Freezable>.</span><span class="sxs-lookup"><span data-stu-id="ec990-103">This example shows how to use the <xref:System.Windows.Freezable.Clone%2A> method to create a writable copy of a read-only <xref:System.Windows.Freezable>.</span></span>  
  
 <span data-ttu-id="ec990-104">После <xref:System.Windows.Freezable> объект помечен как доступный только для чтения («замороженным»), его нельзя изменять.</span><span class="sxs-lookup"><span data-stu-id="ec990-104">After a <xref:System.Windows.Freezable> object is marked as read-only ("frozen"), you cannot modify it.</span></span> <span data-ttu-id="ec990-105">Тем не менее, можно использовать <xref:System.Windows.Freezable.Clone%2A> метод для создания Модифицируемая копия зафиксированного объекта.</span><span class="sxs-lookup"><span data-stu-id="ec990-105">However, you can use the <xref:System.Windows.Freezable.Clone%2A> method to create a modifiable clone of the frozen object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec990-106">Пример</span><span class="sxs-lookup"><span data-stu-id="ec990-106">Example</span></span>  
 <span data-ttu-id="ec990-107">В следующем примере создается Модифицируемая копия зафиксированного <xref:System.Windows.Media.SolidColorBrush> объекта.</span><span class="sxs-lookup"><span data-stu-id="ec990-107">The following example creates a modifiable clone of a frozen <xref:System.Windows.Media.SolidColorBrush> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CloneExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
 <span data-ttu-id="ec990-108">Дополнительные сведения о <xref:System.Windows.Freezable> объектов, см. в разделе [Freezable Общие сведения об объектах](freezable-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ec990-108">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec990-109">См. также</span><span class="sxs-lookup"><span data-stu-id="ec990-109">See also</span></span>

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CloneCurrentValue%2A>
- [<span data-ttu-id="ec990-110">Общие сведения об объектах класса Freezable</span><span class="sxs-lookup"><span data-stu-id="ec990-110">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="ec990-111">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="ec990-111">How-to Topics</span></span>](base-elements-how-to-topics.md)
