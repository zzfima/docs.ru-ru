---
title: "Практическое руководство. Оформление дочерних объектов панели"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], binding to children of Panels
- Panel control [WPF], binding adorners to children
ms.assetid: 4cc9b972-b472-4e5c-bdf3-3702d7fbb1f5
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 70a2c1e7735a6df31a44fce7eb9bb2371acc208b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-adorn-the-children-of-a-panel"></a><span data-ttu-id="72787-102">Практическое руководство. Оформление дочерних объектов панели</span><span class="sxs-lookup"><span data-stu-id="72787-102">How to: Adorn the Children of a Panel</span></span>
<span data-ttu-id="72787-103">В этом примере показано, как программным способом привязки графического элемента к дочерним элементам указанного <xref:System.Windows.Controls.Panel>.</span><span class="sxs-lookup"><span data-stu-id="72787-103">This example shows how to programmatically bind an adorner to the children of a specified <xref:System.Windows.Controls.Panel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72787-104">Пример</span><span class="sxs-lookup"><span data-stu-id="72787-104">Example</span></span>  
 <span data-ttu-id="72787-105">Для привязки элемента оформления к дочерним элементам <xref:System.Windows.Controls.Panel>, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="72787-105">To bind an adorner to the children of a <xref:System.Windows.Controls.Panel>, follow these steps:</span></span>  
  
1.  <span data-ttu-id="72787-106">Объявите новую <xref:System.Windows.Documents.AdornerLayer> и вызовите `static` <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> метод, чтобы найти слой графических элементов, дочерние элементы которого являются оформляемого элемента.</span><span class="sxs-lookup"><span data-stu-id="72787-106">Declare a new <xref:System.Windows.Documents.AdornerLayer> object and call the `static`<xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> method to find an adorner layer for the element whose children are to be adorned.</span></span>  
  
2.  <span data-ttu-id="72787-107">Перечисление дочерних элементов родительского элемента и вызовите <xref:System.Windows.Documents.AdornerLayer.Add%2A> метода для привязки элемента оформления к каждому дочернему элементу.</span><span class="sxs-lookup"><span data-stu-id="72787-107">Enumerate through the children of the parent element and call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind an adorner to each child element.</span></span>  
  
 <span data-ttu-id="72787-108">Следующий пример привязывает (показано выше) к дочерним элементам SimpleCircleAdorner <xref:System.Windows.Controls.StackPanel> с именем *myStackPanel*.</span><span class="sxs-lookup"><span data-stu-id="72787-108">The following example binds a SimpleCircleAdorner (shown above) to the children of a <xref:System.Windows.Controls.StackPanel> named *myStackPanel*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
> [!NOTE]
>  <span data-ttu-id="72787-109">Использование [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для привязки декоративного элемента к другому элементу в настоящее время не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="72787-109">Using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72787-110">См. также</span><span class="sxs-lookup"><span data-stu-id="72787-110">See Also</span></span>  
 [<span data-ttu-id="72787-111">Общие сведения о декоративных элементах</span><span class="sxs-lookup"><span data-stu-id="72787-111">Adorners Overview</span></span>](../../../../docs/framework/wpf/controls/adorners-overview.md)
