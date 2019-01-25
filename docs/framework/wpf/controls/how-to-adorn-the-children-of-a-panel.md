---
title: Как выполнить Декорирование дочерних объектов Panel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], binding to children of Panels
- Panel control [WPF], binding adorners to children
ms.assetid: 4cc9b972-b472-4e5c-bdf3-3702d7fbb1f5
ms.openlocfilehash: ae039243ded93eb2bc7f85f9f07fad1dbe0eac2e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54544982"
---
# <a name="how-to-adorn-the-children-of-a-panel"></a><span data-ttu-id="a12a4-102">Как выполнить Декорирование дочерних объектов Panel</span><span class="sxs-lookup"><span data-stu-id="a12a4-102">How to: Adorn the Children of a Panel</span></span>
<span data-ttu-id="a12a4-103">В этом примере показано, как программным способом привязки декоративного элемента к дочерним элементам указанного <xref:System.Windows.Controls.Panel>.</span><span class="sxs-lookup"><span data-stu-id="a12a4-103">This example shows how to programmatically bind an adorner to the children of a specified <xref:System.Windows.Controls.Panel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a12a4-104">Пример</span><span class="sxs-lookup"><span data-stu-id="a12a4-104">Example</span></span>  
 <span data-ttu-id="a12a4-105">Для привязки декоративного элемента к дочерним элементам <xref:System.Windows.Controls.Panel>, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a12a4-105">To bind an adorner to the children of a <xref:System.Windows.Controls.Panel>, follow these steps:</span></span>  
  
1.  <span data-ttu-id="a12a4-106">Объявите новый <xref:System.Windows.Documents.AdornerLayer> и вызовите `static` <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> метод, чтобы найти слой графических элементов для элемента, дочерние элементы которого нужно декорировать.</span><span class="sxs-lookup"><span data-stu-id="a12a4-106">Declare a new <xref:System.Windows.Documents.AdornerLayer> object and call the `static`<xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> method to find an adorner layer for the element whose children are to be adorned.</span></span>  
  
2.  <span data-ttu-id="a12a4-107">Перечислите дочерние элементы родительского элемента и вызовите <xref:System.Windows.Documents.AdornerLayer.Add%2A> метод для привязки декоративного элемента для каждого дочернего элемента.</span><span class="sxs-lookup"><span data-stu-id="a12a4-107">Enumerate through the children of the parent element and call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind an adorner to each child element.</span></span>  
  
 <span data-ttu-id="a12a4-108">Следующий пример связывает SimpleCircleAdorner (как показано выше) к дочерним элементам <xref:System.Windows.Controls.StackPanel> с именем *myStackPanel*.</span><span class="sxs-lookup"><span data-stu-id="a12a4-108">The following example binds a SimpleCircleAdorner (shown above) to the children of a <xref:System.Windows.Controls.StackPanel> named *myStackPanel*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
> [!NOTE]
>  <span data-ttu-id="a12a4-109">Использование [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для привязки декоративного элемента к другому элементу в настоящее время не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="a12a4-109">Using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a12a4-110">См. также</span><span class="sxs-lookup"><span data-stu-id="a12a4-110">See also</span></span>
- [<span data-ttu-id="a12a4-111">Общие сведения о декоративных элементах</span><span class="sxs-lookup"><span data-stu-id="a12a4-111">Adorners Overview</span></span>](../../../../docs/framework/wpf/controls/adorners-overview.md)
