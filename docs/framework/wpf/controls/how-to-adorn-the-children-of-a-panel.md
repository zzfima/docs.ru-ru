---
title: Практическое руководство. Оформление дочерних объектов панели
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], binding to children of Panels
- Panel control [WPF], binding adorners to children
ms.assetid: 4cc9b972-b472-4e5c-bdf3-3702d7fbb1f5
ms.openlocfilehash: 4babbf1df57f340a3f6be218f213ad1c868ec9f5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33550223"
---
# <a name="how-to-adorn-the-children-of-a-panel"></a><span data-ttu-id="0479a-102">Практическое руководство. Оформление дочерних объектов панели</span><span class="sxs-lookup"><span data-stu-id="0479a-102">How to: Adorn the Children of a Panel</span></span>
<span data-ttu-id="0479a-103">В этом примере показано, как программным способом привязки графического элемента к дочерним элементам указанного <xref:System.Windows.Controls.Panel>.</span><span class="sxs-lookup"><span data-stu-id="0479a-103">This example shows how to programmatically bind an adorner to the children of a specified <xref:System.Windows.Controls.Panel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0479a-104">Пример</span><span class="sxs-lookup"><span data-stu-id="0479a-104">Example</span></span>  
 <span data-ttu-id="0479a-105">Для привязки элемента оформления к дочерним элементам <xref:System.Windows.Controls.Panel>, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="0479a-105">To bind an adorner to the children of a <xref:System.Windows.Controls.Panel>, follow these steps:</span></span>  
  
1.  <span data-ttu-id="0479a-106">Объявите новую <xref:System.Windows.Documents.AdornerLayer> и вызовите `static` <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> метод, чтобы найти слой графических элементов, дочерние элементы которого являются оформляемого элемента.</span><span class="sxs-lookup"><span data-stu-id="0479a-106">Declare a new <xref:System.Windows.Documents.AdornerLayer> object and call the `static`<xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> method to find an adorner layer for the element whose children are to be adorned.</span></span>  
  
2.  <span data-ttu-id="0479a-107">Перечисление дочерних элементов родительского элемента и вызовите <xref:System.Windows.Documents.AdornerLayer.Add%2A> метода для привязки элемента оформления к каждому дочернему элементу.</span><span class="sxs-lookup"><span data-stu-id="0479a-107">Enumerate through the children of the parent element and call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind an adorner to each child element.</span></span>  
  
 <span data-ttu-id="0479a-108">Следующий пример привязывает (показано выше) к дочерним элементам SimpleCircleAdorner <xref:System.Windows.Controls.StackPanel> с именем *myStackPanel*.</span><span class="sxs-lookup"><span data-stu-id="0479a-108">The following example binds a SimpleCircleAdorner (shown above) to the children of a <xref:System.Windows.Controls.StackPanel> named *myStackPanel*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
> [!NOTE]
>  <span data-ttu-id="0479a-109">Использование [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для привязки декоративного элемента к другому элементу в настоящее время не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="0479a-109">Using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0479a-110">См. также</span><span class="sxs-lookup"><span data-stu-id="0479a-110">See Also</span></span>  
 [<span data-ttu-id="0479a-111">Общие сведения о декоративных элементах</span><span class="sxs-lookup"><span data-stu-id="0479a-111">Adorners Overview</span></span>](../../../../docs/framework/wpf/controls/adorners-overview.md)
