---
title: Практическое руководство. Декорирование дочерних элементов Panel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], binding to children of Panels
- Panel control [WPF], binding adorners to children
ms.assetid: 4cc9b972-b472-4e5c-bdf3-3702d7fbb1f5
ms.openlocfilehash: 739ccaa0273e66c4650c35217a1156d64336dbbb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923517"
---
# <a name="how-to-adorn-the-children-of-a-panel"></a><span data-ttu-id="4deaa-102">Практическое руководство. Декорирование дочерних элементов Panel</span><span class="sxs-lookup"><span data-stu-id="4deaa-102">How to: Adorn the Children of a Panel</span></span>
<span data-ttu-id="4deaa-103">В этом примере показано, как программно привязать декоративный элемент к дочерним элементам указанного <xref:System.Windows.Controls.Panel>объекта.</span><span class="sxs-lookup"><span data-stu-id="4deaa-103">This example shows how to programmatically bind an adorner to the children of a specified <xref:System.Windows.Controls.Panel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4deaa-104">Пример</span><span class="sxs-lookup"><span data-stu-id="4deaa-104">Example</span></span>  
 <span data-ttu-id="4deaa-105">Чтобы привязать декоративный элемент к дочерним <xref:System.Windows.Controls.Panel>элементам, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="4deaa-105">To bind an adorner to the children of a <xref:System.Windows.Controls.Panel>, follow these steps:</span></span>  
  
1. <span data-ttu-id="4deaa-106">Объявите новый <xref:System.Windows.Documents.AdornerLayer> объект и `static` <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> вызовите метод, чтобы найти слой декоративных элементов для элемента, чьи дочерние элементы должны быть декоративными.</span><span class="sxs-lookup"><span data-stu-id="4deaa-106">Declare a new <xref:System.Windows.Documents.AdornerLayer> object and call the `static`<xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> method to find an adorner layer for the element whose children are to be adorned.</span></span>  
  
2. <span data-ttu-id="4deaa-107">Перечислите дочерние элементы родительского элемента и вызовите <xref:System.Windows.Documents.AdornerLayer.Add%2A> метод для привязки декоративного элемента к каждому дочернему элементу.</span><span class="sxs-lookup"><span data-stu-id="4deaa-107">Enumerate through the children of the parent element and call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind an adorner to each child element.</span></span>  
  
 <span data-ttu-id="4deaa-108">В следующем примере показано, как привязать SimpleCircleAdorner (показанный выше) к дочерним элементам <xref:System.Windows.Controls.StackPanel> именованного *мистаккпанел*.</span><span class="sxs-lookup"><span data-stu-id="4deaa-108">The following example binds a SimpleCircleAdorner (shown above) to the children of a <xref:System.Windows.Controls.StackPanel> named *myStackPanel*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
> [!NOTE]
> <span data-ttu-id="4deaa-109">Использование [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для привязки декоративного элемента к другому элементу в настоящее время не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="4deaa-109">Using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4deaa-110">См. также</span><span class="sxs-lookup"><span data-stu-id="4deaa-110">See also</span></span>

- [<span data-ttu-id="4deaa-111">Общие сведения о декоративных элементах</span><span class="sxs-lookup"><span data-stu-id="4deaa-111">Adorners Overview</span></span>](adorners-overview.md)
