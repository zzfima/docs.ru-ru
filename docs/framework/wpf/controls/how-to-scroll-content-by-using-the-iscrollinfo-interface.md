---
title: "Практическое руководство. Прокручивание содержимого с помощью интерфейса IScrollInfo"
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
- ScrollViewer control [WPF], scrolling content
- scrolling content [WPF]
- IScrollInfo interface [WPF]
ms.assetid: d8700bef-a3f8-4c12-9de2-fc3b79f32cd3
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1895507c30ad5267d4c2b1afff3acf004e872d40
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-scroll-content-by-using-the-iscrollinfo-interface"></a><span data-ttu-id="84802-102">Практическое руководство. Прокручивание содержимого с помощью интерфейса IScrollInfo</span><span class="sxs-lookup"><span data-stu-id="84802-102">How to: Scroll Content by Using the IScrollInfo Interface</span></span>
<span data-ttu-id="84802-103">В этом примере показано, как выполнять прокрутку содержимого с помощью <xref:System.Windows.Controls.Primitives.IScrollInfo> интерфейса.</span><span class="sxs-lookup"><span data-stu-id="84802-103">This example shows how to scroll content by using the <xref:System.Windows.Controls.Primitives.IScrollInfo> interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84802-104">Пример</span><span class="sxs-lookup"><span data-stu-id="84802-104">Example</span></span>  
 <span data-ttu-id="84802-105">Следующий пример демонстрирует функции <xref:System.Windows.Controls.Primitives.IScrollInfo> интерфейса.</span><span class="sxs-lookup"><span data-stu-id="84802-105">The following example demonstrates the features of the <xref:System.Windows.Controls.Primitives.IScrollInfo> interface.</span></span> <span data-ttu-id="84802-106">В примере создается <xref:System.Windows.Controls.StackPanel> элемент в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , вложенный в родительский элемент <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="84802-106">The example creates a <xref:System.Windows.Controls.StackPanel> element in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that is nested in a parent <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="84802-107">Дочерние элементы <xref:System.Windows.Controls.StackPanel> можно прокручивать логически с помощью методов, определенных <xref:System.Windows.Controls.Primitives.IScrollInfo> интерфейс и приведение к экземпляру <xref:System.Windows.Controls.StackPanel> (`sp1`) в коде.</span><span class="sxs-lookup"><span data-stu-id="84802-107">The child elements of the <xref:System.Windows.Controls.StackPanel> can be scrolled logically by using the methods defined by the <xref:System.Windows.Controls.Primitives.IScrollInfo> interface and cast to the instance of <xref:System.Windows.Controls.StackPanel> (`sp1`) in code.</span></span>  
  
 [!code-xaml[IScrollInfoMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="84802-108">Каждый <xref:System.Windows.Controls.Button> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файла вызывает связанный настраиваемый метод, который управляет поведением прокрутки в <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="84802-108">Each <xref:System.Windows.Controls.Button> in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file triggers an associated custom method that controls scrolling behavior in <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="84802-109">В следующем примере показано, как использовать <xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> и <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A> методов; также в целом показано, как использовать все методы позиционирования, <xref:System.Windows.Controls.Primitives.IScrollInfo> класс определяет.</span><span class="sxs-lookup"><span data-stu-id="84802-109">The following example shows how to use the <xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> and <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A> methods; it also generically shows how to use all the positioning methods that the <xref:System.Windows.Controls.Primitives.IScrollInfo> class defines.</span></span>  
  
 [!code-csharp[IScrollInfoMethods#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="84802-110">См. также</span><span class="sxs-lookup"><span data-stu-id="84802-110">See Also</span></span>  
 <xref:System.Windows.Controls.ScrollViewer>  
 <xref:System.Windows.Controls.Primitives.IScrollInfo>  
 <xref:System.Windows.Controls.StackPanel>  
 [<span data-ttu-id="84802-111">Общие сведения об элементе управления ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="84802-111">ScrollViewer Overview</span></span>](../../../../docs/framework/wpf/controls/scrollviewer-overview.md)  
 [<span data-ttu-id="84802-112">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="84802-112">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/scrollviewer-how-to-topics.md)  
 [<span data-ttu-id="84802-113">Общие сведения о панелях</span><span class="sxs-lookup"><span data-stu-id="84802-113">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
